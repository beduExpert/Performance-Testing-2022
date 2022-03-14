# Ejemplo # 3 - Creación proyecto JMeter con Selenium y JUnit

## Objetivo

Configurar y ejecutar escenario de prueba utilizando JMeter, Selenium y el marco de trabajo JUnit.

## Desarrollo

Primero necesitamos instalar algunas cosas:

- Selenium
- JMeter
- JMeter Plugin WebDriver
- WebDrivers de Chrome, Firefox y/o Edge
- WebDriver Language Bindings para Java
- Intellij Idea o algun otro IDE para Java

Con todo esto podemos comenzar a grabar nuestras pruebas en Selenium. A continuación tenemos un ejemplo:

![1](https://user-images.githubusercontent.com/22419786/158105366-29e56655-3239-412e-978d-33477b63cacb.png)

Luego podemos exportar el script de Selenium a un archivo JUnit:

![2](https://user-images.githubusercontent.com/22419786/158105372-9afc6427-5c85-45df-95d4-c62f5253b3bc.png)

![3](https://user-images.githubusercontent.com/22419786/158105431-655c1a3f-f64f-42c8-9fdc-2987a3f0206c.png)

Finalmente abrimos nuestro IDE de Java (aqui vamos a usar Intellij Idea) y creamos un proyecto de tipo JAVA para añadir nuestro archivo. También se debe crear una carpeta “lib” con las archivos WebDriver Language Bindings descargados desde la pagina de Selenium. La estructura del proyecto debe quedar mas o menos asi:

![4](https://user-images.githubusercontent.com/22419786/158105435-fbff8fc1-9fd5-414b-a459-1f74cb1b7c29.png)

Ahora se deben agregar los paquetes (o librerias) necesarias(como el JUnit); pero en caso de las librerías de Selenium, se deben referenciar los JARs. Para ello, dentro de Intellij Idea vamos al menú:

![5](https://user-images.githubusercontent.com/22419786/158105436-7ea77bde-3580-4f64-a609-f56b9ebe5253.PNG)

Seleccionamos la sección de Dependencies en:

![6](https://user-images.githubusercontent.com/22419786/158105437-512ed814-da50-4dad-9e0f-29bcdd6c7d13.PNG)

Alli agregamos todos los Jars descargados, incluidos los que se encuentran dentro de la carpeta “libs”:

![7](https://user-images.githubusercontent.com/22419786/158105439-09d90037-1742-4f82-bf5a-194c42e36c70.png)

En algunos casos es necesario “ajustar” los selectores de los elementos. También podemos añadir instrucciones para que el test “espere” a la existencia de determinados elementos:

![8](https://user-images.githubusercontent.com/22419786/158105441-eb98e82b-2fbf-4ed0-b6dd-02b48c15e025.PNG)

También se debe configurar el PATH de los WebDrivers; para ello modificamos la función public void setUp() para que quede asi:

![9](https://user-images.githubusercontent.com/22419786/158105442-089f24ce-ba1f-4c5d-8846-c949292663c2.PNG)

En esta sección se determina si se va a usar Chrome, Firefox o Edge para las pruebas

Para terminar, en el caso de Intellij Idea, es necesario especificar la “configuración” de compilación. Para ello, se va a utilizar un proyecto de NUnit para que quede similar a:

![10](https://user-images.githubusercontent.com/22419786/158105444-efedb1d2-831e-4a7f-872c-9c47dd5d666d.png)

Ya podemos ejecutar el proyecto y ver cómo nuestro test grabado en Selenium se reproduce integramente como una caso de pruebas de JUnit. Para eso se procede a crear el archivo JAR a partir del código generado. Para ello debemos crear “Artefacts” en Intellij Idea desde el siguiente menu:

![11](https://user-images.githubusercontent.com/22419786/158105445-96038cd5-244c-42a6-8506-00214beb7b52.PNG)

Seleccionamos la sección de Artifacts en:

![12](https://user-images.githubusercontent.com/22419786/158105446-016c4ce3-2caa-4ea0-b5f9-0388e1227bc9.PNG)

![13](https://user-images.githubusercontent.com/22419786/158105447-5471bad6-b6ca-40d5-b54f-336d74165681.png)

Es importante marcar la opción Include in project builder y anotar el PATH de salida:

![14](https://user-images.githubusercontent.com/22419786/158105448-50e949c2-3288-461b-8c67-fd1a2b2bedbc.png)

Con todo esto, ya se tiene el archivo JAR necesario para importarlo a JMeter. Para ello, copiamos el JAR en el siguiente path:

![15](https://user-images.githubusercontent.com/22419786/158105449-59eed26d-a933-401c-98b1-31c9fa14bb7a.PNG)

Ahora, abrimos JMeter y añadimos los siguientes elementos:

![16](https://user-images.githubusercontent.com/22419786/158105451-f2e5ed8a-6d31-4dd2-9023-d87cc13ece23.PNG)

![17](https://user-images.githubusercontent.com/22419786/158105452-14c27b92-4dc0-4668-a278-37a549917016.png)

Con esto, podemos ir al modulo JUnit Request y marcar la opción Search for JUnit 4 annotations (instead of JUnit3); esto desplegará las ClassName de los JARs que estan en la carpeta \jmeter-x.x\lib\junit:

![18](https://user-images.githubusercontent.com/22419786/158105453-b154cb27-0659-43d1-9694-08b0fa7fd012.png)

Podemos marcar las opciones Append assertion errors y Append runtime exceptions que se encuentran en la parte inferior de la ventana de configuración del JUnit Request.

Con todo esto, podemos ejecutar el TEST y veremos como se reproduce el script de nuestra librería JUnit, presionando el boton START de la barra de herramientas, o presionando los botones Ctrl + R


**Por tener en cuenta**

Podemos crear nuestro proyecto como un WebDriver Sampler, por lo que debemos descargar el JMeter Plugin WebDriver y descomprimir el archivo en la carpeta lib de la instalación de JMeter.

Ahora, abrimos JMeter y añadimos los siguientes elementos:

![19](https://user-images.githubusercontent.com/22419786/158105455-8e3e9f6b-70af-4b45-8293-d2b31b6f411e.PNG)

En el elemento jp@gc WebDriver Sampler podemos añadir nuestro propio código basado en lo que que se realizó con Selenium y JUnit:

![20](https://user-images.githubusercontent.com/22419786/158105456-4801e221-81a5-4699-b26f-ba8ceda127ed.png)

Se puede acceder a este enlace para ver la documentación sobre Web Driver Sampler.

El codigo es muy similar a lo que se tiene escrito en Java para JUnit

![21](https://user-images.githubusercontent.com/22419786/158105457-a4837a52-6f86-4b9e-b372-a63b6164bdc2.PNG)
![22](https://user-images.githubusercontent.com/22419786/158105458-5ce9f926-d71c-426f-98af-5a02760d8d88.PNG)
![23](https://user-images.githubusercontent.com/22419786/158105461-cd0814d2-29be-45fb-bd5a-c5e7ab92b4d7.PNG)

Finalmente en el apartado de Chrome Driver Config se debe establecer el PATH del WebDriver de Chrome:

![24](https://user-images.githubusercontent.com/22419786/158105462-68000adc-b8a5-4a19-b0cf-f2a2cca72f31.png)

Al igual que con JUnit, los resultados de la ejecuci;ón se almacenan en los Listeners
