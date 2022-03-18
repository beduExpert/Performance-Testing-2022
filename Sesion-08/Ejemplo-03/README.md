# Ejemplo # 3 - Extracción de datos de la respuesta JSON con JMeter

## Objetivo

Obtener datos específicos del response JSON luego de ejecución de prueba en JMeter

## Desarrollo

En este ejemplo mostraremos todo lo necesario para dominar las expresiones Json Path .

Formato JSON
Para comprender mejor qué es Json , aquí hay un documento Json de ejemplo:

![1](https://user-images.githubusercontent.com/22419786/158929774-405d0a42-99f7-4484-badd-f11aa6296783.PNG)
 
Json es un formato de datos extremadamente simple que se hizo cargo de XML hace unos años.

Probablemente te preguntes: ¿por qué necesito aprender Json?

Un número cada vez mayor de API y servidores REST utilizan Json como formato principal de intercambio de datos. En OctoPerf, usamos Json en gran medida para intercambiar datos entre nuestro cliente frontend AngularJS y nuestro backend Spring Boot .

Quieres saber la mejor parte?

Desde JMeter 3.0, es mucho más fácil extraer datos de las respuestas Json utilizando el extractor de variables Json. En otras palabras, los extractores de Json están disponibles de forma nativa .

### Complemento JMeter JsonPath

![2](https://user-images.githubusercontent.com/22419786/158929807-954754ff-f6b7-4092-a777-f162261f9983.png)

El complemento JMeter JsonPath Extractor se puede descargar e instalar desde el sitio web de jmeter-plugins. A partir de JMeter 3.0 y superior, el complemento Json es opcional .

**Instalación del complemento JMeter JsonPath**

* Descargue plugins-manager.jar y colóquelo en el JMETER_HOME/lib/extdirectorio,
* Reinicie JMeter,
* Haga clic en Options > Plugins Manageren el menú superior,
* Seleccionar Available Pluginspestaña,
* Seleccione Json Pluginsy haga clic en Aplicar cambios y reiniciar JMeter .

El complemento JMeter Json debería estar disponible en el menú contextual Add > Post Processors > Json Path Extractor. Podemos usar el JsonPath Extractor nativo en su lugar!

### Extractor de ruta JMeter Json

El posprocesador Json de JMeter utiliza Json Way , una API Java Json Path, para realizar la extracción de rutas JSon en las respuestas del servidor.

![3](https://user-images.githubusercontent.com/22419786/158929825-a59e42da-219e-48a3-b257-87d228ef1700.png)

El extractor de Json Path debe colocarse bajo un HTTP Sampler. Tiene varias configuraciones posibles, de ahí que las más relevantes sean:

* Nombres de variables : nombres de variables separados por punto y coma,
* JSON Path Expressions : expresiones para extraer contenido de la respuesta json,
* Números de coincidencia : -1para todos, 0para uno al azar, npara el enésimo,
* Calcule la concatenación var : cree una variable que ${foo_ALL}contenga la concatenación de todos los valores extraídos,
* Y valores predeterminados : en el caso de que la expresión no se aplique al documento json que se está procesando.

### Ejemplos de rutas Json

Aquí hay algunos ejemplos de expresiones de Json Path que se pueden usar para extraer datos del documento Json expuesto anteriormente:

JSONPATH Y RESULTADO
* *$.tienda.libro[*].autor*	Los autores de todos los libros.
* *$..autor*	Todos los autores
* *$.tienda.*	Todas las cosas, tanto libros como bicicletas.
* *$.tienda..precio*	El precio de todo
* *$..libro[0,1]*	Los dos primeros libros
* *$..libro[:2]*	Todos los libros desde el índice 0 (inclusive) hasta el índice 2 (exclusivo)
* *$..libro[2:]*	Libro número dos de cola
* *$..libro[?(@.isbn)]*	Todos los libros con número ISBN
* *$.tienda.libro[?(@.precio < 10)]*	Todos los libros en tienda más baratos que 10
* *$..libro[?(@.precio <= $['caro'])]*	Todos los libros en la tienda que no sean “caros”
* *$..libro[?(@.autor =~ /.*REES/i)]*	Todos los libros que coincidan con expresiones regulares (ignorar mayúsculas y minúsculas)
* *$..*	Dame todo
* *$..libro.longitud()*	el numero de libros

Como puede ver, es fácil y flexible consultar información específica de un documento Json y ponerla en variables. Exploremos algunos de los ejemplos anteriores con JMeter.

### Ejemplos de JMeter

![4](https://user-images.githubusercontent.com/22419786/158929841-24346900-5d24-4d8b-9d95-fd2e65ed8c1a.png)

Nuestro JMX de muestra muestra cómo funcionan tanto JMeter Json Extractor como Plugin JsonPath Extractor . Antes de JMeter 3.0, se requería el complemento para realizar extracciones de JsonPath. A partir de JMeter 3.0, existe un soporte integrado para Json Extracciones.

**Extracción de arreglos**

![5](https://user-images.githubusercontent.com/22419786/158929850-d8a483f1-867f-49ad-8fa1-42ef39eccaa9.png)

Extracción de todos los autores de la tienda
La extracción de matrices hace posible extraer múltiples valores de un solo documento Json a la vez. Por ejemplo, podríamos extraer todos los autores de la librería:

* Nombre de la variable : authorsresultando en variable ${authors},
* Expresión JSONPath : $..authorselecciona todos los autores de cualquier profundidad.

Obtendrá las siguientes variables:

![6](https://user-images.githubusercontent.com/22419786/158929857-e572794e-54e0-4c7a-b9b3-e81ef825a934.PNG)

![7](https://user-images.githubusercontent.com/22419786/158929873-923de0a9-4a0d-44b9-ab2c-79caef271276.png)

**Extracción Condicional**

![8](https://user-images.githubusercontent.com/22419786/158929886-792137b9-151c-4b0b-8b38-e29b08c3e948.png)

Supongamos ahora que queremos extraer el título de los libros cuyo precio es menor o igual a 10:

* Nombre de la variable : titlesresultando en ${titles}variable,
* Número de coincidencia : -1,
* Expresión JSONPath : $.store.book[?(@.price<= 10)].title(títulos de libros con precio <= 10).

Obtendrá las siguientes variables:

![9](https://user-images.githubusercontent.com/22419786/158929894-47461dda-4948-470f-baf2-59a51dd712fe.PNG)

![10](https://user-images.githubusercontent.com/22419786/158929951-c8e04950-28fd-4bac-a5cc-5a0e3f2b055c.png)

**Extracción Múltiple**

![11](https://user-images.githubusercontent.com/22419786/158929968-97567775-1d7b-4f01-bace-e1b7c6912b87.png)

Supongamos ahora que queremos extraer varios campos Json al mismo tiempo. Por ejemplo, nos gustaría consultar todos los autores y títulos:

* Nombre de variable : multiple,
* Número de coincidencia : -1,
* Expresión JSONPath : $..['author','title'].

Obtendrá las siguientes variables:

![12](https://user-images.githubusercontent.com/22419786/158929977-87563c02-4a61-472c-ab55-3c9d90c87642.PNG)

![13](https://user-images.githubusercontent.com/22419786/158929988-c07657f1-70b5-4b8e-81ff-0d26bcc1e54e.png)

Y esos son los resultados que se muestran en la interfaz de usuario de JMeter.

**Extracción de concatenación**

A veces, desea extraer y concatenar todos los resultados en una sola cadena. En este ejemplo, tomé el punto final json de los encabezados HTTPBin .

Esto se puede lograr usando la Compute Concatenation var (suffi _ALL)opción.

![14](https://user-images.githubusercontent.com/22419786/158929999-ce76ec5e-c24e-4eab-92da-c3616c19937a.png)

El punto final devuelve un json que contiene los encabezados enviados por el cliente. Deberías ver algo como:

![15](https://user-images.githubusercontent.com/22419786/158930010-a9ff8387-e316-461c-be33-5780e4262496.PNG)

Ahora modifiquemos el extractor de Json y habilitemos la opción de concatenar resultados:

* Nombre de las variables creadas : foo(dando como resultado ${foo}),
* Expresión de ruta Json : $.headers.*,
* Match Nr : -1lo que significa extraer todas las ocurrencias,
* Calcular concatenación var : verificado.

Ahora veamos el resultado.

![16](https://user-images.githubusercontent.com/22419786/158930020-bab3b93f-4df5-45d6-a885-b7ce45330459.png)

Finalmente, usemos un Debug Sampler para ver la variable que se extrae (nombrada fooaquí).

![17](https://user-images.githubusercontent.com/22419786/158930029-d705a7a2-4d71-41b7-adf3-00dcf6edd577.png)

El resultado debería ser algo como:

![18](https://user-images.githubusercontent.com/22419786/158930042-49e73e37-8222-483f-a1f1-89498126fcd5.PNG)

**Uso de aserción de respuesta**

Esa es una pregunta bastante común: ¿Cómo validar una variable extraída de un json usando una afirmación?

Dicho de otra manera, desea asegurarse de que la variable extraída sea correcta. Veamos cómo hacer esto.

![19](https://user-images.githubusercontent.com/22419786/158930048-b0d8fcc0-2ce9-4aac-a7da-327118de8970.png)

Para este ejemplo, vamos a utilizar el complemento Dummy Sampler . ¿Por qué? Porque permite generar un resultado de muestra con cualquier json que queramos.

Usemos el siguiente Json:

![20](https://user-images.githubusercontent.com/22419786/158930054-981e0278-95d1-477c-9877-f9d117dedf21.PNG)

Simplemente vamos a configurar la muestra ficticia para enviar este Json como respuesta.

![21](https://user-images.githubusercontent.com/22419786/158930058-9165c973-0261-487e-924f-2958664279ce.png)

Muestreador ficticio JMeter Json

Luego, creamos un extractor Json para extraer el firstnamecampo json.

![22](https://user-images.githubusercontent.com/22419786/158930073-66cf6ca1-b59e-498d-b379-43eb4aee7c30.png)

Ahora configuremos una aserción de respuesta .

La aserción de respuesta debe ubicarse después del extractor json para que funcione.

![23](https://user-images.githubusercontent.com/22419786/158930079-ad3483bf-4272-4c67-af4f-15259d1406ed.png)

Las aserciones de respuesta están configuradas de la siguiente manera:

* Aplicar a : nombre de la variable JMeter a usar,
* Campo a probar : respuesta de texto,
* Reglas de coincidencia de patrones : igual a,
* Patrones para probar : Johnen nuestro ejemplo.

Es hora de ejecutar el grupo de subprocesos y ver los resultados.

![24](https://user-images.githubusercontent.com/22419786/158930089-7e65000b-b900-4f85-8f9e-845572ab5356.png)

La aserción se pasa con éxito.

Si reemplazamos los patrones de afirmación para probar por titi.

![25](https://user-images.githubusercontent.com/22419786/158930101-f2fc847b-4b68-427d-ad57-44461a2465ed.png)

La afirmación está fallando

¡Genial! Ahora sabe cómo extraer una variable de una respuesta json y validar el valor de la variable mediante una aserción de respuesta .

### 3 errores comunes

Ahora, probablemente te estés preguntando: ¿qué puede salir mal?

Los 3 errores comunes que se deben evitar son:

* No defina múltiples variables dentro de un solo extractor de Json Path: el script puede volverse difícil de entender/mantener,
* No escriba expresiones susceptibles de funcionar solo en respuestas json específicas, trate de ceñirse al caso general,
* Cuanto más simple sea la solución, mejor será la mantenibilidad del script.

### Para tener en cuenta

Según el caso, puede usar técnicas alternativas para extraer contenido de una respuesta del servidor.

**Extractor de expresiones regulares**

Suponga que tiene un documento Json muy simple con el siguiente contenido y quiere todos los nombres:

![26](https://user-images.githubusercontent.com/22419786/158930122-884b1546-3849-4fca-a7c2-b354f263b3c4.PNG)

En este caso, el extractor de expresiones regulares puede encajar bien porque es muy sencillo escribir una expresión regular.

![27](https://user-images.githubusercontent.com/22419786/158930125-3777d240-f15d-45d7-841f-2f0bef42e41d.png)

Hemos definido los siguientes ajustes:

* Nombre de referencia : firstname_RegEx,
* Expresión regular : "firstName":"(.+?)",
* Plantilla: $1$ ,
* Match Nr : 3, (queremos a Bart )
* Valor predeterminado : D'oh!.

**JSR223 con biblioteca externa**

Al usar la biblioteca Minimal Json y agregarla a JMeter, también puede hacer el trabajo de extraer datos json de una respuesta del servidor.

*Configuración de JMeter con una librería externa*

* Descargue la última versión de la biblioteca Minimal Json ,
* Ponlo adentro <JMeter Home>/lib/ext,
* Reinicie JMeter.

  Ahora cree un posprocesador JSR223 en Http Sampler cuya respuesta del servidor sea un documento Json. Seleccione el lenguaje Java e inspírese con el siguiente script:

![28](https://user-images.githubusercontent.com/22419786/158930132-bf404725-d969-4164-bccc-1b75ead98bd5.PNG)

El código anterior extrae el nombre del tercer miembro de la familia y lo coloca en una variable.
  
**JSR223 con Groovy**
  
JSR223 PostProcessor tiene soporte de lenguaje Groovy que tiene soporte JSON incorporado para que no tenga que agregar ningún .jar. Código de ejemplo:

![29](https://user-images.githubusercontent.com/22419786/158930138-ef95f369-c807-4892-a47a-3847fa129271.PNG)

Luego ${firstname}, se puede reutilizar según sea necesario.

**Extractor BeanShell Json**
  
Aunque se puede lograr el mismo resultado utilizando el posprocesador BeanShell , no recomendamos hacerlo por motivos de rendimiento. Los postprocesadores JSR223 deben usarse en favor de los postprocesadores BeanShell. JSR223 con Groovy es varias magnitudes más rápido que BeanShell.
  
![30](https://user-images.githubusercontent.com/22419786/158930148-240ecf4e-729b-4fdd-8b79-3079ea4c2731.png)

La configuración es muy similar a JSR223 . Aquí tenemos la variable final ${firstname_BSH}.

**Complementos de JMeter (Json Path Extractor)**
  
Desde JMeter 3.0 , JMeter Json Extractor Plugin debe abandonarse en favor del extractor Json Path integrado. Este complemento sigue siendo útil si está utilizando JMeter <= 2.13.

![31](https://user-images.githubusercontent.com/22419786/158930154-fe887bbf-6277-4a9f-ad82-59ec3d993c4b.png)
