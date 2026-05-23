# Determinantes-socioecon-micos-de-la-Pobreza-Municipal-en-M-xico-2020
Resumen final de nuestro proyecto en la materia de Econometría



Roles y estructura del repositorio.
En el desarrollo del proyecto se asignaron roles específicos a cada integrante con el fin de asegurar una adecuada organización del trabajo, así como la correcta ejecución metodológica, técnica y analítica del modelo de regresión lineal múltiple. A continuación, se describen las responsabilidades de cada miembro del equipo:


Líder del proyecto: Alejandra Sánchez Luna
Es responsable de la dirección general del proyecto y de la coherencia metodológica. Entre sus funciones se encuentran la definición de la pregunta de investigación, la formulación de las hipótesis con sustento teórico y la especificación del modelo base. Asimismo, coordina al equipo, da seguimiento al cronograma de trabajo y supervisa que los resultados obtenidos tengan sentido económico o financiero. También valida la integración final del documento y la presentación.

Data Engineer: Ismael Morales Solís
Se encarga de la adquisición, limpieza y preparación de los datos. Sus funciones incluyen la búsqueda y selección de fuentes de información confiables, la descarga y estructuración de la base de datos, el tratamiento de valores faltantes y la detección de inconsistencias. Además, identifica outliers preliminares, elabora el diccionario de variables (definición, tipo y unidad de medida) y genera el conjunto de datos final listo para el modelado, documentando todo el proceso.

Modelador: Luis A. Mariscal Armenta
Es responsable de la construcción y estimación de los modelos econométricos. Sus tareas incluyen la implementación del modelo de regresión lineal múltiple (MCO) en Python, la selección de variables explicativas y el ajuste de la especificación del modelo. También desarrolla modelos alternativos (transformaciones logarítmicas, polinomios, variables dummy o interacciones), interpreta los coeficientes estimados y compara modelos mediante métricas como R², RMSE y MAE.

Validación y diagnóstico: Maryangel Vázquez Alavez
Tiene a su cargo la evaluación estadística del modelo. Realiza el análisis de multicolinealidad mediante el cálculo del VIF y matrices de correlación, así como pruebas de heterocedasticidad como Breusch-Pagan o White. Además, evalúa la correcta especificación del modelo con la prueba de Ramsey RESET y detecta observaciones influyentes mediante indicadores como Cook’s Distance, leverage y DFBetas. Propone ajustes como el uso de errores robustos y analiza la validez general del modelo.

Visualización y narrativa: Ariadna Díaz Durán
Es responsable de la presentación visual y la comunicación de los resultados. Elabora gráficos del análisis exploratorio de datos (distribuciones, correlaciones y outliers), diseña tablas claras de resultados y traduce los hallazgos técnicos a un lenguaje accesible. También desarrolla la presentación en diapositivas, construye la narrativa del proyecto y apoya en la redacción del documento final, así como en la preparación del contenido visual para el video.

Reproducibilidad y QA: Samuel González Islas
Se encarga de garantizar la correcta estructura y funcionamiento técnico del proyecto. Organiza el repositorio (carpetas, datos y notebooks), elabora y mantiene el archivo README, y genera el archivo de dependencias (requirements.txt). Además, asegura que el proyecto sea reproducible, verificando que el código se ejecute sin errores en distintos entornos. También lleva el control de versiones mediante Git, revisa la consistencia y claridad del código, y establece un flujo de ejecución ordenado para facilitar su uso.

Dependencias (pip install -r requirements.txt).
Para la correcta ejecución del proyecto, es necesario instalar previamente las librerías utilizadas en el desarrollo del análisis y la estimación del modelo. Estas dependencias se encuentran especificadas en el archivo requirements.txt, lo que permite su instalación automática mediante el uso del siguiente comando en la terminal: pip install -r requirements.txt

Las principales librerías empleadas en el proyecto son las siguientes:


pandas: utilizada para la manipulación, limpieza y estructuración de los datos.
numpy: empleada para operaciones numéricas y manejo de arreglos.
scipy: utilizada para funciones estadísticas y pruebas complementarias.
statsmodels: empleada para la estimación del modelo de regresión lineal múltiple y la realización de pruebas econométricas.
scikit-learn (sklearn.metrics): utilizada para la evaluación del modelo mediante métricas como RMSE y MAE.
matplotlib: utilizada para la generación de gráficos y visualización de resultados.
El uso del archivo requirements.txt garantiza la reproducibilidad del proyecto, permitiendo que cualquier usuario pueda instalar las mismas versiones de las librerías y ejecutar el código sin inconvenientes.
