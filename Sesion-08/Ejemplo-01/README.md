# Ejemplo # 1 - Enviando Prueba API con JMeter

## Objetivo

PENDIENTE !!!

## Desarrollo

**Rest API login**

Basados en la plataforma Json Rest API, veremos como usar JMeter en nuestro inicio de sesión API。

Pero, ¿cómo funciona la autenticación?ComoSimular inicio de sesión con JMeter？La mayoría de las API de Rest usan lo siguienteFlujo de trabajo de inicio de sesión：

1. Inicie sesión utilizando la solicitud HTTP POSTAl proporcionarusernameYpassword，
2. Recibir un token de autenticación temporalPara solicitar una identificación más tarde,
3. Enviar token de autenticaciónEn solicitudes posteriores, generalmente a través deEncabezado HTTPLo mismoAuthorization: Bearer AUTH_TOKEN。

**Especificación de API de inicio de sesión**

Primero, veamos cómo iniciar sesión. Afortunadamente, nuestra API tiene un Especificación Swagger：SwaggerEs un proporcionarRest API documentación Herramientas.

![1](https://user-images.githubusercontent.com/22419786/158740250-c221b7a1-1e43-490f-9128-1947b48d9fd9.png)

 Swagger SpecDoc especifica cómo iniciar sesión a través de la API

Bien!Ahora echemos un vistazo a las solicitudes requeridas para la falsificación con JMeter:

* Método http: Debe serPOSTSolicitud con algunos parámetros de publicación, (verGET vs POST）
* Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
* Nombre de host：api.octoperf.com，
* Camino :( /public/users/loginRuta del punto final de inicio de sesión),
* Parámetros de publicación：

  - Nombre de usuario: Nombre de usuario de la cuenta, si no lo tiene, puedeAquiRelajadoRegistrarse，
  - Contraseña: La contraseña asociada.
  
Entonces deberíamos recibir uno del servidor Json Response y se ve así:

![2](https://user-images.githubusercontent.com/22419786/158740766-83154381-6194-4ccd-8bb4-1cf7c75a62b3.PNG)


**Realizar inicio de sesión**

IMAGEN 3

Aqui tenemosListo paraLogin Http RequestEnviar a nuestro servidor. Se oculta la información confidencial, pero esta es básicamente la información de su cuenta.ParaIniciar sesión de depuraciónY usaremosView Results Tree Listener.

IMAGEN 4

Podemos ver que la solicitud enviada es unPOST-forma-codificado, Que contiene nuestro nombre de usuario y contraseña.¡Nada difícil aquí!Ahora nosotrosEnviar al servidorDeRespuesta JsonInteresado。

 IMAGEN 5

BienAhora hemos recibidoToken de autenticación, Podemos extraerlo para reutilizarlo en solicitudes posteriores.

**Extraer token de autenticación**

Autenticación basada en tokensEs un mecanismo simple donde los tokensIdentifique de forma exclusiva la sesión del usuario。Necesitamos lidiar con estodynamic parameterPara imitar adecuadamente conJson APIUsuario interactivo。

**Use Json Extractor**
Para comenzar desdeRespuesta del servidorExtraer token de autenticaciónY usaremosJMeter JsonPath Extractor。El proceso de extracción de variables de la respuesta es el siguiente:

1. El servidor devuelve una respuesta a nuestra solicitud de inicio de sesión,
2. UnPostprocesadorComoExtracción JsonPathEstá siguiendo la ejecución
3. ExtractorExtrayendo parte de la respuesta del servidorY ponerlo en una variable${token}。

 IMAGEN 6

TenemosUse esta configuraciónConfiguradoJMeter Json Extractor：

* Crear nombre de variable：token, Lo que conducirá a variables reutilizables con sintaxis${token}，
* Expresión de Json Path：$.token，Para mas informacion,VerEjemplo de expresión JsonPath，
* YMatch Nr: Simplemente1Primero apareció.Pero podemos dejarlo en blanco.

¿Ves dónde puse el extractor?EnloginBajo una solicitud HTTP.También agregamos unoDebug SamplerPara ver si las variables se extrajeron correctamente.

**Habilitar depuración**
 
 IMAGEN 7

EstableciendoVariables JMeterVentrueY habilitamos la muestraVariable de salidaDurante la prueba de funcionamiento.

**Extracción de prueba**

 IMAGEN 8

JMeter Extraiga con éxito el token de la respuesta del servidor utilizando Json Extractor

Grande!Extractor JsonPerfecto。SetokenDe la respuesta de JsonExtracciónCampoEl valor de。Ahora podemos${token}En solicitudes posterioresUsoExpresión para ejecutarSolicitud autenticada。

Veamos cómo podemos reutilizar este token para decirle a nuestra API Rest que somos un usuario determinado.

**Volver a registrar el token de verificación**

Nuestra API de descansoHay muchosRequerir autenticaciónPunto final。Estos puntos finales proporcionan datos para espacios de trabajo de usuarios, proyectos, usuarios virtuales y más.Para acceder a un punto final protegido por el usuario, debe:

* Iniciar sesiónPara obtener un token de autenticación (como lo hicimos antes),
* Authorization: Bearer TOKENPara cada solicitud posterior,Enencabezado de solicitud httpDentro deEnviar token de autenticación.

Esto es exactamente lo que vamos a hacer aquí.

**Recuperando el espacio de trabajo del usuario**

Estamos particularmente interesados ​​ahoraConsultar el espacio de trabajo del usuario。Esto esWorkspacesParte del punto final de la API.

 IMAGEN 9
 APIPunto final de la API de descanso del espacio de trabajo de la documentación de la API de Swagger

Lo haremosGETUsar ruta al punto finalEjecutarSolicitud/workspaces/member-of。Debería volverContiene espacio de trabajo del usuarioDeJsonRespuestaEste es un ejemplo de respuesta:

 IMAGEN 10

Creemos una solicitud HTTP en JMeter para consultarlos.Es simple, como se muestra en la captura de pantalla a continuación.

 IMAGEN 11

Aquí configuramos una solicitud HTTP para consultar el espacio de trabajo del usuario:

* Método http: Debe serGETSolicitud sin parámetros
* Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
* Nombre de host：api.octoperf.com，
* Camino：/workspaces/member-of。

¿Se acabó?Aún noActualmente, si no proporcionamos un token de autenticación, el servidor rechazará nuestra solicitud.

 IMAGEN 12
 
 El servidor devolvió un error. Servidor aError HTTP 4xxRechazar solicitud：401 Unauthorized。

Similar a 403 Prohibido, pero específicamente para situaciones donde se requiere autenticación y ha fallado o no se ha proporcionado.

Necesitamos pasarAuthorizationA peticiónContieneEncabezados vienenProporcionar token de autenticación。Como esHastaSolicitudAgregarAdministrador de encabezado HTTP。

**Agregar encabezado de autorización** 

IMAGEN 13
 Establecer el token extraído en el encabezado de autorización

Recuerda: ya tenemostokenDe/public/users/loginRespuesta del servidor de punto finalExtraído。Ahora es tiempo de reutilizarlo para recuperarAcceso protegidoRecursos:

1. PrimeroEngetWorkspaces HTTP Request AbajoAgrega unoHttp Header Manager，
2. AgregarAuthorizationCon valorDeEncabezadoBearer ${token}。

IMAGEN 14
 Obtener espacio de trabajo del servidor

Eso es genial!¡Está funcionando ahora!Tenemos todos los espacios de trabajo que pertenecen al usuario conectado.

IMAGEN 15

 Se envió el encabezado de autorización en la solicitud

El encabezado de autorización se incluyó correctamente en el encabezado de la solicitud.Sin embargo, una cosa es molesta:El formato Json es incorrecto。Por qué

La mayoría de los servidores envían json en formato compacto, omitiendo la sangría.Esto es por razones de rendimiento (reducir el uso de ancho de banda y el uso de CPU del servidor)

**Formato de respuesta Json**

Para resolver este problema,JSON Formatter PostProcessorPuede hacer bien el trabajo.

IMAGEN 16

JMeter Json Formatter PostProcessorJMeter Json formateador postprocesador

IMAGEN 17

JMeter Json ¡Json imprime maravillosamente ahora!

Ahora podemos usarJson Assertion(EnJMeter 4.0Introducir）Características de gran alcancePara verificar la respuesta del servidor.

**Usar afirmación Json**

Nos aseguraremos de que la respuesta del servidor contengaPersonalÁrea de trabajoEsto esEl trabajo asertivo de Json。Para agregar aserciones Json, haga clic con el botón derecho en la muestra de solicitud HTTP y seleccioneAdd > Post Processor > Json Assertion。

**Configuracion**

IMAGEN 18

JMeter Json La respuesta de afirmación contiene un espacio de trabajo personal

Json afirma la configuración de la siguiente manera:

* La ruta Json afirmada existe：$.[1]['name']Se refiere a la segunda área de trabajo devuelta y tomadaname，
* Valor de afirmación: Verificar para verificarnameCampoEl valor de，
* Valor esperado: Debería serPersonal。

**Ejecutar**

Supongamos que afirmamosValor esperadoSiOtherNo esPersonal。

IMAGEN 19

JMeter Json Encuentra el nombreOtrosEspacio de trabajo, la aserción Json falla

Como se esperaba, la afirmación falla con el siguiente mensaje:

IMAGEN 20

**Rendimiento**

Por supuesto, no está limitado a usar Json Assertion.Si te gustaTambién se puede utilizarJMeter Response Assertion。SeEn términos de rendimientoInclusoBeneficiosoPorqueDe acuerdo a nuestroTabla de comparación de rendimiento de afirmación，Afirmación de respuestaConsume menos recursos de CPU / memoria que las aserciones de Json。

**Simula comportamiento dinámico**

Ahora sabemos cómo iniciar sesión en la API de Json Rest y enviarAcceso protegidoPunto finalSolicitudVamos a ver comodynamically behavingUsando JMeterSimulaciónUsuario.

Esta es la última parte de este tutorial:

* Primero lo haremosExtraer ID de espacio de trabajo aleatorio, (Will${workspaceId}）
* Segundo, usaremos el punto final para consultar el proyecto para ese espacio de trabajo */projects/by-workspace/${workspaceId}/DESIGN*

Projects Rest APIPunto final de API de Rest de proyectos de OctoPerf

IMAGEN 21

El último punto final de Rest API nos interesa.Lo llamaremos desde JMeter, pero primero necesitamosExtraer un espacio de trabajo aleatorio。

**Extraer WorkspaceId** 

IMAGEN 22

Extractor está configurado comogetWorkspacesSolicitudPost procesador,Tiene la siguiente configuración:

* Crear nombre de variable：workspaceId，
* Expresión de Json Path：$..id，
* Número de partido：0Esto es al azar.

Esto extraerá un espacio de trabajo aleatorio y lo colocará en${workspaceId}Variable

**Elemento de consulta**

Finalmente, necesitamos consultar el proyecto en función del contenido extraído previamenteworkspaceId。Para esto yoCopiar y modificar solicitud previaPara tener algo de tiempo.

IMAGEN 23

JMeter Json Consultar proyecto usando workspaceId variable

Aquí configuramos una solicitud HTTP para consultar el proyecto del espacio de trabajo:

* Método http: Debe serGETSolicitud sin parámetros
* Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
* Nombre de host：api.octoperf.com，
* Camino：/design/projects/by-workspace/${workspaceId}/DESIGN。DESIGNEl estado de los proyectos contenidos en el espacio de trabajo.(Y no el resultado, esto seríaRESULT）

¡Creo que estamos listos para una iteración rápida para probar esto!

**Ver resultados**

IMAGEN 24

La ejecución conduce al elemento de consulta

Si ejecutamos al usuario varias veces, veremosFactor de respuestaExtracciónDeEspacio de trabajo aleatorioMientras queDiferente。
