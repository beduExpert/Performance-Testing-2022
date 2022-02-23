# Ejemplo # 3 - Ajustes a dispositivos móviles para grabación

## Objetivo

* PENDIENTE!!!

## Desarrollo


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
