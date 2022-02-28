# Ejemplo # 1 - Preparación aplicación web y JMeter para pruebas de rendimiento

## Objetivo

Preparar la herramienta JMeter y la conexión con el navegador para iniciar las pruebas de carga, estres, estabilidad y recuperación.

## Desarrollo

Vamos a preparar la herramienta JMeter con base en la página web a la que vamos a realizar las pruebas de rendimiento a través de los siguientes pasos:

1. Seleccionamos una aplicación web para simular las pruebas de software, en este caso utilizaremos blazedemo.com

![1](https://user-images.githubusercontent.com/22419786/156011701-004cfffa-57b9-4e0a-9814-c850b90d4cb2.PNG)

2. Abrimos JMeter y creamos nuestro plan de pruebas con Temlate, para esto damos clic en Archivo > Nuevo
    Luego de esto damos clic derecho sobre el Plan de pruebas creado y damos clic en Archivo > Templates

![2](https://user-images.githubusercontent.com/22419786/156011742-8a8b97b4-465f-44e6-933b-032664920b04.PNG)

3. En la lista desplegable buscamos uno que dice "Recording" o grabar en español

![3](https://user-images.githubusercontent.com/22419786/156011775-6c1e3972-bfb3-4c21-9086-249941002e57.PNG)

4. Le damos crear y esperamos un poco

![4](https://user-images.githubusercontent.com/22419786/156011792-bd31d636-63df-47ff-8edd-7dd9c7c067bc.PNG)

5. Ya nos muestra nuestro plan de pruebas con los elementos para nuestra prueba.

![5](https://user-images.githubusercontent.com/22419786/156011802-c72d5e6b-bcc9-471d-adb5-842e8fcd42d3.PNG)

6. Las 3 primeras herramientas se pueden eliminar ya que no se van a necesitar, se seleccionan las 3 manteniendo la tecla control oprimido, clic derecho sobre las 3 y clic en eliminar o remover

![6](https://user-images.githubusercontent.com/22419786/156011832-578cbec8-9018-4b0f-9c67-9e6366fe0f10.PNG)

7. En el plan de pruebas añadimos los receptores o listeners para visualizar nuestros resultados, agregamos estos 3 para validar.

![7](https://user-images.githubusercontent.com/22419786/156011879-e53e0245-beb4-4b58-ba9e-b8dfb7d81aab.PNG)

8. Así se verá nuestro plan de pruebas

![8](https://user-images.githubusercontent.com/22419786/156011885-98132915-7148-40ea-b197-1b35ea69d723.PNG)

9. Ahora vamos a configurar el HTTP(S) Test Script Recorder para grabar nuestra rutina simulando el localhost con base en el puerto 
    A su vez vamos a actualizar el controlador objetivo, en la lista desplegable debemos seleccionar "Test Plan > Thread Group > Recording Controller"

![9](https://user-images.githubusercontent.com/22419786/156011895-3e11e2ae-3b05-432b-a7cc-e55ccefbaa35.PNG)

10. Ahora vamos al navegador a realizar la configuración del proxy. Este tema lo realizamos como se hizo en la sesión 2.
    Buscamos en configuración del navegador, en el buscador buscamos proxy > Configuración > Configuracion manual del proxy > En Proxy HTTP se indica la ip de la máquina que se está probando o localhost y el puerto es el que se configuró en el paso anterior en JMeter > Finalmente se activa la casilla de "Usar tambien este proxy para FTP y HTTPS"

![10](https://user-images.githubusercontent.com/22419786/156011911-889fbb3b-bb01-475e-b923-06b7da1af6c2.PNG)

11. Al actualizar la aplicacion web aparece que el servidor proxy está rechazando las conexiones por lo que solo funcionará cuando se inicie la grabación del escenario.

![11](https://user-images.githubusercontent.com/22419786/156011923-10887101-8f15-45e3-a9fa-1f76110a1cd8.PNG)

12. Para arrancar la grabacion del escenario de prueba vamos a JMeter y en el elemento HTTPS le damos clic en "Arrancar"

![12](https://user-images.githubusercontent.com/22419786/156011944-f40113ac-bbc9-4b04-9494-7d039cd4600a.PNG)

13. Aqui aparece un cuadro que solo se detiene al terminar la grabación. Se actualiza la aplicación web y se inicia la grabación del escenario de prueba. En este caso haremos un ejercicio con la parte de reservas ingresando este nombre en la url

![13](https://user-images.githubusercontent.com/22419786/156011959-78e7f645-6686-403f-995e-8eaaa86b986d.PNG)

14. Aquí ya se puede ver la reserva.php y el anterior que muestra es el paso de la entrada al home y así sucesivamente van apareciendo estos cuadros a medidas que se va dando clic en los pasos

![14](https://user-images.githubusercontent.com/22419786/156011963-0b488c39-9ff9-4c31-a3ac-10304bbb5887.PNG)

15. Se hace una prueba diligenciando varios datos

![15](https://user-images.githubusercontent.com/22419786/156011980-4b16682e-a5df-4cb0-89d7-d0a987081632.PNG)

16. Y ya se puede visualizar en JMeter

![16](https://user-images.githubusercontent.com/22419786/156012011-18c66254-e01a-4c97-83e8-240f446fcb1a.PNG)

17. Puedo seguir interactuando por la palicación, por ejemplo ingresamos tambien al login y registro y ya podemos detener la grabación

![17](https://user-images.githubusercontent.com/22419786/156012020-54eb24c1-da05-4cd3-9976-2182a6f7203a.PNG)

**Con los escenarios de prueba ya grabados podemos iniciar las pruebas!**
