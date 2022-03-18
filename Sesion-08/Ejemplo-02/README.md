# Ejemplo # 2 - Uso de parámetros en archivo CSV para pruebas de API

## Objetivo

Generar un proyecto en JMeter donde se consuma una API y los datos de prueba se incorporen desde un archivo CSV

## Desarrollo

J-Meter es de gran ayuda para enviar detalles masivos, por ejemplo, mil registros de usuarios en una tabla existente en la base de datos a través de un punto final como una forma alternativa de escribir una consulta de actualización.

Para este ejemplo, vamos a cargar los datos de los empleados en la base de datos utilizando la API ficticia http://dummy.restapiexample.com/

**Pasos**

1. Debemos tener instalado JMeter.

2. Cree su primer plan de prueba de JMeter.

Un plan de prueba es donde coloca la configuración general y los pasos que le gustaría que J-Meter ejecutara mientras se ejecuta. Para crear un plan de prueba, debe configurar el grupo de subprocesos. Un grupo de subprocesos es donde especifica la cantidad de usuarios que desea simular. Un hilo = un usuario.

Verifique como la imagen de muestra a continuación

![1](https://user-images.githubusercontent.com/22419786/158883876-70aaee58-cc5f-4bdb-91d8-88291da0588e.png)

**3. Configure su plan de prueba**

Es importante configurar su plan de prueba con la configuración requerida que le permitirá actualizar los datos en la base de datos utilizando el punto final funcional correcto.

i). Primero configure su administrador de encabezado Http indicando el tipo de contenido y la autorización que proporciona el token de portador válido si el punto final lo requiere. Vea la imagen de abajo como un ejemplo

![2](https://user-images.githubusercontent.com/22419786/158883929-96a33531-28aa-427f-aa23-d9977813cb4d.png)

ii). En segundo lugar, coloque la URL de su dominio de solicitudes HTTP como se muestra a continuación

![3](https://user-images.githubusercontent.com/22419786/158883956-f4dcaebc-c97a-4bb0-8a2f-ead44b0c5dec.png)

iii) Describa y configure su grupo de subprocesos especificando su número de usuarios y la acción a tomar después de un error de muestra.

![4](https://user-images.githubusercontent.com/22419786/158883985-9287bff1-bd57-421e-ad68-1da19b52791c.png)

iv) Configure el conjunto de datos CSV colocando la ruta del archivo al CSV dentro de su dispositivo local y colocando los nombres de las variables tal como aparecen en los títulos de las diferentes columnas del archivo CSV en el que desea cargar sus detalles.

![5](https://user-images.githubusercontent.com/22419786/158884014-a0603421-8c31-4d20-88da-acf558b99dcd.png)

Los datos en el archivo CSV que se cargarán

![6](https://user-images.githubusercontent.com/22419786/158884167-e59275a3-e4ad-4a81-81e0-fe623773530f.png)

v) Para configurar la solicitud HTTP, coloque la ruta al punto final que desea usar para cargar datos. Por ejemplo, usé este /api/v1/create .

Seleccione el método de la solicitud que desea hacer, por ejemplo. POST, PUT, PATCH entre otros. Para esto, usaré POST ya que quiero crear nuevos datos que no existen en absoluto en la base de datos.

Además, asegúrese de que los datos del cuerpo colocados en J-meter estén en forma de JSON colocando las claves y valores como {“nombre”: “${nombre}”.

Obtenga más información de la imagen a continuación.

![7](https://user-images.githubusercontent.com/22419786/158884187-ddedc062-b3d1-4f7f-a029-aa1ad5e30762.png)

vi) Después de configurar las configuraciones, puede ejecutar la aplicación para enviar los datos a la base de datos con el primer botón verde de su izquierda, como se muestra a continuación.

![8](https://user-images.githubusercontent.com/22419786/158884209-fdbeaea8-19f9-4de7-9602-94e60be58ab7.png)

vii) A continuación, puede ver los resultados desde el árbol de resultados. Puede confirmar con el código de respuesta 200. Puedes echar un vistazo a esta imagen.

![9](https://user-images.githubusercontent.com/22419786/158884233-39997773-9c48-423c-8256-05b712fe1b2f.png)

Puede ver claramente que la solicitud coincide con la solicitud que enviamos utilizando los datos que necesitábamos cargar que se colocaron en el archivo CSV, desde el árbol de vista de resultados como se muestra a continuación.

![10](https://user-images.githubusercontent.com/22419786/158884268-680ee7c5-b759-41aa-86b9-6f6a324febcb.png)

Puedes echar un vistazo a la respuesta de la imagen de abajo

![11](https://user-images.githubusercontent.com/22419786/158884287-5cc211dc-2244-4fc2-8da0-5b883f4c96b0.png)

Luego puede confirmar sus detalles cargados consultando desde la base de datos.
