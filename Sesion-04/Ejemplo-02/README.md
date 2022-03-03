# Ejemplo # 2 - Parametrización de datos utilizando bases de datos

## Objetivo

* Elaborar pasos a paso una parametrización en JMeter utilizando diferentes bases de datos

## Desarrollo

Otra forma de parametrizar sus scripts de rendimiento es utilizar los datos de la base de datos a través de JDBC. JDBC es una interfaz de programación de aplicaciones que define cómo un cliente puede acceder a una base de datos.

En primer lugar, descargue el controlador JDBC en su base de datos (consulte al proveedor de la base de datos). Por ejemplo, el controlador mysql se puede encontrar aquí. Luego, puede agregarlo agregando el archivo .jar al plan de prueba usando el siguiente formulario:

<img width="671" alt="1" src="https://user-images.githubusercontent.com/22419786/156495995-5aa6f32b-ad7b-4af2-a325-7f1e19c1c036.png">

Pero es mejor agregar el archivo Jar en la carpeta lib y reiniciar JMeter.

Después de eso, configure la conexión de la base de datos utilizando el elemento 'Configuración de conexión JDBC'. Así: haga clic con el botón derecho en Grupo de subprocesos -> Agregar -> Elemento de configuración -> Configuración de conexión JDBC

<img width="672" alt="2" src="https://user-images.githubusercontent.com/22419786/156496004-c48c55d6-8a86-4903-b741-0de4fcbeadfb.png">

Parámetros de 'Configuración de conexión JDBC':

* Nombre: nombre de la configuración de conexión que se mostrará en el árbol de grupos de subprocesos
* Nombre de variable: nombre que se usará como identificador único para la conexión de base de datos (se pueden usar varias conexiones y cada una estará vinculada a un nombre diferente)
* Número máximo de conexiones: número máximo de conexiones permitidas en el conjunto de conexiones. En caso de 0, cada subproceso obtendrá su propio grupo con una sola conexión en él
* Espera máxima (ms): el grupo arroja un error si se excede el tiempo de espera especificado durante la conexión a la base de datos
* Tiempo entre ejecuciones de desalojo (ms): número de milisegundos para pausar entre ejecuciones del subproceso que desaloja las conexiones no utilizadas del grupo de db
* Confirmación automática: sí para activar la confirmación automática para conexiones de base de datos relacionadas
* Probar mientras está inactivo: verifique las conexiones inactivas antes de que se detecte una solicitud efectiva. Más detalles: BasicDataSource.html#getTestWhileIdle
* Soft Min Evictable Idle Time (ms) - período de tiempo durante el cual una conexión específica puede estar inactiva en el grupo de db antes de que pueda ser desalojada. Más detalles: BasicDataSource.html#getSoftMinEvictableIdleTimeMillis
* Consulta de validación: consulta de verificación de estado que se usará para verificar si la base de datos sigue respondiendo
URL de la base de datos: cadena de conexión JDBC para la base de datos. Ver aquí para ejemplos
* Clase de controlador JDBC: nombre apropiado de la clase de controlador (específico para cada base de datos). Por ejemplo, 'com.mysql.jdbc.Driver' para MySql db
* Nombre de usuario - nombre de usuario de la base de datos
* Contraseña: contraseña de la base de datos (se almacenará sin cifrar en el plan de prueba)

En nuestro caso, solo necesitamos configurar los campos obligatorios:

* Nombre de variable Vinculado a la agrupación.
* URL de la base de datos
* Clase de controlador JDBC
* Nombre de usuario
* Clave


El resto de los campos de la pantalla se pueden dejar por defecto:

<img width="671" alt="3" src="https://user-images.githubusercontent.com/22419786/156496028-107c1a56-75e4-4f2f-992f-ae8389a53159.png">

Supongamos que almacenamos las credenciales de usuario de prueba en la base de datos:

<img width="613" alt="4" src="https://user-images.githubusercontent.com/22419786/156496038-8506ff56-c741-4dc5-8627-eefb3de1fa9d.png">

Ahora, cuando la conexión de la base de datos está configurada, podemos agregar la solicitud JDBC y usar su consulta para obtener todas las credenciales de la base de datos: haga clic con el botón derecho en Grupo de subprocesos -> Agregar -> Muestra -> Solicitud JDBC

Al usar la consulta 'Select Statement' y 'Variable Names', podemos analizar la respuesta a las variables personalizadas.

<img width="673" alt="5" src="https://user-images.githubusercontent.com/22419786/156496044-034516da-c236-47b3-8968-fea1bfb8b78f.png">

Ahora tendremos variables de JMeter que se pueden usar más en solicitudes posteriores. Las variables especificadas se crearán con un sufijo incremental (email_1, email_2, email_3…..).

Para usar estas variables en la 'Solicitud de inicio de sesión', necesitamos agregar un contador que se usará para acceder a los valores correctos de la respuesta de consulta de JDBC. Para agregar el elemento 'Contador' en JMeter: haga clic derecho en Grupo de subprocesos -> Agregar -> Elemento de configuración -> Contador

<img width="672" alt="6" src="https://user-images.githubusercontent.com/22419786/156496062-458b8b6f-a2d8-4912-9e51-af1b6f9bf58a.png">

Después de eso, podemos actualizar la 'Solicitud de inicio de sesión' usando la función __V. Esto devuelve el resultado de evaluar una expresión de nombre de variable y se puede usar para evaluar referencias de variables anidadas:

<img width="674" alt="7" src="https://user-images.githubusercontent.com/22419786/156496070-70969e8b-fcfa-4cf2-a2f9-c97423bb2ba5.png">

La configuración especificada es suficiente para usar los valores de la base de datos para ejecutar el script en diferentes usuarios:

<img width="673" alt="8" src="https://user-images.githubusercontent.com/22419786/156496079-db24d365-282b-4ef2-8359-cdc0e0ba3b68.png">


<img width="583" alt="9" src="https://user-images.githubusercontent.com/22419786/156496088-6cad1ae1-a2ac-42ab-8e76-2767d683052c.png">
