## Sesi贸n 3: Tipos de Pruebas con JMeter 馃

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Demostrar la forma correcta de generar pruebas de carga hasta su l铆mite permitido de usuarios.
- Simular peticiones a partir de las pruebas de estr茅s enviando m谩s usuarios de los que acepta la aplicaci贸n.
- Generar pruebas de estabilidad para conocer la cantidad de usuarios permitidos en la aplicaci贸n.
- Ejecutar pruebas de recuperaci贸n cuando una prueba de carga falla.

### 2. Contenido :blue_book:

Las pruebas de rendimiento se dividen en 4 tipos que son las pruebas de carga, las de estr茅s, las de estabilidad y las de confiabilidad o recuperaci贸n. Estas pruebas nos ayudan a mostrar si existe alg煤n cuello de botella en nuestra aplicaci贸n.
  
  En el siguiente ejemplo podemos ver como tener lista nuestra herramienta JMeter para iniciar las pruebas de nuestra aplicaci贸n web.
  
  - [**`EJEMPLO 1: Preparaci贸n aplicaci贸n web y JMeter para pruebas de rendimiento`**](./Ejemplo-01)

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Pruebas de Carga</ins>

Las pruebas de carga  
  
Ya con nuestra configuraci贸n y preparaci贸n hecha en el ejemplo 1, veremos qu茅 factores se deben tener en cuenta y como realizar prueba de carga en este [**`EJEMPLO 2: Par谩metros y ejecuci贸n de prueba de carga`**](./Ejemplo-02).
  
 Con esta pr谩ctica podemos iniciar nuestro reto para este tipo de pruebas.
  
- [**`RETO 1: Prueba de carga`**](./Reto-01)
---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Pruebas de Estr茅s</ins>

Este tipo de pruebas sirven para determinar la solidez de la aplicaci贸n, de manera que empecemos a bombardear la aplicacion con consultar y poder determinar cuando la aplicaci贸n se rompe, o presenta errores. Aqu铆 podemos determinar cu谩l es el l铆mite de consultas simultaneas que la aplicaci贸n puede tener.
  
En esta prueba lo que se hace es duplicar la cantidad de usuarios de consulta de la aplicaci贸n, es decir, si mi aplicaci贸n acepta 10 usuarios lo que hacemos es enviarle 20, despu茅s 40 usuarios, despu茅s 80, despu茅s 160 y as铆 sucesivamente hasta que la aplicaci贸n en alguna de las pruebas se rompa, all铆 podemos sacar el punto m谩ximo donde la aplicaci贸n ya no es capaz de procesar todas las peticiones al tiempo.

Ya con nuestra configuraci贸n y preparaci贸n hecha en el ejemplo 1, veremos qu茅 factores se deben tener en cuenta y como realizar prueba de estr茅s en este [**`EJEMPLO 3: Par谩metros y ejecuci贸n de prueba de estr茅s`**](./Ejemplo-03).
  
 Con esta pr谩ctica podemos iniciar nuestro reto para este tipo de pruebas.
  
- [**`RETO 2: Prueba de estr茅s`**](./Reto-02)

---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Pruebas de Estabilidad</ins>

Estas pruebas nos ayudan a identificar si la aplicacion puede soportar una carga continuada, un ejemplo de una carga continuada es que haya una aplicaci贸n que reciba 10 usuarios y la prueba aqu铆 es ingresar las pruebas en un ciclo infinito done se hacen las 10 consutas, luego se vuelven a hacer las 10 consultas, luego se vuelven a hacer las 10 consultas y as铆 sucesivamente, esto nos sirve para encontrar si hay fugas en la aplicaci贸n, ya que al hacer un ciclo infinito, va a llegar un punto donde la memoria se va a rebosar y podremos ver si la aplicaci贸n resiste un tiempo significativo de cargas continuadas.
  
Ya con nuestra configuraci贸n y preparaci贸n hecha en el ejemplo 1, veremos qu茅 factores se deben tener en cuenta y como realizar prueba de estabilidad en este [**`EJEMPLO 4: Par谩metros y ejecuci贸n de prueba de estabilidad`**](./Ejemplo-04).
  
 Con esta pr谩ctica podemos iniciar nuestro reto para este tipo de pruebas.
  
- [**`RETO 3: Prueba de estabilidad`**](./Reto-03)
---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4: Pruebas de Confiabilidad o Recuperaci贸n</ins>

Las pruebas de confiabilidad o recuperaci贸n son pruebas no funcionales que determinan la capacidad del software para recuperarse de fallas como fallas de software / hardware o cualquier falla de la red.
  
Ya con nuestra configuraci贸n y preparaci贸n hecha en el ejemplo 1, veremos qu茅 factores se deben tener en cuenta y como realizar prueba de confiabilidad o recuperaci贸n en este [**`EJEMPLO 5: Par谩metros y ejecuci贸n de prueba de confiabilidad o recuperaci贸n`**](./Ejemplo-05).
  
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este m贸dulo.

- [**`POSTWORK SESI脫N 3`**](./Postwork/)

<br/>


</div>

