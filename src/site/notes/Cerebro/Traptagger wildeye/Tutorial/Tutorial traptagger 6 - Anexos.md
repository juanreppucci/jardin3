---
{"dg-publish":true,"permalink":"/cerebro/traptagger-wildeye/tutorial/tutorial-traptagger-6-anexos/","noteIcon":""}
---

##### Volver a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]

# Anexo I - Lista de tareas a realizar en Traptagger
La siguiente lista tiene como objetivo ser un ayuda memoria y lista de comprobación para poder ir llevando cuenta de los procedimientos realizados y por realizar. Así como evitar olvidarse de partes importantes. 

### Lista de tareas
- [ ] Corroborar fechas en todas las cámaras 
- [ ] Renombrar/acomodar carpetas [[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos#1.2 - Renombrado de archivos\|Enlace]]
- [ ] Importar imágenes [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Enlace]]
- [ ] Ver detecciones estáticas [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Enlace]]
- [ ] Species tag [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Enlace]]
- [ ] Explorar datos para chequear details a ver si hay algo raro [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Enlace]]
- [ ] Chequear vehicles/humans/livestock (usando Launch/species labeling y eligiendo vehicles/humans/livestock) [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#5.3 - Desglose de grupos de especies\|Enlace]]
- [ ] Corroborar GA (usando results/explore)  [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#Corroborar una especie en particular\|Enlace]]
- [ ] Corroborar GP  (usando results/explore) [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#Corroborar una especie en particular\|Enlace]]
- [ ] Ver las imágenes categorizadas cómo "identificarluego"  [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#Corroborar una especie en particular\|Enlace]]
- [ ] AI species check [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#5.3 - Corroboración de IA\|Enlace]]
- [ ] Subir coordenadas [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos#3b1.1 - Coordinates\|Enlace]]
- [ ] corroborar mapa estaciones y coordenadas (ver que estén todas y en su lugar) [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#5.2 - Corroborar coordenadas\|Enlace]]
- [ ] bajar planilla final [[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación#5.4 - Descarga de Planillas Datos\|Enlace]]
- [ ] Enviar planilla a coordinador 24/7 para agregar a base general 




# Anexo II - Filtrado de tiempo de independencia de detecciones

> [!danger] en construccion
> 

> [!NOTE]  Este paso no es necesario pero podría serles de utilidad

 
Al exportar los datos como se vi en la [sección anterior]([[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]) al exportar los datos en formato tabla, Traptagger nos va a importar los datos utilizando por cada línea un "cluster", estos son definidos a través de la IA, y puede pasar que a veces cuando un animal pase mucho tiempo delante de la cámara y por ejemplo se saque 100 fotos, el sistema lo identifique como un cluster 100 fotos, o también puede ser que lo identifique como dos clusters de 20 y 80 fotos cada uno (por decir cualquier ejemplo), o más clusters. 
Esto nos dará como resultados detecciones repetidas, con la única diferencia de la hora, que normalmente será muy pequeña. 
Es común en estos casos en capturas consecutivas utilizar un tiempo de independencia, para evitar las pseudoreplicación. Es muy común utilizar una hora. 
Bajo estas líneas podrán en encontrar un script para R para eliminar las detecciones repetidas de la base de datos. 



```R
## inputs directorio, archivos, etc
inpDir <- "C:/Traptagger"  # nombre del directorio donde guardamos la salida de traptagger
inpFile <- "AGA.csv" # nombre cone el que se nombro la salida de traptagger, ubicada en la carpeta especificada antriormente
outDir <- inPDir


setwd(inpDir)
library(camtrapR)  
# ANTES DE CARGAR LOS DATOS CONVERTIR CUALQUIER DATO QUE TENGA CAPURA A LAS 0:00 A 0:01 O 23:59 POR QUE SINO, 
# NO TOMA LA FECHA, QUIZAS HACER UN SCRIPT QUE CAMBIE AL AZAR
data<-read.csv(inpFile) 
head(data)

#convertir a formato fecha hora los datos
class(data$timestamp)
data$timestamp[3]  # Ref 1
data$timestamp<-strptime(data$timestamp, format = "%Y-%m-%d %H:%M:%S", tz = "America/Argentina/Jujuy")  # el argumento "format" puede necesitar ajustarse si se manipularon los datos o Traptagger lo cambia
class(data$timestamp)
data$timestamp[3] # Si funciono sin cambiar el argumento mencionado arriba esta línea debería ser igual a la de mas arriba marcada como "Ref 1" 

# creacion de recordtable con independencia de 60 min


filt<-filterRecordTable ( recordTable = data, 
                          minDeltaTime = 60,
                          stationCol = "site",
                          speciesCol = "cluster_labels",
                          recordDateTimeCol = "timestamp",
                          deltaTimeComparedTo = "lastIndependentRecord",
                          timeZone =  "America/Argentina/Jujuy",
                          removeDuplicateRecords = TRUE,
                          writecsv = TRUE,
                          outDir = outDir
)

# listo, se guardo un csv en la misma carpeta donde estaba el archivo exportado de traptagger


```