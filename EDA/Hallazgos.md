# "Excedentes agrícolas para de la Red de Bancos de Alimentos de México (RedBAMX)"

## Introducción

Este proyecto pretende encontrar relaciones entre distintos datos para ver si es factible la predición de excedentes agrícolas. Esto con el objetivo de que la RedBAMX pueda buscar nuevos aliados entre los productores y a su vez se obtengan los insumos para poder distribuírlos a la población en situación de déficit alimenticio.

Para este proyecto se han unido las siguientes fuentes de datos:
 - **SNIIM** (Sistema Nacional de Información e Integración de Mercados): Precios por Kilogramo de Frutas y Hortalizas
 - **SIAP** (Servicio de Información Agroalimentaria y Pesquera): Producción Agrícola
 - **SIAP** (Servicio de Información Agroalimentaria y Pesquera): Índice de Volumen Físico
 - **NASA** : Prediction Of Worldwide Energy Resources (POWER): Variables climatológicas

Cada dataset ha sido descargado, filtrado y limpiado de acuerdo a las especificaciones de la RedBAMX, para finalmente ser unidos en un sólo dataset que contenga toda la información necesaria.

Una vez hecho esto, se ha realizado el análisis exploratorio de los datos (EDA, por sus siglas en inglés) con la intención de explorar los siguientes aspectos:
 - Datos faltantes
 - Anomalías (Outliers)
 - Relaciones entre variables por visualización
 - Correlación entre variables
 - Reducción de características para visualización
 
## Hallazgos

### Acerca de datos SIAP

En el análisis de las gráficas de producción por cultivo y registros por cultivo a nivel global, se destacan tendencias significativas. En la gráfica de registros por cultivo, se identifica que el *Frijol*, *Limón* y *Tomate rojo* son los cultivos con mayor cantidad de registros. Estos cultivos emergen como los más sembrados a lo largo del país. En contraste, la *Berenjena*, *Piña*, *Fresa* y *Frambuesa* se sitúan como los cultivos con menos registros.

La gráfica de producción por cultivo revela que la *Naranja* lidera la producción agrícola en el país, seguida por el *Limón*, *Plátano* y *Mango*. En cuanto a la 'Superficie siniestrada por cultivo', se destaca el *Frijol* y la *Sandía* como los cultivos con mayor superficie afectada, con una diferencia considerable respecto a otros cultivos. Además, *Veracruz* y *Zacatercas* son los estados con mayor superficie siniestrada.

Un análisis de correlación entre las variables muestra que 'Producción', 'Superficie(ha)_Cosechada' y 'Rendimiento(udm/ha)' tienen una fuerte correlación lineal. Encontramos que la variable 'Rendimiento(udm/ha)' se define como la relación entre 'Producción' y 'Superficie(ha)_Cosechada'. Las pequeñas discrepancias en el cálculo se atribuyen al redondeo.

En relación a los datos atípicos, se observa la presencia de numerosos valores atípicos en todas las variables numéricas según el cultivo. A pesar de ello, se opta por no eliminarlos, considerando la posibilidad de que estén vinculados con variables climáticas de otros conjuntos de datos. Este comportamiento atípico lo asociamos principalmente a la gran presencia de registros con valor 0.

En la revisión de las variables a lo largo del tiempo, se destaca que la superficie siniestrada permanece prácticamente en 0 desde finales de 2020 hasta principios de 2023, experimentando un aumento significativo a partir de julio de 2023. Este repunte podría requerir una exploración más detallada para comprender las causas subyacentes y tomar medidas preventivas.

### Acerca de datos SNIIM

No se encontraron datos faltantes, sin embargo, cabe mencionar que el SNIIM actualmente no reporta datos para la *Frambuesa*, así como tampoco reporta precios de ningún producto (entre frutas y hortalizas) dentro del estado de *Tlaxcala*.

En cuanto a datos atípicos, se encontró que la media para el precio por kilogramo ronda los $25.00 MNX. Sin embargo, existen productos cuyo precio alcanza los $300.00 MNX por kilogramo, como es el caso de la *nuez*. Por lo tanto estos datos no se consideran anomalías y se mantienen dentro del análisis.

En relación con los datos de producción agrícola (SIAP), en el EDA automatizado se puede observar que no se encuentran relaciones significativas entre las variables. Sin embargo, cuando se analiza la correlación de variables por agrupamientos de Estados y Cultivos en el periodo 2020-2023, se encuentra que las variables de producción agrícola como lo son: las hectáreas sembradas, cosechadas, siniestradas, las toneladas de producción y por lo tanto el rendimiento, en efecto sí tienen una correlación negativa con el precio. Esto significa, por ejemplo, que cuando la superficie cosechada es 0, el precio del producto sube. 

Es importante mencionar que datos como estos tienen temporalidad, es decir, cada cultivo tiene su tiempo para sembrarse y su tiempo para cosecharse, por lo tanto no se puede esperar que todos los meses se estén reportando hectáreas sembrandas ni tampoco cosechadas o siniestradas. Esto hace que para estas variables tengamos ceros durante la mayor parte del año.

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
