# Ejemplo 2: Elaboración plan de pruebas sin Template

## Objetivo

* Realizar un plan de pruebas incluyendo los elementos necesarios para el funcionamiento de las pruebas.
* Emplear los elementos necesarios para el plan de pruebas.

## Desarrollo

**Configuración de JMeter**

JMeter permite configurar manualmente su área de trabajo. Es más complejo, pero puede hacer que los scripts se ajusten a sus necesidades puntuales.

1. Crear un TestPlan en la herramienta (Proyecto JMeter).

2. La rama "WorkBench" se puede usar como un espacio de trabajo temporal para crear scripts. Se debe tener en cuenta que las entradas agregadas a esta sección no se guardarán con el plan de prueba. Por lo tanto, si desea reutilizar la misma configuración de grabación en el futuro, deberá copiarla y pegarla en la sección "Plan de prueba".

3. Agregue “Controlador de grabación” a “Banco de trabajo”: haga clic derecho en “Banco de trabajo” -> “Agregar” -> “Controlador lógico” -> “Controlador de grabación”.

![Control logico](https://user-images.githubusercontent.com/22419786/155257635-b8c79a2d-644c-4b2c-996e-ee6f7931638b.png)

4. Agregue “HTTP (S) Test Script Recorder” al mismo “WorkBench”: haga clic derecho en “WorkBench” -> “Add” -> “Non-Test Elements” -> “HTTP (S) Test Script Recorder”.

![test script record](https://user-images.githubusercontent.com/22419786/155257690-fd251b2f-90af-4eb8-8ba9-96a7cbef4c42.png)

5. En la página de configuración de "HTTP (S) Test Script Recorder" en "Configuración global: Puerto", debe colocar el mismo puerto que se especifica en la configuración de proxy de su navegador, por ejemplo 8080.

6. Para hacer que JMeter se comporte más como un navegador real, se recomienda agregar el "Administrador de caché HTTP", que le permite simular la funcionalidad de almacenamiento en caché del navegador en sus pruebas de rendimiento. Haga clic derecho en "Plan de prueba" -> "Agregar" -> "Elemento de configuración" -> "Administrador de caché HTTP".

7. Ahora haga clic en el botón 'Inicio', que se encuentra en la parte inferior de la página "HTTP(S) Test Script Recorder", y vaya a través del flujo de trabajo de la aplicación web que desea probar. Cuando regrese a JMeter, debería ver todas las solicitudes capturadas desde su navegador bajo el "Controlador de grabación".

<img width="603" alt="control grab" src="https://user-images.githubusercontent.com/22419786/155258721-8ec5d31c-a813-4e81-924c-36bd925132b8.png">


