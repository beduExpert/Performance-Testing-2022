# Ejemplo 5: Parámetros y ejecución de prueba de Confiabilidad o Recuperación

## Objetivo

Indicar parámetros de entrada para peticiones de pruebas de confiabilidad o recuperación, ejecución y revisión de resultados.

## Desarrollo

Estas pruebas buscan poder garantizar que al encontrarse errores en las pruebas de carga se pueda volver a enviar la misma prueba y el sistema pueda responder favorablemente con estas pruebas de recuperación de fallos.


**Pasos**

1. Después de grabada la transacción de prueba que en este caso es el login y configurados los datos para la prueba de carga, se ejecuta el escenario de prueba.

![1](https://user-images.githubusercontent.com/22419786/156106191-6b7c72f3-7e3b-4e55-9280-4015342b8880.png)


2. Se pueden evidenciar los pasos y en el árbol de resultados, podemos ver varios pasos en rojo o con error.

![2](https://user-images.githubusercontent.com/22419786/156106196-be2931b7-77e1-482c-a5e2-25042e0407d3.png)


3. El propósito ahora en esta prueba es esperar un rato y volver a enviar la misma prueba para ver si el sistema logra recuperarse de cada uno de los fallos presentados.

Se ejecuta y debe mostrar cambios en los resultados, y en este caso ya hay pasos con peticiones exitosas.

![3](https://user-images.githubusercontent.com/22419786/156106233-c59ddf90-a2cb-4653-8660-cf0a3726d504.png)



