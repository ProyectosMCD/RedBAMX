# RedBAMX - Proyecto Excedentes Agrícolas
Este repositorio contiene código y documentación del proyecto "Excedentes agrícolas para la **Red de Bancos de Alimentos de México (RedBAMX)**".
## Link al DashBoard Power BI
https://app.powerbi.com/view?r=eyJrIjoiMjBmYTlhYmYtZTk3ZS00NDdhLTg0YmMtZThkODNmZmJkODliIiwidCI6IjY3NTUzNjQ1LTBkYjMtNDQ4MC1iMTI3LTZmODE5YTc5ZTM2NyIsImMiOjR9

## Introducción

La [**RedBAMX**](https://bamx.org.mx/) es una OSC (Organización de la Sociedad Civil) sin fines de lucro y apartidista, compuesta por 53 Bancos de Alimentos los cuales rescatan alimento a lo largo de toda la cadena de valor para llevarlo a familias, comunidades e instituciones que lo necesitan y así mejorar la alimentación y la nutrición en México.

Dentro de sus programas se encuentra **Pacto por la Comida**, un Acuerdo Voluntario (AV) ambicioso que pretende reunir a organizaciones a lo largo de la cadena de producción de alimentos y bebidas (AyB), desde los productores hasta los consumidores, para lograr que los sistemas de producción y consumo de AyB sean más sostenibles, y así evitar la Pérdida y el Desperdicio de Alimentos (PDA). 

## Objetivo

Los excedentes agrícolas son una de las vías por las cuales la RedBAMX obtiene insumos para distribuír. 

Este proyecto busca en una primer fase, el poder prever un excedente agrícola que le permita a la RedBAMX buscar nuevos aliados entre los productores.

Para ello, se analizan varias fuentes de datos que son de actual interés para la RedBAMX. Esto con el propósito de poder encontrar aquellos escenarios y/o carcaterísticas que pudieran mostrar información relevante tanto para la visualización de la misma, como para posteriormente ser integrada en algún modelo que nos permita lograr el objetivo de este proyecto.


## Datos

Se utilizan las siguientes fuentes de datos:

**Fuente:** [Sistema Nacional de Información e Integración de Mercados](http://www.economia-sniim.gob.mx/)

**Descripción:** El SNIIM proporciona información diaria de precios al mayoreo del mercado agroalimentario a fin de coadyuvar a la toma de decisiones en materia de comercio. Para fines de este proyecto se analiza la **información histórica de los años 2020 al 2023** para las siguientes secciones:
- Mercados Agricolas Nacionales
    - Frutas y Hortalizas
 
**Fuente:** [Servicio de Información Agroalimentario y Pesquera (Índice de Volumen Físico)](https://www.gob.mx/siap/documentos/ivf-correspondiente-al-mes-de-mayo-2017-111668/).

**Descripción:** Presenta un análisis de la evolución real de la producción agropecuaria nacional, por entidad federativa y por cultivo y productos pecuarios. Es un documento de periodicidad mensual. El cálculo del IVF implica comparar la cantidad de producción de un año o período dado con la cantidad de producción en un año base o período de referencia. El año base se toma como un punto de referencia para calcular las variaciones en la producción física en años posteriores.
**Información de los años 2015-2022** para los siguientes sectores:
- Mercados Agrícolas Nacionales
    - Frutas y Hortalizas


**Fuente:** [Servicio de Información Agroalimentario y Pesquera (Producción Agrícola)](https://nube.siap.gob.mx/avance_agricola/).

**Descripción:** Proporciona datos sobre el progreso mensual de la producción de cultivos de seguimiento, en total 64 cultivos, incluyendo información sobre la superficie sembrada, superficie cosechada, superficie siniestrada (todas en hectáreas) , producción obtenida (en toneladas) y rendimiento (en toneladas por hectárea). Los datos están disponibles desglosados por ubicación geográfica, incluyendo municipio, así como por cultivo, ciclo de producción y modalidad hídrica. En la pagina se encuentra **Información de los años 2018 hasta 2023** para los siguientes segmentos: 
- Mercados Agrícolas Nacionales
    - Frutas y Hortalizas 


**Fuente:** [Prediction Of Worldwide Energy Resources (POWER) de la NASA](https://power.larc.nasa.gov/#resources).

**Descripción:** proporciona conjuntos de datos e información relacionada con recursos energéticos en todo el mundo. Estos conjuntos de datos incluyen mediciones y estimaciones de diversos parámetros climáticos, meteorológicos y energéticos, que son esenciales para comprender y evaluar el potencial de energía renovable, la eficiencia energética de los edificios y la agricultura.

    
## Autores
- Axel Castro Fonseca
- Victor Manuel Minjares Neriz
- María Janneth Rivera Reyna
- Kevin Manuel Galván Lara
