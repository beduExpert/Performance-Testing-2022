# Ejemplo # 3 - Parametrización de datos utilizando el controlador parametrizado

## Objetivo

* Elaborar pasos a paso una parametrización en JMeter utilizando el controlador parametrizado

## Desarrollo

Si necesita ejecutar una secuencia repetitiva de la misma acción con diferentes parámetros, use el complemento de terceros 'Controlador parametrizado' del proyecto JMeter-Plugins.

Primero debe instalar este complemento siguiendo el procedimiento de instalación.

Supongamos que queremos parametrizar el flujo de trabajo de inicio de sesión:

<img width="673" alt="1" src="https://user-images.githubusercontent.com/22419786/156497560-067e0722-746e-4b36-bc55-8c4cec4c9178.png">

En primer lugar, debe instalar el complemento 'Controlador parametrizado', ya que no está incluido en el núcleo de JMeter. Los pasos de instalación de ese proceso se pueden encontrar aquí.

Muevamos la 'Solicitud de inicio de sesión' a un controlador separado y desactívelo (haga clic con el botón derecho y seleccione "Deshabilitar"). Esta es la forma más preferible de tener un contenedor de módulos dentro de su plan de prueba y evitar usar Workbench como tal contenedor. Una vez finalizada la instalación, puede agregar dos controladores 'Controlador parametrizado' con diferentes credenciales de usuario: haga clic con el botón derecho en Grupo de subprocesos -> Agregar -> Controlador lógico -> Controlador parametrizado

<img width="674" alt="2" src="https://user-images.githubusercontent.com/22419786/156497577-416eef81-6fd1-46d9-8e2f-7693ce98cb28.png">

Los controladores parametrizados contienen la sección 'Variables definidas por el usuario', donde puede especificar sus parámetros. Coloque las credenciales del primer usuario en el primer controlador parametrizado y las credenciales del segundo usuario en el segundo controlador parametrizado.

<img width="672" alt="3" src="https://user-images.githubusercontent.com/22419786/156497586-b5f71659-0d54-4d5e-8003-eb909e1f25ce.png">

Dentro de ambos controladores parametrizados, agregue referencias al 'Controlador reutilizable' para llamar a la 'Solicitud de inicio de sesión' con diferentes parámetros. Se puede hacer de esta manera:

Haga clic derecho en 'Controlador parametrizado' -> 'Agregar' -> 'Controlador lógico' -> 'Controlador de módulo'<img width="671" alt="4" src="https://user-
  
images.githubusercontent.com/22419786/156497622-0f411376-f366-408e-9fa6-c9d74ba506f9.png">

Al ejecutar su secuencia de comandos, verá que la 'Solicitud de inicio de sesión' activó cada uno de los controladores parametrizados por separado. Puede ser muy útil en caso de que necesite ejecutar su secuencia de comandos en diferentes combinaciones de parámetros de entrada.

<img width="671" alt="5" src="https://user-images.githubusercontent.com/22419786/156497653-10926c65-37a0-48e9-8877-150677e0f603.png">

