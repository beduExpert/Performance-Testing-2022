# Ejemplo 3: Pasos para grabación de tráfico HTTPS

## Objetivo

Mostrar la configuración en JMeter a nivel de tráfico HTTPS teniendo en cuenta la configuración del Proxy SSL.

## Desarrollo

Si su aplicación web utiliza el cifrado SSL, necesita capturar el tráfico HTTPS en lugar de HTTP.
Para registrar el tráfico HTTPS con JMeter, debe configurar los certificados SSL.

**Configure su proxy SSL**

1. Asegúrese de que el proxy SSL esté configurado de la misma manera que el proxy HTTP:

<img width="403" alt="1 proxy" src="https://user-images.githubusercontent.com/22419786/155261737-6b2613cf-cf37-4e47-8909-9e5efbeed6ff.png">

**Configurar JMeter**

2. Inicie la grabación del script utilizando la función "Plantilla de grabación JMeter" como se explica en el ejemplo "Grabación de script con la función de plantilla JMeter".
3. Después de abrir la aplicación web, verá un mensaje sobre una conexión no segura. Para continuar, solo necesita aceptar el certificado ficticio de JMeter:

* Haga clic en 'Avanzado'
* Haga clic en 'Agregar excepción ...'
* Desmarque 'Almacenar permanentemente esta excepción'
* Haga clic en 'Confirmar excepción de seguridad'

<img width="444" alt="2 excepcion" src="https://user-images.githubusercontent.com/22419786/155261817-a9fcaa4a-5328-4237-adbe-0e83dcf782c5.png">

<img width="446" alt="3 location" src="https://user-images.githubusercontent.com/22419786/155261842-8c677321-6ef9-4ad1-bbd5-7b9e9ed5bce7.png">

4. Si ve el mensaje “Este sitio proporciona una identificación válida y verificada. No es necesario agregar una excepción ". Mensaje de advertencia: debe borrar el historial del
navegador de su aplicación, incluidas las cookies, el caché y los datos de sitios web sin conexión. Luego, proceda de nuevo con los mismos pasos.

Este enfoque también funciona para la grabación de scripts móviles, ya que el certificado JMeter debe instalarse solo en el host que se está utilizando para ejecutar JMeter.
