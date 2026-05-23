# Determinantes-socioecon-micos-de-la-Pobreza-Municipal-en-M-xico-2020
Resumen final de nuestro proyecto en la materia de Econometría

# Introducción

## Antecedentes
<P>
  La primera fase de este proyecto se centró en el análisis del "Rendimiento Académico Universitario" mediante modelos econométricos basados en encuestas digitales aplicadas a estudiantes. A pesar de incrementar la muestra de 151 a 337 observaciones tras una segunda emisión del cuestionario, los resultados evidenciaron serios problemas estructurales y de especificación. El principal inconveniente radica en la baja capacidad explicativa del modelo. El coeficiente de determinación  $R^2$  alcanzó apenas un 0.018, indicando que menos del 2% de la variabilidad del promedio académico es explicada por las variables independientes incluidas.

Asimismo, la prueba F global no resultó estadísticamente significativa , lo que invalida la hipótesis general del proyecto al no existir evidencia conjunta de que las variables explicativas afecten al rendimiento académico. A nivel individual, la mayoría de los regresores (como estrés, horas de sueño, redes sociales o trabajo) carecen de significancia estadística; únicamente las variables "Horas de estudio" y "Tiempo de traslado" mostraron significancia en la primera etapa, pero la perdieron por completo al consolidar la muestra final. 

Adicionalmente, la prueba de Shapiro-Wilk rechazó la normalidad de los residuos, afectando la confiabilidad de los intervalos de confianza. La aplicación de transformaciones funcionales (como Box-Cox y modelos log-lineales) no generó mejoras significativas.

Esto demuestra que el problema no deriva de la forma funcional, sino de las limitaciones intrínsecas de la base de datos, caracterizada por variables subjetivas, perceptuales y propensas a sesgos de medición. Por consiguiente, para evitar conclusiones econométricas débiles, se decidió reestructurar el trabajo y cambiar el enfoque hacia el estudio de los determinantes socioeconómicos de la pobreza municipal en México, lo cual ofrece un marco teórico más robusto, mayor objetividad de los datos y viabilidad para diagnósticos econométricos completos.
</P>


## Hipotesis General
<p>
  La hipótesis general que buscamos probar es que todos los factores sociodemográficos que consideramos explican el modelo de manera significativa el porcentaje de pobreza, es decir: 
<p>
  
$$
H_0 : \beta_1 = \beta_2 = \dots = \beta_k = 0 \quad vs \quad H_1 : \exists \beta_k \neq 0
$$

### Hipótesis indivduales
<p>
  Por otro lado, las hipótesis individuales que deseamos probar sobre el efecto de las variables explicativas en la pobreza son las siguientes: 
</p>

•	Se espera que el analfabetismo tenga un efecto positivo sobre el porcentaje de pobreza, ya que menores niveles educativos reducen las oportunidades económicas de la población. 

•	Esperamos que las variables relacionadas con carencias en la vivienda, como servicios básicos insuficientes, hacinamiento, sobreocupación y viviendas con piso de tierra, tengan un efecto positivo debido a que reflejan condiciones de rezago social.

•	Asimismo, se espera que la población ocupada con ingresos de hasta dos salarios mínimos tenga una relación positiva con la pobreza, ya que bajos niveles salariales limitan el acceso a mejores condiciones de vida.

•	También se espera que las localidades menores a 5,000 habitantes presenten mayores niveles de pobreza debido al menor acceso a infraestructura y oportunidades económicas.

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

