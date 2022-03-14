# Reto # 1 - Escenario de prueba JMeter con Selenium

## Objetivo

Generar escenario de prueba de carga en JMeter utilizando Selenium WebDriver

## Desarrollo

El reto de esta sesión consiste en presentar el resultado de la ejecución de un escenario de prueba de carga en JMeter utilizando Selenium Web Driver.

**Prerrequisitos**

- Instalación y configuración de JMeter
- Instalación y configuración de Selenium Web Driver
- Archivos binarios del controlador gecko/chrome descargados en el sistema.
- Establecer la propiedad del sistema para el controlador gecko/chrome en la carpeta de instalación de JMeter.

**Reto**

*- Configurar la propiedad del sistema para el controlador chrome/gecko:*

  - Primero vaya a la carpeta de instalación de JMeter.
  
  -Luego vaya al archivo “bin/system.propertis”
  
  - Ahora configure la ruta del sistema para el controlador gecko/chrome de la siguiente manera: (webdriver.chrome.driver=/home/knoldus/Downloads/apache-jmeter-4.0/bin/chromedriver), (webdriver.gecko.driver=/home/knoldus/ Descargas/apache-jmeter-4.0/bin/geckodriver)
  
*- Crear el proyecto en JMeter*

- Inicie la GUI de JMeter
- Ahora agregue un grupo de subprocesos simple.
- Inserte la configuración del controlador Firefox/chrome.
- A continuación, agregue la muestra de controladores web al grupo de subprocesos.
- Finalmente agregue el listner 'ver resultados en la tabla'.

*- Crear script en Selenium*
