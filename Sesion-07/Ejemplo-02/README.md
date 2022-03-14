# Ejemplo # 2 - Creación proyecto JMeter con Selenium

## Objetivo

Demostrar aplicación de selenium en proyecto de JMeter para pruebas de rendimiento.

## Desarrollo

**Requisitos previos**

Se deben cumplir los siguientes requisitos previos antes de ejecutar un script de Selenium con JMeter :

- Tener JMeter instalado en el sistema que ya hemos trabajado en las sesiones anteriores
- Instalar el complemento " Selenium/WebDriver" usando el administrador de complementos JMeter
- Descargar los binarios del controlador gecko/chrome en el sistema

Ahora podemos avanzar y crear un proyecto JMeter de muestra para ejecutar el script de Selenium.

**Proyecto JMeter - Selenium**

Creamos un Proyecto JMeter para configurarlo y probarlo. Crearemos un Thread Group que tendrá una instancia de Selenium Web Driver Sampler. Incluiremos un script de Selenium en esta muestra y luego lo ejecutaremos.

A continuación se proporciona una descripción detallada:

1. Primero, lanzamos nuestra GUI de JMeter:

![1](https://user-images.githubusercontent.com/22419786/158092696-14021357-f312-48e7-a401-30fdb9483bc0.png)

2. Luego, podemos agregar un "Grupo de subprocesos" simple haciendo clic en "Editar-> Agregar" y seleccionar el Grupo de subprocesos

![2](https://user-images.githubusercontent.com/22419786/158093588-0e6149b1-0aa3-497e-bdcd-79a5c1428307.png)

3. Luego, necesitamos agregar la configuración del controlador de Chrome. Ahora, hacemos clic en la configuración del controlador de Chrome en el panel izquierdo y especificamos la "Ruta al controlador de Chrome":

![3](https://user-images.githubusercontent.com/22419786/158093597-1712dc4a-f7fa-43e4-98e5-5716b60439f8.png)

4. Se debe tener en cuenta que la versión del navegador Chrome debe coincidir con la versión "Chromedrive.exe" para que el script se ejecute correctamente. A continuación, debemos agregar la muestra del controlador web al grupo de subprocesos:

![4](https://user-images.githubusercontent.com/22419786/158093602-dc79ae53-0032-48a2-a63d-e623b17a11ae.png)

5. Podemos agregar el script que se proporciona a continuación al grupo de hilos:

*WDS.sampleResult.sampleStart()
WDS.browser.get('http://blazedemo.com')
WDS.sampleResult.sampleEnd()
WDS.log.info("successfully navigated to http://blazedemo.com/");*

6. Finalmente, agreguemos un escucha 'Ver resultados en tabla' y/o "Ver árbol de resultados" para que podamos ver los resultados de la ejecución del script.

El grupo de subprocesos que creamos arriba se ve como se muestra en la siguiente imagen:

![5](https://user-images.githubusercontent.com/22419786/158093606-cae1bfdc-ef02-41ef-a38e-39493062c7b3.png)

7. *Ejecutar el script de Selenium*: Ahora hemos creado el grupo de subprocesos con el script de Selenium que queremos ejecutar. A continuación, "Ejecutamos el grupo de subprocesos" .

Se crea la instancia de Selenium Web Driver y se abre una nueva ventana de controlador de Chrome que abre la página de inicio de Blazedemo:

![6](https://user-images.githubusercontent.com/22419786/158093613-cb9d681c-fac5-45df-a03f-d1e61f3878e1.png)

8. Como podemos ver en la tabla de resultados de JMeter anterior, hemos ejecutado con éxito el Grupo de subprocesos que contenía un script de Selenium simple que abrió una nueva ventana del navegador Chrome y luego abrió la página web especificada. De esta manera, podemos ejecutar cualquier secuencia de comandos de Selenium agregando un ejemplo de WebDriver en el grupo de subprocesos y luego ejecutándolo.
