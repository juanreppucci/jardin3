---
{"dg-publish":true,"permalink":"/Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación (1)/","noteIcon":""}
---

##### Volver a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]

# 5 - Acciones post clasificación
Luego de clasificar todos los clusters, hay varias tareas que debemos realizar, algunas son obligatorias, otras optativas pero deseables. 

## 5.1 - Explorar datos
Es bueno dar una mirada a los datos en general para encontrar potenciales errores. Para esto, detro del en el que estemos trabajando, nos dirigimos a la sección donde está el Annotation set en el que trabajamos identificando las especies. Presionamos el botón "Details" y nos va a aparecer una lista de las diferentes especies identificacas, es bueno pegar una buena mirada y ver que ningún dato nos llame la atención o pareca erróneo. 

Otra forma de explorar los datos en busca de errores es elegir, la opción "Results" del "Annotation set" y luego presioaar "Explore".  Ahi vamos a poder ver cada sitio de muestreo, especie y utilizar los diferentes filtros. También podemos editar las especies identificadas, esto es importante en caso de errores o si, por ejemplo, si habíamos guardado imágenes para identificar luego (usando el label "identificarluego") con esta opcion podemos filtrar estas imágenes y asignarlas a la especie adecuada. 


> [!warning] Corroborar
> Este es un buen momento para corroborar las especies de las fotos con dudas, por ejemplo las que les pusimos "labels" como: identificarluego, gato_X, zorro_X
>


También puede ser útil ver un mapa de los sitios de muestreo y las localizaciones de las capturas de las diferentes especies. Para esto dentro de "Results", elegir "Statistical tools", luego en el menú desplegable elegir "Spatial analysis", con esto podremos ver la ubicación de los sitos de muestreo sobre una imagen satelital y a la izquierda podemos filtrar por tipo de datos, tiempo, especies. Esto también podría ser útil para explorar los datos en busca de errores. 

## 5.2 - Corroborar coordenadas
Este paso puede hacerse antes o después de la clasificación de especies. Si ya se cargaron coordenadas y luego se agrega un sitio nuevo, pueden agregarse las coordenadas luego. 
Para agregar las coordenadas a cada sitio ir a la pestaña "Surveys", en la parte izquierda del Survey que queremos editar (la derecha serían las propiedades de los "Annotation sets"). Seleccionar "Edit" la primer pestaña es "Coordinates". 
Para subir las coordenadas de cada sitio hay dos formas: Con la opción "File upload" se puede subir un archivo kml con todos los puntos, hay que tener en cuenta que los nombres de los sitios en este archivo tienen que ser exactamente iguales a los del survey. Si elegimos la opcion "Manual" se pueden agregar las coordenadas manualmente, deben utilizarse grados decimales.
Esta última opción de carga manual, es útil para corroborar que todos los sitios tengan las coordenadas cargadas.  
 
## 5.3 - Corroboración de IA
Si se identificaron especies utilizando IA, hay una serie de pasos que deberían realizarse. Si hay datos catalogados como "Vehicles/humans/livestock" debemos desglosar esta categoría en las correspondientes. Para esto proceder como cuando identificamos las especies a nivel general, pero en "Species labeling", en la sección "Annotation level" seleccionar "Vehicles/humans/livestock" y proceder a la identificación de esta categoría. 

Otro paso importante si se utilizó IA para identificar especies es el "AI species check", el sistema nos va a mostar imágenes donde no está de acuerdo con nuestra identificación o tenga un bajo nivel de certeza en la identificación. Este paso no lo voy a explicar por que aún no tenemos IA entrenada para nuestras especies, por lo que si elegimos "MegaDetector" como clasificador de especies, como se recomendó, sólo tendremos que corroborar la categoría "Vehicles/humans/livestock".

## 5.4 - Descarga de Planillas Datos
Una vez que esté todo listo, necesitamos descargar los datos en formato CSV y asi poder sumarlos a la base de datos del programa. Para esto, detro del en el que estemos trabajando, nos dirigimos a la sección donde está el Annotation set en el que trabajamos identificando las especies. Presionamos el botón "Results", luego,  bajo el titulo "Generate CSV" presionamos el botón "Generate", que nos permitirá crear un CSV con las características que nosotros nos interese. 

### 5.4.1 - Creación del CSV
Para la base de datos del programa utilizaremos el siguiente estandar: 

En la opción ROW, elegir cluster. 
En label format, elegir rows. 
Date range dejarlo como está.
en "Include/Exclude Species" seleccionar "Exclude" y del menú desplegable seleccionar "Nothing". De esta manera evitamos exportar los falsos disparos (aunque también puede hacerse luego usando alguna planilla de cálculo como Excel). 
La opción "Custom columns" dejarla como está. 


Y la sección de "Columns" debe ser editada para obtener los siguientes datos. Para editar es conveniente editar la columna "Level" y "Data", los nombres en la columna "Name" se generarán automáticamente 


![Pasted image 20240624154522.png](/img/user/Imagenes/Pasted%20image%2020240624154522.png)

Finalmente presionar "Download", este proceso puede tomar varios minutos/horas. Una vez que la descarga este disponible, la vamos a encontrar en la barra principal de la página arriba a la derecha. 


> [!danger] ¡Último paso!
> Una vez desgargada enviar por email, la planilla al coordinador de programa. 
>


ir a [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexo - tiempo de independencia de detecciones\|Tutorial traptagger 6 - Anexo - tiempo de independencia de detecciones]]