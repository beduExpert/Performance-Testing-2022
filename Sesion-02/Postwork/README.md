# Sesión # 2 - Grabando Test Scripts

## :dart: Objetivos

* Grabar escenarios de prueba con una de las herramientas externas
* Crear las solicitudes (acciones) del navegador a la aplicación web
* Ejecutar las pruebas de rendimiento a partir de los script grabados

## Desarrollo

En esta sesión hemos visto que existen herramientas de grabación externas a JMeter pero que se integran con esta para la ejecución de pruebas de rendimiento, 2 de estas son BlazeMeter y BadBoy.

**Iniciemos:**

* Selecciona una de estas dos herramientas (con la que te sientas más cómodo) para grabación y ejecución de acciones en el navegador
* Descarga la herramienta
* Identifica una página web a la que desees hacerle la grabación de pasos y acciones.
* Inicia la grabación desde tu herramienta seleccionada
* Integrala a JMeter
* Realiza las siguientes pruebas en tu estructura del proyecto de JMeter
    - Ejecutar con 20 hilos (usuarios) la transacción con intervalos de 2 segundos la petición.
        Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos.

    - Ejecutar con 30 hilos (usuarios) la transacción con intervalos de 1 segundos la petición.
        Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos.

    - Ejecutar con 100 hilos (usuarios) la transacción con intervalos de 2 segundos la petición.
        Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos

**Recuerda que:**

* Debes haber configurado el proxy de tu navegador para la comunicación con JMeter
* Debes haber descargado la herramienta que elegiste para tu prueba
* Debes integrar la grabación que hiciste con tu herramienta seleccionada con JMeter para la ejecución de los casos
