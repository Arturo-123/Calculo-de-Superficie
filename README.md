# Calculo-de-Superficie
	Cálculo de Superficie para la Producción de Plátano con Imágenes Satelitales

Arturo Benito Angulo Silva (1), Ricardo Javier Montes (2), Cielo Jazziris Campos Garcia (3)
 (1) Universidad de Colima, Campus Coquimatlán, 28400, aangulo1@ucol.mx (2) ccampos@ucol.mx
Resumen
En este proyecto se pretende realizar un estu-dio acerca de los puntos estratégicos para el plantío de plátanos, que, en el municipio de Tecomán, Colima se exporta una gran cantidad de estos, con las herramientas que hasta ahora tenemos en las materias de Cartografía Digital y Programación de computadoras.
Palabras clave: Plantío, Cartografía, Exportación 
Resumen
En este proyecto se pretende realizar un estu-dio acerca de los puntos estratégicos para el plantío de plátanos, que, en el municipio de Tecomán, Colima se exporta una gran cantidad de estos, con las herramientas que hasta ahora tenemos en las materias de Cartografía Digital y Programación de computadoras.
Palabras clave: Plantío, Cartografía, Exportación number of these are exported, with the tools we have so far in the areas of Digital Cartography and Computer Programming.
Keywords: Planting, Cartography, Export 
1. 	Introducción
Se pretende realizar con ayuda de imágenes satelitales conocer puntos estratégicos para el cultivo de plátanos, enfocándonos en Tecoman, Manzanillo y Armería, con la finalidad de cono-cer los diferentes tipos que se maneja en el estado de Colima.
![palabrasdeTextoAlternativo](https://github.com/Arturo-123/Calculo-de-Superficie/blob/master/poster.jpg)
2. 	Desarrollo
Dentro de este trabajo se realizó un estudio de las zonas plataneras que hay en el estado de Colima, en los municipios de Tecoman, Armería y Manzanillo, con la ayuda de imágenes sateli-tales, que proporciona el INEGI. Este trabajo se hará en la librería de GDAL es una biblioteca de software para la lectura y escritura de formatos de datos geoespaciales, publicada bajo la MIT License por la fundación geoespacial de código abierto.
2.1. 	Metodología
Se desarrolló una investigación (González-Rodríguez, M.S. Escalona-Maurice, M.J. ; Her-nández-Juárez, M. ; Figueroa-Rodríguez, O.L. ; Caamal-Cauich, I.2, 2017) “en Tecomán Coli-ma, México, el cual está ubicado en la porción sureste del estado (103° 59’ a 103° 73’ O y 18° 41’ 20’’ a 19° 06’ N) (INAFED, 2017). En este municipio, los principales tipos de cultivos son perennes y en menor grado cíclicos, existen 38,308 ha de uso agrícola (INEGI, 2016), y destaca por la producción de Plátano, situándo-se como el principal productor de esta fruta a nivel estatal (SIAP, 2016). De acuerdo con el Consejo Estatal de Productores de Plátano de Colima S.C. (CEPPC) la región platanera más importante de Tecomán, se ubica en la locali-dad de Cerro de Ortega, es por esto que se delimito esta zona como el área de estudio. En dicha región existen 25 cuadrillas identificadas por productores que trabajan en el proceso de corte y empaque; cada cuadrilla consta de 12 personas en campo, y para el tamaño de mues-tra se muestreo al 32% del número total de cuadrillas en la comunidad, aplicando una lista de verificación para evaluar las actividades que realizan, se encuesto al 21.3% de la población total que se dedica al proceso de corte y em-paque de plátano en la localidad de estudio.”
2.2. 	Figuras y gráficos
En 2015, Colima registró una superficie sembrada de 5,567.50 hectáreas, generando una producción de 179,819.65 toneladas de plátano con un valor de 404 millones 923 mil pesos. Los principales municipios productores son: Tecomán ($ 269.4 mdp, 66.5%), Manzanillo ($ 121.4 mdp, 30%) y Armería ($13.8 mdp, 3,4%), que conjuntamente representan el 99.9% del valor total de la producción de la fruta
Fuente: https://colima.quadratin.com.mx/colima/platano-producto-prometedor-para-exportacion/
 
Figura 1. Municipios donde se produce el Plátano
2.3. 	Tablas
 
Fuen-te:https://www.eluniversal.com.mx/articulo/menu/2017/04/1/que-tantas-variedades-de-platano-conoces 
3.	Manejo de datos
Se mostrará a continuación los datos que se usaron, como también las herramientas base para la realización de este.
3.1Tipos de datos manejados
Conceptos clave los cuales fueron necesarios:
Qgis: este programa fue necesario ya que con el se procesarán las imágenes donde con ayu-da de otros componentes se hará el procedi-miento.
SIG: este es muy importante, ya que, para te-ner información del área a estudiar, como tam-bién las recomendación de un ingeniero agró-nomo para hacer el estudio del área necesaria para cada planta.
Python: para esto necesitamos el lenguaje de programación Python, para su interacción con el programa a utilizar.
Cálculos estadísticos: Este tipo de cálculos fueron realizados con base a los resultados obtenidos del código, se calculó la media arit-mética de árboles que pueden ser contenidos en una hectárea.
Sistema Operativo
Se trabajará en el sistema operativo Windows

3.3	Equipo utilizado
Para este necesitamos una computadora portá-til con las siguientes características:
 

4. 	Resultados
Finalmente, como resultado obtuvimos que la planta del plátano tiene una productividad por hectárea de 5700 kg aproximadamente, por los que con ayuda de cálculos se llegó a la pro-ducción total que se estima en dos parcelas de 5 Hectáreas cada una, una producción total de 57 toneladas.
 
Lo que el programa se encargo de hacer fue, con ayuda de puntos calcular la superfie, y al finl multiplicar la cantidad de puntos por la superficie de cada uno, con eso se calculo el numero de plantas y al final de ello la producción.
from qgis.core import 
from PyQt4.QtCore import 
from PyQt4.QtGui import 
from osgeo import ogr

 layer = QgsVectorLayer(&quot;xxxxxx;)
if not layer.isValid():
  print &quot;Layer failed to load!&quot;
vlayer = iface.activeLayer()
 
provider = vlayer.dataProvider()
 
path = provider.dataSourceUri()
 
tmp = path.split("|")
 
path_to_shp_data = tmp[0]
 
driver = ogr.GetDriverByName("Datos")
dataSource = driver.Open(path_to_shp_data, 1)
layer = dataSource.GetLayer()
new_field = ogr.FieldDefn("Superficie", ogr.OFTReal)
new_field.SetWidth(40)
new_field.SetPrecision(1) 
layer.CreateField(new_field)
 
for feature in layer:
    geom = feature.GetGeometryRef()
    area = geom.GetArea() 
    print area
    feature.SetField("Superficie", area)
    layer.SetFeature(feature)
 
dataSource = None

Apéndice
Con este proyecto aprendimos que lo importante y necesario que son para nosotros como Ingenieros Topógrafo el uso de las SIG y las librerías que fuimos viendo durante las clases, cabe mencionar que fue interesante, aunque al principio algo complicado por los códigos y por la información que teníamos que ir obteniendo durante el desarrollo de este proyecto, porque no había mucha sobre los cultivos del plátano que fue el tema que estuvimos trabajando.
Arturo Benito Angulo Silva
Cielo Jazziris Campos García
Ricardo Javier Montes Gutiérrez
