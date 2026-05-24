# Determinantes socioeconómicos de la Pobreza Municipal en México 2020
Resumen rapido de nuestro proyecto en la materia de Econometría

## Introducción del Repositorio
<p>
En este repositorio se adjuntan dos proyectos organizados en carpetas separadas: "Rendimiento Académico" y "Pobreza Municipal".
</p>

• El primer proyecto "Rendimiento academico" buscaba analizar los factores del rendimiento escolar universitario, pero los resultados obtenidos fueron débiles (baja capacidad explicativa, falta de significancia estadística). Por esta razón, se dejó de trabajar con ese proyecto y se reestructuró el trabajo hacia un segundo proyecto final.

• El proyecto final "Pobreza municipal" analiza los determinantes de la pobreza municipal en México utilizando datos oficiales de CONEVAL y CONAPO, aplicando un modelo de regresión para medir el impacto de las carencias sociales sobre la pobreza.

<p>
Fuera de las dos carpetas se encuentra este README.md (con la introducción, indicaciones para correr el trabajo final, roles de los integrantes y paqueterías necesarias), así como un Reporte "Proyecto_final2 que resume los resultados obtenidos de los proyectos.
</p>

## Cómo reproducir (comandos).

### 1. Subir el archivo que dejamos en este repositorio a Colab

Primero es necesario entrar a la página oficial de Google Colab a través de:  
https://colab.research.google.com/  
E iniciar sesión con tu cuenta de Google.

#### 1.1. En Colab selecciona:

• Archivo →Subir notebook

#### 1.2. Busca el archivo del proyecto con extensión .ipynb.

#### 1.3. Espera a que cargue.

Cuando termine, aparecerán varias celdas con código.

### 2. Subir la base de datos a Google Drive

Para que nuestro código que se subió en la parte 1 pueda leer el archivo Excel, primero se debe subir a Drive

#### 2.1. Abrimos Drive desde el link:

https://drive.google.com/drive/home

#### 2.2. Dar clic en:

• Nuevo → Subir archivo

#### 2.3. Selecciona la base de datos descargada aquí en el repositorio “base_pobreza_2020 (1) (1) (1).xlsx”

#### 2.4. Y esperar a que se termine de subir.

### 3. Ya dentro del . ipynb que subimos, hay que darle permiso al notebook para leer archivos de Drive.

#### 3.1. Ejecutamos la línea de código con el botón que aparece a la izquierda.

```python
from google.colab import drive
drive.mount('/content/drive')
```

#### 3.2. Se abrirá un enlace.

#### 3.3. Da permisos a Google Colab.

### 4. Obtener la ruta del archivo.

#### 4.1. En el menú izquierdo de Colab abre la carpeta.

#### 4.2. Entra a:

• Drive → MyDrive

#### 4.3. Busca el archivo Excel que subiste.

#### 4.4. Da clic derecho sobre el archivo.

#### 4.5. Selecciona:

• Copiar ruta

### 5. Pegar la ruta en el código

#### 5.1. Busca en el notebook la línea

```python
base = pd.read_excel("")
base.head()
```

#### 5.2. Dentro de las comillas (“”) pega tu ruta de acceso

### 6. Instalar librerías necesarias

#### 6.1. Busca la celda

```python
# Tratamiento dedatos
import pandas as pd
import numpy as np

#Graficos
import matplotlib.pyplot as plt
from matplotlib import style
import seaborn as sns

#Procesado y modelado
from scipy.stats import pearsonr
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import r2_score
from sklearn.metrics import mean_squared_error
import statsmodels.api as sm
import statsmodels.formula.api as smf
from scipy import stats
import statsmodels as sms

#from sklearn.datasets import load_boston
#from sklearn.datasets import fetch_california_housing
#from sklearn.datasets import fetch_openml

from statsmodels.stats.outliers_influence import variance_inflation_factor # para calcular el VIF

# configuración de matplotlib
plt.rcParams['image.cmap']="bwr"
plt.rcParams['figure.dpi']="100"
plt.rcParams['savefig.bbox']="tight"

style.use('ggplot') or plt.style.use('ggplot')

# configuración de warnings
import warnings
warnings.filterwarnings('ignore')

from matplotlib.pyplot import subplots
from statsmodels.api import OLS
import sklearn.model_selection as skm
import sklearn.linear_model as skl
from sklearn.preprocessing import StandardScaler
from ISLP import load_data
from ISLP.models import ModelSpec as MS
from functools import partial
from sklearn.pipeline import Pipeline
from sklearn.decomposition import PCA
from sklearn.cross_decomposition import PLSRegression

from ISLP.models import \
(Stepwise ,
sklearn_selected ,
sklearn_selection_path)

from l0bnb import fit_path
```

#### 6.2. Solo hace falta ejecutarla Ctrl + Enter

### 7. Ejecutar todas las celdas

#### 7.1. en orden de arriba hacia abajo se ejecuta celda por celda


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

