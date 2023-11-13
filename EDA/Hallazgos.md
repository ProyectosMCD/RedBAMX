# "Excedentes agrícolas para de la Red de Bancos de Alimentos de México (RedBAMX)"

## Introducción

Este proyecto pretende encontrar relaciones entre distintos datos para ver si es factible la predición de excedentes agrícolas. Esto con el objetivo de que la RedBAMX pueda buscar nuevos aliados entre los productores y a su vez se obtengan los insumos para poder distribuírlos a la población en situación de déficit alimenticio.

Para este proyecto se han unido las siguientes fuentes de datos:
 - **SNIIM** (Sistema Nacional de Información e Integración de Mercados): Frutas y Hortalizas
 - **SIAP** (Servicio de Información Agroalimentaria y Pesquera): Producción Agrícola
 - **SIAP** (Servicio de Información Agroalimentaria y Pesquera): Índice de Volumen Físico
 - **NASA** : Prediction Of Worldwide Energy Resources (POWER)

Cada dataset ha sido descargado, filtrado y limpiado de acuerdo a las especificaciones de la RedBAMX, para finalmente ser unidos en un sólo dataset que contenga toda la información necesaria.

Una vez hecho esto, se ha realizado el análisis exploratorio de los datos (EDA, por sus siglas en inglés) con la intención de explorar los siguientes aspectos:
 - Datos faltantes
 - Anomalías (Outliers)
 - Relaciones entre variables por visualización
 - Correlación entre variables
 - Reducción de características para visualización
 
## Hallazgos

### PCA

*PC1:* Este componente en particular parece estar vinculado al concepto de temporalidad y a los factores económicos. Al considerar la agrupación colectiva de la velocidad del viento, el precio y el año, es posible que surja un patrón discernible, que puede atribuirse a la fluctuación anual de los precios de los cultivos. Además, es concebible que estas fluctuaciones estén influenciadas por las condiciones meteorológicas, que están inextricablemente vinculadas a la velocidad del viento.

*PC2:* En este caso, podemos establecer una correlación entre la medición de la humedad relativa y la precipitación. Es concebible que este componente en particular sirva como reflejo del impacto que factores climáticos específicos, a saber, la humedad y las precipitaciones, tienen en la producción agrícola. Al alterar estas variables, se hace evidente la posibilidad de influir en el rendimiento de los cultivos.

*PC3:* El enfoque de este componente parece centrarse en la intrincada relación entre la extensión de tierra utilizada para la siembra y la cosecha y su impacto en la producción agrícola. Se puede deducir que el aumento de la superficie dedicada a la siembra y la cosecha está directamente relacionado con el correspondiente aumento de la producción. Esta correlación implica en gran medida una asociación plausible entre estas variables antes mencionadas.

*PC4:* En el siguiente caso, se observa una conexión entre el rendimiento por hectárea, la precipitación y, posiblemente, una medición secundaria de la precipitación. Esta combinación de factores podría sugerir cómo las variaciones en las precipitaciones, junto con el rendimiento por unidad de superficie, pueden afectar significativamente a la producción de los cultivos.

*PC5:* Este componente en particular establece una relación entre la magnitud del daño a las tierras de cultivo, un identificador estatal, y la presión superficial. Esta combinación de factores puede indicar cómo las condiciones climáticas específicas o las presiones superficiales únicas pueden estar interconectadas con los daños sufridos en varios estados o regiones.

Varianza explicada por cada componente: [0.31613549 0.16452929 0.1168629  0.05474033 0.04761315]
Variables principales para PC1: Velocidad_Viento, Precio, Año
Variables principales para PC2: Humedad_Relativa, Precipitacion, Precipitación
Variables principales para PC3: Superficie(ha)_Cosechada, Superficie(ha)_Sembrada, Producción
Variables principales para PC4: Rendimiento(udm/ha), Precipitación, Precipitacion
Variables principales para PC5: Superficie(ha)_Siniestrada, Estado_CVE, Presión_Superficial
