## Sesi贸n 1: Introducci贸n a Performance Testing & JMeter 馃

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Revisar el concepto de las pruebas de rendimiento, su utilidad y el desarrollo de pruebas acorde a requerimientos no funcionales.
- Distinguir los roles y funciones que intervienen en la creaci贸n y ejecuci贸n de pruebas de rendimiento.
- Modelar las pruebas de rendimiento por medio del an谩lisis del paso a paso que tiene un proceso de pruebas.
- Emplear las herramientas JDK y JRE que son prerrequisito de JMeter.
- Establecer la instalaci贸n y configuraci贸n de JMeter, as铆 como la aplicaci贸n de su certificado junto con el plugin que permite su ejecuci贸n.
- Utilizar la aplicaci贸n de JMeter a trav茅s del bat.
- Desarrollar una transacci贸n sencilla Ej: Login.


### 2. Contenido :blue_book:

JMeter te ayudar谩 a certificar que el producto de software para las transacciones que tengas de prueba cumpla con los requerimientos no funcionales para su paso a producci贸n, aqu铆 conocer谩s su definici贸n, importancia y roles que intervienen en los proyectos a nivel de pruebas, adem谩s de conocer como elaborar un documento de seguimiento del proceso de pruebas junto con su procedimiento de instalaci贸n y ejecuci贸n.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: 驴Qu茅 son las pruebas de rendimiento?</ins>

Las pruebas de rendimiento o de performance son pruebas no funcionales que permiten identificar a un producto la cantidad de usuarios simult谩neos que soporta junto con su velocidad de respuesta en la ejecuci贸n de tareas.

Para su correcto funcionamiento se deben enviar condiciones de prueba muy similares a un entorno real donde el resultado esperado es poder atender una alta demanda de usuarios en un determinado tiempo.

**Importancia de las Pruebas**
  
- Las pruebas de rendimiento nos ayudan a ver el comportamiento de un producto con respecto a su velocidad y rendimiento
- Encontrar cuellos de Botella
- Revisar que el producto cumpla con las expectativas deseadas
- Simular diferente cantidad de usuarios simulados para garantizar el rendimiento de las pruebas
- Garantizar el pase a producci贸n del sistema
  
  
**Roles de Pruebas**
  
Existen 2 roles en el 谩mbito de las pruebas de performance, el l铆der y el tester; el l铆der se encarga de recopilar y analizar los requerimientos de prueba de rendimiento, preparar la estrategia de pruebas y participar en las revisiones de cada version entregada, mientras que el teste debe analizar los excenarios grabarlos, ejecutar y analizar sus resultados.
  
---
#### <ins>Tema 2: Proceso de Pruebas</ins>

Las siguientes son las actividades de un proceso de pruebas exitoso:
 
<img src="https://user-images.githubusercontent.com/22419786/154817999-aa42f0fb-3f52-4f6c-b024-21eaba92d7a2.jpg" align="center" height="400"> 

Cada una de estas actividades cumple las siguientes funciones:
  
**Recopilaci贸n de Requerimientos**
  
Se levanta la informaci贸n con el cliente de los requerimientos tanto comerciales como t茅cnicos, esta informaci贸n incluye las tecnolog铆as utilizadas, las bases de datos, arquitectura de la aplicaci贸n, usuarios tentativos, uso y funcionalidad de la aplicaci贸n, los requisitos de hardware y software de pruebas, entre otros, definidos con el cliente.
  
**Selecci贸n de Herramientas de Prueba**
  
A partir de la recopilaci贸n de requerimientos, se puede  identificar la herramienta de pruebas 煤til para su ejecuci贸n, hay que tener en cuenta varios criterios a la hora de seleccionar la herramienta, como su costo, las tecnolog铆as utilizadas, cantidad de usuarios simulados permitidos, los protocolos de la aplicaci贸n, para esto es necesaria una prueba de concepto donde se validan todas estas variables. 
  
**Elaboraci贸n del Plan de Pruebas de Performance**
  
En esta etapa se lleva a cabo la planificaci贸n y el dise帽o de las pruebas, aqu铆 se analizan los criterios, tales como el hardware, los escenarios de prueba, las cantidades de clientes simulados, los tiempos, los datos de prueba, entre otros

**Desarrollo de las Pruebas de Performance**
  
Se inicia con la elaboraci贸n de los casos de uso propios para los escenarios de prueba dise帽ados. Tambi茅n se presentan al cliente para su revisi贸n y aprobaci贸n.

Cuando se han aprobado los casos de uso, se inicia el desarrollo de los scripts en la herramienta seleccionada en la Prueba de Concepto teniendo en cuenta los par谩metros a ajustar (Data), y funciones que deban incluirse de forma personalizada de acuerdo con los requerimientos.
  
**Modelamiento de las Pruebas de Performance**
  
Este es creado para la ejecuci贸n de las pruebas, se simula el rendimiento de la aplicaci贸n de acuerdo con los lineamientos dados por el cliente pero contando con un n煤mero m谩ximo de usuarios que la aplicaci贸n podr铆a soportar o no.
  
**Ejecuci贸n de Pruebas**
  
Esta ejecuci贸n se inicia con la menor cantidad de usuarios simulados y se va realizando de forma incremental de manera que si por ejemplo la cantidad m谩xima de usuarios que voy a probar es de 200, entonces debo iniciar por ejemplo con 10, 30, 60, y as铆 hasta llegar a los 200.
  
**An谩lisis de Resultados**
  
Para el an谩lisis de resultados existen muy buenas pr谩cticas como por ejemplo:
- Incluir en el nombre del caso parte del escenario de la prueba para poder identificar r谩pidamente el prop贸sito de esa prueba.
- N煤mero de usuarios virtuales
- Duraci贸n de la prueba
- Resumen del escenario
- Rendimiento de la prueba
- Tiempos de respuesta
- Defectos encontrados y su forma de gestionar
- Gr谩ficos y comparaciones entre ellos
- Resumen del resultado
- Recomendaciones

  
**Reporte de Resultados**
  
Este es un informe que contiene el resumen de los resultados de las pruebas con una conclusi贸n muy clara teniendo en cuenta el an谩lisis, la comparaci贸n de resultados y la especificaci贸n de c贸mo se obtuvieron los resultados.

---

#### <ins>Tema 3: Instalaci贸n y configuraci贸n de JMeter</ins>

**驴Qu茅 es JMeter?**
  
JMeter es un software de c贸digo abierto dise帽ado totalmente en JAVA cuyo fin es medir el comportamiento y rendimiento de los servidores a trav茅s de pruebas, inicialmente para web pero se ha ampliado a otras funciones.
  
Para iniciar esta herramienta veremos el siguiente ejemplo, empecemos con su instalaci贸n, configuraci贸n y ejecuci贸n.

- [**`EJEMPLO 1: Instalaci贸n de JMeter y las herramientas prerrequisito`**](./Ejemplo-01)

---

#### <ins>Tema 4: Prueba del Test Plan</ins>

En el paso anterior ya vimos c贸mo se ejecuta la aplicaci贸n, ahora vamos a crear nuestro primer Test Plan con una ejecuci贸n sencilla de acuerdo con el siguiente ejemplo:
  
- [**`EJEMPLO 2: Configuraci贸n de un Test Plan`**](./Ejemplo-02)

Ahora, con esta primera ejecuci贸n sencilla que hemos realizado vamos a iniciar con el primer Reto de este curso.
  
  Comencemos!

- [**`RETO 1: Creaci贸n y ejecuci贸n de un test plan b谩sico`**](./Reto-01)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este m贸dulo.

- [**`POSTWORK SESI脫N 1`**](./Postwork/)

<br/>


</div>

