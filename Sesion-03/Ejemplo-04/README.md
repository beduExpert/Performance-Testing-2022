# Ejemplo # 4 - Parámetros y ejecución de prueba de Estabilidad

## Objetivo

Indicar parámetros de entrada para peticiones de pruebas de estabilidad, ejecución y revisión de resultados.

## Desarrollo

Para las pruebas de estabilidad, utilizaremos la configuración hecha en el ejemplo 1. En estas pruebas se hacen las consultas que la aplicación permite de manera concurrente pero a su vez también de forma continua.

El proceso radica en que se ejecutan por ejemplo 10 usuarios, al terminarlos vuelve y envia estos 10 usuarios, y así sucesivamente, esto se hace con el fin de encontrar fugas en el programa, saber cuando se desborda el software en un tiempo establecido ya que el software puede recibir la cantidad de usuarios pero en algun punto puede dejar de recibir usuario o desbordar su memoria.

Con base en esta información se puede determinar si se requiere optimizar la aplicación o si ya se desborda en un número muy grande de peticiones

**Pasos**

1. Primero se debe limpiar el resultado de las ejecuciones de pruebas anteriores y configuramos el thread group que para nuestro ejemplo pusimos 10 usuarios de forma concurrente pero en esta prueba le vamos a activar el check de bucle Sin fin, es decir, que sea infinito, con la finalidad de poder determinar si la aplicacion funciona correctamente de forma continua. > Damos clic en ejecutar

![1](https://user-images.githubusercontent.com/22419786/156089603-484e2a3a-2e89-470a-87d5-ec78f8d7f4ba.PNG)

2. Mientras se ejecuta podemos ir visualizando los resultados, por ejemplo en el reporte resumen se puede ver que por cada transacción (home, reserva, registro, confirmación) va aumentando el campo # Muestras que es donde se evidencia la cantidad de usuarios por grupo enviado, es decir, en este caso se han ejecutado 12 ciclos por cada una de las transacciones y no se ve ningun error durante la ejecución.

![2](https://user-images.githubusercontent.com/22419786/156089593-28b453f7-14d0-406b-814a-0b026b041ff0.PNG)

Se debe tener en cuenta que cada vez que una transacción termina sus 10 usuarios, inicia inmediatamente con sus otros 10 usuarios, independientemente de que hayan transacciones que no hayan finalizado sus 10 usuarios.

3. Detenemos la ejecución, en este caso al ser recurrente cuando detemos la ejecución, aparecen mensajes en los % de error por este stop, aunque no son valores altos. En el árbol de resultados se pueden evidenciar que en promedio hay 10 errores.

![3](https://user-images.githubusercontent.com/22419786/156089581-1b798a3a-3cce-4461-88d2-3f27e3d1e734.PNG)

4. Vamos a ver una de las transacciones, veremos el /home-13-0 que recibió la petición pero nunca recibió respuesta (13-1) pero esto sucude por lo que se canceló el proceso, es decir, se había enviado la petición pero al detener, la respuesta nunca llegó

![4](https://user-images.githubusercontent.com/22419786/156089572-4d6e2c9e-6d80-426b-8a78-511c5d5929c3.PNG)

5. En el gráfico de resultados se ve que es una aplicación muy estable pero tambien se debe tener en cuenta que muy liviana, por lo mismo se puede ver muy estable. Se ve que la media, la mediana y la desviación no superan el rendimiento de la aplicación.

![5](https://user-images.githubusercontent.com/22419786/156089553-723699e1-be0b-415a-8c30-05391f1ae65c.PNG)


**En esta prueba se pudo evidenciar que el software es estable y que su memoria soporta de manera continua y concurrente las peticiones.**
