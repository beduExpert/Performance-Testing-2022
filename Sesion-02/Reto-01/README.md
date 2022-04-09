# Reto 1: Grabación desde herramienta externa y ejecución en JMeter

## Objetivo

Grabar un escenario de prueba con una de las herramientas externas creando las solicitudes a la aplicación web desde dicha herramienta para ejecutar las pruebas de rendimiento a partir de los script grabados desde JMeter.


## Desarrollo

El reto en esta sesión consiste en seleccionar una de las 2 herramientas de grabación externas vistas en la sesión (BlazeMeter y BadBoy) para grabar un escenario de prueba y luego integrarlo con JMeter para que desde allí se configuren la cantidad de usuarios y tiempos de respuesta que las pruebas requieran, realizar la ejecución y revisión de resultados.

**Reto**

* Se debe identificar una transacción de cualquier página web para tener lista al momento de iniciar la grabación del escenario de prueba, puede ser un login, un registro, el ingreso a un homepage, etcétera.
* Elegir y descargar una de las 2 herramientas externas (BlazeMeter o BadBoy).
* Iniciar la grabación en la web para la transacción identificada.
* Integrar la grabación con JMeter en su estructura.
* En JMeter, incluir 15 números de usuarios (Threads) con 1 segundo de tiempo en cada petición.
* Realizar una prueba de rendimiento con esta información y presentar resultados.

**No Olvides**

* Configurar el Proxy para la comunicación entre las herramientas y el navegador.
