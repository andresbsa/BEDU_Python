# Educación y Nivel Socioeconómico
Equipo 19

## Proyecto del módulo de Procesamiento de Datos con Python en el curso de Data Analysis (Santander) de BEDU

### Jupyter Notebook

La libreta en Google Colaboratory con el desarrollo y el programa se puede ver [aquí](https://colab.research.google.com/drive/1INiQblT00YUsz3fwX0n_E9ZCO4vao8nu?usp=sharing).

### Introducción

Según datos del Banco Mundial, México es un país con un nivel socioeconómico medio-alto, y es una de las principales economías de Latinoamérica. Sin embargo, el porcentaje de población que vive en pobreza es alarmantemente alto.

De acuerdo con información proporcionada por el CONEVAL en 2018, el porcentaje de los mexicanos viviendo con ingresos inferiores a la línea de pobreza corresponde al 48.8% de la población. Es necesario aclarar que el CONEVAL mide la línea de pobreza por ingresos a partir de los ingresos mensuales totales por hogar y el número de habitantes en el hogar.

La línea de pobreza utilizada por el CONEVAL en 2018 se localizaba alrededor de los $3,300 MXN mensuales para las zonas urbanas y alrededor de $2,300 MXN mensuales para las zonas rurales. De modo que un hogar con tres habitantes y un ingreso total de $15,000 MXN mensuales estaría por encima de la línea de pobreza, mientras que un hogar con cinco habitantes y un ingreso total de $15,000 MXN mensuales se encontraría en el umbral de pobreza en México.

Un estudio realizado en 2009 por la CEPAL determinó que existe una correlación entre la población en situación de pobreza y un menor nivel de estudios. Se detectó que un individuo con bajo nivel educativo tiene más probabilidades de encontrarse en situación de pobreza. No obstante, el mismo estudio declara que no fue posible determinar si un mayor nivel de estudios permite a las personas salir de la pobreza.

Tomando en cuenta la información presentada previamente se decidió realizar un análisis para determinar si existe una correlación directa entre el nivel educativo y el nivel de ingresos de un individuo, y de ser así, cómo es esta relación.

Con el análisis propuesto se espera obtener información que proporcione una mejor comprensión del problema de la pobreza y la educación en México, pues es necesario conocerlo a fondo para poder desarrollar estrategias eficaces que permitan impulsar el desarrollo del país.

Preguntas de interés:

- ¿La educación universitaria garantiza un mayor nivel socioeconómico?
- ¿En qué medida afecta el nivel socioeconómico a las posibilidades de estudiar?
- ¿Cuál es la relación entre el nivel socioeconómico de los individuos con un cierto grado de estudios respecto a otro?
- ¿Hay una diferencia en los niveles de ingresos de los individuos con únicamente estudios de nivel primaria respecto a los de secundaría?
- ¿El nivel de estudios de un país aumenta en la misma medida que disminuye la pobreza?



### Datasets

Inicialmente se identificaron los datasets más relevantes para el tema dentro de la Encuesta Nacional de Ingresos y Gastos de los Hogares (**ENIGH**) del INEGI de 2018. La documentación de la base de datos general se puede encontrar [aquí](https://www.inegi.org.mx/programas/enigh/nc/2018/#Documentacion). Se descargaron los datasets sobre las viviendas mexicanas relacionada con el nivel socioeconómico y los diferentes tipo de ingresos que recibieron (salarios, comisiones, aguinaldo, trabajo subordinado, etc.) (***concentrado_hogar***), sobre la sociodemografía de las viviendas por cada integrante (***población***) y sobre los ingresos que recibió cada integrante de vivienda en los 6 meses previos al momento de la encuesta (***ingresos***).

Los datasets del INEGI se descargaron directamente del portal y se encuentran en este mismo repositorio.

Por otro lado, también se identificó la base de datos sobre Pobreza y Educación del Banco Mundial. Especificamente, se identificaron los datasets sobre la Tasa de incidencia de la pobreza, sobre la base de la línea de probreza nacional (POV.NAHC), la *Poverty headcount ratio at $5.50 a day* (POV.UMIC) y la Tasa de incidencia de la pobreza, sobre la base de $1.90 por día (POV.DDAY). Estos datasets se pueden encontrar [aquí](https://data.worldbank.org/topic/poverty?view=chart). En el tema de Educación se identificaron los datasets sobre Transición a la escuela secundaria (SE.SEC.PROG.ZS), Inscripción escolar, nivel primario (SE.PRM.ENRR), Inscripción escolar, nivel secundario (SE.SEC.ENRR) e Inscripción escolar, nivel terciario (SE.TER.ENRR). Estos datasets se pueden encontrar [aquí](https://datos.bancomundial.org/tema/educacion?view=chart).

La base de datos del Banco Mundial tiene su propia API con una librería de Python: `world_bank_data`. Por medio de esa API se extrajeron los datasets de esta BDD.

Los archivos "raw" `.csv` descargados con los datos del INEGI se encuentran en este mismo repositorio:

- Datos de [*concentrado_hogar*](https://raw.githubusercontent.com/andresbsa/BEDU_Python/main/conjunto_de_datos_concentradohogar_enigh_2018_ns.csv)
- Datos de [*población*](https://raw.githubusercontent.com/andresbsa/BEDU_Python/main/conjunto_de_datos_poblacion_enigh_2018_ns.csv)
- Datos de [*ingresos*](https://raw.githubusercontent.com/andresbsa/BEDU_Python/main/conjunto_de_datos_ingresos_enigh_2018_ns.csv)
