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


En el análisis de las gráficas de producción por cultivo y registros por cultivo a nivel global, se destacan tendencias significativas. En la gráfica de registros por cultivo, se identifica que el *Frijol*, *Limón* y *Tomate rojo* son los cultivos con mayor cantidad de registros. Estos cultivos emergen como los más sembrados a lo largo del país. En contraste, la *Berenjena*, *Piña*, *Fresa* y *Frambuesa* se sitúan como los cultivos con menos registros.

La gráfica de producción por cultivo revela que la *Naranja* lidera la producción agrícola en el país, seguida por el *Limón*, *Plátano* y *Mango*. En cuanto a la 'Superficie siniestrada por cultivo', se destaca el *Frijol* y la *Sandía* como los cultivos con mayor superficie afectada, con una diferencia considerable respecto a otros cultivos. Además, *Veracruz* y *Zacatercas* son los estados con mayor superficie siniestrada.

Un análisis de correlación entre las variables muestra que 'Producción', 'Superficie(ha)_Cosechada' y 'Rendimiento(udm/ha)' tienen una fuerte correlación lineal. Encontramos que la variable 'Rendimiento(udm/ha)' se define como la relación entre 'Producción' y 'Superficie(ha)_Cosechada'. Las pequeñas discrepancias en el cálculo se atribuyen al redondeo.

En relación a los datos atípicos, se observa la presencia de numerosos valores atípicos en todas las variables numéricas según el cultivo. A pesar de ello, se opta por no eliminarlos, considerando la posibilidad de que estén vinculados con variables climáticas de otros conjuntos de datos. Este comportamiento atípico lo asociamos principalmente a la gran presencia de registros con valor 0.

En la revisión de las variables a lo largo del tiempo, se destaca que la superficie siniestrada permanece prácticamente en 0 desde finales de 2020 hasta principios de 2023, experimentando un aumento significativo a partir de julio de 2023. Este repunte podría requerir una exploración más detallada para comprender las causas subyacentes y tomar medidas preventivas.