# Sesión 1: Introducción a Performance Testing & JMeter 

## :dart: Objetivos

- Ejecutar escenario de prueba con otros datos.
- Emplear una transacción sencilla de una página web.


## Desarrollo

En esta sesión se harán variaciones a los datos que se envían en las peticiones con respecto a cantidad de usuarios vs tiempo de petición, tanto en la misma transacción como en una nueva.

**Asegúrate de comprender:**

- Cómo se estructura un test plan.
- Dónde se indican las variables de prueba (hilos y tiempos).

**Indicaciones Generales**

Con lo trabajado en el work, ya hemos hecho la grabación y ejecución de un escenario de prueba, en este paso vamos a interactuar con los datos enviados para las peticiones de prueba con las siguientes indicaciones:

* Ejecutar con **20 hilos** (usuarios) la transacción con intervalos de 2 segundos la petición.

Luego de la ejecución de la prueba de carga con 20 usuarios simultáneos revisamos el árbol de resultados donde vemos la cantidad de pasos exitosos vs. fallidos que resultaron, si no hay fallidos el sistema está soportando satisfactoriamente la cantidad de usuarios.

* Ejecutar con **30 hilos** (usuarios) la transacción con intervalos de 1 segundos la petición.

Luego de la ejecución de la prueba de carga con 30 usuarios simultáneos revisamos el árbol de resultados donde vemos la cantidad de pasos exitosos vs. fallidos que resultaron, si no hay fallidos el sistema está soportando satisfactoriamente la cantidad de usuarios, de lo contrario vamos revisando cuantos pasos fallidos resultaron y vamos comparando qué cantidad soporta el sistema.

* Ejecutar con **100 hilos** (usuarios) la transacción con intervalos de 2 segundos la petición.

Luego de la ejecución de la prueba de carga con 100 usuarios simultáneos revisamos el árbol de resultados donde vemos la cantidad de pasos exitosos vs fallidos que resultaron, si no hay fallidos el sistema está soportando satisfactoriamente la cantidad de usuarios, de lo contrario vamos revisando cuantos pasos fallidos resultaron y vamos comparando qué cantidad soporta el sistema. Ahora, si en alguno de los 2 pasos anteriores hubo muchos pasos fallidos este va a ser muy probable que ocurra con mayor cantidad.

