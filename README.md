# Metodologias
Readme metodologias
En este trabajo se analizaro datos demográficos para evaluar los posibles efectos de la instalación de centrales hidroeléctricas en 3 comunas de la octava región del Biobío
Estas comunas son: Santa Bárbara, Quilaco, Alto Biobío. 
Las 3 centrales hidroeléctricas se encuentran instaladas en el río Biobío

En primer lugar se procede a limpiar los archivos en R-Studio. Para este trabajo utilizaremos los datos otorgados por el Instituto Nacional de estadísticas (INE) 
especificamente el REDATAM
para esto se requiere cargar los paquetes 
library(tidyverse)
library(readr) 
library(readxl) 

posterior a esto se leen los archivos .xlsx
se limpian los archivos para que queden en un buen formato linea-columna
ejemplo: 
#evolucion poblacional
evolucion_1970_2017 <- read_excel("Metodologias_Demografia-Hidroelectricas - copia/evolucion-demografica-censal-segun-area-de-estimacion-censos-1970-2017.xlsx", skip = 6)
colnames(evolucion_1970_2017)[1:25] <- c(
  "territorio",
  "poblacion1970_total", "poblacion1970_urbano", "poblacion1970_rural", "%urbano_1970",
  "poblacion1982_total", "poblacion1982_urbano", "poblacion1982_rural", "%urbano_1982",
  "poblacion1992_total", "poblacion1992_urbano", "poblacion1992_rural", "%urbano_1992",
  "poblacion2002_total", "poblacion2002_urbano", "poblacion2002_rural", "%urbano_2002",
  "poblacion2017_total", "poblacion2017_urbano", "poblacion2017_rural", "%urbano_2017",
  "%crec_1982/1970", "%crec_1992/1982", "%crec_2002/1992", "%crec_2017/2002")
evolucion_1970_2017<- head(evolucion_1970_2017,-6)

con esto, a los dataset le quedan las columnas con nombres que nosotros le asignamos y se pueden elegir las variables mas facilmente
los nombres quedaron:
evolucion_1970_2017 : variables de poblacion y vivienda desde el 1970 en adelante
poblacion_1992_2017: comparaciones entre censos de 1992, 2002 y 2017
proyecciones2002_2020: proyecciones hechas en el censo 2002
ocupacion2017 : tipos de ocupaciones 2017
censo2002_situacion_laboral: también para comparar oicupaciones pero del 2002

despues se hacen las selecciones de las 3 comunas para despues comparar en el informe
se hace con el modulo%<%

se calculan promedios tanto de las 3 comunas como de la region
se escriben los archivos con un write.csv para poder exportarlos a python y graficar



Pasamos a python
graficamos con ayuda del chatgpt dandole las indicaciones mediante las instrucciones de los modulos entregados en clase
