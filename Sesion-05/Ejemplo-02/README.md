# Ejemplo # 2 - Informes de Resultados en JMeter

## Objetivo

PENDIENTE!!!

## Desarrollo

Lo primero que debemos realizar es agregar a nuestro proyecto de JMeter los elementos de revisión de resultados de las ejecuciones.

Abrimos JMeter > clic derecho en plan de prueba > agregar > seleccionar los oyentes o Listeners

![1](https://user-images.githubusercontent.com/22419786/156910923-b99a7b77-f1e9-4abc-bc13-d6939ba64d88.png)

1. Agregar Gráficos

**Muestras: Número total de muestras.**

  Promedio: Tiempo promedio.
  
  Min: Este es el tiempo mínimo que ha tardado un muestreador en ir al servidor.
  
  Max : Esta es la solicitud de tiempo máximo que se tarda en ir al servidor
  .
  Error%: Número de muestreador de errores / Número total de muestreador.
  
  Rendimiento: El rendimiento es la muestra por segundo que recibe el servidor.
  
  KB recibidos / segundo: Esto define cuántos kilobytes por segundo recibe el Cliente.
  
  KB enviados / segundo: Esto define cuántos kilobytes por segundo se envían al servidor.
  
90% Línea: Representa que el 10% de los muestreadores han superado el tiempo para llegar al servidor.
95% Línea: Representa que el 5% de los muestreadores han superado el tiempo para llegar al servidor.

99% Línea: Representa que el 1% de los muestreadores ha excedido el tiempo para llegar al servidor.

* Con base en esta información, podemos mejorar el rendimiento de la aplicación web de la prueba

![2](https://user-images.githubusercontent.com/22419786/156910942-43bbf320-0698-4155-8e35-e4fa827e2bfc.png)

* En forma gráfica lo podemos ver a través del Listener > Display Graph

![3](https://user-images.githubusercontent.com/22419786/156910950-463ce43b-9b71-4fe5-9409-24173588c400.png)

**Informe Agregado**

Los dos informes anteriormente creados sirve para brindar los datos para el análisis del usuario, solo que uno en forma gráfica y el otro en términos estadísticos

![4](https://user-images.githubusercontent.com/22419786/156910952-f5fc7ceb-7228-424a-b9d6-63db7f7c02b3.png)

**Resultados de afirmación**

El escucha de resultados de aserción se utiliza para verificar si la aserción aplicada es correcta o no. A medida que verifica el resultado de la aserción, el oyente siempre debe crearse una vez que se crea la aserción para el muestreador y las solicitudes.

![5](https://user-images.githubusercontent.com/22419786/156910957-7682c49d-2e4e-4088-a7ff-4644992e9f6d.png)

**Ver resultados en tabla**

Mustra en filas y columnas y proporciona información clave para análisis. Este oyente no se puede utilizar para pruebas de carga completas ya que consume una gran cantidad de CPU / memoria.

![6](https://user-images.githubusercontent.com/22419786/156910961-95f23ae4-b5b0-46a9-99b3-15835f4cc2c4.png)

*Componentes:*

Nombre: Nombre del oyente

Comentarios: Si alguna se puede proporcionar aquí.

El oyente muestra los siguientes datos:

Muestra #: Número total de muestreadores

Hora de inicio: Es el momento en que se emitieron las muestras.

Nombre del hilo: Nombre del hilo.

Etiqueta: Etiquetar como se proporciona.

Tiempo de muestra (ms): Una vez que el servidor inicia la solicitud, el tiempo necesario para obtener la respuesta de la solicitud es el tiempo de muestra.

Estado: Estado como símbolo Pasa / No pasa.

Bytes: Bytes recibidos por el cliente.

Bytes enviados: Bytes enviados al servidor.

Latencia: Es el retraso en la respuesta de la aplicación a la solicitud enviada por el usuario.

Tiempo de conexión (ms): Este es el tiempo que tarda una solicitud en llegar al servidor.

**Ver resultados en árbol**

Este oyente tiene la ventaja de que puede verificar tanto la solicitud como la respuesta, ya que compara el requisito y el resultado real. No muestra los resultados de la aserción de aprobación.

![7](https://user-images.githubusercontent.com/22419786/156910967-a8bec595-9825-4af1-8425-b826334470a5.png)

Los diferentes formatos disponibles son: Text, Regexp tester, Boundary Extractor Tester, CSS / JQuery Tester, Xpath Tester, JSON Path tester, HTML, HTML con formato de fuente, HTML (recursos de descarga), Documento, JSON, XML, Navegador.

![8](https://user-images.githubusercontent.com/22419786/156910985-be608de8-4ac8-482a-974b-bcf460a4313b.png)

Este oyente también es bueno solo para pruebas básicas y no para pruebas de carga, ya que consume una gran cantidad de fuentes como CPU y memoria.

**Informe resumen JMeter**

![9](https://user-images.githubusercontent.com/22419786/156910988-38814a4f-4480-45c2-bc4d-8964de15835b.png)

El oyente proporciona los siguientes datos:

Etiqueta: Etiqueta es el nombre o URL de la solicitud.

Num de Muestras: No. de muestras es el número de usuarios por solicitud

Promedio: El tiempo medio se calcula en función del tiempo que tardan las muestras en ejecutar la etiqueta.

Min: Tiempo mínimo o mínimo que toma una muestra para la etiqueta.

Max: Tiempo máximo o más largo que toma una muestra para la etiqueta.

Std Dev : Es una desviación del valor medio del tiempo de respuesta de la muestra.

Error%: Porcentaje de solicitudes fallidas.

Rendimiento: Es el número de solicitudes procesadas por el servidor.

KB / seg: Son los datos descargados en KB / seg mientras se realiza la ejecución del rendimiento.

**Generando resultados resumidos**

Generar resultados resumidos Oyente genera un informe de resumen en forma de registro es decir, se crea un archivo de registro y su formato se especifica en el archivo de propiedades de JMeter.

![10](https://user-images.githubusercontent.com/22419786/156910997-757c1918-8901-4f66-9ddc-259926684331.png)

**Graficar resultados**

Resultados gráficos El usuario utiliza el oyente si requiere resultados en forma gráfica . El gráfico representa los datos del último muestreador y el tiempo de respuesta en los ejes xey, respectivamente.

![11](https://user-images.githubusercontent.com/22419786/156911003-adee5986-b5f3-4e56-bcb5-3d5e9c35c2ba.png)

**Guardar respuestas en un archivo**

Como se muestra en la siguiente captura de pantalla, la respuesta se puede guardar usando varias opciones. Como fallamos y aprobamos las respuestas, seleccionar el campo proporcionará solo los datos requeridos.

Puede haber varias razones para guardar las respuestas ya que a veces no podemos encontrar las razones de la falla en el momento de la ejecución, por lo que guardar los datos nos ayuda a analizar los datos más adelante para conocer la razón de la falla.

![12](https://user-images.githubusercontent.com/22419786/156911010-49b2d518-f858-45f8-aa5c-7be861a6014c.png)


**Escritor de datos simple**

El oyente registra la respuesta y la escribe en un archivo plano.

![13](https://user-images.githubusercontent.com/22419786/156911029-75387d96-5b24-4825-a710-a9c0df7604ff.png)
