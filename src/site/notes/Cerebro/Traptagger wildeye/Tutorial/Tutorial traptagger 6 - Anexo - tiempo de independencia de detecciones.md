---
{"dg-publish":true,"permalink":"/Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 6 - Anexo - tiempo de independencia de detecciones/","noteIcon":""}
---

##### Volver a:
[[Cerebro/Traptagger wildeye/Tutorial Traptagger - Índice\|Tutorial Traptagger - Índice]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial Traptagger 1 - Preparación datos\|Tutorial Traptagger 1 - Preparación datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 2 - Subida datos\|Tutorial traptagger 2 - Subida datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 3 - Primer procesado de datos\|Tutorial traptagger 3 - Primer procesado de datos]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 4 - Clasificación de especies\|Tutorial traptagger 4 - Clasificación de especies]]
[[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]



> [!danger] en construccion
> 


Al exportar los datos como se vi en la [sección anterior]([[Cerebro/Traptagger wildeye/Tutorial/Tutorial traptagger 5 - Acciones post clasificación\|Tutorial traptagger 5 - Acciones post clasificación]]) al exportar los datos en formato tabla, Traptagger nos va a importar los datos utilizando por cada línea un "cluster", estos son definidos a través de la IA, y puede pasar que a veces cuando un animal pase mucho tiempo delante de la cámara y por ejemplo se saque 100 fotos, el sistema lo identifique como un cluster 100 fotos, o también puede ser que lo identifique como dos clusters de 20 y 80 fotos cada uno (por decir cualquier ejemplo), o más clusters. 
Esto nos dará como resultados detecciónes repetidas, con la única diferencia de la hora, que normalmente será muy pequeña. 
Es común en estos casos en capturas consecutivas utilizar un tiempo de independencia, para evitar las pseudoreplicación. Es muy común utilizar una hora. 
Bajo estas líneas podrán en contrar un script para R para eliminar las detecciones repetidas de la base de datos. 



> [!NOTE] hacer
> adaptar y probar el siguiente script

Primero crear dos columans nuevas al archivo bajado de traptagger y en una extraer la fecha y en otra la hora, nombrarlas "fecha" y "hora" respectivamente

aca esta el script para ir trabajando
c:\24-7\scri.R 

```R
## inputs directorio, archivos, etc
inpDir <- "d:/Documentos mios/W/Tigre/monitoreos_APN/2023/R/"
inpFile <- "d:/Documentos mios/W/Tigre/monitoreos_APN/2023/planillas/de traptagger/cali_bari_23.csv"
outDir <- "d:/Documentos mios/W/Tigre/monitoreos_APN/2023/R/result"


setwd(inpDir)
library(camtrapR)  
# ANTES DE CARGAR LOS DATOS CONVERTIR CUALQUIER DATO QUE TENGA CAPURA A LAS 0:00 A 0:01 O 23:59 POR QUE SINO, 
# NO TOMA LA FECHA, QUIZAS HACER UN SCRIPT QUE CAMBIE AL AZAR
data<-read.csv(inpFile) 
head(data)

#convertir a formato fecha hora los datos
class(data$timestamp)
data$timestamp[3]
data$timestamp<-strptime(data$timestamp, format = "%m/%d/%Y %H:%M", tz = "America/Argentina/Jujuy")
class(data$timestamp)
data$timestamp[3]

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

```