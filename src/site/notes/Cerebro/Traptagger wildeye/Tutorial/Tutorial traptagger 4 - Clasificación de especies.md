---
{"dg-publish":true,"permalink":"/Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies/","noteIcon":""}
---

##### Ir a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexos\|Tutorial traptagger 6 - Anexos]]
# 4a - Clasificación de especies
Una vez creado el nuevo Annotation Set, aparecerán a la derecha del survey nuevos botones.
![Pasted image 20240905121505.png](/img/user/Imagenes/Pasted%20image%2020240905121505.png)

## 4a.1 - Details
En details podemos ver el avance de la aplicación de los labels. Es importante corroborar esto par ver si aparecen cosas raras, o nos falta hacer algo. Ya vamos a ampliar en esto. 
## 4a.2 - Launch 
Inicia el clasificador de imágenes. 
## 4a.3 - Edit
Permite modificar los labels que se usarán en el Annotation Set.
## 4a.4 - Results
En esta sección podemos ver los resultados, corroborar datos, bajar las fotos, planillas, etc. Veremos esta parte más adelante.
## 4a.5 - Delete
Este botón borrará el Annotation Set.

# 4b - Procedimiento de identificación de especies
Luego de presionar "Launch" nos aparecera una nueva pantalla, como se ve a continuación:
![Pasted image 20240905122114.png](/img/user/Imagenes/Pasted%20image%2020240905122114.png)
 
En esta ventana hay varias opciones en las pestañas, pero como aún no se comenzó con la identificación, por ahora solo tenemos habilitada la primera. Podemos grupos de fotos (cluster) queremos ver en esta sesión, es recomendable dejarlo en 200.

Un cluster es un grupo de imágenes que la IA identifica como un evento, en general corresponde al número de imágenes que la trampa cámara toma por evento de detección, pero hay casos que la IA agrupa más fotos dentro de un cluster, por ejemplo en los casos que el animal se queda mucho tiempo frente a la cámara. 

Presionar "Launch". El sistema necesitará unos minutos (u horas dependiendo de la cantidad) para compilar las imágenes, mientras tanto podra leerse "innitiating" debajo del nombre del Annotation Set. Cuando esté listo en la sección Surveys de TrapTagger podremos ver esto en nuesto Survey creado
![Pasted image 20240905180158.png](/img/user/Imagenes/Pasted%20image%2020240905180158.png)

Se puede ver una barra de avance y nos muestra en número de Clusters que nos faltan identicicar. Presionamos la flechita y nos llevará a la pestania "Jobs", en esta pestaña están todos los trabajos que nos quedan por hacer.  Presionamos "Take Job" en nuestro survey y nos aparecerá la siguiente ventana:
![Pasted image 20240905180548.png](/img/user/Imagenes/Pasted%20image%2020240905180548.png)
Es una ventana similar a la de las detecciones falsas, donde podemos ver la primer foto del cluster, bajo la foto se ven los circulitos que indican la cantidad de fotos (en este caso el cluster tiene seis fotos), clickeando en los circulos se pueden ver las otras fotos, así como usando las flechas del teclado o los botones correspondientes.
A la derecha verán una larga lista de botones, muchos de estos botones corresponden a las palabras claves (labels) con los que identificaremos las fotos, entre paréntesis esta el nombre de la tecla que puede usarse en lugar de hacer click en el botón (por ejemplo para el label gatoandino es la tecla A). 
Si con la primer imagen ya podemos identificar a la especie, no es necesario ver las otras fotos, solo presionamos la tecla correspondiente a la especia y nos pasará automáticamente al próximo cluster de imágenes. 
Los labels coinciden con los del [Protocolo Programa en el campo 24/7](https://gatoandino.org/wp-content/uploads/2023/12/Protocolo_Programa_En_el_campo_24_7_AGA_V2.4.pdf).
Nótese que se clasificarán todas las especies detectadas, al menos a grupos generales, como aves, reptiles, roedores.  
Una vez que terminamos con este Batch (grupo de 200 clústers) podemos seguir con el próximo, usando el mismo procedimiento desde la pestaña Surveys. 
## Multiples especies en un clúster
Si hubiera mas de una especie en la foto, o cluster, presionamos la tecla "Control" o el botón "Multiple Species (Ctrl)", luego las teclas correspondientes a las especies que identificamos, finalmente presionamos Control otra vez y ya nos pasa a el próximo cluster. 

## Máscaras
Si hubiera muchas detecciones falsas que pensamos son causadas por algo que se mueve siempre en el mismo lugar de la foto, podemos enmascarar esa parte entonces la IA ya no buscará animales en esa parte. Para eso utilizar el botón "Mask Area". 
En la lista de la derecha podrán ver las diferentes especies o grupos de especies con las que podremos clasificar las imágenes. 

## Clústers sin animales
En el caso de que la imagen no tenga ningún animal (corroborar en todas las imágenes del cluster), se puede clasificar como que no tiene nada, presionando la tecla N, o el botón "Nothing (N)".

## Cámara caída
La tecla Q o botón "Knoked Down (Q)" indicará que la cámara trampa fue volteada y ya no esta muestreando, por lo que le pondrá este label a esa y todas las imágenes siguientes de esa cámara trampa. 

## Clústers no idintificables
Si detectamos que hay un animal, pero no podemos identificar de que se trata, le colocamos el label "Unknown" presionando la tecla U o el botón correspondiente. 
Los labels "gato_x" y "zorro_x" son para utilizar para cuando en las fotos identificamos que es un gato o un zorro pero no podemos asegurar la especie. 
El label "identificarluego"  (tecla X) es para cuando como en el caso anterior identificamos que nay un animal y no lo podemos identificar, pero creemos que con ayuda de alguien podríamos identificarlo. Esto permitirá encontrar estas imágenes fácilmente.  

## Guardar cambios
Si tenemos muchas cluster y queremos terminar este trabajo en otro momento, podemos presionar "Save & Exit" para guardar el avance y salir. Podemos retomar la tarea en otro momento. 

## Agregar comentarios
A cada cluster se le pueden agregar comentarios relevantes, presionando enter y escribiendo los mismos en la ventana emergente.  Algunos recomendables son, el número de individuos en el caso que sean mas de uno, precencia de cachorros, o si una foto esta buena y pude ser usada para difusión (usando la palabra "buena" o "muy buena").

## Mejorar la imagen
En algunos casos se va a complicar identificar la especie con la imagen tal cual salió de la cámara, para realizar algunas mejoras, podemos usar las siguientes herramientas:
Zoom: Poniendo el puntero sobre la imagen y girando la rueda del mouse

- Delete o [ : Disminuir brillo 
- Insert o ]: Incrementar brillo. 
- End or ;: Disminuir contraste.
- Home or ': Aumentar contraste.
- PageDown or <: Disminuir saturación.
- PageUp or >: Aumentar saturación.
- Backspace or /: Volver a la brillo, contraste y saturación original de la imagen.

## Cartel "Alert"
En algunos casos cuando estamos etiquetando fotos nos sale el siguiente cartel:

![Clipboard_03-17-2025_01.jpg](/img/user/Imagenes/Clipboard_03-17-2025_01.jpg)

El cuál nos avisa que es posible que además del animal que estamos viendo en la foto, puede haber alguno más en otras fotos del clúster por lo que es conveniente mirarlas. Para poder continuar hay que cerrar el cuadro emergente (presionando "Close" o las teclas de flecha hacia la derecha) revisar las siguientes imágenes y etiquetar a la/las especies correspondientes con normalidad. 



[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]