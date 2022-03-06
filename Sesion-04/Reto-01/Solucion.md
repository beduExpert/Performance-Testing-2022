## Solución
  
La solución a este reto es presentar el resultado de la ejecución de un plan de pruebas en JMeter enviando los datos de la prueba como parámetros desde un archivo externo .CSV


**Pasos**

* Crear un plan de pruebas con template básico de grabación
* Agregar Thread Group
* Dentro del Thread Group con la transaccion creada agregar elemento CSV y el visor de resultados

![SOLUC](https://user-images.githubusercontent.com/22419786/156577172-4af2f0b5-4472-474b-9169-5a0cb7bf16f4.PNG)

* Configurar carga de archivo CSV con los parámetros del nombre del archivo y de las variables

<img width="671" alt="5" src="https://user-images.githubusercontent.com/22419786/156576790-f9c7cd9b-888c-41e1-8df9-690a266816bc.png">

* Ejecutar la prueba con los datos del archivo y presentar el arbol de resultados - **Resultado Esperado**

<img width="670" alt="7" src="https://user-images.githubusercontent.com/22419786/156576694-172b6397-3e79-4298-89be-12c99a19b2c8.png">
