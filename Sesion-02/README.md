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

Se detalla como configurar el navegador proxy tanto para Chrome, como Safari, como Firefox..

- [**`EJEMPLO 1`**](./Ejemplo-01)

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Configuración JMeter (Sin uso de Template)</ins>

PENDIENTE!!!

- [**`EJEMPLO 2`**](./Ejemplo-02)
  
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

PENDIENTE!!!
  
- [**`EJEMPLO 3`**](./Ejemplo-03)

---
  
  <img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 5: Grabación de secuencias de comandos y guiones con diferentes herramientas</ins>

PENDIENTE!!!
  
- [**`EJEMPLO 4`**](./Ejemplo-04)

---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 1`**](./Postwork/)

<br/>


</div>





