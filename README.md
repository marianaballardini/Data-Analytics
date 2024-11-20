## Proyecto de Ciencia de Datos: Aumento del acceso a internet por provincia

## 1. Contexto y motivación  
En este proyecto, se busca analizar el acceso a internet en distintas provincias y evaluar el incremento en la penetración de internet en los hogares a lo largo del tiempo. Este análisis es relevante para comprender la distribución y el crecimiento del acceso a la conectividad en diferentes regiones, con el fin de identificar áreas de mejora y proporcionar recomendaciones para el aumento de la penetración de internet en cada provincia.

## 2. Objetivo del proyecto  
El objetivo principal es medir el crecimiento en el acceso a internet en cada provincia, con un KPI específico de aumentar el acceso en un 2% por cada 100 hogares para el próximo trimestre. El análisis incluye estudiar los tipos de tecnologías disponibles, su distribución geográfica y su evolución en el tiempo.

## 3. Metodología y análisis  
Este proyecto sigue una metodología de análisis exploratorio de datos (EDA) para comprender las tendencias actuales, así como de ingeniería de datos para calcular métricas específicas. A continuación, describimos los pasos llevados a cabo:




  # Exploración de datos

   ## Análisis del archivo 'Penetracion_hogares':  


  
Hacemos la revisión de valores faltantes y duplicados. En este caso no hay nada de esto en los datos por lo que se continúa sin problema con el análisis.  
Realizamos un chequeo general de los datos aplicando la función `head()`, observamos que el archivo contiene cuatro columnas:  
-Año  
-Trimestre  
-Provincia  
-Accesos por cada 100 hogares  
  

### Análisis detallado de outliers y su impacto en las métricas

### Identificación de outliers
Utilizamos un gráfico de boxplot para identificar valores atípicos en los accesos por cada 100 hogares para cada provincia. El análisis reveló que Santa Cruz presenta valores superiores al rango intercuartílico en los trimestres más recientes, lo que sugiere un comportamiento anómalo en comparación con otras provincias.
# GRAFICO OUTLIERS  

### Análisis de Santa Cruz
Filtramos los datos de Santa Cruz y realizamos un análisis temporal. Observamos un crecimiento sostenido de los accesos a internet a partir de 2022, con un fuerte incremento en 2023 y 2024. Aunque estos valores son elevados en relación con otras provincias, su exclusión no afecta significativamente las métricas generales, como lo demuestra el cálculo de la media y la mediana.

### Impacto de los outliers en las métricas generales
Realizamos cálculos adicionales para evaluar el impacto de Santa Cruz en las métricas generales. Comparando los valores de media y mediana con y sin Santa Cruz, encontramos que los resultados se mantienen consistentes. Esto indica que los valores atípicos de esta provincia no distorsionan la tendencia general de la penetración de internet a nivel nacional.

### Conclusión
El análisis sugiere que, aunque Santa Cruz tiene un comportamiento atípico y un crecimiento acelerado en los últimos años, su impacto en la tendencia nacional es limitado. Este hallazgo nos permite centrarnos en patrones generales sin necesidad de ajustar las métricas generales debido a estos valores atípicos.

Se investigan posibles causas del crecimineto acelerado y confirmamos que fue gracias a  un convenio de ampliación de la Red Federal de Fibra Óptica en la provincia, que permitió garantizar un servicio de calidad a las y los santacruceños.  
Este acuerdo se da en el marco del Plan Conectar, impulsado desde la Secretaría de Innovación Pública y tiene como objetivo implementar políticas públicas federales para potenciar el acceso a internet de calidad y reducir la brecha digital, a través del uso eficaz de las infraestructuras físicas de telecomunicaciones existentes, tanto provinciales como nacionales. [Fuente](https://www.argentina.gob.ar/noticias/el-gobierno-amplia-la-conectividad-en-santa-cruz)

### Análisis descriptivo de la penetración de internet
Realizamos el análisis inicial de la columna `Accesos cada 100 hogares` con la funcion `describe()`, el cual ofrece una visión detallada de la distribución de la cobertura de internet en cada provincia. Este análisis es fundamental para entender las disparidades geográficas y ayudar a enfocar las estrategias de mejora en las áreas que más lo necesitan.  


Resumen de los resultados:

**Media (Promedio)**: La media de 52.80 accesos por cada 100 hogares nos muestra una cobertura promedio, que podría considerarse un valor representativo para el análisis nacional. Sin embargo, esta cifra por sí sola no es suficiente para evaluar las desigualdades en la penetración de internet, ya que no refleja cómo se distribuyen esos accesos entre las provincias.

**Mediana:** Con un valor de 50.13 accesos por cada 100 hogares, la mediana indica que la mitad de las provincias tienen una penetración de internet superior a este valor y la otra mitad tiene valores inferiores. Esto es relevante porque nos da una idea de que la distribución de la penetración no está completamente sesgada hacia un extremo (como podría ocurrir si hubiera un solo valor muy alto que arrastrara la media).

**Rango:**

  -**Mínimo** (9.51 accesos por cada 100 hogares): El valor mínimo señala que algunas provincias tienen una penetración de internet extremadamente baja. Esto podría ser una indicación de que en ciertas regiones el acceso a internet sigue siendo limitado o poco accesible, lo cual podría reflejar zonas rurales o de difícil acceso. Estas áreas probablemente requieren una atención prioritaria para mejorar la infraestructura y aumentar la cobertura.

  -**Máximo** (124.06 accesos por cada 100 hogares): El valor máximo de 124.06 accesos sugiere que, en algunas provincias, los hogares tienen acceso a múltiples conexiones a internet, lo que podría ser resultado de un acceso extendido a internet de alta velocidad o acceso múltiple en un solo hogar. Este fenómeno podría indicar que algunas áreas urbanas tienen una oferta de servicios de internet más robusta y diversificada, lo que podría ser un reflejo de un entorno más competitivo o con mayor disponibilidad de infraestructura tecnológica.

**Desviación estándar (24.13):** La desviación estándar es un indicador importante de la disparidad en la cobertura de internet entre las provincias. Un valor tan alto indica que existe una gran variabilidad entre las provincias. Algunas tienen una penetración cercana al promedio, mientras que otras están muy por debajo o por encima. Esto resalta una distribución desigual en la cobertura, lo que podría llevar a la conclusión de que no todos los hogares tienen el mismo nivel de acceso a internet, lo cual puede generar desigualdades en el desarrollo socioeconómico, educativo y laboral.

#### Podemos observar ciertos comportamientos:
**Desigualdad Regional en el Acceso a Internet:** La alta desviación estándar (24.13) refleja una disparidad significativa en el acceso a internet entre las provincias. Esto indica que algunas áreas tienen una penetración de internet mucho más alta que otras. Esta información es crucial para la formulación de políticas públicas o estrategias de desarrollo, ya que las provincias con baja penetración deben ser priorizadas en términos de inversión en infraestructura tecnológica.

**Impacto de los valores extremos:** La presencia de valores extremos en el rango, como los 124.06 accesos por cada 100 hogares, puede distorsionar la percepción general de la cobertura de internet si solo nos basáramos en la media. Aunque el valor promedio sugiere una penetración de más del 50%, este valor puede estar influenciado por las provincias más conectadas. Esto podría llevar a una sobreestimación de la cobertura real en el país, ya que muchas provincias podrían estar luchando con una baja penetración de acceso.

En este análisis inicial, utilizamos el método describe() para obtener un resumen estadístico de la variable. Sin embargo, debido a la presencia de valores atípicos que podrían distorsionar la interpretación de la media, hemos decidido utilizar la mediana como medida más robusta para un análisis más profundo. Este enfoque nos permitirá obtener una visión más precisa y representativa de la penetración de internet en los hogares, especialmente en áreas con accesos extremadamente altos.  

  
  


### Análisis de la distribución de la penetración de internet  
Para analizar la distribución de la penetración de internet en las localidades, hemos generado un histograma de la variable "Accesos por cada 100 hogares". El histograma muestra cómo se distribuyen los valores de penetración de internet en las diferentes localidades, y nos proporciona una visión general de las tendencias y variabilidad de los datos.  

#### Resultados Observados:

**Mayor concentración en rangos medios:** La mayoría de las localidades se concentran en rangos de penetración entre 40 y 80 hogares por cada 100. Esto sugiere que existe un grupo significativo de localidades con un nivel de acceso a internet moderado. Este hallazgo podría indicar que, aunque el acceso a internet está presente, aún hay margen para mejorar la cobertura en varias zonas.

**Dispersión en los valores:** Se observa un número considerable de localidades con penetración inferior a 40 hogares por cada 100, lo que señala que existen zonas con un acceso a internet limitado. Esto puede reflejar brechas en el acceso a internet en regiones rurales o menos urbanizadas.

**Menor frecuencia en los extremos:** Existen menos localidades con penetración muy baja (por debajo de 20 hogares) o muy alta (por encima de 100 hogares). Los casos extremos son menos frecuentes, lo que sugiere que los valores de penetración muy baja o muy alta son excepcionales y no representan la mayoría de las localidades.

#### Conclusiones preliminares:

**Desigualdad en el acceso a internet:** El histograma revela una notable desigualdad en el acceso a internet entre las localidades. Mientras que algunas áreas tienen una penetración bastante alta, otras presentan niveles considerablemente más bajos. Esto podría indicar que el acceso a internet no está distribuido de manera equitativa.

**Potencial de expansión:** La presencia de localidades con baja penetración sugiere que existe un significativo potencial de crecimiento en términos de cobertura de internet. Las políticas públicas pueden centrarse en mejorar la infraestructura en las áreas con menores accesos.


### Análisis de la penetración de internet por provincias
El gráfico presenta la comparación de la penetración de Internet por cada 100 hogares en diversas provincias de Argentina. A continuación, se detallan algunos aspectos clave observados en el análisis:

**Variabilidad regional:** La penetración de Internet varía notablemente entre las provincias, con algunas mostrando una adopción significativamente más alta que otras. Esta variabilidad puede estar influenciada por factores económicos, geográficos y demográficos.

**Provincias con alta penetración:** Algunas provincias presentan una penetración de Internet considerablemente alta, lo que sugiere un mejor acceso a infraestructura y servicios de Internet. Estas provincias pueden estar más urbanizadas o contar con políticas de promoción del acceso a Internet más efectivas.

**Provincias con baja penetración:** Por otro lado, algunas provincias muestran una penetración de Internet relativamente baja. Esto podría ser indicativo de desafíos en la infraestructura, menor inversión en tecnología o barreras socioeconómicas que limitan el acceso a Internet.

**Desigualdad Digital:** La disparidad en la penetración de Internet entre las provincias resalta la desigualdad digital existente en el país. Es crucial identificar y abordar las causas subyacentes de esta desigualdad para promover un acceso equitativo a la información y las oportunidades que brinda Internet.            


### Análisis de la evolución temporal de la penetración de internet por categoría

En este análisis, hemos decidido agrupar las provincias en tres categorías de penetración de internet: baja, media y alta. La clasificación se realizó utilizando la mediana de los accesos a internet por cada 100 hogares. 

El análisis de la penetración de internet a lo largo del tiempo indica una clara tendencia al alza, lo que refleja un aumento generalizado en el acceso a internet en las regiones estudiadas. Las regiones categorizadas como de "alta penetración" y "media penetración" muestran un crecimiento más acelerado, sugiriendo una dinámica de adopción más rápida en áreas con mayor conectividad inicial.

Sin embargo, el gráfico también revela períodos de estabilización en el crecimiento, lo que podría atribuirse a factores como la saturación del mercado, cambios en las políticas públicas o eventos económicos que afectaron la demanda de servicios de internet. Estos hallazgos resaltan la importancia de considerar tanto las tendencias generales como los factores contextuales al analizar la evolución de la penetración de internet.  

El gráfico titulado "evolución temporal de la penetración de internet por categoría" ilustra cómo ha cambiado la penetración de internet en tres categorías (alta, media y baja) a lo largo del tiempo, desde 2014 hasta 2024.

#### Alta penetración
La categoría de alta penetración, representada en azul, muestra una tendencia general a la baja con fluctuaciones notables en ciertos periodos. Esto podría indicar que, aunque inicialmente había un alto acceso a internet en ciertas áreas, ha habido una disminución en la penetración debido a posibles factores económicos, tecnológicos o de infraestructura.

#### Media y baja penetración
Por otro lado, las categorías de media y baja penetración, representadas en verde y naranja respectivamente, muestran una tendencia ligeramente ascendente. Esto sugiere que, aunque estas áreas comenzaron con un menor acceso a internet, ha habido un esfuerzo continuo para mejorar la conectividad en estas regiones. La tendencia ascendente, aunque modesta, indica un progreso en la reducción de la brecha digital.

#### Conclusión
Este análisis es crucial para entender las disparidades en el acceso a internet y puede ayudar a formular políticas y estrategias para mejorar la conectividad en áreas con baja penetración. Además, resalta la importancia de monitorear y evaluar continuamente la evolución de la penetración de internet para asegurar un acceso equitativo a la tecnología.



### Filtrado de provincias con baja penetración de internet y análisis de su evolución temporal

En esta etapa del análisis, se realiza un filtrado de las provincias con baja penetración de internet, clasificadas por la cantidad de accesos a internet por cada 100 hogares. Según las categorías definidas previamente, se considera baja penetración a aquellas provincias con entre 0 y 40 accesos por cada 100 hogares.

Este filtrado permite identificar específicamente las provincias que se encuentran dentro de la categoría de baja penetración en el momento actual. Una vez identificadas, se analiza su evolución a lo largo del tiempo para observar cómo ha cambiado la cantidad de accesos por cada 100 hogares en cada provincia.

El propósito de este análisis es detectar tendencias de mejora, estancamiento o retroceso en estas provincias y proporcionar una visión más clara de los avances en la penetración de internet, lo que puede ser útil para la planificación de políticas y acciones futuras.     

### Análisis de la evolución de los accesos a internet en Formosa

#### Crecimiento Sostenido
El gráfico de evolución de los accesos a internet en la provincia de Formosa revela un crecimiento constante a lo largo de la última década. Desde 2014, el número de accesos por cada 100 hogares ha incrementado de manera progresiva, destacando un avance significativo en la conectividad digital de la región.

#### Picos Notables
Se observan picos de crecimiento más pronunciados en los años 2018 y 2020. Estos aumentos pueden ser resultado de la implementación de políticas públicas, inversiones en infraestructura, o programas específicos para mejorar el acceso a internet en la provincia. Estos picos reflejan esfuerzos concretos por reducir la brecha digital en áreas tradicionalmente desatendidas.

#### Implicaciones del Crecimiento
El incremento en la penetración de internet tiene varias implicaciones positivas:
- **Inclusión Digital**: Mayor acceso a recursos educativos, información y servicios digitales.
- **Desarrollo Económico**: Facilita el comercio electrónico, nuevas oportunidades de negocio y empleo.
- **Participación Ciudadana**: Mejora la comunicación y participación en procesos democráticos y gubernamentales.

#### Conclusión
El análisis del crecimiento de los accesos a internet en Formosa es una muestra del progreso hacia una mayor equidad en la conectividad digital. Es fundamental continuar con políticas y programas que sigan impulsando este crecimiento, asegurando que más habitantes de la región puedan beneficiarse de los avances tecnológicos.

Este análisis subraya la importancia de monitorear y evaluar el impacto de las iniciativas de conectividad, adaptando las estrategias para maximizar su efectividad y alcance.    
  

**_____________________________________________________________________________________________________________________** 
## Análisis del archivo "Accesos_tecnologia_localidad" 
Hacemos la revisión de valores faltantes y duplicados. En este caso hay 6 valores nulos en la columna "Accesos" por lo que vamos a revisar detalladamente que vemos en los datos y tomar una desición al respecto, de ser necesaria.  
Se observa que los nulos pertenecen a la tecnología "Otros" y esto no aporta valor significativo a nuestro análisis por lo que se decide eliminarlos.  


Realizamos un chequeo general de los datos aplicando la función `head()`, observamos que el archivo contiene cuatro columnas:  
* Provincia 
* Partido  
* Localidad  
*	Tecnologia  
* Link Indec  
*	Accesos

La columna Link Indec se elimina porque no la vamos a utilizar en nuestro análisis.  

### Análisis estadistico con la función `describe()`  

Al aplicar dicha función nos encontramos con que no estaba tomando la columna como numérica como debería ser sino por cadena de texto, procedemos a realizar una serie de chequeos para resolver esto y poder obtener las estadisticas descriptivas correctamente.  


**Tendencias Generales:** La media (112.14) muestra que, en promedio, cada localidad cuenta con poco más de 100 accesos. Sin embargo, la alta desviación estándar (198.96) indica una gran dispersión en los datos, reflejando que algunas localidades tienen significativamente más accesos que otras.

**Desigualdades:** Los percentiles evidencian disparidades:

Un 25% de las localidades tienen 2 accesos o menos, lo que refleja áreas con muy poca conectividad.
La mediana (14.93) sugiere que más de la mitad de las localidades están por debajo de este valor, destacando una concentración mayoritaria en accesos bajos.
**Outliers o Límites:** La localidad con el mayor número de accesos (998) se presenta como un outlier significativo que puede requerir un análisis adicional para comprender las razones detrás de esta diferencia.

En resumen, esta información será útil para identificar patrones de conectividad y desigualdad entre las localidades, lo cual puede guiar futuras estrategias de expansión tecnológica.  

### Tratamiento de outliers  
### Descripción del Dataset

El conjunto de datos contiene información detallada sobre el acceso a diferentes tecnologías de internet (ADSL, SATELITAL, CABLEMODEM, FIBRA OPTICA, WIRELESS, entre otras) en diversas localidades de Argentina. Las columnas incluyen:

- **Provincia**: La provincia correspondiente al acceso a internet.
- **Partido**: El partido o municipio dentro de la provincia.
- **Localidad**: La localidad específica dentro del partido.
- **Tecnologia**: El tipo de tecnología de acceso a internet.
- **Accesos**: El número de accesos a internet disponibles en la localidad.

### Identificación de Outliers

El gráfico de caja y bigotes (boxplot) presentado ilustra la distribución de los accesos a internet por distintas tecnologías en Argentina. Las tecnologías analizadas incluyen ADSL, Cablemodem, Fibra Óptica, Satelital, Wireless, Otros, Dial-Up y WiMAX. Este tipo de gráfico es crucial para identificar la dispersión de los datos y detectar valores atípicos (outliers) que pueden proporcionar insights valiosos sobre la conectividad en diversas regiones.

### Descripción del Gráfico
- **Eje X**: Representa las diferentes tecnologías de acceso a internet.
- **Eje Y**: Representa la cantidad de accesos.
- **Cajas**: Muestran el rango intercuartílico (IQR), que es la diferencia entre el primer cuartil (Q1) y el tercer cuartil (Q3). La línea dentro de la caja indica la mediana.
- **Bigotes**: Extienden hasta 1.5 veces el IQR desde los cuartiles Q1 y Q3.
- **Puntos**: Representan valores atípicos, que son accesos significativamente diferentes del resto de los datos.

### Observaciones Clave
1. **Valores Atípicos**:
   - Las tecnologías como Wireless y Satelital muestran varios valores atípicos, indicando que hay localidades con accesos a internet significativamente diferentes del promedio.
   - La presencia de outliers en Fibra Óptica y Cablemodem sugiere áreas con un acceso excepcionalmente alto o bajo en comparación con otras tecnologías.

2. **Dispersión de Datos**:
   - La tecnología de Fibra Óptica presenta una amplia dispersión, lo que indica variabilidad en la disponibilidad de este servicio en diferentes regiones.
   - ADSL y Dial-Up tienen una menor dispersión, reflejando una mayor consistencia en el acceso a estas tecnologías.


- **Políticas de Mejora**:
  - Implementar políticas que aborden las disparidades en el acceso a internet, enfocándose en reducir la brecha digital en las regiones menos atendidas.
  - Promover iniciativas para estabilizar el acceso a internet en tecnologías con alta dispersión, asegurando una conectividad más uniforme.

### Conclusión
El análisis de valores atípicos en los accesos a internet por tecnología es esencial para comprender las variaciones en la conectividad y detectar áreas con necesidades específicas de mejora. La identificación de outliers proporciona una base para dirigir inversiones en infraestructura y formular políticas que promuevan un acceso equitativo a internet en todo el país.








### Análisis de la distribución de accesos por tecnología  

En el análisis de las tecnologías de acceso a Internet, se encontraron diferencias significativas en los promedios de accesos por tecnología. Las tecnologías con mayor promedio de accesos incluyen WIRELESS (285,962), FIBRA OPTICA (187,487), y ADSL (220,008), destacándose como las más utilizadas o disponibles en términos de promedio. Por el contrario, tecnologías más antiguas o de menor implementación, como DIAL UP (9,745), SATELITAL (2,930), y WIMAX (2,238), presentan promedios considerablemente más bajos.

Además, se detectaron inconsistencias en la nomenclatura de las tecnologías, por ejemplo, CABLEMODEM y Cablemodem, así como OTROS y Otros. Estas inconsistencias pueden influir en la interpretación de los datos y requieren un proceso de normalización para asegurar resultados precisos en el análisis y la generación de KPIs. Esto evidencia la importancia de la limpieza y estandarización de datos como paso crítico en cualquier proyecto de análisis.  

**Normalización**

Para garantizar que los valores fueran uniformes y facilitar el análisis posterior, se realizó una normalización convirtiendo todos los valores a mayúsculas.  

Se utilizó el método `.str.upper()` de pandas para estandarizar los valores de la columna Tecnologia. Esto permite que nombres con la misma semántica pero diferentes formatos sean tratados como iguales (por ejemplo, Cablemodem y CABLEMODEM se unificaron en CABLEMODEM).  

Luego se verificaron los valores únicos de la columna después de la normalización para confirmar que todas las variaciones se habían unificado correctamente.  

**Resultado:**
La columna Tecnologia quedó completamente normalizada, con los siguientes valores únicos:
['ADSL', 'CABLEMODEM', 'DIAL UP', 'FIBRA OPTICA', 'OTROS', 'SATELITAL', 'WIMAX', 'WIRELESS'].


#GRAFICO DE BARRAS   

En este análisis, se visualiza la distribución de los accesos a internet segmentados por tecnología. El gráfico de barras muestra cómo se distribuyen los accesos a internet en las distintas tecnologías, permitiendo observar las tecnologías con mayor penetración en el mercado. El gráfico ayuda a identificar tendencias clave y facilita la interpretación de los datos para posibles recomendaciones o decisiones estratégicas.
  
        
El gráfico de barras presentado visualiza la distribución de los accesos a internet según la tecnología utilizada. Los resultados obtenidos a partir de este análisis permiten extraer las siguientes conclusiones:

Dominancia de WIRELESS: Se posiciona como la más utilizada por los usuarios.  

Crecimiento de la fibra óptica: La fibra óptica, a pesar de no ser la tecnología más utilizada, muestra un crecimiento constante, lo que indica una tendencia hacia conexiones de mayor velocidad y estabilidad.
Declive del Dial Up: La tecnología DIAL UP, caracterizada por bajas velocidades de conexión, muestra una disminución significativa en su uso, lo que es esperable debido a la aparición de tecnologías más modernas.
Heterogeneidad de "OTROS": La categoría "OTROS" agrupa un conjunto diverso de tecnologías, lo que dificulta realizar un análisis más detallado sin información adicional. Sería recomendable desglosar esta categoría en tecnologías más específicas para obtener una visión más precisa.


# GRAFICO MAPA DE CALOR
El gráfico de calor presentado en el archivo "EDAjpynb" muestra la distribución del acceso a diferentes tecnologías de internet en las provincias de Argentina. Este análisis es crucial para entender la penetración de diversas tecnologías de conectividad en el país y para identificar áreas que requieren mejoras en infraestructura.

### Descripción del gráfico
El gráfico incluye las siguientes tecnologías:
- **ADSL**
- **Cablemodem**
- **Dial-Up**
- **Fibra óptica**
- **Otros**
- **Satelital**
- **WiMAX**
- **Wireless**

Cada celda en la tabla de calor representa la cantidad de accesos a una tecnología específica en una provincia, con una escala de colores que varía desde el amarillo claro (menos accesos) hasta el azul oscuro (más accesos).

### Observaciones detalladas
1. **Provincias con mayor acceso**:
   - **Buenos Aires**: lidera en accesos a ADSL, cablemodem, fibra óptica y wireless.
   - **Córdoba**: también muestra altos niveles de acceso en ADSL, cablemodem, fibra óptica y wireless.
   - **Santa Fe**: destaca en accesos a ADSL, cablemodem, fibra óptica y wireless.

2. **Provincias con menor acceso**:
   - **La Rioja** y **Formosa**: tienen los menores accesos en casi todas las tecnologías.
   - **Tierra del Fuego**: muestra un acceso nulo en varias tecnologías como WiMAX y wireless.

3. **Tecnologías predominantes**:
   - **Fibra óptica**, **cablemodem** y **wireless**: son las tecnologías con mayor penetración en la mayoría de las provincias.
   - **Dial-Up**: tiene una presencia mínima, lo que indica una transición hacia tecnologías más modernas.  


## Análisis del gráfico de correlación entre accesos a tecnologías
# GRAFICO MATRIZ CORRELACION  
El gráfico presentado es una matriz de correlación que ilustra la relación entre diferentes tecnologías de acceso a internet en diversas provincias. La matriz de correlación es una herramienta estadística que mide la relación entre dos variables, en este caso, diferentes tecnologías de acceso a internet. Los valores de correlación oscilan entre -1 y 1:

- **1**: Correlación positiva perfecta, lo que significa que a medida que una tecnología aumenta, la otra también lo hace en la misma proporción.
- **-1**: Correlación negativa perfecta, indicando que a medida que una tecnología aumenta, la otra disminuye en la misma proporción.
- **0**: No hay correlación entre las tecnologías.

### Observaciones 
1. **ADSL y Cablemodem**: Tienen una correlación negativa muy débil de -0.076, lo que sugiere que no hay una relación significativa entre estas dos tecnologías.
2. **Dial-Up y Fibra Óptica**: Muestran una correlación negativa de -0.35, indicando que en las provincias donde el acceso a Dial-Up es alto, el acceso a Fibra Óptica tiende a ser bajo.
3. **Satelital y WiMAX**: Tienen una correlación positiva de 0.52, sugiriendo que estas tecnologías tienden a coexistir en las mismas provincias.
4. **Wireless y Satelital**: Presentan una correlación negativa de -0.45, lo que indica que en las provincias con alto acceso a Wireless, el acceso a Satelital tiende a ser bajo.

### Conclusión
Este análisis proporciona una visión clara de la distribución del acceso a internet en Argentina, destacando las disparidades regionales y ofreciendo una base sólida para la toma de decisiones en políticas de infraestructura tecnológica. La identificación de correlaciones entre tecnologías puede ayudar a dirigir inversiones y esfuerzos hacia áreas que más lo necesitan.


## Análisis comparativo del gráfico 
# GRAFICO BARRAS PROMEDIO ACCESOS

Este análisis se basa en un conjunto de datos que compara el promedio de accesos a las tres tecnologías mas usadas de internet (fibra óptica, wireless y ADSL) en diferentes provincias argentinas. Los resultados revelan una desigualdad significativa en el acceso a internet a nivel regional.

Se propone un enfoque multidimensional para identificar las provincias con mayor necesidad de inversión en infraestructura de telecomunicaciones, considerando tanto el nivel actual de conectividad como el potencial de crecimiento del mercado.

Las recomendaciones presentadas buscan guiar a los tomadores de decisiones en la elaboración de estrategias de inversión que permitan reducir la brecha digital y promover el desarrollo socioeconómico en todo el territorio nacional.  

**Factores socioeconómicos:** Es importante considerar factores como el nivel de ingresos, el nivel educativo y la urbanización al analizar las causas de la desigualdad en el acceso a internet.
**Políticas públicas:** Las políticas gubernamentales en materia de telecomunicaciones pueden influir significativamente en la expansión de la infraestructura y en el acceso a servicios de internet.
**Sustentabilidad:** Es fundamental evaluar la sostenibilidad de las inversiones a largo plazo, considerando aspectos como el mantenimiento de la infraestructura y la evolución de las tecnologías.

### Recomendaciones
- **Mejorar la infraestructura**: en provincias con menor acceso, es crucial invertir en infraestructura para tecnologías como fibra óptica y cablemodem.  

- **Políticas focalizadas**: implementar políticas que incentiven la adopción de tecnologías avanzadas en regiones con menor penetración.
- **Monitoreo continuo**: realizar análisis periódicos para evaluar el progreso y ajustar las estrategias de implementación.

### Conclusión
Este análisis proporciona una visión clara de la distribución del acceso a internet en Argentina, destacando las disparidades regionales y ofreciendo una base sólida para la toma de decisiones en políticas de infraestructura tecnológica.


**_____________________________________________________________________________________________________________________** 
## Análisis del archivo "Accesos_tecnologia" 

Se carga el archivo, **Eliminación de filas 1007 y 1008**

Durante la revisión del dataset, se identificaron dos filas problemáticas (1007 y 1008). La fila 1007 presentaba valores vacíos, mientras que la fila 1008 contenía un aviso del tipo:

*“Los datos provinciales no coinciden a nivel nacional, ya que se reincorporó información que no contiene apertura a nivel geográfico.”*

Tras analizar el contenido del archivo original y el objetivo del proyecto, se decidió eliminar ambas filas por las siguientes razones:

1. **Irrelevancia para el análisis:** El texto de la fila 1008 era solo una nota aclaratoria y no proporcionaba datos numéricos útiles para el análisis.
2. **Foco en datos provinciales:** El análisis está enfocado exclusivamente en entender los accesos a nivel provincial para formular recomendaciones de inversión. Por lo tanto, la consistencia con los datos a nivel nacional no es prioritaria en este contexto.
3. **Limpieza del dataset:** Mantener filas con texto explicativo o valores nulos podría introducir ruido en el análisis y generar errores en los cálculos o visualizaciones posteriores. Además, eliminamos la columna totales porque no la vamos a utilizar.

Esta decisión está alineada con el propósito del proyecto y asegura que el dataset sea adecuado para responder a las preguntas de análisis planteadas. La limpieza del dataset fue documentada y verificada para garantizar la calidad de los datos restantes.    

### Tratamiento de outliers  

Nos enfocamos en las columnas que nos interesan, en este caso las de tecnologías mas usadas.
* Cablemodem
* ADSL
* Fibra óptica

#### Decisión sobre los Outliers

En el proceso de análisis de los accesos a internet por provincia, se identificaron valores atípicos (outliers) que, aunque significativamente diferentes de la mayoría de los datos, podrían tener una justificación válida dentro del contexto de la información que estamos analizando.

Al observar ciertas provincias con valores de acceso a internet mucho mayores que otras, se concluyó que estos valores extremos no representan errores ni distorsiones en los datos, sino que reflejan una realidad legítima. Por ejemplo, algunas provincias pueden contar con concentraciones de población o infraestructura tecnológica más desarrolladas, lo que puede resultar en un número de accesos superior al de otras regiones.

En lugar de imputar o eliminar estos outliers, se decidió conservarlos tal como están, ya que representan fenómenos reales dentro del análisis. Modificar o eliminar estos valores podría haber alterado la representación fiel del acceso a internet por provincia y afectado negativamente los cálculos de los KPIs.

Por lo tanto, optamos por no imputar los outliers para mantener la autenticidad y precisión de los datos, y para garantizar que los resultados reflejen adecuadamente las disparidades reales entre las provincias en términos de acceso a internet.  


Durante la etapa de limpieza de datos, se identificaron inconsistencias en las columnas "Año" y "Trimestre", donde ciertos valores incluían un asterisco (*) que indicaba datos provenientes de totales nacionales o información agregada sin desglose geográfico.

Debido a la falta de granularidad y confiabilidad en estas filas, y para mantener la coherencia con decisiones anteriores (como no trabajar con totales nacionales), se decidió eliminarlas. Estas filas representaban un 7.2% del total de datos, un porcentaje suficientemente bajo como para no comprometer la representatividad del análisis.

Este paso garantiza que los resultados reflejen únicamente datos precisos y consistentes, lo que es fundamental para la validez de los análisis y proyecciones posteriores.  


###  Análisis de tendencias a lo largo del tiempo  

El gráfico presenta las tendencias de adopción de tecnologías de acceso a internet en Argentina durante el período 2014-2024, desglosadas por ADSL, Cablemodem y Fibra Óptica. Los aspectos destacados son:

**Fibra Óptica como tecnología emergente:** Desde 2018, se aprecia un crecimiento sostenido en los accesos a Fibra Óptica, que supera a las tecnologías tradicionales hacia 2022. Esto indica una transición hacia soluciones de mayor capacidad y velocidad.

**Estancamiento de ADSL:** Los accesos a ADSL se mantienen estables, con una ligera tendencia a la baja en los años recientes, lo que refleja su posible obsolescencia frente a alternativas más modernas.

**Comportamiento de Cablemodem:** Aunque esta tecnología muestra un crecimiento inicial, alcanza una meseta y presenta fluctuaciones leves, sugiriendo que ha alcanzado su máxima penetración en el mercado.

**Desviaciones representadas:** Las bandas sombreadas alrededor de las líneas representan la variabilidad de los datos, mostrando una menor dispersión en tecnologías tradicionales y mayor incertidumbre en la adopción de Fibra Óptica durante los primeros años.

**Conclusión:** El gráfico evidencia una transición tecnológica hacia soluciones más avanzadas como Fibra Óptica, impulsada posiblemente por cambios en la infraestructura y la demanda de conexiones de alta velocidad. Este análisis es clave para entender las dinámicas de modernización en el sector de telecomunicaciones.


### Análisis de desviaciones temporales en accesos a las tecnologías   

El gráfico analiza las variaciones en el acceso a internet por tipo de tecnología entre 2014 y 2024, indicando cambios importantes en la preferencia tecnológica. Las principales observaciones son:

**Transición a Fibra Óptica:** A partir de 2020, se aprecia un incremento exponencial en los accesos a internet por Fibra Óptica, alcanzando su punto máximo entre 2021 y 2022. Este comportamiento sugiere una mayor adopción de tecnologías de alta velocidad, posiblemente impulsada por la necesidad de conectividad durante la pandemia.

**Estabilidad en ADSL y Cablemodem:** Estas tecnologías muestran un comportamiento plano a lo largo del tiempo, lo que podría indicar que su uso ha alcanzado una meseta o está siendo desplazado por alternativas más modernas.

**Caída posterior:** Tras el auge de Fibra Óptica en 2022, se observa una reducción en el crecimiento, lo que puede asociarse con saturación del mercado o limitaciones en la infraestructura.

**Conclusión:** El gráfico destaca la evolución tecnológica hacia servicios de mayor calidad, siendo Fibra Óptica la protagonista en los últimos años. Este cambio tiene implicaciones clave para estrategias de expansión y mejoramiento del acceso en las distintas regiones del país.



## Análisis de archivo 4: "Velocidad_provincia.csv"  

**Exploración Inicial de Datos y Limpieza**  

**Carga de Datos:** Se cargó el archivo Velocidad_provincia.csv en un DataFrame denominado df_vel para su análisis.

**Revisión de Valores Nulos:** Se realizó un chequeo de valores nulos en el conjunto de datos usando el método .isnull().sum() para asegurarnos de que no existieran valores faltantes. El resultado mostró que no había valores nulos en ninguna columna.

**Eliminación de Espacios Extra:** Se procedió a eliminar los espacios en blanco extra que pudieran existir en los nombres de las columnas y en los valores de las filas (si eran de tipo object) para evitar problemas durante el procesamiento y análisis posterior. Esto se hizo utilizando el método .str.strip() tanto para las columnas como para los valores de las columnas tipo texto.

**Revisión de Duplicados:** Se verificó la existencia de filas duplicadas con el método .duplicated().sum(). El análisis indicó que no había filas duplicadas en el conjunto de datos.

**Descripción Estadística:** Se exploró la distribución estadística básica de las columnas numéricas con el método .describe(). Los resultados mostraron un rango de velocidades de bajada desde 2.57 Mbps hasta 234.44 Mbps, con una media de 24.72 Mbps. También se identificaron los cuartiles y el valor máximo, lo que ayuda a entender la dispersión de los datos y a identificar posibles outliers.  

#### Tratamiento de outliers   

**Decisión sobre Outliers**
En este análisis, decidimos no tratar los outliers presentes en el conjunto de datos, ya que, al igual que en los archivos anteriores, se consideran necesarios para proporcionar una visión completa de los accesos a la velocidad de internet en las distintas provincias. Estos valores extremos son parte integral de la distribución de los datos y, por lo tanto, se mantendrán para garantizar la coherencia en nuestro análisis.  

**Las observaciones clave son las siguientes:**

**Alta concentración en Capital Federal y Buenos Aires:** Estas dos regiones destacan con la mayor cantidad de outliers. Esto puede estar relacionado con su elevada densidad poblacional, una amplia diversidad de usuarios y conexiones, y mayores variaciones en la calidad del servicio.

**Distribución más uniforme en el resto de las provincias:** Las demás regiones presentan un menor número de outliers, reflejando una variabilidad más moderada en las velocidades de bajada.

**Implicaciones:** La presencia de outliers puede deberse a situaciones extremas como conexiones de muy alta o baja velocidad, infraestructuras específicas o factores regionales. Decidimos mantener estos valores extremos en el análisis para reflejar mejor la diversidad de accesos en cada provincia.

**Conclusión:** Este análisis pone de manifiesto las disparidades en la calidad del servicio de internet entre regiones, con Capital Federal y Buenos Aires mostrando mayor heterogeneidad. Estos datos son esenciales para entender las variaciones extremas y su impacto en la experiencia del usuario.

#### Análisis de evolución temporal de velocidad por provincia  
 # GRAFICO DE LINEAS 
## Análisis de la Tendencia de la Velocidad de Bajada por Provincia

El gráfico titulado "Tendencia de la Velocidad Media de Bajada por Provincia a lo Largo del Tiempo" ilustra la evolución de la velocidad de bajada de internet en diversas provincias argentinas desde 2014 hasta 2024. Cada línea de color diferente representa una provincia específica, permitiendo observar cómo ha variado la velocidad media de bajada (en Mbps) en diferentes regiones a lo largo del tiempo.

### Observaciones Clave
1. **Incremento Generalizado**: Se observa un incremento generalizado en la velocidad de bajada en la mayoría de las provincias, especialmente a partir de 2018.
2. **Variabilidad entre Provincias**: Algunas provincias muestran un aumento más pronunciado que otras. Por ejemplo, las provincias representadas por las líneas roja y naranja (Buenos Aires y Capital Federal) tienen un incremento significativo en comparación con otras.
3. **Estabilidad Inicial**: Hasta aproximadamente 2016, la mayoría de las provincias muestran una velocidad de bajada relativamente estable y baja.
4. **Picos de Crecimiento**: A partir de 2018, se observan picos de crecimiento en varias provincias, lo que podría estar relacionado con inversiones en infraestructura y mejoras tecnológicas.

### Implicaciones y Recomendaciones
- **Política Pública**: Los resultados de este análisis pueden servir como base para diseñar políticas públicas orientadas a reducir la brecha digital y garantizar un acceso equitativo a internet de alta velocidad en todo el territorio nacional.
- **Inversión en Infraestructura**: Es fundamental realizar inversiones significativas en la expansión y modernización de la infraestructura de telecomunicaciones, especialmente en las áreas con menor conectividad.
- **Incentivos para Proveedores**: Se pueden implementar incentivos para que los proveedores de servicios de internet extiendan sus redes y mejoren la calidad de sus servicios en las zonas menos atendidas.
- **Estudios más Profundos**: Se recomienda realizar estudios adicionales para identificar las causas exactas de las desigualdades en la velocidad de internet y evaluar el impacto de diferentes factores, como la densidad poblacional, el tipo de tecnología utilizada y las políticas regulatorias.

### Conclusión
El análisis del gráfico de tendencia de la velocidad de bajada por provincia proporciona una visión clara de cómo ha evolucionado la conectividad a internet en Argentina en la última década. Las diferencias regionales en la velocidad de internet destacan la necesidad de políticas y inversiones específicas para mejorar la infraestructura y reducir las disparidades en el acceso a servicios de alta velocidad.  









#### Análisis de velocidad media de bajada por provincia  

El gráfico presentado visualiza de manera clara las desigualdades en la velocidad de descarga de internet a nivel provincial. Se observa una amplia variación entre las provincias, lo que sugiere una distribución heterogénea de la infraestructura y los servicios de internet en el país.

Las provincias con las velocidades más altas probablemente cuentan con una mayor inversión en infraestructura de telecomunicaciones, una mayor densidad poblacional o un acceso más fácil a las redes troncales de internet. Por el contrario, las provincias con velocidades más bajas podrían enfrentar desafíos relacionados con la geografía, la densidad poblacional, la falta de inversión o políticas regulatorias menos favorables.

Implicaciones y Recomendaciones:

**Política pública:** Los resultados de este análisis pueden servir como base para diseñar políticas públicas orientadas a reducir la brecha digital y garantizar un acceso equitativo a internet de alta velocidad en todo el territorio nacional.
**Inversión en infraestructura:** Es fundamental realizar inversiones significativas en la expansión y modernización de la infraestructura de telecomunicaciones, especialmente en las áreas con menor conectividad.
**Incentivos para proveedores:** Se pueden implementar incentivos para que los proveedores de servicios de internet extiendan sus redes y mejoren la calidad de sus servicios en las zonas menos atendidas.
**Estudios más profundos:** Se recomienda realizar estudios más detallados para identificar las causas exactas de las desigualdades en la velocidad de internet y evaluar el impacto de diferentes factores, como la densidad poblacional, el tipo de tecnología utilizada y las políticas regulatorias.  


**Conclusiones:**

La disparidad en la velocidad de internet entre las provincias es un problema que debe abordarse de manera integral y coordinada. Al reducir la brecha digital, se pueden impulsar el desarrollo económico, la educación, la innovación y la inclusión social en todo el país.



### Análisis de KPI's 

#### KPI 1: Aumentar en un 2% el acceso al servicio de internet para el próximo trimestre, cada 100 hogares, por provincia. 

En este análisis se evaluó el progreso del KPI de incremento en el acceso al servicio de internet, que establece un objetivo de aumentar el acceso en un 2% en cada 100 hogares para el próximo trimestre (comparando el primer y segundo trimestre de 2024). Tras el cálculo, los resultados muestran una situación mixta entre las provincias:

- **Provincias con disminución significativa o aumento inferior al 2%**: Buenos Aires (-1.55%), Capital Federal (-2.64%), Chaco (-5.65%), y varias otras provincias (como Corrientes, Mendoza, La Rioja, entre otras), donde el acceso ha disminuido o el incremento ha sido menor al 2%.
- **Provincias que cumplen con el KPI**: Chubut (1.70%) y Misiones (1.71%) son ejemplos de provincias que han logrado mantener o incrementar el acceso al servicio de internet en línea con el objetivo propuesto, aunque el aumento sigue siendo relativamente modesto.

Este análisis pone en evidencia que muchas provincias no lograron cumplir con el objetivo de un aumento del 2% en el acceso al servicio de internet. En particular, las provincias más pobladas, como Buenos Aires y Capital Federal, mostraron caídas en los accesos, lo que sugiere que pueden existir factores que limitan la expansión de la conectividad, como infraestructura insuficiente, dificultades en la oferta del servicio o problemas socioeconómicos locales.

Es recomendable profundizar en las causas detrás de estas caídas en el acceso y considerar estrategias para aumentar la conectividad en estas regiones críticas.

#### KPI 2: Incrementar la velocidad promedio de conexión en un 5% en las provincias con menores velocidades actuales  


Este KPI tiene como objetivo mejorar la velocidad promedio de descarga en las provincias con menor rendimiento en el primer trimestre de 2024, tomando como referencia el cuartil inferior de velocidades promedio de ese periodo. Se analizaron los datos de velocidad promedio de descarga entre el primer y segundo trimestre de 2024, y se calculó el incremento porcentual para las provincias seleccionadas.

### Resultados:
- **Cumplimiento del KPI:** 
  - Provincias que alcanzaron o superaron el incremento del 5%:
    - Chubut: 5.71%
    - La Pampa: 8.21%
    - San Juan: 5.20%
    - Santiago Del Estero: 9.02%
  - Estas provincias lograron implementar mejoras significativas en sus velocidades de descarga.

- **No cumplimiento del KPI:**
  - Provincias que no alcanzaron el 5%:
    - Santa Cruz: -5.41% (reducción en velocidad promedio)
    - Tierra Del Fuego: 2.55% (incremento insuficiente)
  - Estas provincias requieren atención prioritaria para implementar mejoras tecnológicas o de infraestructura que impulsen el rendimiento.

### Conclusión:
El análisis muestra que 4 de las 6 provincias evaluadas lograron cumplir con el KPI, representando un desempeño positivo en general. Sin embargo, Santa Cruz y Tierra Del Fuego presentan áreas de oportunidad clave para continuar cerrando la brecha de conectividad y mejorar la experiencia de los usuarios.  


#### KPI 3: Aumentar acceso de fibra óptica en un 10% en provincias con menos del 30% de penetración actual  

### Evaluación de Cumplimiento del KPI de Penetración de Fibra Óptica

En el análisis realizado, el objetivo era evaluar el cumplimiento de un KPI relacionado con la **penetración de fibra óptica** en las provincias con menos del 30% de acceso a esta tecnología. El KPI establece que se debe lograr un **aumento del 10%** en la penetración de fibra óptica durante los trimestres 1 y 2 del año 2024.

#### Resultados:

- Se analizaron 24 provincias que cumplen con el criterio de tener menos del 30% de penetración de fibra óptica al inicio de 2024.
- Para cada una de estas provincias, se calculó el aumento necesario (10%) en los accesos de fibra óptica.
- Se verificó si en al menos uno de los dos trimestres (1 y 2) de 2024 se alcanzó el objetivo de aumento.

**Resultado final:**
- **24 de 24 provincias** cumplían con el KPI de aumento de acceso a fibra óptica. Esto significa que todas las provincias bajo el análisis lograron superar el objetivo de un 10% de aumento en el acceso a fibra óptica, lo que refleja una mejora significativa en la penetración de esta tecnología en las áreas más necesitadas.

**Provincias que cumplen el KPI:**
- Buenos Aires, Capital Federal, Catamarca, Chaco, Chubut, Corrientes, Córdoba, Entre Ríos, Formosa, Jujuy, La Pampa, La Rioja, Mendoza, Misiones, Neuquén, Río Negro, Salta, San Juan, San Luis, Santa Cruz, Santa Fe, Santiago Del Estero, Tierra Del Fuego, Tucumán.

Este éxito sugiere que las políticas o esfuerzos implementados en estas provincias han sido eficaces para mejorar el acceso a la fibra óptica, contribuyendo positivamente al objetivo nacional de ampliar la conectividad en áreas de menor acceso.






## 4. Resultados y Conclusiones
Los resultados del análisis indican las provincias con menor penetración de fibra óptica y los tipos de tecnología más adoptados en diferentes localidades. Estos hallazgos ayudan a guiar las recomendaciones sobre dónde enfocar los esfuerzos para mejorar la cobertura de Internet.

### Recomendaciones:
Para mejorar la penetración de Internet en las provincias con menores tasas, se podrían implementar políticas específicas, tales como:

Incentivos fiscales para empresas de telecomunicaciones.
Programas de educación digital.
Subsidios para la adquisición de dispositivos y servicios de Internet.
Necesidad de políticas focalizadas:
Para reducir la brecha digital y garantizar el acceso universal, es crucial implementar políticas públicas focalizadas que apunten a mejorar la conectividad en las zonas con mayor carencia de acceso. Algunas acciones recomendadas incluyen:

Ampliación de la infraestructura de telecomunicaciones.
Implementación de soluciones específicas para áreas rurales o de difícil acceso.
Áreas clave de intervención:
Infraestructura: Es crucial invertir en tecnologías avanzadas como Fibra Óptica y Cablemodem en provincias con menor acceso.
Políticas Focalizadas: Implementar políticas que incentiven la adopción de tecnologías avanzadas en regiones con menor penetración.
Monitoreo Continuo: Realizar análisis periódicos para evaluar el progreso y ajustar las estrategias de implementación.
Recomendaciones para inversión en infraestructura
Basándonos en el análisis de accesos por tecnología y la identificación de provincias con baja penetración en ciertos servicios, se sugieren las siguientes acciones:

Inversión en tecnología de fibra óptica: Provincias con un acceso limitado a tecnologías avanzadas, como la fibra óptica, deben ser priorizadas para la expansión de infraestructura. Especialmente en áreas rurales o geográficamente aisladas, la falta de acceso a una conexión de alta velocidad puede ser un obstáculo para el desarrollo económico y la competitividad de la región.

Infraestructura en provincias con alta demanda: Para las provincias que muestran un crecimiento significativo en el uso de tecnologías específicas (por ejemplo, 4G o fibra), se recomienda evaluar la posibilidad de expandir la cobertura en estas áreas. La alta demanda podría indicar una oportunidad para satisfacer una necesidad insatisfecha del mercado, lo que puede generar un retorno positivo a largo plazo.

Mejoras en la conectividad para áreas marginadas: Las regiones que tienen un bajo índice de accesos tecnológicos deben recibir atención para reducir las brechas digitales. Esto no solo mejora el acceso a servicios básicos, sino que también promueve el desarrollo social y económico de las comunidades más desfavorecidas.

Estudio de casos excepcionales: Los outliers identificados, especialmente aquellos que muestran una anomalía significativa en el acceso, deben ser analizados a fondo. Pueden indicar mercados nicho o oportunidades inexploradas que no han sido atendidas por la infraestructura actual. Aprovechar estos casos excepcionales puede ser clave para la creación de nuevas oportunidades de negocio.

Estas recomendaciones buscan optimizar la distribución de la infraestructura tecnológica, asegurando que las regiones con más necesidades o potencial sean las que reciban atención prioritaria.

### Recomendaciones de Inversión
Basándose en los resultados obtenidos, se recomienda priorizar la inversión en infraestructura de telecomunicaciones en las provincias con menor número de accesos, especialmente en aquellas donde la tecnología de fibra óptica presenta una menor penetración. En particular, Tierra del Fuego y La Rioja deberían ser las principales candidatas para recibir inversiones adicionales.

Los resultados del análisis muestran una distribución desigual de los accesos a tecnologías de la información y comunicación entre las provincias analizadas. La presencia de una brecha digital significativa, especialmente en lo que respecta a la tecnología de fibra óptica, subraya la necesidad de políticas públicas y estrategias de inversión que promuevan la equidad en el acceso a servicios de telecomunicaciones.

Se recomienda enfocar la inversión en el despliegue de redes de fibra óptica, lo que permitiría mejorar la calidad y velocidad de los servicios de internet, así como ampliar la cobertura en áreas rurales y remotas.

Es importante tener en cuenta que este análisis se basa en una muestra limitada de datos. Para tomar decisiones de inversión más precisas, se recomienda realizar un estudio más exhaustivo que incluya un mayor número de provincias, tecnologías, así como variables socioeconómicas y geográficas relevantes.  

### Conclusiones
Desigualdad en la Penetración de Tecnología por Provincia: El análisis ha revelado una distribución desigual en la penetración de tecnologías de acceso a Internet, especialmente en lo que respecta a la fibra óptica. Algunas provincias, como Tierra del Fuego y La Rioja, muestran una penetración significativamente baja, lo que sugiere la necesidad urgente de políticas focalizadas para mejorar la conectividad en estas áreas.

Cumplimiento de los KPI en el 2024: El análisis de los trimestres 1 y 2 del 2024 ha demostrado que todas las provincias que presentan una penetración inferior al 30% de fibra óptica han cumplido con el objetivo de aumento del 10% en el acceso a esta tecnología. Esto sugiere que los esfuerzos y políticas implementadas hasta la fecha han tenido un impacto positivo.

Identificación de Áreas de Alta Demanda: El estudio de las tecnologías más utilizadas ha puesto de manifiesto un aumento en la demanda de tecnologías como la fibra óptica en algunas provincias. Esto representa una oportunidad para expandir y mejorar la infraestructura de telecomunicaciones en áreas con alta demanda, lo que puede generar un retorno positivo a largo plazo.

Necesidad de Inversión en Infraestructura: Es evidente que algunas provincias, especialmente las rurales o geográficamente aisladas, requieren una mayor inversión en infraestructura tecnológica, principalmente en fibra óptica. La expansión de esta tecnología permitirá mejorar la calidad del acceso a Internet y reducir la brecha digital entre las regiones más desarrolladas y las más desfavorecidas.

Importancia de las Políticas Públicas Focalizadas: Para lograr una reducción significativa de la brecha digital, es esencial implementar políticas públicas que promuevan la adopción de tecnologías avanzadas en las provincias con menor penetración. Estas políticas deben incluir incentivos fiscales, programas de educación digital y subsidios para la adquisición de dispositivos y servicios.

Monitoreo Continuo para Ajuste de Estrategias: Finalmente, se concluye que es crucial realizar análisis periódicos para evaluar el progreso de las políticas implementadas y ajustar las estrategias de inversión en telecomunicaciones según los resultados obtenidos. Un monitoreo continuo garantizará que las inversiones se realicen de manera eficiente y se ajusten a las necesidades cambiantes de las provincias.

## 5. Instrucciones de Instalación
Requisitos Previos:
Asegúrate de tener Python 3 y las bibliotecas necesarias instaladas (pandas, matplotlib, seaborn).

Clonación del Repositorio:
Descarga el proyecto con el siguiente comando:

Copiar código
git clone [\[enlace al repositorio\]  ](https://github.com/marianaballardini/Data-Analytics.git)


Instalación de Dependencias:
Instala las dependencias con el siguiente comando:

Copiar código
pip install -r requirements.txt  

## 6. Contribución
Se anima a otros a contribuir al proyecto reportando errores, sugiriendo mejoras o implementando nuevas funcionalidades. Para contribuir, crea un pull request o reporta un issue en el repositorio.

## 7. Licencia
Este proyecto está distribuido bajo la Licencia MIT.

