# Determinantes socioeconómicos de la Pobreza Municipal en México 2020
Resumen rapido de nuestro proyecto en la materia de Econometría

## Fuente y Descripción de la Base de Datos
<p>
Para realizar el análisis de los determinantes de la pobreza municipal, combinamos dos fuentes de información oficiales y de acceso público, obtenidas a través de la Plataforma Nacional de Datos Abiertos:
</p>

•	Base de Datos de Pobreza Municipal (CONEVAL): Se utilizó el concentrado histórico de indicadores de pobreza multidimensional a nivel municipal (desagregado por año y sexo). Estos datos corresponden a las estimaciones oficiales de los años 2010, 2015 y 2020, calculadas bajo los lineamientos institucionales del CONEVAL.

•	Indicadores de Marginación 2020 (CONAPO): Se descargó la base que contiene las variables socioeconómicas y estructurales utilizadas para construir el Índice de Marginación más reciente.

<p>
Ambas bases de datos originales cubren el total de los 2,466 municipios que integran el territorio mexicano, lo que garantiza que el modelo trabaje con todas las observaciones.
</p>

###  justificación de Variables
<p>
La justificación teórica y económica para la inclusión de cada una de estas variables independientes en el modelo base se detalla a continuación:
</p>

•	Educación (ANALF y SBASC): El rezago educativo es una de las carencias sociales más importantes. La falta de alfabetización  y de educación básica  limita el acceso a empleos formales, bien remunerados y con seguridad social. Estas variables explican la trampa intergeneracional de la pobreza: "A menor preparación, menores ingresos futuros".

•	Vivienda (OVSPS, VHAC, OVSDE y OVSAE): El piso de tierra es históricamente uno de los indicadores más robustos y sensibles de la pobreza extrema en México, estando directamente asociado con problemas de salud insalubre y una falta severa de inversión patrimonial.

El hacinamiento  refleja la incapacidad económica de los hogares para expandir su vivienda conforme crece la familia, afectando discretamente la calidad de vida y la privacidad.
    
La carencia de drenaje y agua entubada miden la infraestructura pública y el bienestar sanitario. Al no depender del ingreso del individuo sino de la inversión del Estado, son indicadores puros de "Pobreza estructural" rural y periurbana.

•	Distribución de la Población (PL_5000): Esta variable capta la dispersión poblacional en México. Las localidades rurales de menos de 5,000 habitantes sufren de altos costos de transporte, falta de mercados competitivos y difícil acceso a clínicas y escuelas de nivel medio-superior, existiendo una correlación histórica altísima entre ruralidad y pobreza.

•	Ingresos (PO2sm): El ingreso es el eje económico de la pobreza. En México, percibir dos salarios mínimos o menos para una familia promedio condena al hogar a mantenerse por debajo de la canasta alimentaria y no alimentaria, capturando la precarización laboral y el peso de la economía informal.

•	Marginación (GM_Bajo, GM_Medio, GM_Alto y GM_Muy\_Alto): Estas variables absorben el impacto de la exclusión social regional. Al segmentar el Grado de Marginación en variables dicotómicas, el modelo no solo analiza los factores individuales del hogar, sino que pondera el entorno socioeconómico general de la región donde viven.

## Cómo reproducir (comandos).

```
import numpy as np
import pandas as pd
import statsmodels.api as sm
import matplotlib.pyplot as plt
```


## Roles y estructura del repositorio.

<p>
En el desarrollo del proyecto se asignaron roles específicos a cada integrante con el fin de asegurar una adecuada organización del trabajo, así como la correcta ejecución metodológica, técnica y analítica del modelo de regresión lineal múltiple. A continuación, se describen las responsabilidades de cada miembro del equipo:
<p>

- ##### Líder del proyecto: Alejandra Sánchez Luna
> Es responsable de la dirección general del proyecto y de la coherencia metodológica. Entre sus funciones se encuentran la definición de la pregunta de investigación, la formulación de las hipótesis con sustento teórico y la especificación del modelo base. Asimismo, coordina al equipo, da seguimiento al cronograma de trabajo y supervisa que los resultados obtenidos tengan sentido económico o financiero. También valida la integración final del documento y la presentación.
- ##### Data Engineer: Ismael Morales Solís
>Se encarga de la adquisición, limpieza y preparación de los datos. Sus funciones incluyen la búsqueda y selección de fuentes de información confiables, la descarga y estructuración de la base de datos, el tratamiento de valores faltantes y la detección de inconsistencias. Además, identifica outliers preliminares, elabora el diccionario de variables (definición, tipo y unidad de medida) y genera el conjunto de datos final listo para el modelado, documentando todo el proceso.
- ##### Modelador: Luis A. Mariscal Armenta
>Es responsable de la construcción y estimación de los modelos econométricos. Sus tareas incluyen la implementación del modelo de regresión lineal múltiple (MCO) en Python, la selección de variables explicativas y el ajuste de la especificación del modelo. También desarrolla modelos alternativos (transformaciones logarítmicas, polinomios, variables dummy o interacciones), interpreta los coeficientes estimados y compara modelos mediante métricas como R², RMSE y MAE.
- ##### Validación y diagnóstico: Maryangel Vázquez Alavez
>Tiene a su cargo la evaluación estadística del modelo. Realiza el análisis de multicolinealidad mediante el cálculo del VIF y matrices de correlación, así como pruebas de heterocedasticidad como Breusch-Pagan o White. Además, evalúa la correcta especificación del modelo con la prueba de Ramsey RESET y detecta observaciones influyentes mediante indicadores como Cook’s Distance, leverage y DFBetas. Propone ajustes como el uso de errores robustos y analiza la validez general del modelo.
- ##### Visualización y narrativa: Ariadna Díaz Durán
>Es responsable de la presentación visual y la comunicación de los resultados. Elabora gráficos del análisis exploratorio de datos (distribuciones, correlaciones y outliers), diseña tablas claras de resultados y traduce los hallazgos técnicos a un lenguaje accesible. También desarrolla la presentación en diapositivas, construye la narrativa del proyecto y apoya en la redacción del documento final, así como en la preparación del contenido visual para el video.
- ##### Reproducibilidad y QA: Samuel González Islas
> Se encarga de garantizar la correcta estructura y funcionamiento técnico del proyecto. Organiza el repositorio (carpetas, datos y notebooks), elabora y mantiene el archivo README, y genera el archivo de dependencias (requirements.txt). Además, asegura que el proyecto sea reproducible, verificando que el código se ejecute sin errores en distintos entornos. También lleva el control de versiones mediante Git, revisa la consistencia y claridad del código, y establece un flujo de ejecución ordenado para facilitar su uso.

## Dependencias (pip install -r requirements.txt).

<p>
Para la correcta ejecución del proyecto, es necesario instalar previamente las librerías utilizadas en el desarrollo del análisis y la estimación del modelo. Estas dependencias se encuentran especificadas en el archivo requirements.txt, lo que permite su instalación automática mediante el uso del siguiente comando en la terminal:
pip install -r requirements.txt

Las principales librerías empleadas en el proyecto son las siguientes:
<p>

- pandas: utilizada para la manipulación, limpieza y estructuración de los datos.
- numpy: empleada para operaciones numéricas y manejo de arreglos.
- scipy: utilizada para funciones estadísticas y pruebas complementarias.
- statsmodels: empleada para la estimación del modelo de regresión lineal múltiple y la realización de pruebas econométricas.
- scikit-learn (sklearn.metrics): utilizada para la evaluación del modelo mediante métricas como RMSE y MAE.
- matplotlib: utilizada para la generación de gráficos y visualización de resultados. 

<p>
El uso del archivo requirements.txt garantiza la reproducibilidad del proyecto, permitiendo que cualquier usuario pueda instalar las mismas versiones de las librerías y ejecutar el código sin inconvenientes.
<p>

