# Ejemplo 3: Parámetros y ejecución de prueba de estrés

## Objetivo

Indicar parámetros de entrada para peticiones de pruebas de estrés, ejecución y revisión de resultados.

## Desarrollo

Para las pruebas de estrés, utilizaremos la configuración hecha en el ejemplo 1. Recordemos que en este tipo de pruebas debemos duplicar el número de hilos o número de usuarios que van a consultar la aplicación, las peticiones de estos usuarios van a ser todas al mismo tiempo, simulando que esta cantidad de usuarios ingresan al tiempo. En la prueba de carga hicimos con 10 usuarios y funcionó correctamente, ahora lo que se debe hacer es probar duplicando los usuarios, es decir, sigue 20, después 40, después 80 pero vamos a enviar una prueba enviando de una vez 100 para ver el comportamiento con esta carga de usuarios.

1. En nuestro Thread Group vamos al número de hilos y donde estaba el 10 ahora ponemos 100 y el contador del bucle lo seguimos dejando en 1 porque deseamos ver inicialmente si la máquina en la que se está realizando la prueba es capaz de resistir 100 usuarios al mismo tiempo.

![1](https://user-images.githubusercontent.com/22419786/156018494-08598e76-a2fe-4d86-a98f-f8108ae2eec6.PNG)

2. Limpiamos los datos de la anterior prueba en este icono. Con este limpia los resultados de todos los elementos.

![2](https://user-images.githubusercontent.com/22419786/156018521-59419f00-538f-4708-baf3-bb685679fb87.PNG)

3. Se ejecuta la prueba desde el botón play y se puede visualizar en la parte superior de ella la cantidad de procesos ejecutados, inicia con el número mayor y los ejecuta de forma descendente.

![3](https://user-images.githubusercontent.com/22419786/156018535-e71b0f8c-579d-4d33-b2ac-f23f2cc0561a.PNG)

4. Visualizamos la gráfica que se va construyendo

![4](https://user-images.githubusercontent.com/22419786/156077213-4c56e81c-53b6-42d5-9dd2-95902eb88ebe.PNG)

5. En el reporte de resumen vemos que hay unos porcentajes de error que se validaran en el árbol de resultados

![5](https://user-images.githubusercontent.com/22419786/156018550-ae35b38f-f98f-40e2-82f1-cfb24ade963a.PNG)

6. En el árbol de resultados se identifican unas transacciones con error, por ejemplo en home-13 hay un error, se despliega la acción y muestra que la petición sí la hizo pero no recibió la confirmación del servidor

![6](https://user-images.githubusercontent.com/22419786/156018574-c0107af1-41d7-4655-9ddb-5fe870e06637.PNG)


**Con base en esto podemos determinar que la aplicación en algún punto está fallando para esta cantidad de usuarios y es donde se debe hacer énfasis en su revisión, ya sea por un falso positivo o porque realmente sea un error.**


