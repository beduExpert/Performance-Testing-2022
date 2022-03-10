# Ejemplo # 2 - Integración JMeter con Jenkins y Git

## Objetivos

* Instalar Plugin en Jenkins para integración con github
* Configurar Jenkins job para obtener el sript de JMeter desde Github
* Ejecutar script de JMeter como parte del job de Jenkins

## Desarrollo

Para la integración entre JMeter, Jenkins y github estos son los pasos que vamos a realizar:

1. Vamos a instalar el plugin para la integración con Github en "Manage Jenkins"
![1](https://user-images.githubusercontent.com/22419786/157596633-a34f0195-2340-41ea-bf9e-37c1017669ba.PNG)

2. Bajamos el scroll hasta que lleguemos a la opcion de "Manage Plugins" y hacemos clic
![2](https://user-images.githubusercontent.com/22419786/157596635-b135c015-1cdb-4bd6-a2d7-da3b7a93a2ee.PNG)

3. Escribimos en el buscador la palabra "git"

![3](https://user-images.githubusercontent.com/22419786/157596640-f7642a2c-bfbc-4196-a3aa-545e2a9a8da2.PNG)

4. Damos clic en la pestaña "Installed" aquí podemos ver los plugins que tenemos ya instalados

![4](https://user-images.githubusercontent.com/22419786/157596646-230d165b-a1b9-4913-879c-a7984c232120.PNG)

5. En este ejemplo ya tenemos GitHub plugin en los instalados

![5](https://user-images.githubusercontent.com/22419786/157596650-963ab15d-2f4f-48df-a1aa-b3b8bb8ffae7.PNG)

6. Vamos a la pestaña "Available" para descargar "CCM" que es un plugin para análisis de resultados

![6](https://user-images.githubusercontent.com/22419786/157596659-57f29dd2-c674-4fa6-b3f9-c527d876b9f1.PNG)

7. Ahora, para crear el job de Jenkins, vamos a "New Item"

![7](https://user-images.githubusercontent.com/22419786/157596676-e0386afb-1490-4714-8894-4748f45c6399.PNG)

8. Ingresamos el nombre que deseamos ponerle y seleccionamos "Freestyle project"

![8](https://user-images.githubusercontent.com/22419786/157596685-15cefd1f-5d84-42eb-b067-e419477f2730.PNG)

9. Aqui ya lo tenemos creado y ahora damos clic derecho y escogemos Configure

![9](https://user-images.githubusercontent.com/22419786/157596693-91220c4e-b3e9-4025-a048-3015adcdb717.PNG)

10. En la pestaña "Source Code Management" bajamos a la parte de "Source Code Management" y es donde podemos configurar Git, allí ponemos la URL de nuestro repositorio Git

![10](https://user-images.githubusercontent.com/22419786/157596698-4b825675-1a77-4fd8-96a5-32d0c77b09a8.PNG)

11. Esta URL se obtiene desde nuestro Git en la opcion de "Clone or download"

![11](https://user-images.githubusercontent.com/22419786/157596710-3edb442e-3b6a-4122-b639-5e1d85bd83db.PNG)

12. Añadimos la credencial de Jenkins

![12](https://user-images.githubusercontent.com/22419786/157596715-289340a3-6bc2-47d4-90e0-8f36a47f4cca.PNG)

13. Dejamos la siguiente información en Domain y Kind++

![13](https://user-images.githubusercontent.com/22419786/157596719-4c1bd328-6c67-4700-8192-efd8ae44343f.PNG)

14. Indicamos el branch de construccion


![14](https://user-images.githubusercontent.com/22419786/157596743-91385f4f-5d85-4850-87db-d91f2787f495.PNG)

15. Indicamos el subdirectorio del repositorio

![15](https://user-images.githubusercontent.com/22419786/157596753-fc7438e5-ef4e-4bc7-b408-43e02525d253.PNG)

16. En la parte de Build, debemos incorporar el comando del Shell

*pwd; ls -ltrh;
java -version;
curl http://mirror.cc.columbia.edu/pub/sof...
 -o apache-jmeter-5.3.tgz;
tar -xvzf apache-jmeter-5.3.tgz;
cd apache-jmeter-5.3/bin;
sh jmeter.sh -n -t ../../jmeterGitJenkins/jmeter/jmeterGitJenkinsTestplan.jmx -l result.jtl -*

![16](https://user-images.githubusercontent.com/22419786/157596758-c794465b-7e07-47e8-a49d-3068b75ac532.PNG)

17. Finalmente damos clic en el botón "Save"

![17](https://user-images.githubusercontent.com/22419786/157596788-c673acd3-7ff4-47f0-bf5f-afc0d80f8bc8.PNG)

18. Ahora vamos a Build Now

![18](https://user-images.githubusercontent.com/22419786/157596796-6356a3a4-a683-468c-9b57-dbaef5e45c53.PNG)

19. Identificamos la ejecución > clic derecho > console Output

![19](https://user-images.githubusercontent.com/22419786/157596801-f05156c8-37c0-4b15-b03b-717f8f32948a.PNG)

20. Aquí podemos ver la ejecución

![20](https://user-images.githubusercontent.com/22419786/157596814-2e9dbce1-104d-491f-bb6c-4cf6df654ec2.PNG)

21. Podemos ir viendo los resultados

![21](https://user-images.githubusercontent.com/22419786/157596822-276f8462-8aa3-452b-adc8-43b54d54ebc2.PNG)

22. Esperamos a que aparezca fin de la ejecución y el estado exitoso o fallido

![22](https://user-images.githubusercontent.com/22419786/157596827-9b5a446d-809a-48ed-871c-b54a6d922b3d.PNG)

23. Ya en el proyectioo vamos a Workspace

![23](https://user-images.githubusercontent.com/22419786/157596836-5452eac9-4af6-414f-b4a5-4ecb12682837.PNG)

24. Vemos la carpeta creada

![24](https://user-images.githubusercontent.com/22419786/157596853-73cd11a5-cdd2-4309-a15f-efa62e556b83.PNG)

25. Abrimos la carpeta jmeter

![25](https://user-images.githubusercontent.com/22419786/157596860-8af3b774-5279-4a07-9dd8-d4bffdf64624.PNG)

26. Encontramos nuestro proyecto de JMeter en .jmx

![26](https://user-images.githubusercontent.com/22419786/157596870-841e7c1b-b42e-4f7e-9904-bd0b9fdbae08.PNG)

27. Nos devolvemos e ingresamos nuevamente a workspace y vamos a apache jmeter > bin > result.jtl (view)

![27](https://user-images.githubusercontent.com/22419786/157596880-9487e2c1-ffcc-4240-a217-c4387e52c7a5.PNG)

28. Finalmente podemos ver el archivo que teniamos en JMeter 

![28](https://user-images.githubusercontent.com/22419786/157596885-894b08e4-370e-4f6f-9b95-00f6aca91ec5.PNG)


