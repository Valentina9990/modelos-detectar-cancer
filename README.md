# Modelos de Detección de Cáncer de Mama

Este proyecto implementa y compara múltiples modelos de Machine Learning para la detección y clasificación de cáncer de mama utilizando el conjunto de datos "Breast Cancer Wisconsin (Diagnostic)" de la UCI Machine Learning Repository.

## 📋 Descripción del Proyecto

El proyecto realiza un análisis completo de datos y modelado predictivo para diagnosticar cáncer de mama (benigno o maligno) basándose en características extraídas de imágenes digitalizadas de aspiración con aguja fina (FNA) de masas mamarias.

## 🗂️ Dataset

- **Fuente**: UCI Machine Learning Repository (ID: 17)
- **Nombre**: Breast Cancer Wisconsin (Diagnostic)
- **Características**: 30 variables continuas que describen características de núcleos celulares
- **Variables objetivo**: Diagnóstico (Benigno/Maligno)
- **Instancias**: 569 casos
- **Valores faltantes**: No

### Características del Dataset

Las características se calculan para cada imagen de núcleo celular y describen:
- Radio (radio1, radio2, radio3)
- Textura (texture1, texture2, texture3)
- Perímetro (perimeter1, perimeter2, perimeter3)
- Área (area1, area2, area3)
- Suavidad (smoothness1, smoothness2, smoothness3)
- Compacidad (compactness1, compactness2, compactness3)
- Concavidad (concavity1, concavity2, concavity3)
- Puntos cóncavos (concave_points1, concave_points2, concave_points3)
- Simetría (symmetry1, symmetry2, symmetry3)
- Dimensión fractal (fractal_dimension1, fractal_dimension2, fractal_dimension3)

## 🤖 Modelos Implementados

El proyecto implementa y compara los siguientes algoritmos de Machine Learning:

### 1. **Decision Tree (Árbol de Decisión)**
- Criterio: Entropy
- Profundidad máxima: 3
- Mínimo de muestras por hoja: 7
- Mínimo de muestras para dividir: 2

### 2. **Random Forest (Bosque Aleatorio)**
- Número de estimadores: 1000
- Criterio: Gini
- Profundidad máxima: 3
- Máximo de características: 0.3
- Mínimo de muestras por hoja: 10

### 3. **Support Vector Machine (SVM)**
- Kernel: RBF
- C: 2
- Gamma: 0.001
- Función de decisión: OVR (One-vs-Rest)

### 4. **K-Nearest Neighbors (KNN)**
- Análisis de rendimiento con k de 1 a 20 vecinos
- Selección del valor óptimo de k basado en accuracy

### 5. **Naive Bayes Gaussiano**
- Implementación estándar de GaussianNB

### 6. **Random Forest Optimizado**
- Optimización mediante GridSearchCV
- Parámetros explorados:
  - n_estimators: [10, 20, 30, 50]
  - max_features: [0.2, 0.3, 0.5]
  - criterion: ['entropy', 'gini']
  - max_depth: [2, 3, 5, 10]
  - min_samples_split: [2, 3, 5]
  - min_samples_leaf: [1, 5, 8]

## 📊 Métricas de Evaluación

El proyecto evalúa cada modelo utilizando las siguientes métricas:

- **Accuracy**: Proporción de predicciones correctas
- **F1 Score**: Media armónica entre precisión y recall
- **Precision**: Proporción de verdaderos positivos sobre todos los positivos predichos
- **Recall**: Proporción de verdaderos positivos sobre todos los positivos reales
- **Confusion Matrix**: Matriz de confusión para cada modelo

Adicionalmente, se realiza una comparación estadística entre modelos utilizando la librería CompStats.

## 🛠️ Tecnologías y Librerías

El proyecto utiliza las siguientes herramientas:

- **Python 3.x**
- **scikit-learn**: Implementación de modelos ML y métricas
- **pandas**: Manipulación y análisis de datos
- **numpy**: Operaciones numéricas
- **matplotlib**: Visualización de datos
- **seaborn**: Visualización estadística
- **ucimlrepo**: Acceso al repositorio UCI ML
- **CompStats**: Análisis estadístico comparativo de modelos

## 🚀 Instalación y Uso

### Prerrequisitos

```bash
pip install scikit-learn pandas numpy matplotlib seaborn ucimlrepo
```

### Ejecución

1. Clona este repositorio:
```bash
git clone https://github.com/Valentina9990/modelos-detectar-cancer.git
cd modelos-detectar-cancer
```

2. Abre el notebook en Jupyter o Google Colab:
```bash
jupyter notebook ModelosCancerIA.ipynb
```

3. Ejecuta las celdas secuencialmente para:
   - Cargar y explorar el dataset
   - Preprocesar los datos (escalado con StandardScaler)
   - Entrenar cada modelo
   - Evaluar y comparar resultados

## 📈 Estructura del Proyecto

```
modelos-detectar-cancer/
│
├── ModelosCancerIA.ipynb    # Notebook principal con análisis y modelos
└── README.md                 # Este archivo
```

## 🔍 Metodología

1. **Carga de Datos**: Importación del dataset desde UCI ML Repository
2. **Análisis Exploratorio**: Identificación de variables categóricas y continuas
3. **Preprocesamiento**: 
   - Escalado de variables continuas con StandardScaler
   - Codificación de etiquetas con LabelEncoder
4. **División de Datos**: 70% entrenamiento, 30% prueba (stratified split)
5. **Entrenamiento**: Ajuste de cada modelo con sus hiperparámetros
6. **Evaluación**: Cálculo de métricas de rendimiento
7. **Optimización**: GridSearchCV para Random Forest
8. **Comparación**: Análisis estadístico entre todos los modelos

## 📝 Resultados

El notebook genera:
- Métricas de rendimiento para cada modelo
- Gráficas de comparación de accuracy para KNN
- Matrices de confusión
- Comparación estadística entre modelos usando CompStats
- Tabla concentrada con todas las predicciones

## 👥 Contribuciones

Las contribuciones son bienvenidas. Por favor, abre un issue o pull request para sugerencias y mejoras.

## 📄 Licencia

Este proyecto es de código abierto y está disponible para fines educativos y de investigación.

## 🔗 Referencias

- [UCI Machine Learning Repository - Breast Cancer Wisconsin](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)
- Dataset original: W.N. Street, W.H. Wolberg and O.L. Mangasarian (1993)
