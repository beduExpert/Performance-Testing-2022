# Ejemplo # 1 - Configuración del Proxy

## Objetivo

* Configurar el navegador proxy para uso de la grabadora de JMeter, de manera que se puedan hacer las solicitudes de las peticiones del navegador.

## Desarrollo

Para utilizar la grabadora JMeter, debe configurar su navegador para enviar todas las solicitudes a través de proxy. Se puede usar cualquier navegador para estas necesidades, aunque puede haber diferencias entre las ubicaciones de las configuraciones de los navegadores, que son específicas del navegador y pueden variar según el sistema operativo.

**Opciones de configuración de acuerdo al navegador**

* Chrome : botón Menú -> Configuración -> Mostrar configuración avanzada ... -> Red -> Cambiar configuración de proxy.
* Safari : Preferencias -> Avanzado -> Proxies -> Cambiar configuración ...
* Firefox : botón Menú -> Preferencias -> Avanzado -> Red -> Conexión -> Configuración.

**Configuración en la máquina**

* Cambie el puerto al puerto en el HTTP Script Recorder utilizando el localhost 127.0.0.1.

![Proxy http](https://user-images.githubusercontent.com/22419786/155257299-cbfcbd89-fe18-464a-9230-4d3a0299798a.png)


**Configuración de JMeter**

* JMeter permite configurar manualmente su área de trabajo. Es más complejo, pero puede hacer que los scripts se ajusten a sus necesidades puntuales.

* La rama "WorkBench" se puede usar como un espacio de trabajo temporal para crear scripts. Tenga en cuenta que las entradas agregadas a esta sección no se guardarán con el plan de prueba. Por lo tanto, si desea reutilizar la misma configuración de grabación en el futuro, deberá copiarla y pegarla en la sección "Plan de prueba".

* Agregue “Controlador de grabación” a “Banco de trabajo”: haga clic derecho en “Banco de trabajo” -> “Agregar” -> “Controlador lógico” -> “Controlador de grabación”

![Control logico](https://user-images.githubusercontent.com/22419786/155257635-b8c79a2d-644c-4b2c-996e-ee6f7931638b.png)

* Agregue “HTTP (S) Test Script Recorder” al mismo “WorkBench”: haga clic derecho en “WorkBench” -> “Add” -> “Non-Test Elements” -> “HTTP (S) Test Script Recorder”

![test script record](https://user-images.githubusercontent.com/22419786/155257690-fd251b2f-90af-4eb8-8ba9-96a7cbef4c42.png)

* En la página de configuración de "HTTP (S) Test Script Recorder" en "Configuración global: Puerto", debe colocar el mismo puerto que se especifica en la configuración de proxy de su navegador, por ejemplo 8080.
