---
{"dg-publish":true,"permalink":"/cerebro/traptagger-wildeye/tutorial/tutorial-traptagger-3-primer-procesado-de-datos-1/","noteIcon":""}
---


##### Volver a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]

# 3a - Primer procesado de datos
Una vez que los datos estén subidos completamente al servidor, podremos ver en que estado de procesamiento están. Esta informacion se encuentra en la solapa "Surveys" y dentro del la sección de Survey que creamos esta esta información debajo del nombre del survey, bajo el título "Status", en el ejemplo siguiente las imágenes se están importando (importing), después pasa por otros estados como "Identifying".

![Pasted image 20240904172014.png](/img/user/Imagenes/Pasted%20image%2020240904172014.png)

Este proceso puede tardar bastante tiempo dependiendo del tamaña del set de datos subidos. Puede superar las 24 horas.

En este primer procesado vamos editar el Survey, agregar algunos datos, arreglar otros si fuera necesario e indentificar zonas de falsas detecciones recurrentes. Estas ocurren generalmente por alguna planta o algo que se mueve frente a la cámara dejando ver algo de diferente temperatura por detras de la misma causando falsos disparos de la trampa cámara, alguna roca que la inteligencia artificial identifica como un posible animal. 

Una vez que las fotos esten listas, se podra ver que el Status dice "Ready", luego de esto pueden pasar dos cosas. Y estas son los ejemplos de las pantallas que aparecerán. 

Caso 1:
![Pasted image 20240905101456.png](/img/user/Imagenes/Pasted%20image%2020240905101456.png)

Caso 2:
![Pasted image 20240905101518.png](/img/user/Imagenes/Pasted%20image%2020240905101518.png)

En el Caso 1, no hay que hacer nada se puee empezar a editar el survey y crear el "Annotation set", que es la forma en la que identificamos las fotos y clasificamos su contenido. 

En el Caso 2, la IA (Inteligencia Articial) detectó que hay muchas detecciones estáticas por lo que nos da la oportunidad de revisarlas, esto sucede cuando la IA detecta siempre algo en el mismo lugar, quieto, por lo que sospecha que puede ser una detección falsa. Estas detecciones suelen ser rocas, plantas, o en algunos casos son animales que les gusta pararse mucho en cierto lugar, loque le parece sospechoso a la IA, y nos da la oportunidad de corroborar (en el caso de la foto de abajo, es una viscacha que se para siempre en la misma piedra). Esto nos va a ayudar posteriormente en la identificacion de fotos, quitándonos falsas detecciones.  
Para esto, presionamos "Launch", y va a abrir una ventana nueva, abajo puede verse un ejemplo con indicaciones en amarillo. 

![screen_traptagger.jpg](/img/user/Imagenes/screen_traptagger.jpg)
En el centro de la página podemos ver el grupo de fotos que se considera detectaron la misma cosa, como una detección falsa, de este grupo se ve la primera foto, par pasar a las demás se pueden presionar las fechas (derecha e izquierda), resionar los número que estan debajo de la foto (1) o los botones "< Previous Image" y "Next Image >". Puede verse también el total de fotos que forman esta grupo de potenciales falsas detecciones. En el ejemplo son 75. 
Dentro de la foto se ven unos rectángulos naranja que marcan el lugar de la detección (animal o alguna otra cosa en el caso de una detección falsa). A veces como son muchos rectángulos superpuestos es difícil ver que está abajo, si presionamos la barra espaciadora, estos rectángulos desaparecerán mientras se mantenga apretada. 
En la parte baja de la pantalla (2), se puede ver que cantidad de grupos de detecciones falsas, en este caso 4. Esta barra funcionará también para indicarnos el grado de avance en el proceso.
A la derecha (3), hay tres botones ("Accept (A)", "Reject (R)" y "Save and Exit"). 

Para realizar el procedimiento de identificación, lo que tenemos que hacer es revisar los grupos de potenciales falsas detecciones. Para esto, vamos a mirar las fotos (usando las felchas o seleccionando los numeros (1)), y ver si son realmente falsas detecciones o no. Conviene ver una buena cantidad de estas fotos antes de tomar la desición de si es o no una falsa detección. 
Si presionamos "Accept (A)", con el mouse o usando la tecla "A", aceptamos que la detección es falsa, las fotos se marcarán como que no tienen animales y la plataforma no nos las va a mostrar en el proceso de categorización de las imágenes. Por el contrario si rechazamos la falsa detección, (clickeando "Reject (R)" o tecla "R"), le estamos diciendo que no es una falsa detección y nos dará la oportunidad de identificar las detecciones asignandole a que especie pertenece cada imagen o grupo de imágenes. 
Cuando aceptamos o rechazamos la falsa detección, nos mostrará la siguiente para poder evaluarla. En el ejemplo de la foto anterior, rechazaríamos la falsa detección ya que en realidad no lo es sino que son viscachas. 

Si tenemos muchas detecciones y queremos teminar este trabajo en otro momento, podemos presionar "Save & Exit" para guardar el avance y salir. Podemos retomar la tarea en otro momento. 

Una vez que terminemos, el sistema se va a tomar un tiempo para acomodar los datos, esto se denotará por que el Status no va a decir "Ready", dirá por ejemplo "Processing", y los botones van a estar como mas grises y no se van a poder clickear. 

Luego de hacer esta revisión de falsas detecciones, o si el sistema nos dió una pantalla como el Caso 1, lo próximo es editar el Survey. 

# 3b - Edición del Survey
Una vez que subimos las fotos hay varias cosas que pueden ajustarse en el Survey o relevamiento/campaña. En algunos casos el sistema nos va a poner una alerta para hacer primero las detecciones falsas (Caso 2), en el caso que no lo hiciera puede ser que no las hubiera o también lo podemos hacer luego como explicaremos a continuación. 
Si nos apareció una pantalla como el Caso 1 o luego de idnetificación de falsas detecciónes, nos van a aparecer cuatro botones:  "Edit", "Add Files", "Add Annotation Set" y "Delete". 

## 3b.1 - Edit 
Al presionar este botón nos aparecerá una pantalla emergente con deferentes pestañas con diferentes opciones: 
![Pasted image 20240905112228.png](/img/user/Imagenes/Pasted%20image%2020240905112228.png)
### 3b1.1 - Coordinates
En esta sección debemos agregar las coordenadas para cada estación/cámara trampa. Hay dos métodos, uno es el manual, tipeando las coordenadas de cada camara en formato grados decimales o subiendo un archivo kml (que se puede exportar usango Google Earth), este archivo tiene que tener las posiciones de todas las camaras. En esta caso hay que asegurarse de que los nombres coniciden exactamente en la capa (kml Google Earth) y en sistema (carpetas subidas a TrapTagger).
### 3b1.2 - Camera Timestamps
Esta opción nos permitirá arreglar la fecha, y hora e las fotos en el caso de que fuera errónea. Consultar por instrucciones de uso.
### 3b1.3 - File Timestamps
Esta opción se utiliza en casos raros en que el sistema no puede extraer los datos de fecha y hora de las imágenes.
### 3b1.4 - Species Classifier
En esta sección podemos cambiar el tipo de clasificador de especies, en nuestro caso nos vamos a quedar siempre con MegaDetector ya que no hay una IA entrenada en detectar las especies en estudio. MegaDetector diferenciará entre imagenes en blanco, animales, humanos y vehículos, lo cual ya nos ahorará mucho tiempo. 
### 3b1.5 - Advanced Options
En esta sección podremos inidcar a la AI que no detecte animales muy pequeños o que no lo haga en la zona de cielo par evitar detecciones de aves. No vamos a usar estas opciones.  
### 3b1.6 - Masks
Esta opción nos permitirá editar máscaras realizadas durante la indetificación de especies. Estas máscaras nos permiten seleccionar una parte de la imagen, que la AI no evaluará. Por ejemplo usando la máscara para cubrir alguna planta que se esta moviendo y causando disparons en falso, el problema es que podemos perder detecciones de animales que estuvieran en la zona de la máscara. 
### 3b1.7 - Static Detections
Esta sección nos permitira evaluar las detecciones estáticas, como ya se explicó antes en este documento. 
### 3b1.8 - Structure
En esta sección podemos ver la estructura de carpetas que detectó TrapTagger, _es bueno corroborar esta estructura_ para ver si el sistema detecto bien las diferentes estaciones/sitios de muestreo y las cámaras trampa. 

## 3b.2 - Add Files
El botón "Add Files", nos permitirá agregar más imágene al Survey, de manera similar a la subida de imágenes inicial. 

## 3b.3 - Add Annotation Set 
Cada Survey puede tener diferentes conjuntos de anotaciones (o Annotation Sets), esta opcion de agregar mas de uno, sirve por ejemplo, para comparar la identificación por diferentes usuarios. En nuestro caso, en general vamos a usar uno solo, pero está la opción de hacer uno como para familiarizarse con el sistema y luego hacer el definitivo.
Al presionar "Add Annotation Set" nos aparece una ventana emergente. Primero tenemos que elegir un nombre para el Set, esta bueno que sea algo informativo, como el nombre de la persona que va a realizar la identificación. 
Debajo elegimos "New Annotation Set".
En "Load Labels" elegimos "" del menú desplegable, y luego elegir la versión más alta de los labels del nuevo que aparece (labels_AGA_3 en el ejemplo).

![Pasted image 20240905120055.png](/img/user/Imagenes/Pasted%20image%2020240905120055.png)

Los labels es el conjuto de palabras clave que se van a usar para clasificar las imagenes del survey, cada palabra clave corresponde generalmente a una especie o grupo de especies. 
Como se ve en la captura de pantalla de arriba, cada label tiene el nombre de una especie y a la derecha puede verse la tecla que corresponderá a éste Label. No se preocupen en recordad/anotar esto ahora, ya que lo tendrán disponible al momento de clasificar las imágenes. 
Presionar "Next", en la parte mas baja de la ventana y aparecerá esta ventana:
![Pasted image 20240905120800.png](/img/user/Imagenes/Pasted%20image%2020240905120800.png)

"animal" dejarlo como está (seleccionaremos nosotros que especie son) y en "human" seleccionen "vehicles/humans/livestock". Después vamos a clasificar esto también pero a veces es cómodo que el sistema ya nos haga una preclasificación.
Presionar "Next", y aparecerá esta pantalla, en la cual seleccionaremos las opciones como se ve en la imagen: 

![Pasted image 20240905121034.png](/img/user/Imagenes/Pasted%20image%2020240905121034.png)

Presionar "Submit" y se habrá creado el "Annotation Set"
## 3b.4 - Delete
Este botón borrará el Survey.


[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]


