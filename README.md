# TFM-Pollution

### Este proyecto intentará hayar una predicción de la contaminación en la ciudad de Madrid.

### Se utilizarán python como herramienta principal.

### Los datos son obtenidos de la web del Ayuntamiento de Madrid y son datos públicos y gratuitos.

## Introducción:

En este proyecto se va a intentar descubrir los días de mayor contaminación en la ciudad de Madrid.

Para ello se ha recogido todos los datos disponibles por días del Ayuntamiento de Madrid ('http://datos.madrid.es/portal/site/egob')

La recogida de estos datos ha dado como resultado un fichero por cada año desde el año 2001 hasta hoy.
En cada fichero se pueden ver diariamente los indices de las particulas que el Ayuntamiento de Madrid investiga y captura.
Estos son:

-Dióxido de Azufre
-Monóxido de carbono
-Monóxido de Nitrógeno
-Dióxido de Nitrogeno
-Óxidos de Nitrógeno
-Ozono
-Tolueno
-Benceno
-Etilbenceno
-Metaxileno
-Paraxileno
-Ortoxileno
-Hidrocarburos totales
-Hidrocarburos no metánicos

Dentro del conjunto de datos podremos ver que segn su terminación, si es en 'v' o en 'N', significar que el dato está validado y por lo tanto se podrá incluir en el conjunto de datos a analizar, en caso contrario, se retirará de la muestra ya que el dato se encontrará erroneo y no se podrá obtener el verdadero.

El Ayuntamiento de Madrid ha utilizado dos formatos de datos ligeramente distintos, un primero desde el año 2001 hasta el año 2010 y otro desde el 2011 en adelante, lo que implica que la recogida de datos se deberá de hacer por duplicado, respetando los formatos de cada uno y posteriormente juntándolos en un solo conjunto de datos.

## Descripción de los datos:

Los datos proporcionados por el Ayuntamiento de Madrid son descargados en texto plano en formato .txt, junto con los datos, el Ayuntamiento de Madrid provee de un manual de uso de estos datos, donde se encuentra una leyenda y un manual de los datos, sobre que significa cada dato y como obtenerlos de forma correcta.

Cada fichero .txt contiene las siguientes columnas, más una por cada día del mes.

-Estacion
-Técnica
-Magnitud
-Tecnica
-Año
-Mes
-Dato Horario
-Día 1
-Día 2
  .
  .
  .
  
Los valores de cada día vienen expresados de la siguientes manera '00005V' o '00000N', diferenciandos así los validados de los no validados.

## Metodología

Para este proyecto se utiliza python y se incluyen todos los datos en un DataFrame. Los pasos seguidos son:
  -Extracción de los datos de todos los txt.
  -Unión de todos los datos extraidos en un solo DataFrame.
  -Por seguridad y manejabilidad de exportan todos estos datos a un csv que contiene todos los datos en bruto con una leve       limpieza, donde se comprueba que el valor de los datos esté validado y acto seguido, se elimina la 'V' final y se convierte el datos en float para su mejor manejo. En caso de no estar validado el dato, se sustituye por 0.0.
  -Creación de un DataFrame que contenga una fila por cada día único y no todos los días del mes en columnas por cada mes.
  
  
