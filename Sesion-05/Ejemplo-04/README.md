# Ejemplo # 4 - Elaboración documento plan de pruebas

## Objetivo

Presentar a través de un ejemplo práctico los pasos y temario que debe tener un documento de pruebas de rendimiento.

## Desarrollo

En este ejemplo presentamos las partes de un documento que debe tener un plan de pruebas que en este caso nuestro ejemplo serán pruebas de rendimiento a la navegación por una aplicación web de un banco en la transacción de consultas de productos de los clientes.

Todo documento debe tener lo siguiente:

### 1. Introducción

Tenemos una aplicación web bancaria que permite consultar los productos que tienen los clientes, se debe analizar cuantos usuarios simultaneamente puede soportar la aplicación, para esto realizaremos nuestras pruebas de carga.

**1.1. Objetivos**

* Realizar pruebas de carga, de estres y de estabilidad a la aplicación web del banco para la transacción de consultas.
* Garantizar el rendimiento de la aplicación, la disponibilidad del servicio y la estabilidad de la aplicación.
* Verificar que los tiempos de respuesta de las transacciones se mantienen dentro de la tolerancia aceptable sobre el perfil de carga creciente.


**1.2. Arquitectura**

Se debe incorporar el diagrama de arquitectura de su proyecto


### 2. Alcance

Este proyecto tiene como alcance lo siguiente:

* Comprender la funcionalidad de la transacción a probar (Negocio)
* Grabación de escenario de consulta de productos del banco desde su aplicación web
* Iteracion de datos para pruebas de carga
* Pruebas de estres
* Pruebas de estabilidad
* Uso del token y accesibilidad como prerrequisito
* Validación del entorno y ambiente de pruebas 
* Publicar los resultados de las pruebas de rendimiento

*A nivel del proyecto en JMeter*

* Generación de datos de prueba
* Recomentaciones de rendimiento
* Soporte a infraestructura
* Optimización del rendimiento

### 3. Enfoque

**Escenarios de pruebas de rendimiento**

- *Escenario 1:*  Validar acceso a opción de consultas de la app web con **10** usuarios simultaneos en un tiempo de **1** segundo entre cada petición
- *Escenario 2:*  Validar acceso a opción de consultas de la app web con **10** usuarios simultaneos en un tiempo de **5** segundos entre cada petición
- *Escenario 3:*  Validar acceso a opción de consultas de la app web con **20** usuarios simultaneos en un tiempo de **1** segundo entre cada petición
- *Escenario 4:*  Validar acceso a opción de consultas de la app web con **20** usuarios simultaneos en un tiempo de **5** segundos entre cada petición
- *Escenario 5:*  Validar acceso a opción de consultas de la app web con **50** usuarios simultaneos en un tiempo de **1** segundo entre cada petición
- *Escenario 6:*  Validar acceso a opción de consultas de la app web con **50** usuarios simultaneos en un tiempo de **5** segundos entre cada petición
- *Escenario 7:*  Validar acceso a opción de consultas de la app web con **100** usuarios simultaneos en un tiempo de **1** segundo entre cada petición
- *Escenario 8:*  Validar acceso a opción de consultas de la app web con **100** usuarios simultaneos en un tiempo de **5** segundos entre cada petición

![2](https://user-images.githubusercontent.com/22419786/156946167-77be6ef8-c484-4453-94fc-e6abf9d9c4c0.PNG)
*Configuración de usuarios y tiempo*



**Tipos de pruebas de rendimiento**

- *Pruebas de Carga*

Indicar cantidad de usuarios y tiempo de espera entre peticiones y presentar arbol de resultados, gráfico y reporte resumen

*Arbol de resultados*
![7-2](https://user-images.githubusercontent.com/22419786/156946329-a90201e7-5c08-453a-be43-7ed2b2753357.PNG)

*Gráfico de resultados*
![5](https://user-images.githubusercontent.com/22419786/156946344-c97460c2-e8cd-4e64-9513-e84d03477e3f.PNG)

*Reporte resumen*
![6](https://user-images.githubusercontent.com/22419786/156946353-afcd0702-8fed-463d-9570-6b53d6add120.PNG)


- *Pruebas de Estres*

Indicar cantidad de usuarios y tiempo de espera entre peticiones y presentar arbol de resultados, gráfico y reporte resumen

*Arbol de resultados*
![6](https://user-images.githubusercontent.com/22419786/156946418-79fd6e2c-f7f6-4cc2-8ed5-6ca3cd583e68.PNG)

*Gráfico de resultados*
![4](https://user-images.githubusercontent.com/22419786/156946423-c9a6b54b-7848-46dd-a489-f2316f959cb5.PNG)

*Reporte resumen*
![5](https://user-images.githubusercontent.com/22419786/156946430-8c07fb34-7453-40e8-8314-6027e8a9a1ff.PNG)


- *Pruebas de Estabilidad*

Indicar cantidad de usuarios y tiempo de espera entre peticiones y presentar arbol de resultados, gráfico y reporte resumen

*Arbol de resultados*
![4](https://user-images.githubusercontent.com/22419786/156946451-b1943440-0435-4907-ba3e-cbc9b3addd93.PNG)

*Gráfico de resultados*
![5](https://user-images.githubusercontent.com/22419786/156946460-e603c76b-823f-45ff-9049-edde2e725ded.PNG)

*Reporte resumen*
![2](https://user-images.githubusercontent.com/22419786/156946467-b4f63a95-2d2f-44d0-88e3-317e34e217bb.PNG)



- *Pruebas de Recuperación*

Indicar cantidad de usuarios y tiempo de espera entre peticiones y presentar arbol de resultados para pruebas de carga en recuperación

*Arbol de resultados*

![3](https://user-images.githubusercontent.com/22419786/156946494-c483166c-ed75-4764-ac7c-ceaa78566316.png)


**Métricas de rendimiento**

Nuestros parámetros base para el análisis de resultados y métricas de rendimiento son el mínimo, el máximo, el promedio y el % de error que se presentan en la siguiente imagen

![1](https://user-images.githubusercontent.com/22419786/156946784-cadf3888-afa7-4752-9b7d-915caec1efb5.PNG)


**Actividades y entregables de pruebas de rendimiento**

![2](https://user-images.githubusercontent.com/22419786/156946894-3ae5014d-8e20-4966-b23e-3d3fdcf02e9f.PNG)


### 4. Datos de prueba

Como datos de prueba tenemos:

- 10 usuarios concurrentes de 1 segundo entre peticiones
- 10 usuarios concurrentes de 5 segundos entre peticiones
- 20 usuarios concurrentes de 1 segundo entre peticiones
- 20 usuarios concurrentes de 5 segundos entre peticiones
- 50 usuarios concurrentes de 1 segundo entre peticiones
- 50 usuarios concurrentes de 5 segundos entre peticiones
- 100 usuarios concurrentes de 1 segundo entre peticiones
- 100 usuarios concurrentes de 5 segundos entre peticiones

### 5. Criterios de entrada y salida

*Criterios de entrada*

- Acceso a todas las aplicaciones del entorno.
- Preparación del entorno completo.
- Preparación de datos de prueba de rendimiento.

*Criterios de salida*

- Informe de resultados de acuerdo al reporte resumen
- Gráfico de resultados
- Arbol de resultados con request y response
- Metricas de resultados

### 6. Gestión de defectos

Los defectos los podemos gestionar desde una herramienta que en nuestro caso es JIRA

![18](https://user-images.githubusercontent.com/22419786/156957347-f49bf636-1e71-4b9c-86ba-73919bca2ee8.PNG)

### 7. Herramientas y técnicas de prueba

Herramienta JMeter

### 8. Criterios de suspensión y reanudación

Se vuelve un tema bloqueante cuando:

- No está el ambiente configurado
- La aplicación está inestable
- No hay datos de prueba disponibles

### 9. Entregables de prueba

- Estrategia de prueba de rendimiento
- Documento de requisitos de desempeño
- Documento de escenario de prueba de rendimiento
- Guiones de prueba de rendimiento
- Resultados de la prueba de rendimiento


### 10. Funciones y responsabilidades

![10](https://user-images.githubusercontent.com/22419786/156947549-ef089c44-8cd9-42d3-8a22-2815e6b8e22d.PNG)

### 11. Riesgos potenciales y plan de mitigación

![11](https://user-images.githubusercontent.com/22419786/156948331-9b407317-60af-4f02-b9b5-c78975caebe6.PNG)

### 12. Abreviaturas

![14](https://user-images.githubusercontent.com/22419786/156948335-f1d7ccc8-3927-4eac-a292-7c6da8241f3c.PNG)
