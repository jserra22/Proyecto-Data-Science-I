# Análisis de Supervivencia del Titanic con Machine Learning

Este proyecto final de Data Science I analiza el famoso conjunto de datos del Titanic. El objetivo principal es determinar qué factores demográficos y socioeconómicos influyeron más en la probabilidad de supervivencia de los pasajeros, utilizando técnicas de análisis exploratorio y modelos de aprendizaje automático (Machine Learning).

## 📄 Descripción del Proyecto

El hundimiento del Titanic es uno de los naufragios más infames de la historia. Aunque hubo un elemento de suerte involucrado en sobrevivir, parece que algunos grupos de personas tenían más probabilidades de sobrevivir que otros.

Este análisis busca responder: **¿Qué tipo de personas tenían más probabilidades de sobrevivir?**

El proyecto se divide en dos etapas principales:
1.  **Análisis Exploratorio de Datos (EDA):** Visualización y entendimiento de las variables.
2.  **Modelado Predictivo:** Entrenamiento de un algoritmo para predecir la supervivencia.

## 🎯 Hipótesis

> La probabilidad de supervivencia en el Titanic estuvo significativamente influenciada por factores demográficos, especialmente la edad y el género, reflejando decisiones de evacuación y normas sociales de la época (como "mujeres y niños primero"). Además, se plantea que el estatus socioeconómico actuó como un filtro secundario.

## 🛠️ Tecnologías Utilizadas

* **Python 3**
* **Pandas & NumPy:** Para la manipulación y limpieza de datos.
* **Matplotlib & Seaborn:** Para la visualización de datos.
* **Scikit-Learn:** Para el preprocesamiento (LabelEncoder), selección de características y el modelo de clasificación (Random Forest).

## 🚀 Metodología Aplicada

### 1. Preprocesamiento de Datos
* **Limpieza:** Se imputaron los valores nulos en `Age` y `Fare` utilizando la mediana para evitar sesgos por valores atípicos.
* **Codificación:** Se transformaron variables categóricas como `Sex` a formato numérico (0/1) para su procesamiento matemático.

### 2. Selección de Características (Feature Selection)
Se utilizó la técnica de **Feature Importance** mediante un modelo de Random Forest preliminar.
* **Variables Descartadas:** `Name`, `Ticket`, `Cabin`, `Embarked`, `SibSp`, `Parch` (por su baja influencia predictiva o alta cardinalidad).
* **Variables Seleccionadas:** `Pclass`, `Sex`, `Age`, `Fare`.

### 3. Modelo de Machine Learning
Se entrenó un **Random Forest Classifier** con la siguiente configuración para asegurar generalización y evitar sobreajuste:
* `n_estimators`: 100
* `max_depth`: 5
* `test_size`: 20% (Validación)

## 📊 Resultados

El modelo final obtuvo los siguientes resultados en el conjunto de prueba:

* **Exactitud (Accuracy):** ~81%
* **Matriz de Confusión:** Mostró un buen balance entre sensibilidad y precisión, aunque con una ligera dificultad mayor para identificar falsos negativos en comparación con los positivos.

## 📝 Conclusiones

1.   **Validación del Modelo**: El modelo de Random Forest alcanzó una exactitud de aproximadamente el **81%**. Esto nos indica que es posible predecir la tasa de supervivencia de una forma fehaciente con tan solo 4 variables: Clase, Género, Edad y Tarifa.

2.   **Confirmación de Hipótesis**: El uso de las variables Género y Edad confirma que, estadísticamente, la norma social de "mujeres y niños primero" a la hora de evacuar la nave fue un factor determinante para la supervivencia de estos grupos.

3.   **Dimensión Socioeconómica de la hipótesis**: Las variables de Clase y Tarifa mostraron que los pasajeros con mayor poder adquisitivo tuvieron un acceso privilegiado a los botes salvavidas, actuando como un segundo filtro de supervivencia después del género.

---
**Autor:** Joaquin Serra
**Dataset:** Titanic - Machine Learning from Disaster (Kaggle)
