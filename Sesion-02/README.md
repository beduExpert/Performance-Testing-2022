## Sesi贸n 2: Grabando Test Scripts 馃

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Configurar el navegador proxy para uso de la grabadora de JMeter, de manera que se puedan hacer las solicitudes de las peticiones del navegador.
- Elaborar un plan de pruebas incluyendo los elementos necesarios para el funcionamiento de las pruebas.
- Configurar el navegador proxy y JMeter cuando se requiere capturar tr谩fico HTTPS con una aplicaci贸n web con cifrado SSL.
- Grabar scripts de prueba con herramientas propias de grabaci贸n integradas a JMeter.

### 2. Contenido :blue_book:

Existen diferentes formas de grabaci贸n de scripts para pruebas de rendimiento, unas hechas por herramientas propias de grabaci贸n, donde todo lo que se graba tal cual queda pero es m谩s complejo de modificar sus acciones, y grabaci贸n directamente desde JMeter controlando los pasos y acciones depurando la grabaci贸n, para este tipo de grabaciones es necesaria la configuraci贸n del navegador proxy para la correcta comunicaci贸n a las peticiones del navegador, en esta sesi贸n pondremos en pr谩ctica esta configuraci贸n para p谩ginas HTTP y con cifrado SSL para HTTPS.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Configuraci贸n Proxy</ins>

Se detalla como configurar el navegador proxy tanto para Chrome, como Safari, como Firefox.

- [**`EJEMPLO 1: Configuraci贸n del Proxy`**](./Ejemplo-01)

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Configuraci贸n JMeter (Sin uso de Template)</ins>

Con la inicializaci贸n de la herramienta JMeter, hemos podido ver cu谩l es la estructura b谩sica de un proyecto para pruebas de rendimiento, lo hemos hecho a trav茅s de un template de grabaci贸n para comprender los elementos que debe tener dicho proyecto. En esta instancia ya podemos crear un proyecto dentro de la herramienta sin usar el template sino ir a帽adiendo los elementos que requerimos para nuestra prueba, teniendo en cuenta el plan de pruebas, nuestro elemento para los escenarios de prueba, el grabador y nuestro 谩rbol de resultados.
  
  En el siguiente [**`EJEMPLO 2: Elaboraci贸n plan de pruebas sin Template`**](./Ejemplo-02) veremos c贸mo realizarlo.
  
---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Grabaci贸n de secuencia de comandos para dispositivos m贸viles</ins>

JMeter tambi茅n se puede usar para grabar pruebas de rendimiento m贸viles. La grabaci贸n de scripts m贸viles es muy similar a la grabaci贸n de scripts de aplicaciones web.
  
**Configuraci贸n del tel茅fono m贸vil**

Una vez preparada la configuraci贸n de JMeter, incluido el elemento JMeter "HTTP (S) Test Script Recording" iniciado en un puerto espec铆fico, puede configurar su tel茅fono m贸vil para enviar una
solicitud a la aplicaci贸n web que est谩 probando a trav茅s del proxy de JMeter. 

**IOS:**
* Configuraci贸n -> Wi-Fi
* Haga clic en la red conectada
* Ir a la secci贸n de configuraci贸n "HTTP PROXY"
* Haga clic en la pesta帽a "Manual"
* Configure la IP de la computadora La aplicaci贸n JMeter se est谩 ejecutando en "Servidor" 
* Configure el puerto que se especifica en la "Grabaci贸n de script de prueba HTTP (S)" en "Puerto"

**Android:**

* Configuraci贸n -> Wi-Fi
* Haga clic en la red conectada y haga clic en la opci贸n 'Modificar red'
* Haga clic en la casilla de verificaci贸n "Opciones avanzadas"
* Establezca la opci贸n "Proxy" en "Manual"
* Establezca el "Nombre de host del proxy" como la direcci贸n IP de su computadora y el "Puerto de proxy" como se especifica en la configuraci贸n de "HTTP (S) Test Script Recording" en "Puerto"
* Clic en Guardar"

Ahora puede comenzar a ejecutar la aplicaci贸n en su dispositivo m贸vil. Las solicitudes se registrar谩n en JMeter.


---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4: Grabaci贸n de tr谩fico HTTPS</ins>

JMeter cuenta con un elemento para realizar la grabaci贸n del tr谩fico HTTP "HTTP Test Script Recorder", antes era conocido como "HTTP Proxy server", este elemento permite la captura y el redireccionamiento de las peticiones HTTP o HTTPS como un servidor Proxy  desde el controlador de grabaci贸n como al servidor destino, tal como lo podemos ver en este [**`EJEMPLO 3: Pasos para grabaci贸n de tr谩fico HTTPS`**](./Ejemplo-03).

---
  
  <img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 5: Grabaci贸n de secuencias de comandos y guiones con diferentes herramientas</ins>

Otra forma que podemos realizar grabaciones en JMeter para nuestras pruebas de rendimiento es el uso de herramientas externas que se pueden integrar a JMeter, es decir, por un lado grabo las acciones en la web de prueba, integro con JMeter, y por otro lado, dentro del mismo JMeter realizo las configuraciones respectivas de mis escenarios de prueba para que desde all铆 las pueda ejecutar y analizar sus resultados.
  
- [**`EJEMPLO 4 - Herramientas propias de grabaci贸n`**](./Ejemplo-04)
  
Te invitamos a que iniciemos el reto de esta sesi贸n.
  
  - [**`RETO 1 - Grabaci贸n desde herramienta externa y ejecuci贸n en JMeter`**](./Reto-01)

---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este m贸dulo.

- [**`POSTWORK SESI脫N 2`**](./Postwork/)

<br/>


</div>





