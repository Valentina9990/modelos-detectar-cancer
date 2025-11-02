# 🧬 Clasificación de Cáncer de Mama — UCI Breast Cancer Wisconsin Diagnostic

Este proyecto implementa y compara varios modelos de **Machine Learning** para la clasificación de tumores **benignos o malignos** utilizando el conjunto de datos **Breast Cancer Wisconsin (Diagnostic)** del repositorio de **UCI Machine Learning Repository**.

---

## 📚 Descripción del Proyecto

El objetivo del proyecto es construir un pipeline de **preprocesamiento, entrenamiento, evaluación y comparación de modelos de clasificación**, aplicando diferentes algoritmos supervisados:

- **Árbol de Decisión**
- **Random Forest**
- **Random Forest Optimizado (GridSearchCV)**
- **SVM (Support Vector Machine)**
- **K-Nearest Neighbors (KNN)**
- **Naive Bayes**

Se utilizan métricas de rendimiento como **Accuracy**, **Precision**, **Recall** y **F1-score**, y finalmente se comparan los modelos mediante la librería **CompStats**.

---

## ⚙️ Requisitos

Asegúrate de tener instaladas las siguientes dependencias antes de ejecutar el proyecto:

```bash
pip install ucimlrepo scikit-learn pandas matplotlib numpy statsmodels CompStats
