# Ejemplo # 1 - Enviando Prueba API con JMeter

## Objetivo

Realizar pruebas de rendimiento en JMeter consumiendo una API

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

Bien! Ahora echemos un vistazo a las solicitudes requeridas para la falsificación con JMeter:

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

![3](https://user-images.githubusercontent.com/22419786/158842224-a3e640ac-61ca-4969-a953-93ca2a764cb5.png)

Aqui tenemos listo para el login nuestro Http Request, debemos enviar a nuestro servidor, se oculta la información confidencial, pero esta es básicamente la información de su cuenta. Para iniciar sesión de depuración utilizaremos View Results Tree Listener.

![4](https://user-images.githubusercontent.com/22419786/158842241-78a0173d-08af-42e9-9ea0-23855098fddf.png)

Podemos ver que la solicitud enviada es un POST-forma-codificado, que contiene nuestro nombre de usuario y contraseña. Ahora vamos a enviar al servidor de respuesta el  Json interesado。

![5](https://user-images.githubusercontent.com/22419786/158842273-b70c48c4-8503-4f3b-a9f1-1b631c40fffd.png)

Ahora hemos recibido el Token de autenticación y podemos extraerlo para reutilizarlo en solicitudes posteriores.

**Extraer token de autenticación**

Autenticación basada en tokens

Es un mecanismo simple donde los tokens se identifican de forma exclusiva para la sesión del usuario。Necesitamos hacer uso de esto dynamic parameter para imitar adecuadamente conJson API Usuario interactivo。

**Use Json Extractor**
Para comenzar desde la respuesta del servidor se extrae el token de autenticación y usaremos JMeter JsonPath Extractor。El proceso de extracción de variables de la respuesta es el siguiente:

1. El servidor devuelve una respuesta a nuestra solicitud de inicio de sesión,
2. UnPostprocesadorComoExtracción JsonPathEstá siguiendo la ejecución
3. ExtractorExtrayendo parte de la respuesta del servidorY ponerlo en una variable${token}。

![6](https://user-images.githubusercontent.com/22419786/158842296-f8198474-4138-4eae-bc90-25d59a190c78.png)

TenemosUse esta configuraciónConfiguradoJMeter Json Extractor：

* Crear nombre de variable：token, Lo que conducirá a variables reutilizables con sintaxis${token}，
* Expresión de Json Path：$.token，Para mas informacion,VerEjemplo de expresión JsonPath，
* YMatch Nr: Simplemente1Primero apareció.Pero podemos dejarlo en blanco.

¿Ves dónde puse el extractor?EnloginBajo una solicitud HTTP.También agregamos unoDebug SamplerPara ver si las variables se extrajeron correctamente.

**Habilitar depuración**
 
![7](https://user-images.githubusercontent.com/22419786/158842312-d110cc3e-43ad-4a29-b6bc-75194a78c25a.png)

EstableciendoVariables JMeterVentrueY habilitamos la muestraVariable de salidaDurante la prueba de funcionamiento.

**Extracción de prueba**

![8](https://user-images.githubusercontent.com/22419786/158842335-212f467d-f1bb-4244-8b65-345c84531bac.png)

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

![9](https://user-images.githubusercontent.com/22419786/158842360-bad54db1-22c1-4b9f-9f43-0420548ebffb.png)
 APIPunto final de la API de descanso del espacio de trabajo de la documentación de la API de Swagger

Lo haremosGETUsar ruta al punto finalEjecutarSolicitud/workspaces/member-of。Debería volverContiene espacio de trabajo del usuarioDeJsonRespuestaEste es un ejemplo de respuesta:

![10](https://user-images.githubusercontent.com/22419786/158842384-b5182852-e959-4c29-ab01-e508b0d4829b.PNG)

Creemos una solicitud HTTP en JMeter para consultarlos.Es simple, como se muestra en la captura de pantalla a continuación.

![11](https://user-images.githubusercontent.com/22419786/158842407-9afeabd3-d56b-4e95-bb39-bc2e3ef63347.png)

Aquí configuramos una solicitud HTTP para consultar el espacio de trabajo del usuario:

* Método http: Debe serGETSolicitud sin parámetros
* Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
* Nombre de host：api.octoperf.com，
* Camino：/workspaces/member-of。

¿Se acabó?Aún noActualmente, si no proporcionamos un token de autenticación, el servidor rechazará nuestra solicitud.

![12](https://user-images.githubusercontent.com/22419786/158842423-66104715-0518-4184-9d1d-e4485c449072.png)
 
 El servidor devolvió un error. Servidor aError HTTP 4xxRechazar solicitud：401 Unauthorized。

Similar a 403 Prohibido, pero específicamente para situaciones donde se requiere autenticación y ha fallado o no se ha proporcionado.

Necesitamos pasarAuthorizationA peticiónContieneEncabezados vienenProporcionar token de autenticación。Como esHastaSolicitudAgregarAdministrador de encabezado HTTP。

**Agregar encabezado de autorización** 

![13](https://user-images.githubusercontent.com/22419786/158842469-41e59f3d-3853-494d-b324-f1db3a0ed197.png)
Establecer el token extraído en el encabezado de autorización

Recuerda: ya tenemos token D/public/users/loginRespuesta del servidor de punto final extraído。Ahora es tiempo de reutilizarlo para recuperar Acceso protegido Recursos:

1. Primero EngetWorkspaces HTTP Request Abajo Agrega un Http Header Manager，
2. AgregarAuthorization Con valor De Encabezado Bearer ${token}。

![14](https://user-images.githubusercontent.com/22419786/158842521-10cef544-c9fb-42d7-bc0b-16ea01b763ea.png)

Obtener espacio de trabajo del servidor

Eso es genial!¡Está funcionando ahora!Tenemos todos los espacios de trabajo que pertenecen al usuario conectado.

![15](https://user-images.githubusercontent.com/22419786/158842530-a63d853d-925b-4d1b-8a38-9543e8023352.png)

 Se envió el encabezado de autorización en la solicitud

El encabezado de autorización se incluyó correctamente en el encabezado de la solicitud.Sin embargo, una cosa es molesta:El formato Json es incorrecto。Por qué

La mayoría de los servidores envían json en formato compacto, omitiendo la sangría. Esto es por razones de rendimiento (reducir el uso de ancho de banda y el uso de CPU del servidor)

**Formato de respuesta Json**

Para resolver este problema,JSON Formatter PostProcessor Puede hacer bien el trabajo.

![16](https://user-images.githubusercontent.com/22419786/158842561-ee2a310e-3e4e-41a5-abc5-0a7f269786e3.png)

JMeter Json Formatter PostProcessorJMeter Json formateador postprocesador

![17](https://user-images.githubusercontent.com/22419786/158842577-41705cba-a530-4fc9-9ed6-bfb29fde7711.png)

JMeter Json ¡Json imprime maravillosamente ahora!

Ahora podemos usarJson Assertion(EnJMeter 4.0Introducir）Características de gran alcancePara verificar la respuesta del servidor.

**Usar afirmación Json**

Nos aseguraremos de que la respuesta del servidor contenga Personal Área de trabajo Esto es el trabajo asertivo de Json。Para agregar aserciones Json, haga clic con el botón derecho en la muestra de solicitud HTTP y seleccioneAdd > Post Processor > Json Assertion。

**Configuracion**

![18](https://user-images.githubusercontent.com/22419786/158842618-c1db0089-bda4-4885-9a7b-64ca31229f80.png)

JMeter Json La respuesta de afirmación contiene un espacio de trabajo personal

Json afirma la configuración de la siguiente manera:

* La ruta Json afirmada existe：$.[1]['name']Se refiere a la segunda área de trabajo devuelta y tomadaname，
* Valor de afirmación: Verificar para verificarnameCampoEl valor de，
* Valor esperado: Debería serPersonal。

**Ejecutar**

Supongamos que afirmamosValor esperadoSiOtherNo esPersonal。

![19](https://user-images.githubusercontent.com/22419786/158842643-2567e5f3-4106-4aa2-be69-4cbc47d0cfb6.png)

JMeter Json Encuentra el nombre Otros Espacio de trabajo, la aserción Json falla

Como se esperaba, la afirmación falla con el siguiente mensaje:

![20](https://user-images.githubusercontent.com/22419786/158842669-119dde43-01c1-41b5-8cfa-58812356467e.PNG)

**Rendimiento**

Por supuesto, no está limitado a usar Json Assertion. Si te gusta, también se puede utilizar JMeter Response Assertion。En términos de rendimiento incluso es beneficioso porque de acuerdo a nuestra tabla de comparación de rendimiento de afirmación，afirmación de respuesta consume menos recursos de CPU / memoria que las aserciones de Json。

**Simula comportamiento dinámico**

Ahora sabemos cómo iniciar sesión en la API de Json Rest y enviar Acceso protegido a Punto final. Vamos a ver como dinámicamente behaving Usando JMeter Simulación Usuario.

Esta es la última parte de este tutorial:

* Primero lo haremosExtraer ID de espacio de trabajo aleatorio, (Will${workspaceId}）
* Segundo, usaremos el punto final para consultar el proyecto para ese espacio de trabajo */projects/by-workspace/${workspaceId}/DESIGN*

Projects Rest APIPunto final de API de Rest de proyectos de OctoPerf

![21](https://user-images.githubusercontent.com/22419786/158842751-e9bdcaa1-7c8d-4eda-b0d3-1dbda894d642.png)

El último punto final de Rest API nos interesa.Lo llamaremos desde JMeter, pero primero necesitamos Extraer un espacio de trabajo aleatorio。

**Extraer WorkspaceId** 

![22](https://user-images.githubusercontent.com/22419786/158842771-b3c6e321-c878-4161-aa52-71f85f758329.png)

Extractor está configurado comogetWorkspacesSolicitudPost procesador, tiene la siguiente configuración:

* Crear nombre de variable：workspaceId，
* Expresión de Json Path：$..id，
* Número de partido：0Esto es al azar.

Esto extraerá un espacio de trabajo aleatorio y lo colocará en${workspaceId}Variable

**Elemento de consulta**

Finalmente, necesitamos consultar el proyecto en función del contenido extraído previamente workspaceId。Para esto Copiar y modificar la solicitud previa para tener algo de tiempo.

![23](https://user-images.githubusercontent.com/22419786/158842795-30c41324-9bb9-4812-9057-d7f8fb08dd2f.png)

JMeter Json Consultar proyecto usando workspaceId variable

Aquí configuramos una solicitud HTTP para consultar el proyecto del espacio de trabajo:

* Método http: Debe serGETSolicitud sin parámetros
* Http Scheme：httpsGracias a nuestra API RestProtegido por SSL，
* Nombre de host：api.octoperf.com，
* Camino：/design/projects/by-workspace/${workspaceId}/DESIGN。DESIGNEl estado de los proyectos contenidos en el espacio de trabajo.(Y no el resultado, esto seríaRESULT）

¡Creo que estamos listos para una iteración rápida para probar esto!

**Ver resultados**

![24](https://user-images.githubusercontent.com/22419786/158842818-6ba76821-dfb0-4bf8-bee4-6b45ca353eca.png)

La ejecución conduce al elemento de consulta

Si ejecutamos al usuario varias veces, veremos factor de respuesta extracción de espacio de trabajo aleatorio。
