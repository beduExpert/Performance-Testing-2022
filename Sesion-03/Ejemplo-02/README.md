# Ejemplo # 2 - Parámetros y ejecución de prueba de Carga

## Objetivo

PENDIENTE!!!

## Desarrollo

Para las pruebas de carga, utilizaremos la configuración hecha en el ejemplo 1 

1. Ingresamos al Thread Group indicando los parámetros para esta prueba

IMAGEN 1

2. Diligenciamos el campo "Número de Hilos" con valor 10 que es la cantidad de usuarios que la aplicación va a recibir simultaneamente, el "Periodo de Subida" lo dejamos en 1 y el "Contador de bucle" lo dejamos en 1, es decir, que se va a hacer la petición de 10 usuarios una sola vez, esto con el fin de ver si la aplicación es capaz de cargar por lo menos los usuarios que se esperan simultaneamente.

IMAGEN 2

3. Se ejecuta la prueba y si no se ha guardado el proyecto pide que se guarde y permite continuar

IMAGEN 3

4. Mientras está ejecutando, el botón de play está inhabilitado y cuando termina la ejecución vuelve a habilitarse

IMAGEN 4

A medida que se va ejecutando podemos ir viendo los resultados.

5. El Gráfico de resultados para esta prueba no es muy diciente, pero en las proximas pruebas se puede detectar mejor

IMAGEN 5

6. En Reporte resumen, la columna que nos interesa es el % de error, que hasta ese momento ya terminando la ejecución, el % de error en cada una de las dependencias es de 0%, es decir, que todas las peticiones fueron cargadas de forma correcta.

IMAGEN 6

7. En el árbol de resultados, podemos ver reflejado lo que hay en el reporte de resumen, en este caso todas fueron ejecutadas de forma correcta. Por ejemplo, al desplegar el /home-13 se muestran 2 items:

      * 13-0 es la petición al servidor y nos muestra el Código de respuesta:302
    
    IMAGEN 7-1
  
      * 13-1 es la respuesta del servidor cuyo mensaje de respuesta es OK, dando a conocer que recibió la petición y ya se recibió

    IMAGEN 7-2
    
**En esta prueba podemos evidenciar que las pruebas de carga se ejecutaron de forma correcta.**
