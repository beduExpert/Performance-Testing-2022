## Sesión 5: Métricas de rendimiento y análisis de resultados de pruebas 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

- Demostrar como generar métricas a partir de los resultados de ejecuciones de pruebas de rendimiento
- Comparar resultados de ejecuciones de diferentes tipos de pruebas de rendimiento
- Implementar los bugs en herramienta JIRA de incidencias y defectos
- Elaborar un documento de plan de pruebas para control y formalización del proyecto

  
### 2. Contenido :blue_book:
En este work conoceremos como revisar y analizar los resultados de las pruebas de rendimiento en JMeter, conocer las métricas y evaluarlas. Además veremos como gestionar defectos encontrados y como documentar un plan de pruebas completo.

---

<img src="images/tools.png" align="right" height="90"> 

#### <ins>Tema 1: Métricas en pruebas de rendimiento</ins>

Desde JMeter 2.13, se pueden obtener resultados en tiempo real enviados a un backend a través de Backend Listener usando potencialmente cualquier backend (JDBC, JMS, Webservice, …) al proporcionar una clase que implementa AbstractBackendListenerClient.

  JMeter se envía con:

* Un GraphiteBackendListenerClient que le permite enviar métricas a un Graphite Backend.
  
    Esta característica proporciona:
  
      - Resultados en vivo
      - Gráficos para métricas.
      - Capacidad para comparar 2 o más pruebas de carga
      - Almacenar datos de monitoreo siempre que JMeter resulte en el mismo backend
* Un InfluxDBBackendListenerClient introducido en JMeter 3.2 que le permite enviar métricas a un InfluxDB Backend utilizando los protocolos UDP o HTTP. 
  
  Esta función proporciona:

      - Resultados en vivo
      - Gráficos para métricas.
      - Capacidad para comparar 2 o más pruebas de carga
      - Posibilidad de agregar anotaciones a los gráficos
      - Almacenar datos de monitoreo siempre que JMeter resulte en el mismo backend
  
En este [**`EJEMPLO 1 - Configuración para graficar los datos`**](./Ejemplo-01) presentaremos la configuración para graficar e historizar los datos en diferentes backends:

  - Configuración de InfluxDB para InfluxDBBackendListenerClient
  - Configuración de InfluxDB para GraphiteBackendListenerClient
  - Grafana

---

<img src="images/structure.png" align="right" height="90"> 

#### <ins>Tema 2: Análisis de resultados de pruebas</ins>

Para analizar adecuadamente los resultados de las pruebas de performance en JMeter, podemos tener en cuenta varios elementos en el proyecto JMeter y como comprender sus resultados. 
  
En el siguiente [**`EJEMPLO 2 - Informes de Resultados en JMeter`**](./Ejemplo-02) revisaremos como.

---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3: Gestión de defectos</ins>

Los defectos encontrados en nuestras pruebas de rendimiento deben tener una complejidad en cuanto a su manejo porque pueden ser críticos o bajos de manera que sean bloqueantes o no, para llevar un control de los defectos se deben manejar bajo herramientas para gestión de defectos, tal como se puede evidenciar en el  [**`EJEMPLO 3 - Creación de defectos en JIRA`**](./Ejemplo-03) donde mostraremos como generar un defecto en una de las herramientas más comunes como es JIRA. 
    
---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4: Creación de documento con el plan de pruebas</ins>

Nuestro plan de pruebas debe estar muy bien documentado y estructurado, para ello podemos basarnos en este [**`EJEMPLO 4 - Elaboración documento plan de pruebas`**](./Ejemplo-04) y poder realizar nuestro propio documento de pruebas. 
   
---

 Bienvenido a nuestro RETO de esta sesión.
  
  - [**`RETO 1`**](./Reto-01)
  
 --- 
  
### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 1`**](./Postwork/)

<br/>


</div>

