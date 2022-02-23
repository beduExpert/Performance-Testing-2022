# Ejemplo # 4 - Herramientas de grabación directamente

## Objetivo

* PENDIENTE!!!

## Desarrollo

**Grabación de secuencias de comandos con la extensión de Chrome BlazeMeter**

Hasta ahora hemos cubierto las formas básicas de registrar escenarios de prueba. Pero una de las maneras más rápidas y fáciles de grabar sus scripts de rendimiento, que también es gratis, es usar la extensión Chrome de BlazeMeter Recorder . Estas grabaciones se pueden ejecutar en JMeter o en BlazeMeter.

La razón por la que la extensión es tan útil es que le permite grabar scripts de rendimiento desde su navegador sin tener que configurar su proxy.

<img width="239" alt="1  blazemeter grab" src="https://user-images.githubusercontent.com/22419786/155262087-5076c731-2116-46a1-a772-d03e04c6fea6.png">

Para crear una nueva secuencia de comandos de rendimiento:
1. Abre la grabadora desde tu Chrome
2. Ingrese un nombre de prueba en el campo superior
3. Comience a grabar haciendo clic en el botón de grabación, en forma de círculo, y realice las acciones web que desea grabar. Todas sus peticiones serán capturadas. Blazemeter
Chrome Extension también admite la grabación de tráfico HTTPS.
4. Después de terminar de grabar, haga clic en el botón de detener, en forma de un cuadrado. También puede pausar su grabación y luego reanudarla, así como editarla, en formato .jmx o JSON, o en la nube.
5. Exporte su grabación: para ejecutar la prueba en JMeter, exporte al formato .jmx haciendo clic en el botón .jmx. Para ejecutar la prueba en BlazeMeter, haga clic en 'jugar'.

**Grabación de guiones con BadBoy**

Otra herramienta de grabación útil de terceros es BadBoy. Sin embargo, funciona solo para el sistema operativo Windows. Para crear una nueva secuencia de comandos de rendimiento:

1. Instala BadBoy aquí
2. Ingrese la URL bajo prueba en la barra de direcciones

<img width="609" alt="2  badboy" src="https://user-images.githubusercontent.com/22419786/155262267-80985e33-4a95-4c50-9a79-4f7948ffd010.png">

3. Presione el botón de grabación, con forma de círculo rojo y realice las acciones que desea capturar.
4. Exporte su script a JMeter - Archivo -> Exportar a JMeter 
