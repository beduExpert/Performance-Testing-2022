## Sesión 3: Tipos de Pruebas con JMeter 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Exponer la correcta forma de generar pruebas de carga hasta su límite permitido de usuarios.
- Simular peticiones a partir de las pruebas de estres enviando más usuarios de los que acepta la aplicación.
- Generar pruebas de estabilidad para conocer la cantidad de usuarios permitidos en la aplicación.
- Ejecutar pruebas de recuperación cuando una prueba de carga falla.

### 2. Contenido :blue_book:

Las pruebas de rendimiento se dividen en 4 tipos que son las pruebas de carga, las de estrés, las de estabilidad y las de confiabilidad o recuperación. Estas pruebas nos ayudan a mostrar si existe algun cuello de botella en nuestra aplicación.
  
  En el siguiente ejemplo podemos ver como tener lista nuestra herramienta JMeter para iniciar las pruebas de nuestra aplicacion web.
  
  - [**`EJEMPLO 1 - Preparación aplicación web y JMeter para pruebas de rendimiento`**](./Ejemplo-01)

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Pruebas de Carga</ins>

Las pruebas de carga  
  
Ya con nuestra configuración y preparación hecha en el ejemplo 1, veremos que factores se deben tener en cuenta y como realizar prueba de carga en este [**`EJEMPLO 2 - Parámetros y ejecución de prueba de Carga`**](./Ejemplo-02)
  
 Con esta práctica podemos iniciar nuestro reto para este tipo de pruebas
  
- [**`RETO 1 - Prueba de Carga`**](./Reto-01)
---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Pruebas de Estrés</ins>

Este tipo de pruebas sirven para determinar la solidez de la aplicación, de manera que empecemos a bombardear la aplicacion con consutar y poder determinar cuando la aplicación se rompe, o presenta errores. Aquí podemos determinar cual es el límite de consultas simultaneas que la aplicación puede tener.
  
En esta prueba lo que se hace es duplicar la cantidad de usuarios de consulta de la aplicación, es decir, si mi aplicación acepta 10 usuarios lo que hacemos es enviarle 20, despues 40 usuarios, despues 80, despues 160 y así sucesivamente hasta que la aplicación en alguna de las pruebas se rompa, allí podemos sacar el punto máximo donde la aplicación ya no es capaz de procesar todas las peticiones al tiempo.

Ya con nuestra configuración y preparación hecha en el ejemplo 1, veremos que factores se deben tener en cuenta y como realizar prueba de estres en este [**`EJEMPLO 3 - Parámetros y ejecución de prueba de Estres`**](./Ejemplo-03)
  
 Con esta práctica podemos iniciar nuestro reto para este tipo de pruebas
  
- [**`RETO 2 - Prueba de Estrés`**](./Reto-02)

---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Pruebas de Estabilidad</ins>

Estas pruebas nos ayudan a identificar si la aplicacion puede soportar una carga continuada, un ejemplo de una carga continuada es que haya una aplicación que reciba 10 usuarios y la prueba aquí es ingresar las pruebas en un ciclo infinito done se hacen las 10 consutas, luego se vuelven a hacer las 10 consultas, luego se vuelven a hacer las 10 consultas y así sucesivamente, esto nos sirve para encontrar si hay fugas en la aplicación, ya que al hacer un ciclo infinito, va a llegar un punto donde la memoria se va a rebosar y podremos ver si la aplicación resiste un tiempo significativo de cargas continuadas.
  
Ya con nuestra configuración y preparación hecha en el ejemplo 1, veremos que factores se deben tener en cuenta y como realizar prueba de estabilidad en este [**`EJEMPLO 4 - Parámetros y ejecución de prueba de Estabilidad`**](./Ejemplo-04)
  
 Con esta práctica podemos iniciar nuestro reto para este tipo de pruebas
  
- [**`RETO 3 - Prueba de Estabilidad`**](./Reto-03)
---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4: Pruebas de Confiabilidad o Recuperación</ins>

Las pruebas de confiabilidad o recuperación son pruebas no funcionales que determinan la capacidad del software para recuperarse de fallas como fallas de software / hardware o cualquier falla de la red.
  
Ya con nuestra configuración y preparación hecha en el ejemplo 1, veremos que factores se deben tener en cuenta y como realizar prueba de confiabilidad o recuperación en este [**`EJEMPLO 5 - Parámetros y ejecución de prueba de Confiabilidad o Recuperación`**](./Ejemplo-05)
  
 Con esta práctica podemos iniciar nuestro reto para este tipo de pruebas
  
- [**`RETO 4 - Prueba de Confiabilidad o Recuperación`**](./Reto-04)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 1`**](./Postwork/)

<br/>


</div>

