Clasificación de Ingresos con Árboles de Decisión y Random Forest
==================================================================

Este proyecto analiza y predice el nivel de ingresos de individuos utilizando técnicas de Machine Learning, específicamente Árboles de Decisión y Random Forest, sobre el dataset Adult Income (https://www.kaggle.com/datasets/wenruliu/adult-income-dataset).  
Se incluye un **informe completo** en PDF: `Clasificación_de_Ingresos_con_Árboles-de_Decisión_y_Random_Forest.pdf` adjuntado en el repositorio.

Estructura del proyecto
-----------------------

project/
│
├── data/
│   ├── raw/                 # Dataset original sin procesar
│   └── processed/           # Dataset limpio y listo para modelado
│
├── notebooks/
│   ├── 01_eda.ipynb         # Análisis exploratorio de datos
│   ├── 02_preprocessing.ipynb  # Limpieza y preprocesamiento
│   └── 03_modeling.ipynb    # Entrenamiento y evaluación de modelos
│
├── models/                  # Modelos entrenados exportados
│   ├── decision_tree.joblib
│   └── random_forest.joblib
│
├── Clasificación_de_Ingresos_con_Árboles-de_Decisión_y_Random_Forest.pdf  # Informe completo
├── requirements.txt         # Dependencias del proyecto
└── README.md

Requisitos
----------

Para instalar las dependencias:

pip install -r requirements.txt

Dependencias principales:

- Python 3.10+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- joblib

Uso del proyecto
----------------

1. **Análisis exploratorio (EDA)**  
   Ejecutar `01_eda.ipynb` para explorar la distribución de variables, detectar valores faltantes y visualizar patrones en el dataset.

2. **Preprocesamiento de datos**  
   Ejecutar `02_preprocessing.ipynb` para:
   - Eliminar duplicados y valores nulos
   - Codificar variables categóricas
   - Guardar el dataset limpio en `data/processed/adult_clean.csv`

3. **Entrenamiento y evaluación de modelos**  
   Ejecutar `03_modeling.ipynb` para:
   - Entrenar Árbol de Decisión y Random Forest
   - Evaluar rendimiento con métricas de precisión, recall, F1-score y exactitud
   - Visualizar matrices de confusión
   - Guardar modelos entrenados en `models/`

4. **Cargar modelos y hacer predicciones**

from joblib import load

dtc = load('models/decision_tree.joblib')
rf = load('models/random_forest.joblib')

predicciones = dtc.predict(X_nuevo)

Informe completo
----------------

Se adjunta el informe PDF `Clasificación_de_Ingresos_con_Árboles-de_Decisión_y_Random_Forest.pdf` que cubre:
- Justificación del preprocesamiento y selección de variables
- Exploración de datos y gráficos relevantes
- Comparativa de modelos y métricas
- Conclusiones y recomendaciones

Conclusiones
------------

- Las variables más relevantes para predecir ingresos son: estado civil, educación, ganancias de capital, edad, y características laborales como workclass y ocupación.  
- Ambos modelos identifican correctamente ingresos bajos, pero tienen dificultades para predecir ingresos altos debido al desbalance de clases.  
- Árbol de Decisión: más interpretable  
- Random Forest: más robusto y ligeramente mejor en la clase minoritaria  

Referencias
-----------

- Dataset Adult Income: https://www.kaggle.com/datasets/wenruliu/adult-income-dataset 
- Documentación scikit-learn: https://scikit-learn.org

Este proyecto está disponible bajo la licencia MIT.
