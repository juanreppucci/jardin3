---
{"dg-publish":true,"permalink":"/Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos/","noteIcon":""}
---


> [!danger] Aclaración
> Traptagger es una plataforma que se encuentra en continua evolución y cambio. Nuevos procedimientos y funciones son agregadas con regularidad. Esto ocaciona que la platafoma cambie, por lo que en algunos casos estas instrucciones pueden variar con lo que encontramos en la página. Ante cualqueir duda consulta la ayuda de la página en cuestión (botón "help" hubicado arriba a la derecha) o contactarme vía **email** al juanreppucci@gmail.com 

# Índice
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexos\|Tutorial traptagger 6 - Anexos]]


> [!NOTE] Ayuda memoria
> En el [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexos#Anexo I - Lista de tareas a realizar en Traptagger\|Anexo I]] podrán encontrar una Lista de tareas a realizar, la cual les puede servir de guía y ayuda memoria para completar el proceso completo. En la lista están los enlaces a las secciones a donde se describe el paso a realizar. 

# 1 - Preparación de datos para importar a Traptagger


 Primero que nada hay que tener toda la información bien organizada, para recién poder iniciar la subida de datos a la plataforma. 
Los datos tienen que estar organizados en carpetas, el primer nivel sería una carpeta con el nombre del relevamiento o área de muestreo (p.ej. Pucasaya2023). Sinceramente no se si afecta, pero una buena norma general al nombrar archivos o carpetas es no usar nombres largos, ni espacios, ni signos raros (preferiblemente limitarse a guion y guion bajo), de esta manera maximizamos la compatibilidad. Para el ejemplo anterior otras opciones podrían ser: Puca_23, Pucasaya-2023, etc. 
Dentro de esta carpeta se encontrarán las subcarpetas correspondientes a las estaciones de muestreo, estas tienen que nombrarse todas con el mismo prefijo seguido de un número. Siguiendo el ejemplo anterior podría ser: PUCA1, PUCA2... o P1, P2... PU1, PU2... etc. No pueden usarse más texto después del número, ya que no sería reconocido (por ejemplo el caso PUCA2B no sería válido). 
Dentro de la carpeta de estación se colocará una carpeta para cada cámara que tenga la estación, utilizando siempre la misma estructura de nombres: CAM1, CAM2, etc.

En el siguiente ejemplo se detalla un relevamiento en Pucasaya, con dos estaciones de muestreo llamadas PUCA1 y PUCA2, donde la primer estación tiene una sola trampa cámara y la segunda dos.
```
Pucasaya_2023
	PUCA1
		CAM1
			1.jpg
			2.jpg
			3.jpg
			...
	PUCA2
		CAM1
			1.jpg
			2.jpg
			3.jpg
			...
		CAM2
			1.jpg
			2.jpg
			3.jpg
			...

```


Para tener un mejor orden de los datos y evitar tener archivos con los mismos nombres es recomendable renombrar todas las imágenes. A veces cuando descargamos las tarjetas obtenemos algo como el siguiente ejemplo (siguiendo la nomenclatura el ejemplo anterior), donde la tarjeta de la estación de muestreo PUCA1, tenía cuatro carpetas, cada una con muchas imágenes.   

```
Pucasaya_2023
	PUCA1
		CAM1
			103EK113\
			102EK113\
			101EK113\
			100EK113\
```

## 1.2 - Renombrado de archivos 
En muchos casos estas carpetas tienen imágenes con nombres que se repiten con las carpetas hermanas, así que no sería posible unir todas las fotos en una sola carpeta como en el primer ejemplo. Para poder hacerlo necesitamos renombrar los archivos (las fotos o videos). Esto puede hacerse de muchas maneras y con diferentes programas (Bridge, Lightroom, Total Commander, Acdsee, FastStone, Exiftool, R, Camera Sweet, etc), yo recomiendo ExifPRo 2.1 (que puede descargarse de la sección ["recursos/software recomendado"](https://sites.google.com/view/guia-reporte-campanas/recursos) de la página de instrucciones de informes del programa *En el Campo 24/7*), pueden ver el procedimiento [en este enlace]([[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos#Renombrado con ExifPro 2.1\|Tutorial Traptagger 1 - Preparación datos#Renombrado con ExifPro 2.1]]). Para el caso de los videos habría que hacerlos con Adeobe Bridge (también disponible en la sección ["recursos/software recomendado"](https://sites.google.com/view/guia-reporte-campanas/recursos) y en [este enlace](https://www.youtube.com/watch?v=nPruj8_gOqE) hay un ejemplo de uso (bastaría adaptarlo al formato que se detalla continuación). Estos programas se van a valer de los metadatos  contenidos en la imagen para generar un nombre con cierta información.

Pero al idea sería renombrar cada archivo siguiendo el siguiente formato. 
```
para estaciones con una sola cámara:
[Estacion]_[Y.M.D]_[H:M]_[N]
Ejemplo PUCA1_2023.03.1_23:43_11120620.JPG 

Para estaciones con más de uan cámara:
[Estacion]_[cam]_[Y.M.D]_[H:M]_[N]
Ejemplo PUCA2_CAM1_2023.03.1_23:43_11120620.JPG
```

es decir, nombre de la estación _ nombre de la cámara (en los casos que son más de una por estación) _ fecha (en formato, año.día.mes) _ hora _ nombre original del archivo.
Una vez renombrado, cada archivo tendrá un nombre único y podremos guardarlos todos juntos en la carpeta indicada sin problemas de duplicados. 

### 1.2.1 - Alternativa
Si esto les parece muy complicado pueden subirse las imágenes manteniendo una estructura como esta:
```
Pucasaya_2023
	PUCA1
		CAM1
			103EK113\
			102EK113\
			101EK113\
			100EK113\
```

Siendo obligatorias las primeras tres carpetas, y las mas interiores podrian tener cualquier otro nombre. Esto es menos ordenado y posiblemente tendríamos muchas fotos con nombres duplicados, pero el sistema deberían interpretarlo de todos modos. Con el método recomendado tendremos en la imagen mucha mas información y menos posibilidades de errores. 

### 1.2.2 - Consideraciones finales

Es importante que antes de comenzar con este procedimiento (sea o no con el método recomendado), se haya realizado previamente una copia de respaldo de todos los archivos.  

Es importante asegurarse de que la organización de imágenes/videos y carpetas esta hecha correctamente, si no estamos seguros de algo, por ejemplo el nombre de una estación, es conveniente dejar esa carpeta aparte y recién subirla cuando ya estemos seguros, ya que una vez cargados los archivos no puede modificarse la estructura. 


### 1.2.3 - Renombrado con ExifPro 2.1
Una vez abierto el programa, utilizando el arbol de carpetas de la izquierda navegamos hasta la carpeta que contiene los archivos que queremos renombrar. Cuando abrimos la carpeta, en la parte inferior derecha va a decir el progreso del programa en leer el contenido de la carpeta, en algunos casos vamos a trabajar con carpetas de casi 1000 fotos por lo que puede tardar un rato. Cuando ya no diga "scanning" va a aparecer el número de imágenes en la carpeta y la cantidad que tenemos seleccionada. Seleccionamos a todas las imágenes con la opción en el menú "edit" (o atajo de teclado CTRL + A). Corroboramos que estén todas seleccionadas en la parte inferior derecha y abrimos el menú "Tools" y elegimos la opción "Rename Images" (o atajo de teclado CTRL + K). De la ventana emergente en la primer pestaña, en la parte derecha pueden ir previsualizando como cambiaría el nombre de acuerdo a las especificaciones que indicamos. Por ejemplo para una imagen tomada por la CAM1 en la estación de muestreo PUCA2, tenemos que indicar los siguientes parámetros en el campo en el campo "Rename pattern"  

PUCA_CAM1_%Y.%m.%d_%H.%M_%f (pueden copiar y pegar e ir modificando la parte que de los nombres de la estación y cámara)

En la parte de la derecha pueden ver que el resultado será:
PUCA2_CAM1_2023.03.1_23:43_11120620.JPG

Abajo a la derecha presionan "Rename" y listo.

Deben repetir esta tarea para cada carpeta, para poder juntar las imágenes de manera ordenada para su carga en Traptagger. 


##### Ir a [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]

