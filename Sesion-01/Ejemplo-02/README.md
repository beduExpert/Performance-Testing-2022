# Ejemplo # 2 - Configuración de un Test Plan

## Objetivos

* Crear un plan de pruebas desde la herramienta JMeter
* Utilizar un template base para la estructura del plan de pruebas
* Mapear objetos y acciones de una página web
* Ejecutar las acciones grabadas

## Desarrollo

**Configuración de un Test Plan**

* En el paso anterior ya vimos cómo se ejecuta la aplicación, ahora en File > New se puede incluir un Test Plan para iniciar a trabajar

![Imagen17](https://user-images.githubusercontent.com/22419786/154819568-ec1988a1-a490-44e9-a200-cf2d9c8b1adc.png)

Sin embargo para los primeros usos de la herramienta se puede utilizar un template que trae listos los servicios a utilizar.

**Uso de Template para Test Plan**

* En File > Templates se selecciona y abre la siguiente ventana, allí en la lista desplegable se elige “Recording” y “Create”.

![Imagen18](https://user-images.githubusercontent.com/22419786/154819607-ec204ed8-3e1a-42ad-8163-8f8d559e3124.png)

* Debe quedar con la siguiente estructura donde están los request, el plan de pruebas, el script de grabación y la tabla de resultados.
![Imagen19](https://user-images.githubusercontent.com/22419786/154819623-88cf2947-d944-4809-8d2f-54a1ca867ff9.png)

* En Thread Group se debe ingresar el nombre del escenario de prueba, la cantidad de usuarios a simular y el tiempo en segundo en el que se debe ejecutar cada petición.
![Imagen22](https://user-images.githubusercontent.com/22419786/154821737-86512f11-0686-4d8c-b31d-6518c0ade6f2.png)

* En HTTP(S) Test Script Recorder es nuestro grabador donde tambien podemos cambiar el nombre y en el botón "Start" es donde iniciamos la grabación en nuestro aplicativo web.
![Imagen23](https://user-images.githubusercontent.com/22419786/154821776-5c0baf74-b16e-426f-a714-fda98ddb5fa0.png)

* Se ejecutan los pasos y acciones dentro del producto web y estos van quedando registrados en nuestro arbol de resultados, cuando deseo terminar la grabación doy clic en el botón "Stop".

![Imagen24](https://user-images.githubusercontent.com/22419786/154821802-eb282c89-8ccc-4c02-8547-e9533b8116cb.png)

* Con base en esto se pueden ir creando las transacciones definidas dentro del plan de pruebas.

![Imagen20](https://user-images.githubusercontent.com/22419786/154819633-bd9d9ff4-f243-4f4f-9068-e9807dfe631e.png)

* En esta opción se muestran los resultados de la ejecución de los test
![Imagen21](https://user-images.githubusercontent.com/22419786/154819644-bc8ebda3-8404-4dfd-b5a6-8113928389b2.png)
