# Ejemplo # 2 - Parámetros y ejecución de prueba de Carga

## Objetivo

PENDIENTE!!!

## Desarrollo

Para las pruebas de carga, utilizaremos la configuración hecha en el ejemplo 1 

1. Ingresamos al Thread Group indicando los parámetros para esta prueba

![1](https://user-images.githubusercontent.com/22419786/156011377-b604f61f-a5a1-423f-9c21-7031ac9b2abd.PNG)

2. Diligenciamos el campo "Número de Hilos" con valor 10 que es la cantidad de usuarios que la aplicación va a recibir simultaneamente, el "Periodo de Subida" lo dejamos en 1 y el "Contador de bucle" lo dejamos en 1, es decir, que se va a hacer la petición de 10 usuarios una sola vez, esto con el fin de ver si la aplicación es capaz de cargar por lo menos los usuarios que se esperan simultaneamente.

![2](https://user-images.githubusercontent.com/22419786/156011431-673aa974-642f-417b-ab1c-1bda45e5920e.PNG)

3. Se ejecuta la prueba y si no se ha guardado el proyecto pide que se guarde y permite continuar

![3](https://user-images.githubusercontent.com/22419786/156011442-19b83a2b-b0d1-4cdd-8f16-9a9681459b90.PNG)

4. Mientras está ejecutando, el botón de play está inhabilitado y cuando termina la ejecución vuelve a habilitarse

![4](https://user-images.githubusercontent.com/22419786/156011450-535bf569-d75d-4ed0-be07-bc257121eae3.PNG)

A medida que se va ejecutando podemos ir viendo los resultados.

5. El Gráfico de resultados para esta prueba no es muy diciente, pero en las proximas pruebas se puede detectar mejor

![5](https://user-images.githubusercontent.com/22419786/156011493-051b0fc4-d599-492c-a7b6-c4386919d4c0.PNG)

6. En Reporte resumen, la columna que nos interesa es el % de error, que hasta ese momento ya terminando la ejecución, el % de error en cada una de las dependencias es de 0%, es decir, que todas las peticiones fueron cargadas de forma correcta.

![6](https://user-images.githubusercontent.com/22419786/156011528-2a239242-cbaf-450a-9a0e-288a8f27dc68.PNG)

7. En el árbol de resultados, podemos ver reflejado lo que hay en el reporte de resumen, en este caso todas fueron ejecutadas de forma correcta. Por ejemplo, al desplegar el /home-13 se muestran 2 items:

      * 13-0 es la petición al servidor y nos muestra el Código de respuesta:302
    
          ![7-1](https://user-images.githubusercontent.com/22419786/156011559-48163fdf-7123-4cdb-aa82-30dd82ee49bf.PNG)
  
      * 13-1 es la respuesta del servidor cuyo mensaje de respuesta es OK, dando a conocer que recibió la petición y ya se recibió

           ![7-2](https://user-images.githubusercontent.com/22419786/156011588-7ea73403-df70-43a4-9392-eae88f6ce43a.PNG)

    
**En esta prueba podemos evidenciar que las pruebas de carga se ejecutaron de forma correcta.**
