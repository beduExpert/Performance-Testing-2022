## Solución
  
La solución a este reto es presentar el resultado de la ejecución del proyecto en JMeter consumiendo una API y cargando datos desde un archivo CSV.

**Pasos**

* Crear proyecto en JMeter con toda la estructura que ya hemos trabajado

* Crear la solicitud HTTP  para el consumo de la API

![1](https://user-images.githubusercontent.com/22419786/158936700-91008d86-9663-450e-aa6a-4f37d77a8377.png)

* Incorporar archivo CSV

![2](https://user-images.githubusercontent.com/22419786/158936711-b0a7f2c9-6d6c-4360-aa18-760305fee456.png)

* Agregar el formato de respuesta JSON

![3](https://user-images.githubusercontent.com/22419786/158936727-2dfacc4b-64d7-41e7-ad6b-3cebdf79f353.png)

* Indicar método (GET-POST) para inicio de la prueba

![4](https://user-images.githubusercontent.com/22419786/158936743-aad17526-4200-4043-b5e3-0f4d97f6445a.png)

* Agregar JSON Extractor e indicar la expresion que se desea extraer

![5](https://user-images.githubusercontent.com/22419786/158936761-040ea238-6d0f-4c21-b51d-98abec08fb07.png)

* Preparar la prueba indicando más de 1 usuario simulado

![6](https://user-images.githubusercontent.com/22419786/158936802-54bebfbf-00a3-49f4-819d-70017efcadc7.png)

* Ejecutar el proyecto

![7](https://user-images.githubusercontent.com/22419786/158936814-15576b42-d392-4c01-b6d9-d526d03739da.png)

* Presentar resultado Sampler

![8](https://user-images.githubusercontent.com/22419786/158936854-6fea0495-3cf5-42ee-8cca-c9dcf7ba1f2e.png)

* Presentar request

![9](https://user-images.githubusercontent.com/22419786/158936870-a6ac3364-334b-420a-b96b-ff8aa9ae18b3.png)

* Presentar response

![10](https://user-images.githubusercontent.com/22419786/158936891-51ac9268-ff49-41bf-a0f9-4d0b28b95db5.png)
