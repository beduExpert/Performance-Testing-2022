# Ejemplo # 1 - Configuración para graficar los datos

## Objetivo

Demostrar como enviar métricas de resultados con herramientas por medio de tablas y gráficos.

## Desarrollo

### Métricas expuestas

**Métricas de subprocesos/usuarios virtuales**

Las métricas del hilo son las siguientes:

      - <rootMetricsPrefix>test.minAT
    Subprocesos activos mínimos
     - <prefijo de métricas raíz> prueba.maxAT
    Máximo de subprocesos activos
     - <rootMetricsPrefix>test.meanAT
    Subprocesos activos medios
      - <rootMetricsPrefix>test.startedT
    Temas iniciados
    - <rootMetricsPrefix>prueba.finalizadoT
    Hilos terminados
    
    
### Configuración JMeter

Para hacer que JMeter envíe métricas al backend, se debe agregar un BackendListener usando InfluxDBBackendListenerClient.

![1](https://user-images.githubusercontent.com/22419786/156910054-95c29558-5e16-4633-9d1e-a73b30aa1c97.png)

*Configuración de InfluxDB*


### Configuración de InfluxDB

Realizar una de las siguientes acciones para almacenar datos enviados por Backend Listener:

* Para la configuración de InfluxDB 2, se debe crear un cubo JMeter
* Para la configuración de InfluxDB 1.x, se debe crear una base de datos JMeter usando la CLI de Influx

También se puede usar la API HTTP, es decir, curl -i -XPOST http://localhost:8086/query --data-urlencode "q=CREATE DATABASE jmeter"

**Configuración de InfluxDB para InfluxDBBackendListenerClient**

InfluxDB es una base de datos de series temporales, distribuida y de código abierto que permite almacenar métricas fácilmente. 
La instalación y configuración es muy fácil, y se puede realizar desde este sitio web https://docs.influxdata.com/influxdb/v2.1/

Los datos de InfluxDB se pueden ver fácilmente en un navegador a través de Grafana .

**Configuración de InfluxDB 2 para InfluxDBBackendListenerClient**

La configuración debe especificar el parámetro influxdbToken y también especificar el depósito y la organización como parámetros de consulta en influxdbUrl. La API de InfluxDB v2 se puede ver con más detalle en https://docs.influxdata.com/influxdb/v2.0/api/#operation/PostWrite

![2](https://user-images.githubusercontent.com/22419786/156910058-34f9e450-b4e5-4d39-9235-a65fec5b4214.png)

*Configuración de InfluxDB 2*


### Configuración de Grafana

La instalación de esta opcion  se puede obtener de https://grafana.com/docs/

Este es el tipo de tablero que puede obtener:

![3](https://user-images.githubusercontent.com/22419786/156910060-95928d20-d918-4868-bc9d-82777a399591.png)

*Tablero de Grafana*
