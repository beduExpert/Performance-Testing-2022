# Ejemplo # 1 - Instalación Eclipse y plugins Selenium

## Objetivo

Realizar la instalación y configuración de Selenium

## Desarrollo

En este ejemplo explicaremos paso a paso como configurar el entorno de desarrollo Eclipse para codificar pruebas automatizadas con Selenium Webdriver.

**Descargar Selenium WebDriver para Java**

Puedes descargar el Selenium Java Client Driver Aquí. Encontrará Drivers de cliente para otros lenguajes de programación allí, pero sólo elija el de Java.

![1](https://user-images.githubusercontent.com/22419786/158108052-0a038467-8b87-4c98-90b3-200f9f0540a5.png)

Esta descarga viene como un archivo zip llamado «selenium-java-3.6.0». Para simplificar, extraiga el contenido de este archivo zip en su unidad C para que tenga el directorio «C:selenium-java-3.6.0«. Este directorio contiene todos los archivos jar que posteriormente importamos en Eclipse.
Si aún no tienes descargado e instalado eclipse y java te recomiendo visitar la siguiente entrada: 
Cómo instalar Eclipse y java para Selenium Webdriver
Luego de tener instalado eclipse, java y descargado Selenium Java Client Driver, estaremos listos para empezar a configurar Eclipse para Selenium Webdriver.
 
1. Ejecute el archivo eclipse.exe ubicado dentro de la carpeta «Eclipse» que se encuentra en la ruta configurada al momento de instalar Eclipse.

2. Cuando se le pide que seleccione un espacio de trabajo (Workspace), simplemente acepte la ubicación predeterminada.
 
![2](https://user-images.githubusercontent.com/22419786/158108437-67a2a2bf-bc6d-42a2-98f2-66d300684c46.png)

3. Crear un nuevo proyecto a través de Archivo>New>Java Proyect. Nombrar el proyecto como «NewProject».

![3](https://user-images.githubusercontent.com/22419786/158108439-a3ad5c91-550a-4dd1-87fa-edf0fc6ddc80.png)

Se abrirá una nueva ventana emergente, diligenciar la ventana como a continuación.
 - Project Name
 - Location to save project
 - Select an execution JRE
 - Select layout project option
 - Click on Finish button

![3-1](https://user-images.githubusercontent.com/22419786/158108440-f78e26bc-d709-457e-9251-03e697d270a7.png)

4. En este paso, Haga clic con el botón derecho en el proyecto recién creado y Seleccione new > package  y nombre ese paquete como «newpackage».

![4](https://user-images.githubusercontent.com/22419786/158108442-2864facc-43b4-4bac-8f9f-ae2d784db8fd.png)

Una ventana emergente se abrirá para nombrar el paquete, introduzca el nombre del paquete haga clic en el botón «Finish»

![4-1](https://user-images.githubusercontent.com/22419786/158108444-649ad924-a5e0-4eb2-9c13-e72faea40584.png)

5. Cree una nueva clase Java en newpackage haciendo clic con el botón derecho en ella y, a continuación  New > Class, y a continuación, nombre como «MyClass». Eclipse debería verse como la imagen de abajo.

![5](https://user-images.githubusercontent.com/22419786/158108445-113de119-69ab-47e4-a5bd-b3257b27f50b.png)

6. Al hacer clic en «Class», se abrirá una ventana emergente, ingrese los detalles como
 - nombre de la clase 
 - haga clic en el botón «Finish»

![6](https://user-images.githubusercontent.com/22419786/158108447-8c2c74be-613b-4e8f-87df-d76f22380fa4.png)

7. Así es como se ve después de crear la clase.

![7](https://user-images.githubusercontent.com/22419786/158108448-6ea2af86-386a-4985-8c82-d2a32077fdfb.png)

8. Agregar Selenium WebDriver a nuestro proyecto

 - Haga clic con el botón derecho en «NewProject» y seleccione «Properties».
 - En el cuadro de dialogo «Properties», haga clic en «Java Build Path».
 - Haga clic en la pestaña Libraries , y entonces
 - Clic en  «Add External JARs..»

![8](https://user-images.githubusercontent.com/22419786/158108450-e66eb3ad-8dbc-42be-9460-c9d856c53edd.png)

9. Al hacer clic en «Add External JARs..» Se abrirá una ventana emergente. Seleccione los archivos jar que se encuentran en la carpeta «lib».

![9](https://user-images.githubusercontent.com/22419786/158108451-86e5c66c-da92-4624-af60-bc32d5965dec.png)

10. Seleccionar archivos fuera de la carpeta lib.

![10](https://user-images.githubusercontent.com/22419786/158108452-cf951ba5-c81f-4516-b63d-2f951d2cefdf.png)

11. Al agregar las anteriores Jar, damos clic en el botón «Apply and Close» y el cuadro de diálogo Propiedades debe verse similar a la imagen de abajo.

![11](https://user-images.githubusercontent.com/22419786/158108453-4a572e19-bfd7-4738-8f96-73de661b0e91.png)
