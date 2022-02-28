## Sesión 2: Grabando Test Scripts 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Configurar el navegador proxy para uso de la grabadora de JMeter, de manera que se puedan hacer las solicitudes de las peticiones del navegador.
- Elaborar un plan de pruebas incluyendo los elementos necesarios para el funcionamiento de las pruebas.
- Configurar el navegador proxy y JMeter cuando se requiere capturar tráfico HTTPS con una aplicación web con cifrado SSL.
- Grabar scrips de prueba con herramientas propias de grabación integradas a JMeter.

### 2. Contenido :blue_book:

Existen diferentes formas de grabación de scripts para pruebas de rendimiento, unas hechas por herramientas propias de grabación, donde todo lo que se graba tal cual queda pero es más complejo de modificar sus acciones, y grabación directamente desde JMeter controlando los pasos y acciones depurando la grabación, para este tipo de grabaciones es necesaria la configuración del navegador proxy para la correcta comunicacion a las peticiones del navegador, en esta sesión pondremos en práctica esta configuración para páginas HTTP y con cifrado SSL para HTTPS.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Configuración Proxy</ins>

Se detalla como configurar el navegador proxy tanto para Chrome, como Safari, como Firefox.

- [**`EJEMPLO 1 - Configuración del Proxy`**](./Ejemplo-01)

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Configuración JMeter (Sin uso de Template)</ins>

Con la inicialización de la herramienta JMeter, hemos podido ver cual es la estructura básica de un proyecto para pruebas de rendimiento, lo hemos hecho a través de un template de grabación para comprender los elementos que debe tener dicho proyecto. En esta instancia ya podemos crear un proyecto dentro de la herramienta sin usar el template sino ir añadiendo los elementos que requerimos para nuestra prueba, teniendo en cuenta el plan de pruebas, nuestro elemento para los escenarios de prueba, el grabador y nuestro árbol de resultados.
  
  En el siguiente [**`EJEMPLO 2 - Elaboración plan de pruebas sin Template`**](./Ejemplo-02) veremos como realizarlo.
  
---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Grabación de secuencia de comandos para dispositivos móviles</ins>

JMeter también se puede usar para grabar pruebas de rendimiento móviles. La grabación de scripts móviles es muy similar a la grabación de scripts de aplicaciones web.
  
**Configuración del teléfono móvil**

Una vez preparada la configuración de JMeter, incluido el elemento JMeter "HTTP (S) Test Script Recording" iniciado en un puerto específico, puede configurar su teléfono móvil para enviar una
solicitud a la aplicación web que está probando a través del proxy de JMeter. 

**IOS:**
* Configuración -> Wi-Fi
* Haga clic en la red conectada.
* Ir a la sección de configuración "HTTP PROXY"
* Haga clic en la pestaña "Manual"
* Configure la IP de la computadora La aplicación JMeter se está ejecutando en "Servidor" 
* Configure el puerto que se especifica en la "Grabación de script de prueba HTTP (S)" en "Puerto"

**Android:**

* Configuración -> Wi-Fi
* Haga clic en la red conectada y haga clic en la opción 'Modificar red'
* Haga clic en la casilla de verificación "Opciones avanzadas"
* Establezca la opción "Proxy" en "Manual"
* Establezca el "Nombre de host del proxy" como la dirección IP de su computadora y el "Puerto de proxy" como se especifica en la configuración de "HTTP (S) Test Script Recording" en "Puerto"
* Clic en Guardar"

Ahora puede comenzar a ejecutar la aplicación en su dispositivo móvil. Las solicitudes se registrarán en JMeter.


---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4: Grabación de tráfico HTTPS</ins>

JMeter cuenta con un elemento para realizar la grabación del tráfico HTTP "HTTP Test Script Recorder", antes era conocido como "HTTP Proxy server", este elemento permite la captura y el redireccionamiento de las peticiones HTTP o HTTPS como un servidor Proxy  desde el controlador de grabación como al servidor destino, tal como lo podemos ver en este [**`EJEMPLO 3 - Pasos para grabación de tráfico HTTPS`**](./Ejemplo-03)

---
  
  <img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 5: Grabación de secuencias de comandos y guiones con diferentes herramientas</ins>

Otra forma que podemos realizar grabaciones en JMeter para nuestras pruebas de rendimiento es el uso de herramientas externas que se pueden integrar a JMeter, es decir, por un lado grabo las acciones en la web de prueba, integro con JMeter, y por otro lado, dentro del mismo JMeter realizo las configuraciones respectivas de mis escenarios de prueba para que desde allí las pueda ejecutar y analizar sus resultados.
  
- [**`EJEMPLO 4 - Herramientas propias de grabación`**](./Ejemplo-04)
  
Te invitamos a que iniciemos el reto de esta sesión.
  
  - [**`RETO 1 - Grabación desde herramienta externa y ejecución en JMeter`**](./Reto-01)

---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 2`**](./Postwork/)

<br/>


</div>





