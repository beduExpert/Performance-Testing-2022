# Sesión #1: Introducción a Performance Testing & JMeter 

## :dart: Objetivos

- Ejecutar escenario de prueba con otros datos.
- Grabar y ejecutar otra transacción sencilla de una página web.


## Desarrollo

En esta sesión se harán variaciones a los datos que se envían en las peticiones con respecto a cantidad de usuarios vs tiempo de petición, tanto en la misma transacción como en una nueva.

**Asegúrate de comprender:**

- Cómo se estructura un test plan
- Donde se indican las variables de prueba (hilos y tiempos)

**Indicaciones Generales**

Ya hemos hecho la grabación y ejecución de un escenario de prueba, en este paso vamos a interactuar con los datos enviados para las peticiones de prueba con las siguientes indicaciones:

* Ejecutar con 20 hilos (usuarios) la transacción con intervalos de 2 segundos la petición.

    Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos.


* Ejecutar con 30 hilos (usuarios) la transacción con intervalos de 1 segundos la petición.

    Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos.


* Ejecutar con 100 hilos (usuarios) la transacción con intervalos de 2 segundos la petición.

    Revisamos árbol de resultados y comparamos cantidad de pasos exitosos vs. fallidos
