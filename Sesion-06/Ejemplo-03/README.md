# Ejemplo # 3 - Análisis de KPIs en JMeter 

## Objetivo

Analizar los KPIs generados para la ejecución de una prueba de carga en JMeter.

## Desarrollo

Una de las formas de manejar nuestros KPIs es en BlazeMeter configurando nuestro test de JMeter

1. Ingresamos a BlazeMeter y en nuestro dashboard elegimos la configuración de JMeter (Botón) en la que vamos a trabajar.

![1](https://user-images.githubusercontent.com/22419786/157734267-0d8815fe-fd5c-4b72-99a4-838cb84cecd0.PNG)

2. Adjuntamos nuestro script de JMeter

![2](https://user-images.githubusercontent.com/22419786/157734295-98dab632-8238-4b45-9f37-055b9ba556e8.PNG)

3. Seleccionamos los criterios de fallas de las pruebas

![3](https://user-images.githubusercontent.com/22419786/157734317-0c8e7c9c-600b-4148-a7b2-8e4599cbf611.PNG)

4. Aquí podemos elegir el KPI que deseemos valorar, en este ejemplo iniciaremos con "responseTime.avg"

![4](https://user-images.githubusercontent.com/22419786/157734363-aabf0b72-670c-47b5-a949-83ca78b53819.PNG)

5. Diligenciamos toda la información

![5](https://user-images.githubusercontent.com/22419786/157734378-841fd0d5-9030-4391-b492-f585522f3225.PNG)

6. Agregamos los KPIs que deseemos

![6](https://user-images.githubusercontent.com/22419786/157734384-f23a7622-d1f7-455c-8058-710dc6f5978a.PNG)

7. Ya tenemos 2 KPIs configurados y ahora vamos a "Network Emulation"

![7](https://user-images.githubusercontent.com/22419786/157734393-157278ad-4e59-48ec-921a-976045cdbe8e.PNG)

8. Diligenciamos la información de red y aplicamos

![8](https://user-images.githubusercontent.com/22419786/157734401-c4e91a25-a0bd-48f1-a3fc-1dd130165d21.PNG)

9. Diligenciamos la informaciómn de la parte derecha donde están los valores y tiempos por configurar y guardamos

![9](https://user-images.githubusercontent.com/22419786/157734410-7b1e1b20-e010-4170-bd7d-d56ed70a7d0b.PNG)

10. Tenemos 3 escenarios previamente grabados en JMeter con BlazeMeter

![10](https://user-images.githubusercontent.com/22419786/157734420-f07a5273-30c1-446c-b82d-2f8ff67c7de0.PNG)

11. Volvemos a BlazeMeter y damos clic en crear test y en Multi Test

![11](https://user-images.githubusercontent.com/22419786/157734449-3a0b6b3d-6a7e-4a8a-bd23-8c59122d1d37.PNG)

12. Agregamos los escenarios de la prueba

![12](https://user-images.githubusercontent.com/22419786/157734437-bdc94991-bc74-4030-acab-1df94477c217.PNG)

13. Aquí podemos desplegar la información del escenario

![13](https://user-images.githubusercontent.com/22419786/157734456-0d9113ae-e940-42d6-90a8-fa041da8d26e.PNG)

14. Podemos cambiar el nombre de este proyecto, guardamos y ejecutamos 

![14](https://user-images.githubusercontent.com/22419786/157734127-a107d934-317b-46dd-9ffc-8c5ba15d1c06.PNG)

15. Nos muestra la configuración hecha para la prueba

![15](https://user-images.githubusercontent.com/22419786/157734131-6ca88c66-5b72-440d-8dd3-9ca90e79a920.PNG)

16. Esperamos mientras termina la ejecución

![16](https://user-images.githubusercontent.com/22419786/157734134-0f9bd1f2-c576-4d1a-91e1-9743b4b6d83b.PNG)

17. Ya podemos visualizar los resultados en el resumen

![17](https://user-images.githubusercontent.com/22419786/157734135-163a4a9f-9241-4146-b017-ec397039aa99.PNG)

18. El reporte de la línea de tiempo

![18](https://user-images.githubusercontent.com/22419786/157734137-fe6157ef-c9fc-4c99-b7de-d310dff1ed2b.PNG)

19. A este reporte le podemos activar las variables que deseemos que se muestren y se grafiquen

![19](https://user-images.githubusercontent.com/22419786/157734142-78bdb72a-19c1-4549-ab10-081d56f641f2.PNG)

20. Podemos visualizar la latencia y tiempo de respuesta sobre el gráfico

![20](https://user-images.githubusercontent.com/22419786/157734149-ffe0060f-9e40-441c-8381-3ea2cbd0f8bd.PNG)

21. Podemos descargar el gráfico como un tipo imagen

![21](https://user-images.githubusercontent.com/22419786/157734153-d60d7c2b-44dd-41a1-8f05-51f4ad759a6e.PNG)

22. Visualizar el estado de la ejecucion como vemos el reporte en JMeter

![22](https://user-images.githubusercontent.com/22419786/157734158-b1e880f7-03c3-45eb-827f-1177ef0f37e9.PNG)

23. El rendimiento

![23](https://user-images.githubusercontent.com/22419786/157734161-f6be6f0a-5a07-431a-9162-107e10b001ae.PNG)

24. La parte de errores

![24](https://user-images.githubusercontent.com/22419786/157734166-3a01e6ba-5a56-420d-bdc3-baaad3e6b69d.PNG)

25. Esta parte de errores la podemos revisar en el proyecto BlazeMeter en los criterios de fallas

![25](https://user-images.githubusercontent.com/22419786/157734171-d713299d-e1a6-401b-a898-39461d7a1173.PNG)

26. En esta pestaña podemos ver la configuración original de la prueba

![26](https://user-images.githubusercontent.com/22419786/157734176-aa0d1bad-4ada-4e70-b28e-f6fa503fdc75.PNG)

27. Y en este botón podemos ver el resumen de todo el reporte en un solo documento y listo para imprimir

![27](https://user-images.githubusercontent.com/22419786/157734179-6b36a0c2-fe2a-422b-aefb-99bca016ff26.PNG)

28. Vemos el resumen con los datos básicos

![28](https://user-images.githubusercontent.com/22419786/157734182-80c7e13a-622f-47bb-acd3-70805b3e9ebe.PNG)

29. Graficas

![29](https://user-images.githubusercontent.com/22419786/157734185-4ee0447c-49bd-4414-a2be-2b9ac93b02b4.PNG)
 
30. Instrucciones

![30](https://user-images.githubusercontent.com/22419786/157734193-ca43c9ab-4600-4c64-b79d-91b78d8191e9.PNG)







