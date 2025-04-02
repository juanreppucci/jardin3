---
{"dg-publish":true,"permalink":"/Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación/","noteIcon":""}
---

##### Ir a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexos\|Tutorial traptagger 6 - Anexos]]
# 5 - Acciones post clasificación
Luego de clasificar todos los clusters, hay varias tareas que debemos realizar, algunas son obligatorias, otras optativas pero deseables. 

## 5.1 - Coordenadas
### Subir coordenadas
Este paso puede hacerse antes o después de la clasificación de especies. Si ya se cargaron coordenadas y luego se agrega un sitio nuevo, pueden agregarse las coordenadas luego. 
Para agregar las coordenadas a cada sitio ir a la pestaña "Surveys", en la parte izquierda del Survey que queremos editar (la derecha serían las propiedades de los "Annotation sets"). Seleccionar "Edit" la primer pestaña es "Coordinates". 
Para subir las coordenadas de cada sitio hay dos formas: Con la opción "File upload" se puede subir un archivo kml con todos los puntos, hay que tener en cuenta que los nombres de los sitios en este archivo tienen que ser exactamente iguales a los del survey. Si elegimos la opcion "Manual" se pueden agregar las coordenadas manualmente, deben utilizarse grados decimales.
Esta última opción de carga manual, es útil para corroborar que todos los sitios tengan las coordenadas cargadas.  
### Corroborar coordenadas
Para corroborar si las coordenadas fueron incorporadas correctamente es una buena práctica mirar el mapa. Para esto nos dirigimos a la pestaña "Surveys" y ahi presionamos el botón "Results" en el panel derecho del Survey en el que estamos trabajando. En la ventana emergente cliqueamos "View" bajo el título "Statistical Tools".  Aparecerá una nueva ventana donde elegiremos "Spatial tools" del menú desplegable. AL hacer esto, aparecerá el mapa con las ubicaciones de los sitios de muestreo. Tambien pueden elegirse especies a la derecha y nos calculará un nube de probabilidad, basada en las detecciones de dicha especie. 
## 5.2 - Explorar datos
Es bueno dar una mirada a los datos en general para encontrar potenciales errores. Para esto, detro del en el que estemos trabajando, nos dirigimos a la sección donde está el Annotation set en el que trabajamos identificando las especies. Presionamos el botón "Details" y nos va a aparecer una lista de las diferentes especies identificadas, es bueno pegar una buena mirada y ver que ningún dato nos llame la atención o parezca erróneo. 

Otra forma de explorar los datos en busca de errores es elegir, la opción "Results" del "Annotation set" y luego presionar "Explore".  Ahi vamos a poder ver cada sitio de muestreo, especie y utilizar los diferentes filtros. También podemos editar las especies identificadas, esto es importante en caso de errores o si, por ejemplo, si habíamos guardado imágenes para identificar luego (usando el label "identificarluego") con esta opcion podemos filtrar estas imágenes y asignarlas a la especie adecuada. 


> [!warning] Corroborar
> Este es un buen momento para corroborar las especies de las fotos con dudas, por ejemplo las que les pusimos "labels" como: identificarluego, gato_X, zorro_X
>


También puede ser útil ver un mapa de los sitios de muestreo y las localizaciones de las capturas de las diferentes especies. Para esto dentro de "Results", elegir "Statistical tools", luego en el menú desplegable elegir "Spatial analysis", con esto podremos ver la ubicación de los sitos de muestreo sobre una imagen satelital y a la izquierda podemos filtrar por tipo de datos, tiempo, especies. Esto también podría ser útil para explorar los datos en busca de errores. 

### Corroborar una especie en particular
Para corroborar un grupo todos los clusters asignados a una categoria o especie (ya sea por nosotros la IA), podemos dirigirnos  Para esto nos dirigimos a la pestaña "Surveys" y ahi presionamos el botón "Results" en el panel derecho del Survey en el que estamos trabajando. En la ventana emergente cliqueamos "Explore". Una vez que se abre la nueva ventana es importante esperar sin tocar ninguna de las opciones hasta que aparezca la primer imagen, esto debe repetirse para todos los cambios que se realicen en los filtros ("Filters" sección a la derecha). 
Para corroborar por ejemplo las fotos de gato andino, en la sección "Filters" seleccionamos gatoandino de las opciones desplegables del campo "Species". Esto nos va a mostrar todos los clusters categorizados como gatoandino, pueden utilizarse los filtros de más abajo para filtrar cosas más específicas, por ejemplo los gatos andinos identificados por la IA (seleccionando AI en el filtro "Annotator") o de una particular sitio de muestreo, usando el filtro "Site". 
Los filtros pueden combinarse, como se mencionó con anterioridad, es importante esperar a que aparezca la primer foto luego de cambiar cada uno.

## 5.3 - Desglose de grupos de especies
Si se identificaron especies utilizando IA, hay una serie de pasos que deberían realizarse. Si hay datos catalogados como "Vehicles/humans/livestock" debemos desglosar esta categoría en las correspondientes. Para esto proceder como cuando identificamos las especies a nivel general, pero en "Species labeling", en la sección "Annotation level" seleccionar "Vehicles/humans/livestock" y proceder a la identificación de esta categoría.  

## 5.4 Corroboración de IA
Otro paso importante si se utilizó IA para identificar especies es el "AI species check". Para eso nos dirigimos a la sección "Surveys" y presionamos "Launch" y seleccionamos la pestaña "AI species check" y luego el botón de abajo "Lauch".

Una vez que el sistema recopile los datos nos aparecerá el trabajo disponible en la sección "Jobs".   Presionando la flechita nos abrirá una nueva ventana que nos va a mostrar las imágenes donde la IA no está de acuerdo con nuestra identificación o tenga un bajo nivel de certeza en la identificación. Arriba de la primer imagen del cluster, nos indica a la izquierda, el label que le pusimos nosotros y a la derecha lo que "piensa" la IA con su nivel de seguridad en percentage. Para cada cluster debemos elegir una de las opciones a la derecha (o su respectivo atajo de teclado) para pasar al siguiente clúster hasta el final. Las opciones son:

_accept_ acepta lo que dice la AI (lo que esta arriba a la derecha de la foto), deja el puesto por el usuario (quedan los dos)
_reject_  deja como estaba (queda solo el puesto por el usuario)
_overwrite_ pone el sugerido por la AI en lugar del puesto por el usuario
_other_ te permite poner cualquier otra especie



## 5.5 Descarga de Planillas Datos
Una vez que esté todo listo, necesitamos descargar los datos en formato CSV y así poder sumarlos a la base de datos del programa. Para esto, dentro del en el que estemos trabajando, nos dirigimos a la sección donde está el Annotation set en el que trabajamos identificando las especies. Presionamos el botón "Results", luego,  bajo el titulo "Generate CSV" presionamos el botón "Generate", que nos permitirá crear un CSV con las características que nosotros nos interese. 

### 5.5.1 - Creación del CSV
Para la base de datos del programa utilizaremos el siguiente estándar: 

En la opción ROW, elegir cluster. 
En label format, elegir rows. 
Date range dejarlo como está.
en "Include/Exclude Species" seleccionar "Exclude" y del menú desplegable seleccionar "Nothing". De esta manera evitamos exportar los falsos disparos (aunque también puede hacerse luego usando alguna planilla de cálculo como Excel). 
La opción "Custom columns" dejarla como está. 


Y la sección de "Columns" debe ser editada para obtener los siguientes datos. Para editar es conveniente editar la columna "Level" y "Data", los nombres en la columna "Name" se generarán automáticamente 


![Pasted image 20240624154522.png](/img/user/Imagenes/Pasted%20image%2020240624154522.png)
El documento a exportar tendrá 12 columnas.

Finalmente presionar "Download", este proceso puede tomar varios minutos/horas. Una vez que la descarga este disponible, la vamos a encontrar en la barra principal de la página arriba a la derecha. 


> [!danger] ¡Último paso!
> Una vez desgargada enviar por email, la planilla al coordinador de programa. 
>


ir a [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexos\|Tutorial traptagger 6 - Anexos]]