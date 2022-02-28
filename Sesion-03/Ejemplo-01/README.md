# Ejemplo # 1 - Preparación aplicación web y JMeter para pruebas de rendimiento

## Objetivo

* PENDIENTE!!!

## Desarrollo

Vamos a preparar la herramienta JMeter con base en la página web a la que vamos a realizar las pruebas de rendimiento a través de los siguientes pasos:

1. Seleccionamos una aplicación web para simular las pruebas de software, en este caso utilizaremos blazedemo.com

IMAGEN 1

2. Abrimos JMeter y creamos nuestro plan de pruebas con Temlate, para esto damos clic en Archivo > Nuevo
    Luego de esto damos clic derecho sobre el Plan de pruebas creado y damos clic en Archivo > Templates

IMAGEN 2

3. En la lista desplegable buscamos uno que dice "Recording" o grabar en español

IMAGEN

4. Le damos crear y esperamos un poco

IMAGEN

5. Ya nos muestra nuestro plan de pruebas con los elementos para nuestra prueba.

IMAGEN

6. Las 3 primeras herramientas se pueden eliminar ya que no se van a necesitar, se seleccionan las 3 manteniendo la tecla control oprimido, clic derecho sobre las 3 y clic en eliminar o remover

IMAGEN

7. En el plan de pruebas añadimos los receptores o listeners para visualizar nuestros resultados, agregamos estos 3 para validar.

IMAGEN

8. Así se verá nuestro plan de pruebas

IMAGEN

9. Ahora vamos a configurar el HTTP(S) Test Script Recorder para grabar nuestra rutina simulando el localhost con base en el puerto 
    A su vez vamos a actualizar el controlador objetivo, en la lista desplegable debemos seleccionar "Test Plan > Thread Group > Recording Controller"

IMAGEN

10. Ahora vamos al navegador a realizar la configuración del proxy. Este tema lo realizamos como se hizo en la sesión 2.
    Buscamos en configuración del navegador, en el buscador buscamos proxy > Configuración > Configuracion manual del proxy > En Proxy HTTP se indica la ip de la máquina que se está probando o localhost y el puerto es el que se configuró en el paso anterior en JMeter > Finalmente se activa la casilla de "Usar tambien este proxy para FTP y HTTPS"

IMAGEN

11. Al actualizar la aplicacion web aparece que el servidor proxy está rechazando las conexiones por lo que solo funcionará cuando se inicie la grabación del escenario.

IMAGEN

12. Para arrancar la grabacion del escenario de prueba vamos a JMeter y en el elemento HTTPS le damos clic en "Arrancar"

IMAGEN

13. Aqui aparece un cuadro que solo se detiene al terminar la grabación. Se actualiza la aplicación web y se inicia la grabación del escenario de prueba. En este caso haremos un ejercicio con la parte de reservas ingresando este nombre en la url

IMAGEN

14. Aquí ya se puede ver la reserva.php y el anterior que muestra es el paso de la entrada al home y así sucesivamente van apareciendo estos cuadros a medidas que se va dando clic en los pasos

IMAGEN

15. Se hace una prueba diligenciando varios datos

IMAGEN

16. Y ya se puede visualizar en JMeter

IMAGEN

17. Puedo seguir interactuando por la palicación, por ejemplo ingresamos tambien al login y registro y ya podemos detener la grabación

IMAGEN

**Con los escenarios de prueba ya grabados podemos iniciar las pruebas!**
