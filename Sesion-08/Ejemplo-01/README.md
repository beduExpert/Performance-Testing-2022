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
  
Entonces deberíamos recibir uno del servidorJson ResponseY se ve así:

![2](https://user-images.githubusercontent.com/22419786/158740766-83154381-6194-4ccd-8bb4-1cf7c75a62b3.PNG)

¿Ves la ficha aquí?Esto es algo que usaremos más adelante para identificarnos en la API Rest.Pero primero echemos un vistazoSolicitud

**Realizar inicio de sesión**

iMAGEN 3

Aqui tenemosListo paraLogin Http RequestEnviar a nuestro servidor.Acabo de ocultar información confidencial, pero esta es básicamente la información de su cuenta.ParaIniciar sesión de depuraciónY usaremosView Results Tree Listener。

IMAGEN 4

Podemos ver que la solicitud enviada es unPOST-forma-codificado, Que contiene nuestro nombre de usuario y contraseña.¡Nada difícil aquí!Ahora nosotrosEnviar al servidorDeRespuesta JsonInteresado。

 HTTP Recibir respuesta del servidor

BienAhora hemos recibidoToken de autenticación, Podemos extraerlo para reutilizarlo en solicitudes posteriores.

Extraer token de autenticación
Autenticación basada en tokensEs un mecanismo simple donde los tokensIdentifique de forma exclusiva la sesión del usuario。Necesitamos lidiar con estodynamic parameterPara imitar adecuadamente conJson APIUsuario interactivo。

Use Json Extractor
Para comenzar desdeRespuesta del servidorExtraer token de autenticaciónY usaremosJMeter JsonPath Extractor。El proceso de extracción de variables de la respuesta es el siguiente:

El servidor devuelve una respuesta a nuestra solicitud de inicio de sesión,
UnPostprocesadorComoExtracción JsonPathEstá siguiendo la ejecución
ExtractorExtrayendo parte de la respuesta del servidorY ponerlo en una variable${token}。
JMeter Json ExtractorExtraer token de autenticación de la respuesta del servidor

TenemosUse esta configuraciónConfiguradoJMeter Json Extractor：

Crear nombre de variable：token, Lo que conducirá a variables reutilizables con sintaxis${token}，
Expresión de Json Path：$.token，Para mas informacion,VerEjemplo de expresión JsonPath，
YMatch Nr: Simplemente1Primero apareció.Pero podemos dejarlo en blanco.
¿Ves dónde puse el extractor?EnloginBajo una solicitud HTTP.También agregamos unoDebug SamplerPara ver si las variables se extrajeron correctamente.

Habilitar depuración
JMeter Habilitar variables JMeter en Debug Sampler

EstableciendoVariables JMeterVentrueY habilitamos la muestraVariable de salidaDurante la prueba de funcionamiento.

Extracción de prueba
JMeter Extraiga con éxito el token de la respuesta del servidor utilizando Json Extractor

Grande!Extractor JsonPerfecto。SetokenDe la respuesta de JsonExtracciónCampoEl valor de。Ahora podemos${token}En solicitudes posterioresUsoExpresión para ejecutarSolicitud autenticada。

Veamos cómo podemos reutilizar este token para decirle a nuestra API Rest que somos un usuario determinado.

Volver a registrar el token de verificación
Nuestra API de descansoHay muchosRequerir autenticaciónPunto final。Estos puntos finales proporcionan datos para espacios de trabajo de usuarios, proyectos, usuarios virtuales y más.Para acceder a un punto final protegido por el usuario, debe:

Iniciar sesiónPara obtener un token de autenticación (como lo hicimos antes),
Authorization: Bearer TOKENPara cada solicitud posterior,Enencabezado de solicitud httpDentro deEnviar token de autenticación。
Esto es exactamente lo que vamos a hacer aquí.

Recuperando el espacio de trabajo del usuario
Estamos particularmente interesados ​​ahoraConsultar el espacio de trabajo del usuario。Esto esWorkspacesParte del punto final de la API.

 APIPunto final de la API de descanso del espacio de trabajo de la documentación de la API de Swagger

Lo haremosGETUsar ruta al punto finalEjecutarSolicitud/workspaces/member-of。Debería volverContiene espacio de trabajo del usuarioDeJsonRespuestaEste es un ejemplo de respuesta:

[
  {
    "created": "2018-04-23T12:40:00.133Z",
    "description": "This is my personal workspace.",
    "id": "workspaceId",
    "lastModified": "2018-04-23T12:40:00.133Z",
    "name": "Personal",
    "userId": "myUserId"
  }
]
Creemos una solicitud HTTP en JMeter para consultarlos.Es simple, como se muestra en la captura de pantalla a continuación.

 APILlamar a miembros de punto final desde JMeter

Aquí configuramos una solicitud HTTP para consultar el espacio de trabajo del usuario:

Método http: Debe serGETSolicitud sin parámetros
Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
Nombre de host：api.octoperf.com，
Camino：/workspaces/member-of。
¿Se acabó?Aún noActualmente, si no proporcionamos un token de autenticación, el servidor rechazará nuestra solicitud.

 El servidor devolvió un error.

Servidor aError HTTP 4xxRechazar solicitud：401 Unauthorized。

Similar a 403 Prohibido, pero específicamente para situaciones donde se requiere autenticación y ha fallado o no se ha proporcionado.

Necesitamos pasarAuthorizationA peticiónContieneEncabezados vienenProporcionar token de autenticación。Como esHastaSolicitudAgregarAdministrador de encabezado HTTP。

Agregar encabezado de autorización
 Establecer el token extraído en el encabezado de autorización

Recuerda: ya tenemostokenDe/public/users/loginRespuesta del servidor de punto finalExtraído。Ahora es tiempo de reutilizarlo para recuperarAcceso protegidoRecursos:

PrimeroEngetWorkspaces HTTP Request AbajoAgrega unoHttp Header Manager，
AgregarAuthorizationCon valorDeEncabezadoBearer ${token}。
 Obtener espacio de trabajo del servidor

Eso es genial!¡Está funcionando ahora!Tenemos todos los espacios de trabajo que pertenecen al usuario conectado.

 Se envió el encabezado de autorización en la solicitud

El encabezado de autorización se incluyó correctamente en el encabezado de la solicitud.Sin embargo, una cosa es molesta:El formato Json es incorrecto。Por qué

La mayoría de los servidores envían json en formato compacto, omitiendo la sangría.Esto es por razones de rendimiento (reducir el uso de ancho de banda y el uso de CPU del servidor)

Formato de respuesta Json
Para resolver este problema,JSON Formatter PostProcessorPuede hacer bien el trabajo.

JMeter Json Formatter PostProcessorJMeter Json formateador postprocesador

Mira nuestroGuía de instalación del complemento JMeterPara aprender a instalarComplemento Json。Otra opción es usarScript JSR223Formatee Json usted mismo。

JMeter Json ¡Json imprime maravillosamente ahora!

Ahora podemos usarJson Assertion(EnJMeter 4.0Introducir）Características de gran alcancePara verificar la respuesta del servidor.

Usar afirmación Json
Nos aseguraremos de que la respuesta del servidor contengaPersonalÁrea de trabajoEsto esEl trabajo asertivo de Json。Para agregar aserciones Json, haga clic con el botón derecho en la muestra de solicitud HTTP y seleccioneAdd > Post Processor > Json Assertion。

Configuracion
JMeter Json La respuesta de afirmación contiene un espacio de trabajo personal

Json afirma la configuración de la siguiente manera:

La ruta Json afirmada existe：$.[1]['name']Se refiere a la segunda área de trabajo devuelta y tomadaname，
Valor de afirmación: Verificar para verificarnameCampoEl valor de，
Valor esperado: Debería serPersonal。
Ejecutar
Supongamos que afirmamosValor esperadoSiOtherNo esPersonal。

JMeter Json Encuentra el nombreOtrosEspacio de trabajo, la aserción Json falla

Como se esperaba, la afirmación falla con el siguiente mensaje:

Assertion error: false
Assertion failure: true
Assertion failure message: Value expected to be 'Other', but found 'Personal'
Rendimiento
Por supuesto, no está limitado a usar Json Assertion.Si te gustaTambién se puede utilizarJMeter Response Assertion。SeEn términos de rendimientoInclusoBeneficiosoPorqueDe acuerdo a nuestroTabla de comparación de rendimiento de afirmación，Afirmación de respuestaConsume menos recursos de CPU / memoria que las aserciones de Json。

Simula comportamiento dinámico
Ahora sabemos cómo iniciar sesión en la API de Json Rest y enviarAcceso protegidoPunto finalSolicitudVamos a ver comodynamically behavingUsando JMeterSimulaciónUsuario.

Esta es la última parte de este tutorial:

Primero lo haremosExtraer ID de espacio de trabajo aleatorio, (Will${workspaceId}）
Segundo, usaremos el punto final para consultar el proyecto para ese espacio de trabajo/projects/by-workspace/${workspaceId}/DESIGN。
Projects Rest APIPunto final de API de Rest de proyectos de OctoPerf

El último punto final de Rest API nos interesa.Lo llamaremos desde JMeter, pero primero necesitamosExtraer un espacio de trabajo aleatorio。

Extraer WorkspaceId
JMeter Json Extraer ID de espacio de trabajo aleatorio

Extractor está configurado comogetWorkspacesSolicitudPost procesador,Tiene la siguiente configuración:

Crear nombre de variable：workspaceId，
Expresión de Json Path：$..id，
Número de partido：0Esto es al azar.
Esto extraerá un espacio de trabajo aleatorio y lo colocará en${workspaceId}Variable

Elemento de consulta
Finalmente, necesitamos consultar el proyecto en función del contenido extraído previamenteworkspaceId。Para esto yoCopiar y modificar solicitud previaPara tener algo de tiempo.

JMeter Json Consultar proyecto usando workspaceId variable

Aquí configuramos una solicitud HTTP para consultar el proyecto del espacio de trabajo:

Método http: Debe serGETSolicitud sin parámetros
Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
Nombre de host：api.octoperf.com，
Camino：/design/projects/by-workspace/${workspaceId}/DESIGN。DESIGNEl estado de los proyectos contenidos en el espacio de trabajo.(Y no el resultado, esto seríaRESULT）
¡Creo que estamos listos para una iteración rápida para probar esto!

Ver resultados
JMeter Json La ejecución conduce al elemento de consulta

Si ejecutamos al usuario varias veces, veremosFactor de respuestaExtracciónDeEspacio de trabajo aleatorioMientras queDiferente。

Palabras finales
JMeterExcelente para las pruebas de API Rest, especialmente aquellas basadas enPrueba de formato Json。Probar Json API con JMeter es muy fácil。

Básicamente, si dominasMencionado arribaDeComponentes JMeter, Entonces eres feliz!

Si desea profundizar más, le recomiendo leer nuestro artículo:

JMeter JsonPath Extractor: Extraiga cualquier cosa de la respuesta de Json para aprender sobreSintaxis de JsonPathMás información，
JMeter Json Assertion: Afirmando específicamente la respuesta json,
YComplemento JMeterComoFormato JsonPuede hacer que tu vida sea mucho más fácil de pasarFormato de salida。
Si lo encuentra útil, ¡no dude en compartir esta guía!

Reimpreso en: https://www.cnblogs.com/a00ium/p/10351482.html


Recomendación Inteligente

[Esquema] Algunos tiros
Soy responsable del diseño de roles, las configuraciones de escena han sido dibujadas por algunos conceptores de pinturas originales. Recientemente me han determinado el guión, prob&eacu...


¿Cómo utilizar EFM32 ZERO GECKO para medir el consumo de energía de otras placas?
1. Descargue el software de desarrollo de Silicon:Simplicity Studio 4 2. Primero, debe comprar una pieza: EFM32ZG-STK3200; 3. Descargue el SDK relacionado:Uso de Simplicity Studio 4 4. Conexión...

Disparador en MySQL (disparador)
1. Activar en MySQL nuevo ---- se refiere al objeto que activó el disparador Ejemplos de bienes y precios totales Después ---- Ejecuta el código lógico de disparo despu&eac...


Remote Debugging connecting to a Remote Stub using the Microsoft Debugging Tools for Windows
The Microsoft Debugging Tools for Windows provide a couple ways to create a remote debugging connection including "Connecting to a remote session" and &quo...

operador php / función / matriz / cadena
1 Operadores aritméticos Operador expresión Operador de suma $a+$b Operador de resta $a-$b Operador de multiplicación $a*$b Operador de división $a/$b Operador de mó...


También te puede interesar

[Notas de estudio del sistema operativo] - [2] Proceso, subproceso, punto muerto
Este artículo hace referencia a: JavaGuide Sistema operativo de posgrado Kingsway CS-Notes Directorio de artículos 1. El concepto, composición y características del proceso...


Newbe.Claptrap-Un marco de desarrollo del lado del servidor basado en "Trazabilidad de eventos" y "Modo actor" ...
Este artículo es una introducción al contenido principal del proyecto Newbe.Claptrap. Los lectores pueden utilizar este artículo para obtener una comprensión general del co...


[Serie Leetcode] [Algoritmo] [Medio] Diferentes árboles de búsqueda binaria II (problema de números de Cattelland))
tema: Enlace de título:https://leetcode-cn.com/problems/unique-binary-search-trees-ii/   Ideas de resolución de problemas: Si solo pide el número, puede pasar directamenteN&u...

Método para transmitir archivos entre Linux
　　 Financiado en: https://www.cnblogs.com/jeray/p/8761264.html...

Cierres
Tabla de contenido Expresión de cierre Cierre final Captura de valor El cierre es un tipo de referencia Cierre de escape Los cierres adoptan una de las siguientes tres formas "Una funci&oa...



Artículos relacionados
API de parámetro dinámico de prueba de JMeter
Ruby llama al método de prueba API REST
Guía de la API del marco REST de Django (26): pruebas
Wisdom RESTClient es una herramienta para pruebas automatizadas de REST API.
Cómo usar jmeter para la prueba de presión de la interfaz API
Utilice jmeter para la prueba de esfuerzo de la interfaz api
Jenkins Ant Jmeter integró pruebas de API automatizadas.
Prueba automatizada de Dubbo API basada en JMeter (3)
Prueba automatizada de Dubbo API basada en Jmeter (6)
Utilice Jmeter para realizar pruebas de rendimiento en API

Articulos Populares
openpyxl lee archivos execl (dos) hojas múltiples
Notas de estudio de Android diez: componentes básicos de la vista: ImageView e ImageButton
Acerca de los escenarios de aplicación específicos y el uso de CDN
El mecanismo de actualización de DOM en Angular
Variables de plantilla y filtros de plantilla Referencia a archivos estáticos
Esperando efecto de animación
Instale la herramienta de captura de pantalla Shutter en ubuntu y configure la tecla de acceso directo Ctrl + SuperL
Intellij IDEA nuevo proyecto javaweb en Mac
MyEclipse chino
Complemento forzado de Jenkins (notas de estudio ocho)

Artículo Recomendado
DAPP-TAIQUIAN - Cadena de distrito - Contrato de función - Relación Bitcoin
vue.min.js:288 ReferenceError: acEntity is not defined
Tres preguntas de la entrevista sobre "Clases internas"
Subplantilla art-template
Practicación de samba
[Descubrimiento de características] Características de Java encontradas en la suma de secuencias de palíndromos
Ir al límite de goroutine
La relación entre varias secuencias en la operación de archivos java (3)
Descarga del archivo de simulación (1): descarga manual
Ventana, ajuste de la aplicación Linux ---- Método de proceso de depuración de archivos de escritura

Etiquetas Relacionadas
JMeter
Prueba
Parámetros dinámicos
url
api
Pruebas de rendimiento
Pintura original
sistema operativo
Serie Leetcode


© 2020-2022 All rights reserved by programmerclick.com
