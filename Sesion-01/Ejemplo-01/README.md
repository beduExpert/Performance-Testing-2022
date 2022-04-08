# Ejemplo 1: Instalación de JMeter y las herramientas prerrequisito.

## Objetivo

* Instalar las herramientas que son prerrequisitos para la instalación de JMeter
* Instalar la herramienta JMeter junto con su certificado de seguridad

## Desarrollo

**Requisitos**

Para el correcto funcionamiento de la herramienta se deben tener en cuenta los siguiente requisitos previos, correcta instalación y configuración, cargue de certificado de prueba y archivo .bat con el que se inicia la ejecución de la herramienta.

* La máquina debe tener instalado Java 1.6 o superior. Tener JRE y JDK correctamente instalados y el conjunto de variables de entorno JAVA_HOME.

Revisión versión JAVA por consola.

<img src="https://user-images.githubusercontent.com/22419786/154817183-d83de04e-6c4e-488a-808e-8aebd8c1b8d9.jpg" align="center" height="160"> 


* JRE y JDK en carpeta Java.
<img src="https://user-images.githubusercontent.com/22419786/154818838-5dd92a74-97bb-4477-9735-048d6edcf6dc.jpg" align="center" height="160"> 

* En el equipo, ingresar a las Propiedades del sistema e ingresar a las variables de entorno.
<img src="https://user-images.githubusercontent.com/22419786/154818842-e8fff57e-92d2-4988-981c-9c2a7b4ffd30.jpg" align="center" height="180"> 

* En las variables del sistema debe estar la variable JAVA_HOME con la ruta donde está alojado el bin del jdk.
<img src="https://user-images.githubusercontent.com/22419786/154818838-5dd92a74-97bb-4477-9735-048d6edcf6dc.jpg" align="center" height="160"> 

* Descargar la herramienta del siguiente sitio:
http://jmeter.apache.org/download_jmeter.cgi

Este enlace trae una descarga .zip

<img src="https://user-images.githubusercontent.com/22419786/154818845-22dfda12-6704-4414-884c-1460ea8cd996.jpg" align="center" height="160"> 

**Instalación**

* Al descomprimir la carpeta queda de esta manera.
<img src="https://user-images.githubusercontent.com/22419786/154818846-720130d7-4b50-4100-95c1-62f603f4c5fb.jpg" align="center" height="160">

* Se debe descargar la última versión del paquete de plugins de la siguiente ruta:
http://jmeter-plugins.org/downloads/all/
<img src="https://user-images.githubusercontent.com/22419786/154818847-9a64f636-86f9-48d3-9cfc-4e0591983a6d.jpg" align="center" height="160">

* Este jar (JMeterPlugins.jar) se debe incluir en la carpeta JMETER_INSTALL_DIR/lib/ext/
<img src="https://user-images.githubusercontent.com/22419786/154818848-7f71a265-be10-4ed5-a7ec-4e4078bd8260.jpg" align="center" height="160">

* Por defecto, JMeter no registra un contador de threads en archivos JTL. Para modificar la configuración de archivos JTL, es necesario abrir el archivo
JMETER_INSTALL_DIR/bin/jmeter.properties en la línea: #jmeter.save.saveservice.thread_counts= true

descomentarla y verificar que esté true.

<img src="https://user-images.githubusercontent.com/22419786/154818849-07375a5d-f62c-4058-9da9-a173a3a636d0.jpg" align="center" height="160">

**Certificado**

Se debe instalar el certificado de seguridad de JMeter en el navegador donde se va a realizar la grabación del script.

* En Chrome ir a los puntos de la parte superior derecha > seleccionar configuración > Seguridad y privacidad > Gestionar certificados
<img src="https://user-images.githubusercontent.com/22419786/154818850-e4ca6443-a3a3-4ca4-bdc5-ed4108f599d9.jpg" align="center" height="160">

* Importar el certificado.

Ir a la pestaña “Entidades de certificación raíz de confianza” > “Importar”

![S1-12Importacion](https://user-images.githubusercontent.com/22419786/154819124-6d662f5b-4b08-43e0-ad91-b6ac53f282b1.jpg)

* Importar el certificado desde esta ruta.

![S1-13SeleccCertificado](https://user-images.githubusercontent.com/22419786/154819140-4e15f3ca-63f2-40a5-ac95-686820899082.jpg)

* Validar certificado importado exitosamente.

![S1-14CertifImport](https://user-images.githubusercontent.com/22419786/154819156-11234859-f4fe-41a1-9aa2-5f27f12f9f40.jpg)

Importar el certificado desde esta ruta.

**Ejecución**
* En el directorio bin abrir el archivo “jmeter.bat”.

![S1-15JMeterBat](https://user-images.githubusercontent.com/22419786/154819264-2b73e11b-8159-4dfe-8941-4214eb1b64f9.jpg)

* Se abre una ventana así, la información de la consola es un mensaje informativo.
![S1-15JMeterBat](https://user-images.githubusercontent.com/22419786/154819235-f965b5ad-6b8c-4870-9f02-ae8a90b2ec3a.jpg)
