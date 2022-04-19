# Ejemplo 1: Parametrización de datos utilizando archivos externos

## Objetivo

* Elaborar pasos a paso una parametrización en JMeter utilizando archivos externos.

## Desarrollo

Una de las formas comunes de parametrizar sus scripts de rendimiento es usar un archivo CSV. El mejor ejemplo del uso de archivos de entrada CSV es un proceso de inicio de sesión. Si desea probar su aplicación con diferentes usuarios, debe proporcionar una lista de credenciales de usuario.

Supongamos que tenemos una solicitud de inicio de sesión que funciona para un usuario específico:

<img width="670" alt="1" src="https://user-images.githubusercontent.com/22419786/156495274-ae167287-4d95-4ef4-886c-e8b606dcae77.png">

Podemos parametrizar fácilmente esa solicitud usando un archivo CSV externo y ejecutando el script entre diferentes usuarios. Para agregar la configuración de parametrización de CSV:

Haga clic derecho en la solicitud de inicio de sesión -> Agregar -> Elemento de configuración -> Configuración de conjunto de datos CSV

<img width="670" alt="2" src="https://user-images.githubusercontent.com/22419786/156495285-345d4cd5-6841-48c0-a554-7d5911535aec.png">

**Una breve explicación de los parámetros 'CSV Data Set Config':**

* Nombre: nombre del elemento tal como se utilizará en el árbol de JMeter.
* Nombre de archivo: nombre del archivo de entrada. Los nombres de archivo relativos se resuelven en función de la ruta del plan de prueba activo. También se admiten nombres de archivo absolutos.
* Codificación de archivos: codificación del archivo de entrada, si no es el valor predeterminado de la plataforma.
* Nombres de variables: lista de nombres de variables separados que se utilizarán como contenedor para los valores analizados. Si está vacío, la primera línea del archivo se interpretará como la lista de nombres de variables.
* Delimitador: delimitador que se usará para dividir los valores analizados del archivo de entrada.
* ¿Permitir datos citados? - verdadero en caso de que desee ignorar las comillas dobles y permitir que dichos elementos contengan un delimitador.
* ¿Reciclar en EOF? - verdadero en caso de que el plan de prueba del archivo deba iterar sobre el archivo más de una vez. Le indicará a JMeter que mueva el cursor al comienzo del archivo.
* ¿Detener hilo en EOF? - falso en caso de iteración de bucle sobre el archivo CDC y verdadero si desea detener el hilo después de leer todo el archivo.
* Modo de uso compartido:
    - Todos los subprocesos: el archivo se comparte entre todos los usuarios virtuales (predeterminado).
    - Grupo de subprocesos actual: el archivo se abrirá una vez para cada grupo de subprocesos.
    - Subproceso actual: cada archivo se abrirá por separado para cada uno de los subprocesos.
    - Identificador: todos los subprocesos que comparten el mismo identificador también comparten el mismo archivo.


Vamos a crear un archivo csv que contenga diferentes usuarios con nombres y contraseñas.

<img width="448" alt="3" src="https://user-images.githubusercontent.com/22419786/156495294-0c74be11-5d04-46fc-8f65-519400a63431.png">

Ahora podemos usar este archivo con la configuración del conjunto de datos CSV. En nuestro caso, es suficiente agregar los valores de configuración "Nombre de archivo" y "Nombres de variables":

<img width="673" alt="4" src="https://user-images.githubusercontent.com/22419786/156495326-0be2671c-a636-4e84-9288-6bae910f5d68.png">

El último paso que tenemos que dar es parametrizar la solicitud de inicio de sesión con variables CSV. Esto se puede hacer sustituyendo los valores iniciales con las variables apropiadas del campo de configuración "Nombres de variables" de la configuración del conjunto de datos CSV, así:

<img width="671" alt="5" src="https://user-images.githubusercontent.com/22419786/156495335-40164f46-ee37-4378-8e3e-4c46e6a1f6ae.png">

sí ejecutamos nuestro script de prueba ahora, JMeter sustituirá estas variables con valores de los 'TestUsers. archivo csv'. Cada usuario virtual de JMeter recibirá credenciales de la siguiente línea del archivo csv.

La solicitud de inicio de sesión del primer usuario:

<img width="672" alt="6" src="https://user-images.githubusercontent.com/22419786/156495353-9f0aa8c4-1265-4f5a-ac1b-07f129f71fb6.png">

La solicitud de inicio de sesión del segundo usuario:

<img width="670" alt="7" src="https://user-images.githubusercontent.com/22419786/156495369-e3453fc4-396f-4621-b2ea-03fe110c0a69.png">


