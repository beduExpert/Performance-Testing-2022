# Ejemplo # 1 - Prueba de carga con Reporte HTML

## Objetivo

Identificar los tipos de reporte que se pueden obtener de las ejecuciones de pruebas de performance

## Desarrollo

1. Tenemos preparado un test sencillo sobre una API Soap en la que lo que hace es multiplicar 2 valores, ejecutamos los elementos y vemos que aparecen con éxito

![1](https://user-images.githubusercontent.com/22419786/157589755-342ab0df-b355-472f-a357-09859f363ca9.PNG)

2. Vemos los parámetros que requiere el reporte HTML para esta ejecución, vamos a Tools y "Generate HTML report"

![2](https://user-images.githubusercontent.com/22419786/157589772-81d1f05e-3499-4b10-8985-bf9a1b13e191.PNG)

3. Pide unos parámetros (Resultados en formato csv o jtl, el archivo properties del usuario y un directorio de salida donde quedará alojado el reporte

![3](https://user-images.githubusercontent.com/22419786/157589777-9394ec8b-a83a-428b-88a2-33d8a74026d9.PNG)

4. Lo primero que vamos a hacer es crear el archivo de resultados en formato csv o jtl, para esto añadimos un escritor de datos simple desde el receptor 

![4](https://user-images.githubusercontent.com/22419786/157589789-bd7ef363-4f35-4073-bde9-707327306b06.PNG)

5. Ponemos un nombre de archivo 

![5](https://user-images.githubusercontent.com/22419786/157589795-321f35a0-735f-468a-9217-c441fbcb8676.PNG)

6. Aquí ya tenemos uno creado y lo adjuntamos 

![6](https://user-images.githubusercontent.com/22419786/157589803-f30284b4-142f-4633-962e-197ffcf2090b.PNG)

7. Ahora ejecutamos la prueba

![7](https://user-images.githubusercontent.com/22419786/157589809-791922f2-1663-4990-8b3d-7feade21c32a.PNG)

8. Ya con lo resultados, generamos el reporte HTML

![8](https://user-images.githubusercontent.com/22419786/157589815-114eafb3-d0fb-462a-b931-b14bd8dfc26a.PNG)

9. Diligenciamos los parámetros, cabe aclarar que el output directory debe ser una carpeta totalmente vacía,.

![9](https://user-images.githubusercontent.com/22419786/157589822-3986315a-b5fb-4a40-93dc-a826048c6e18.PNG)

10. Hacemos clic en generar y empeiza la generación del reporte

![10](https://user-images.githubusercontent.com/22419786/157589828-a0c66dfe-a794-4a72-a278-3a4c5246e605.PNG)

11. Aparece que se generó correctamente

![11](https://user-images.githubusercontent.com/22419786/157589831-dfae5ffe-95ea-4e30-bd8f-1f572b221dee.PNG)

12. Vamos a la carpeta output creada y vemos los componentes con que quedó.

![12](https://user-images.githubusercontent.com/22419786/157589841-ae8d6563-65ee-41c8-81dc-45cd2307d237.PNG)

13. Al abrir el archivo vemos como es creado el reporte en formato HTML. Vemos el archivo csv utilizado, las fechas y los resultados de nuestros test

![13](https://user-images.githubusercontent.com/22419786/157589849-7a6cd802-8928-46e4-9f7a-1f7e23184fe7.PNG)

14. Estadisticas relacionadas con rendimiento

![14](https://user-images.githubusercontent.com/22419786/157589855-6b6f66b6-17f2-4b2c-bf58-67ff30d2fd3f.PNG)


