## Solución
  
La solución a este reto es presentar las evidencias de la prueba de carga hecha en JMeter y haciendo uso de Selenium Web Driver.

**Pasos**

- Configurar la propiedad del sistema para el controlador chrome/gecko:

  - Primero vaya a la carpeta de instalación de JMeter.
  
  -Luego vaya al archivo “bin/system.propertis”
  
  - Ahora configure la ruta del sistema para el controlador gecko/chrome de la siguiente manera: (webdriver.chrome.driver=/home/knoldus/Downloads/apache-jmeter-4.0/bin/chromedriver), (webdriver.gecko.driver=/home/knoldus/ Descargas/apache-jmeter-4.0/bin/geckodriver)
  
  ![1](https://user-images.githubusercontent.com/22419786/158101508-3c58a4b5-9cb3-4aa7-8523-0441c6660782.png)
  
- Crear el proyecto en JMeter

  - Inicie la GUI de JMeter
  - Ahora agregue un grupo de subprocesos simple.
  - Inserte la configuración del controlador Firefox/chrome.
  - A continuación, agregue la muestra de controladores web al grupo de subprocesos.
  - Finalmente agregue el listner 'ver resultados en la tabla'.

![2](https://user-images.githubusercontent.com/22419786/158101576-23aef2da-14d8-474a-a537-3fed540afd62.png)

- Crear script en Selenium

*WDS.sampleResult.sampleStart()
WDS.browser.get('http://google.com')
WDS.sampleResult.sampleEnd()
WDS.log.info("Sample ended - navigated to http://google.com/");*

Así aparece en la herramienta, solo que en lugar de google.com debe presentar la url de la prueba.

![3](https://user-images.githubusercontent.com/22419786/158101646-43b5fa63-6ffd-4710-bfe7-351f9493b9b8.png)

- El listener de resultados presenta la información de la ejecución

![6](https://user-images.githubusercontent.com/22419786/158101786-ee7e7480-b1da-4688-a962-edddcd16a44b.png)

