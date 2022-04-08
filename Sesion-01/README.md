## Sesión 1: Introducción a Performance Testing & JMeter 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Revisar el concepto de las pruebas de rendimiento, su utilidad y el desarrollo de pruebas acorde a requerimientos no funcionales.
- Distinguir los roles y funciones que intervienen en la creación y ejecución de pruebas de rendimiento.
- Modelar las pruebas de rendimiento por medio del análisis del paso a paso que tiene un proceso de pruebas.
- Emplear las herramientas JDK y JRE que son prerrequisito de JMeter.
- Establecer la instalación y configuración de JMeter, así como la aplicación de su certificado junto con el plugin que permite su ejecución.
- Utilizar la aplicación de JMeter a través del bat.
- Desarrollar una transacción sencilla Ej: Login.


### 2. Contenido :blue_book:

JMeter te ayudará a certificar que el producto de software para las transacciones que tengas de prueba cumpla con los requerimientos no funcionales para su paso a producción, aquí conocerás su definición, importancia y roles que intervienen en los proyectos a nivel de pruebas, además de conocer como elaborar un documento de seguimiento del proceso de pruebas junto con su procedimiento de instalación y ejecución.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: ¿Qué son las pruebas de rendimiento?</ins>

Las pruebas de rendimiento o de performance son pruebas no funcionales que permiten identificar a un producto la cantidad de usuarios simultáneos que soporta junto con su velocidad de respuesta en la ejecución de tareas.

Para su correcto funcionamiento se deben enviar condiciones de prueba muy similares a un entorno real donde el resultado esperado es poder atender una alta demanda de usuarios en un determinado tiempo.

**Importancia de las Pruebas**
  
- Las pruebas de rendimiento nos ayudan a ver el comportamiento de un producto con respecto a su velocidad y rendimiento
- Encontrar cuellos de Botella
- Revisar que el producto cumpla con las expectativas deseadas
- Simular diferente cantidad de usuarios simulados para garantizar el rendimiento de las pruebas
- Garantizar el pase a producción del sistema
  
  
**Roles de Pruebas**
  
Existen 2 roles en el ámbito de las pruebas de performance, el líder y el tester; el líder se encarga de recopilar y analizar los requerimientos de prueba de rendimiento, preparar la estrategia de pruebas y participar en las revisiones de cada version entregada, mientras que el teste debe analizar los excenarios grabarlos, ejecutar y analizar sus resultados.
  
---
#### <ins>Tema 2: Proceso de Pruebas</ins>

Las siguientes son las actividades de un proceso de pruebas exitoso:
 
<img src="https://user-images.githubusercontent.com/22419786/154817999-aa42f0fb-3f52-4f6c-b024-21eaba92d7a2.jpg" align="center" height="400"> 

Cada una de estas actividades cumple las siguientes funciones:
  
**Recopilación de Requerimientos**
  
Se levanta la información con el cliente de los requerimientos tanto comerciales como técnicos, esta información incluye las tecnologías utilizadas, las bases de datos, arquitectura de la aplicación, usuarios tentativos, uso y funcionalidad de la aplicación, los requisitos de hardware y software de pruebas, entre otros, definidos con el cliente.
  
**Selección de Herramientas de Prueba**
  
A partir de la recopilación de requerimientos, se puede  identificar la herramienta de pruebas útil para su ejecución, hay que tener en cuenta varios criterios a la hora de seleccionar la herramienta, como su costo, las tecnologías utilizadas, cantidad de usuarios simulados permitidos, los protocolos de la aplicación, para esto es necesaria una prueba de concepto donde se validan todas estas variables. 
  
**Elaboración del Plan de Pruebas de Performance**
  
En esta etapa se lleva a cabo la planificación y el diseño de las pruebas, aquí se analizan los criterios, tales como el hardware, los escenarios de prueba, las cantidades de clientes simulados, los tiempos, los datos de prueba, entre otros

**Desarrollo de las Pruebas de Performance**
  
Se inicia con la elaboración de los casos de uso propios para los escenarios de prueba diseñados. También se presentan al cliente para su revisión y aprobación.

Cuando se han aprobado los casos de uso, se inicia el desarrollo de los scripts en la herramienta seleccionada en la Prueba de Concepto teniendo en cuenta los parámetros a ajustar (Data), y funciones que deban incluirse de forma personalizada de acuerdo con los requerimientos.
  
**Modelamiento de las Pruebas de Performance**
  
Este es creado para la ejecución de las pruebas, se simula el rendimiento de la aplicación de acuerdo con los lineamientos dados por el cliente pero contando con un número máximo de usuarios que la aplicación podría soportar o no.
  
**Ejecución de Pruebas**
  
Esta ejecución se inicia con la menor cantidad de usuarios simulados y se va realizando de forma incremental de manera que si por ejemplo la cantidad máxima de usuarios que voy a probar es de 200, entonces debo iniciar por ejemplo con 10, 30, 60, y así hasta llegar a los 200.
  
**Análisis de Resultados**
  
Para el análisis de resultados existen muy buenas prácticas como por ejemplo:
- Incluir en el nombre del caso parte del escenario de la prueba para poder identificar rápidamente el propósito de esa prueba.
- Número de usuarios virtuales
- Duración de la prueba
- Resumen del escenario
- Rendimiento de la prueba
- Tiempos de respuesta
- Defectos encontrados y su forma de gestionar
- Gráficos y comparaciones entre ellos
- Resumen del resultado
- Recomendaciones

  
**Reporte de Resultados**
  
Este es un informe que contiene el resumen de los resultados de las pruebas con una conclusión muy clara teniendo en cuenta el análisis, la comparación de resultados y la especificación de cómo se obtuvieron los resultados.

---

#### <ins>Tema 3: Instalación y configuración de JMeter</ins>

**¿Qué es JMeter?**
  
JMeter es un software de código abierto diseñado totalmente en JAVA cuyo fin es medir el comportamiento y rendimiento de los servidores a través de pruebas, inicialmente para web pero se ha ampliado a otras funciones.
  
Para iniciar esta herramienta veremos el siguiente ejemplo, empecemos con su instalación, configuración y ejecución.

- [**`EJEMPLO 1: Instalación de JMeter y las herramientas prerrequisito`**](./Ejemplo-01)

---

#### <ins>Tema 4: Prueba del Test Plan</ins>

En el paso anterior ya vimos cómo se ejecuta la aplicación, ahora vamos a crear nuestro primer Test Plan con una ejecución sencilla de acuerdo con el siguiente ejemplo:
  
- [**`EJEMPLO 2: Configuración de un Test Plan`**](./Ejemplo-02)

Ahora, con esta primera ejecución sencilla que hemos realizado vamos a iniciar con el primer Reto de este curso.
  
  Comencemos!

- [**`RETO 1: Creación y ejecución de un test plan básico`**](./Reto-01)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 1`**](./Postwork/)

<br/>


</div>

