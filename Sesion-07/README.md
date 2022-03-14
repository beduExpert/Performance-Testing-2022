## Sesión 7: Integración con Selenium 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Ejecutar los pasos requeridos para la instalación y configuración de Selenium
- Elaborar un proyecto en JMeter integrado con Selenium
- Estructurar proyecto en Selenium con programación orientada a objetos
- Utilizar marcos de trabajo para ejecución controlada de casos.


### 2. Contenido :blue_book:

Los controladores web como Selenium pueden automatizar la ejecución y la recopilación de las métricas de rendimiento en el lado del cliente (navegador en este caso), por lo tanto, mientras que la prueba de carga de JMeter pondrá suficiente carga en el sistema, el plan JMeter WebDriver (selenium) obtendrá los tiempos de respuesta y otros comportamientos desde el punto de vista de la experiencia del usuario.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Configuración e Instalación de Selenium</ins>
  
Selenium se instala a través de plugins en eclipse del siguiente modo [**`EJEMPLO 1: Instalación Eclipse y plugins Selenium`**](./Ejemplo-01)

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Integración JMeter con Selenium</ins>

JMeter proporciona una solución de código abierto para pruebas de rendimiento y carga. También se puede utilizar para pruebas funcionales. Pero con el avance de tecnologías como CSS , JS y HTML5, impulsamos cada vez más la lógica y el comportamiento del cliente. Por lo tanto, muchas más cosas se suman al tiempo de ejecución del navegador. Estas cosas incluyen:

- Ejecución de Javascript del lado del cliente: AJAX, plantillas JS, etc.
- Transformaciones CSS: transformaciones de matriz 3D, animaciones, etc.
- Complementos de terceros: me gusta de Facebook, anuncios de doble clic, etc.

  A su vez, esto podría afectar el rendimiento general de un sitio web o una aplicación web. Pero JMeter no tiene tal matriz para medir estos desempeños percibidos. JMeter tampoco puede medir la experiencia del usuario en las representaciones del cliente, como el tiempo de carga o la representación de la página, ya que JMeter no es un navegador real.
  
Los controladores web como Selenium pueden automatizar la ejecución y la recopilación de las métricas de rendimiento discutidas anteriormente en el lado del cliente (navegador en este caso). Por lo tanto, mientras que la prueba de carga de JMeter pondrá suficiente carga en el sistema, el plan JMeter WebDriver obtendrá los tiempos de respuesta y otros comportamientos desde el punto de vista de la experiencia del usuario.

Por lo tanto, además de medir el rendimiento, también podemos medir otros comportamientos cuando usamos un conjunto de WebDriver con JMeter. En este [**`EJEMPLO 2: Creación proyecto JMeter con Selenium`**](./Ejemplo-02) podemos ver como utilizar JMeter con Selenium.
  
---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Marco de trabajo JUnit</ins>

JUnit es un marco de trabajo para la automatización de pruebas en los proyectos de software, este permite tener de manera controlada la ejecución de los casos de prueba, para implementarlo podemos ver este [**`EJEMPLO 3: Creación proyecto JMeter con Selenium y JUnit`**](./Ejemplo-03)

---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Reto</ins>

Bienvenido a nuestro RETO de esta sesión.

- [**`RETO 1: Escenario de prueba JMeter con Selenium`**](./Reto-01)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 7`**](./Postwork/)

<br/>


</div>

