## Sesi贸n 7: Integraci贸n con Selenium 馃

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

* Realizar la instalaci贸n y configuraci贸n de Selenium.
* Desarrollar un proyecto en JMeter integrado con Selenium.
* Hacer uso de la programaci贸n orientada a objetvos en el proyecto de Selenium.
* Utilizar marcos de trabajo para la ejecuci贸n controlada de casos.


### 2. Contenido :blue_book:

Los controladores web como Selenium pueden automatizar la ejecuci贸n y la recopilaci贸n de las m茅tricas de rendimiento en el lado del cliente (navegador en este caso), por lo tanto, mientras que la prueba de carga de JMeter pondr谩 suficiente carga en el sistema, el plan JMeter WebDriver (selenium) obtendr谩 los tiempos de respuesta y otros comportamientos desde el punto de vista de la experiencia del usuario.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Configuraci贸n e Instalaci贸n de Selenium</ins>
  
Selenium se instala a trav茅s de plugins en eclipse del siguiente modo [**`EJEMPLO 1: Instalaci贸n Eclipse y plugins Selenium`**](./Ejemplo-01)

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Integraci贸n JMeter con Selenium</ins>

JMeter proporciona una soluci贸n de c贸digo abierto para pruebas de rendimiento y carga. Tambi茅n se puede utilizar para pruebas funcionales. Pero con el avance de tecnolog铆as como CSS , JS y HTML5, impulsamos cada vez m谩s la l贸gica y el comportamiento del cliente. Por lo tanto, muchas m谩s cosas se suman al tiempo de ejecuci贸n del navegador. Estas cosas incluyen:

- Ejecuci贸n de Javascript del lado del cliente: AJAX, plantillas JS, etc.
- Transformaciones CSS: transformaciones de matriz 3D, animaciones, etc.
- Complementos de terceros: me gusta de Facebook, anuncios de doble clic, etc.

  A su vez, esto podr铆a afectar el rendimiento general de un sitio web o una aplicaci贸n web. Pero JMeter no tiene tal matriz para medir estos desempe帽os percibidos. JMeter tampoco puede medir la experiencia del usuario en las representaciones del cliente, como el tiempo de carga o la representaci贸n de la p谩gina, ya que JMeter no es un navegador real.
  
Los controladores web como Selenium pueden automatizar la ejecuci贸n y la recopilaci贸n de las m茅tricas de rendimiento discutidas anteriormente en el lado del cliente (navegador en este caso). Por lo tanto, mientras que la prueba de carga de JMeter pondr谩 suficiente carga en el sistema, el plan JMeter WebDriver obtendr谩 los tiempos de respuesta y otros comportamientos desde el punto de vista de la experiencia del usuario.

Por lo tanto, adem谩s de medir el rendimiento, tambi茅n podemos medir otros comportamientos cuando usamos un conjunto de WebDriver con JMeter. En este [**`EJEMPLO 2: Creaci贸n proyecto JMeter con Selenium`**](./Ejemplo-02) podemos ver como utilizar JMeter con Selenium.
  
---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Marco de trabajo JUnit</ins>

JUnit es un marco de trabajo para la automatizaci贸n de pruebas en los proyectos de software, este permite tener de manera controlada la ejecuci贸n de los casos de prueba, para implementarlo podemos ver este [**`EJEMPLO 3: Creaci贸n proyecto JMeter con Selenium y JUnit`**](./Ejemplo-03)

---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Reto</ins>

Bienvenido a nuestro RETO de esta sesi贸n.

- [**`RETO 1: Escenario de prueba JMeter con Selenium`**](./Reto-01)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este m贸dulo.

- [**`POSTWORK SESI脫N 7`**](./Postwork/)

<br/>


</div>

