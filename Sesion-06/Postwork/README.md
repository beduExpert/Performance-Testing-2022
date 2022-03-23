# Sesión # 6 - Reportes e integraciones con JMeter

## :dart: Objetivos

- Emplear proyecto para pruebas de performance en JMeter
- Incorporar proyecto jmx en github
- Configurar job de jenkins para comunicación con github


## Desarrollo

En esta sesión crearemos un proyecto en JMeter donde integremos con Github y llamemos desde el job de Jenkins


**Indicaciones Generales**

* Crear un proyecto en JMeter
  - Crear el plan de pruebas

* Crear los elementos del proyecto en JMeter.
  - Elementos básicos de grabación
  - Configuración de datos
  - Árbol de resultados
  - Reporte resumen
  - Gráfico de resultados

* Subir el proyecto a GitHub.
  - Obtenemos el link del repositorio Git donde se aloja el proyecto

* Abrir la aplicación de Jenkins.

* Configurar Git.
  - En la parte de Source Code Management incluir el link del repositorio GIT

* Indicar las credenciales con el branch de construcción
  - Configuración de Jenkins
  - Configurar comando shell.
  - Dentro de Build indicar esta instrucción
    pwd; ls -ltrh; java -version; curl http://mirror.cc.columbia.edu/pub/sof... -o apache-jmeter-5.3.tgz; tar -xvzf apache-jmeter-5.3.tgz; cd apache-jmeter-5.3/bin; sh jmeter.sh -n -t ../../jmeterGitJenkins/jmeter/jmeterGitJenkinsTestplan.jmx -l result.jtl -

* Ejecutar proyecto validando consola output.
  - En Build Now

* Finalizar ejecución.

* Verificar archivo .jtl para ver los resultados.
  - Al final del resultado aparece “Finished:” Satisfactorio o Fallido

