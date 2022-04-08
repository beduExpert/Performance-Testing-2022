# Ejemplo 1: Configuración del Proxy

## Objetivo

* Realizar la configuración del navegador proxy para uso de la grabadora de JMeter, de manera que se puedan hacer las solicitudes de las peticiones de este.

## Desarrollo

Para utilizar la grabadora JMeter, debe configurar su navegador para enviar todas las solicitudes a través de proxy. Se puede usar cualquier navegador para estas necesidades, aunque puede haber diferencias entre las ubicaciones de las configuraciones de los navegadores, que son específicas del navegador y pueden variar según el sistema operativo.

**Opciones de configuración de acuerdo con el navegador**

* Chrome : botón Menú -> Configuración -> Mostrar configuración avanzada ... -> Red -> Cambiar configuración de proxy
* Safari : Preferencias -> Avanzado -> Proxies -> Cambiar configuración
* Firefox : botón Menú -> Preferencias -> Avanzado -> Red -> Conexión -> Configuración

**Configuración en la máquina**

* Cambie el puerto al puerto en el HTTP Script Recorder utilizando el localhost 127.0.0.1.

![Proxy http](https://user-images.githubusercontent.com/22419786/155257299-cbfcbd89-fe18-464a-9230-4d3a0299798a.png)
