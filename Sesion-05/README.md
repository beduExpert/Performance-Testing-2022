## Sesión 5: Métricas de rendimiento y análisis de resultados de pruebas 🤖

<img src="../images/android-kotlin.png" align="right" height="120" hspace="10">
<div style="text-align: justify;">

### 1. Objetivos :dart: 

PENDIENTE!!!!

### 2. Contenido :blue_book:

PENDIENTE!!!!

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

#### <ins>Tema 2</ins>

Una vez que el proyecto está creado, la estructura o forma en la que se organiza es de suma importancia. No sólo nos ayuda a mantener nuestro código organizado, sino que también es importante para el funcionamiento de nuestra nueva app.

- [**`EJEMPLO 2`**](./Ejemplo-02)
- [**`RETO 1`**](./Reto-01)
---

<img src="images/emulator.jpg" align="right" height="90"> 

#### <ins>Tema 3</ins>

Ahora que tenemos mayor conocimiento de nuestro proyecto, vamos a configurar un emulador de algún dispositivo móvil para poder correr nuestra aplicación! :iphone:. Es decir, vamos a correr un dispositivo móvil virtual en nuestra computadora para simular la funcionalidad de nuestra app.

**Nota al Experto:**
  
 + Recuerda que cada subtema puede contener un ejemplo, un reto, o más de un ejemplo y más de un reto. Recuerda borrar esta línea después de haberla leído.
- [**`RETO 2`**](./Reto-02)
---

<img src="images/chaomi.png" align="right" height="110"> 

#### <ins>Tema 4</ins>

Basta de emulaciones, ahora veamos como funciona en el mundo real. Nuestra app, por muy sencilla que sea ya está lista para ser instalada en un dispositivo móvil y para verla en acción.

**Nota al Experto:**
  
 + Recuerda que cada subtema puede contener un ejemplo, un reto, o más de un ejemplo y más de un reto. Recuerda borrar esta línea después de haberla leído.
- [**`RETO 3`**](./Reto-03)
---

### 3. Postwork :memo:

Encuentra las indicaciones y consejos para reflejar los avances de tu proyecto de este módulo.

- [**`POSTWORK SESIÓN 1`**](./Postwork/)

<br/>


</div>

