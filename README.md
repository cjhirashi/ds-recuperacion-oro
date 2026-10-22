# 📊 Optimización de Recuperación de Oro

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML%20Models-orange?logo=scikitlearn)](https://scikit-learn.org/stable/)
[![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue?logo=numpy)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue?logo=matplotlib)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Visualization-blue?logo=seaborn)](https://seaborn.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)

---

## 🚀 Descripción

Proyecto de Machine Learning para la **optimización de procesos industriales de recuperación de oro** mediante la predicción de eficiencia en las etapas de flotación y purificación. El modelo predice la recuperación de oro tanto en el concentrado rougher como en el concentrado final, utilizando datos de sensores del proceso minero y parámetros operacionales.

El proyecto implementa la métrica **sMAPE (Symmetric Mean Absolute Percentage Error)** con ponderación específica para el dominio minero, donde la recuperación final tiene mayor importancia (75%) que la recuperación rougher (25%).

---

## ✨ Instrucciones y Objetivos del proyecto

* **Preparación de datos**: Validar la consistencia de los cálculos de recuperación usando las fórmulas del dominio industrial
* **Análisis exploratorio**: Examinar concentraciones de metales (Au, Ag, Pb) a través de las etapas del proceso
* **Validación de distribuciones**: Comparar distribuciones entre conjuntos de entrenamiento y prueba para garantizar validez del modelo
* **Detección de anomalías**: Identificar y tratar valores anómalos en concentraciones totales de sustancias
* **Modelado predictivo**: Entrenar modelos para predecir recuperación en ambas etapas del proceso
* **Evaluación con métricas personalizadas**: Implementar sMAPE ponderado específico para el proceso minero
* **Validación cruzada**: Evaluar modelos mediante técnicas robustas de validación

---

## 🧰 Tecnologías utilizadas

* [Python 3.11](https://www.python.org/)
* [Pandas](https://pandas.pydata.org/)
* [NumPy](https://numpy.org/)
* [Scikit-Learn](https://scikit-learn.org/stable/)
* [Matplotlib](https://matplotlib.org/)
* [Seaborn](https://seaborn.pydata.org/)
* [Jupyter Notebook](https://jupyter.org/)
* [Conda](https://docs.conda.io/) — gestión de entornos y dependencias

---

## ✅ PASOS DEL PROYECTO

### 📑 Pasos en el Notebook

**Sección 1: Introducción y Configuración**

* 1.1 Objetivo del proyecto y contexto del proceso minero
* 1.2 Importación de librerías, configuración visual y versiones

**Sección 2: Preparación de Datos**

* 2.1 Carga y exploración inicial de datasets
* 2.2 Validación de cálculos de recuperación
* 2.3 Análisis de características faltantes en conjunto de prueba
* 2.4 Preprocesamiento de datos

**Sección 3: Análisis Exploratorio de Datos**

* 3.1 Evolución de concentraciones metálicas por etapa
* 3.2 Comparación de distribuciones entre conjuntos
* 3.3 Análisis de concentraciones totales y detección de anomalías

**Sección 4: Construcción del Modelo**

* 4.1 Implementación de función sMAPE personalizada
* 4.2 Entrenamiento y evaluación de múltiples modelos
* 4.3 Selección del mejor modelo y evaluación final

---

### ⚙️ Pasos previstos para `src/`

* **`data_preprocessing.py`**
  Funciones para carga, limpieza, validación de fórmulas de recuperación y preprocesamiento de datos mineros

* **`eda_functions.py`**
  Funciones para análisis exploratorio, visualizaciones de concentraciones metálicas y detección de anomalías

* **`model_evaluation.py`**
  Implementación de sMAPE ponderado, funciones de validación cruzada y evaluación de modelos

* **`recovery_calculations.py`**
  Funciones para cálculo y validación de recuperación de oro según fórmulas del proceso industrial

---

## ⚙️ Estructura del proyecto

```bash
.
├── datasets/
│   ├── gold_recovery_train.csv      # Dataset de entrenamiento
│   ├── gold_recovery_test.csv       # Dataset de prueba
│   └── gold_recovery_full.csv       # Dataset completo fuente
├── notebooks/
│   └── gold_recovery_analysis.ipynb # Notebook principal con análisis y modelos
├── src/
│   ├── data_preprocessing.py        # Funciones de preprocesamiento
│   ├── eda_functions.py             # Funciones de análisis exploratorio
│   ├── model_evaluation.py          # Funciones de evaluación y métricas
│   └── recovery_calculations.py     # Cálculos específicos del dominio minero
├── reports/
│   └── figures/                     # Gráficos y visualizaciones
├── environment.yml                   # Archivo para recrear el entorno con conda
└── README.md
```

---

## 📑 Dataset

**Archivos principales:**

* `datasets/gold_recovery_train.csv` → Dataset de entrenamiento con variables objetivo
* `datasets/gold_recovery_test.csv` → Dataset de prueba sin variables objetivo
* `datasets/gold_recovery_full.csv` → Dataset fuente completo

**Características principales:**

* **Indexación temporal**: `date` - fecha y hora de adquisición de datos

* **Etapas del proceso**:

  * `rougher.*` → Proceso de flotación inicial
  * `primary_cleaner.*` → Primera etapa de purificación
  * `secondary_cleaner.*` → Segunda etapa de purificación
  * `final.*` → Concentrado final

* **Tipos de parámetros**:

  * `input` → Parámetros de materia prima
  * `output` → Parámetros del producto
  * `state` → Estado actual de la etapa
  * `calculation` → Características calculadas

* **Variables objetivo**:

  * `rougher.output.recovery` → Recuperación en flotación
  * `final.output.recovery` → Recuperación final

* **Metales monitoreados**: Au (oro), Ag (plata), Pb (plomo)

---

## 📊 Conclusiones y Resultados Esperados

### ✅ Conclusión general

El proyecto logró cumplir con el objetivo principal: **desarrollar un modelo de Machine Learning capaz de predecir la recuperación de oro en las etapas de flotación (rougher) y purificación final**, utilizando datos de sensores y parámetros operativos del proceso industrial.

Tras un análisis riguroso que incluyó:

* **Preparación de datos**: limpieza, validación de fórmulas de recuperación y gestión de valores faltantes.
* **Análisis exploratorio**: estudio de concentraciones de metales (Au, Ag, Pb), comparación de distribuciones entre train y test, y detección de anomalías en concentraciones totales.
* **Construcción del modelo**: implementación de la métrica **sMAPE ponderada** (25% rougher, 75% final), entrenamiento de múltiples algoritmos y evaluación comparativa.

Se determinó que el modelo **Gradient Boosting** presentó el mejor desempeño:

* **Validación (CV):** sMAPE Total = 8.29%
* **Prueba (TEST):** sMAPE Total = 10.13%

Esto implica una degradación moderada de desempeño (+1.84 pp), lo cual confirma que el modelo **generaliza adecuadamente** en datos no vistos.

**Conclusiones clave:**

* El modelo es **robusto y apto** para recomendaciones iniciales en la optimización del proceso de recuperación de oro.
* La métrica sMAPE ponderada permitió priorizar la etapa de recuperación final, alineándose con las necesidades del negocio.
* Se identificaron algunas limitaciones: pérdida de ~560 registros en el conjunto de prueba por valores faltantes en los objetivos, y posible *feature drift* entre train/test.

**Recomendaciones futuras:**

1. Ajustar hiperparámetros de Gradient Boosting (learning rate, profundidad, n_estimators).
2. Implementar validación temporal (TimeSeriesSplit) para reflejar mejor la naturaleza secuencial de los datos.
3. Analizar causas de exclusión de filas en test y considerar estrategias de imputación.
4. Evaluar la estabilidad de las variables más influyentes en la predicción.

---

## ▶️ Instalación y uso

1. **Clonar repositorio**

   ```bash
   git clone https://github.com/cjhirashi/proyecto-sprint-12.git
   ```

2. **Acceder a carpeta del proyecto**

   ```bash
   cd proyecto-sprint-12
   ```

3. **Crear entorno con Conda**

   ```bash
   conda env create -f environment.yml
   ```

4. **Activar el entorno ya creado**

   ```bash
   conda activate sprint12-gold-recovery
   ```

5. **Ejecutar Notebook**

   ```bash
   jupyter notebook notebooks/gold_recovery_analysis.ipynb
   ```

---

## ♻️ Gestión del entorno con Conda

* **Eliminar entorno**:

  ```bash
  conda env remove -n sprint12-gold-recovery
  ```

* **Recrear entorno**:

  ```bash
  conda env create -f environment.yml
  conda activate sprint12-gold-recovery
  ```

* **Desactivar entorno**:

  ```bash
  conda deactivate
  ```

---

## 👨‍💻 Autor

Carlos Jiménez Hirashi 💼 Data Scientist Jr. | Python & Machine Learning 📧 [cjhirashi@gmail.com](mailto:cjhirashi@gmail.com) · 🌐 [LinkedIn](https://www.linkedin.com/in/cjhirashi)
