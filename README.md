# 📊 Telecom X – Predicción de Cancelación de Clientes (Churn)

Este proyecto corresponde a la **segunda etapa** del desafío de análisis de datos para la empresa ficticia **Telecom X**, enfocado en construir modelos de machine learning que predigan la cancelación de servicios por parte de los clientes (**churn**).

## 🎯 Objetivos del Proyecto

- Preparar y transformar los datos para el modelado.
- Analizar la correlación entre variables y su impacto en la cancelación.
- Entrenar y evaluar distintos modelos de clasificación.
- Interpretar la importancia de variables predictoras.
- Generar conclusiones y recomendaciones estratégicas.

---

## 📁 Dataset

Se utiliza el archivo `datos_tratados (1).csv`, previamente depurado en la Parte 1 del desafío. Este dataset contiene información estructurada y estandarizada de clientes, incluyendo:

- Tipo de contrato
- Método de pago
- Servicios contratados
- Soporte técnico
- Gastos mensuales y totales
- Variable objetivo: `Churn` (cancelación)

---

## 🧹 Preprocesamiento

1. **Eliminación de columnas irrelevantes:** Se descarta `customerID` por ser un identificador único que no aporta valor predictivo.
2. **Codificación de variables categóricas:** Se aplica `pd.get_dummies()` con `drop_first=True` para transformar variables categóricas a formato numérico binario, evitando multicolinealidad.
3. **Normalización:** Se aplica `StandardScaler()` para modelos sensibles a escala (como regresión logística).
4. **Balanceo de clases (opcional):** Se emplea **SMOTE** si se detecta fuerte desbalance entre clases.

---

## 🔍 Análisis Exploratorio

- Se visualiza la distribución de cancelaciones (`Churn`).
- Se calcula la matriz de correlación para identificar variables relevantes.
- Se visualizan patrones entre `Churn` y variables como `MonthlyCharges`, `Contract` o `PaymentMethod`.

---

## 🤖 Modelado

Se entrenaron dos modelos:

### 1. **Regresión Logística** (requiere normalización)

- Entrenamiento sobre datos escalados.
- Métricas evaluadas: `Accuracy`, `Precision`, `Recall`, `F1-score`.
- Interpretación de coeficientes.

### 2. **Random Forest** (no requiere normalización)

- Entrenamiento sobre datos originales.
- Se obtiene la importancia de variables.
- Se evita overfitting mediante evaluación sobre set de test.

---

## 📊 Métricas de Evaluación

Para ambos modelos se evalúa:

- Matriz de confusión
- Accuracy
- Precision
- Recall
- F1-score

Además, se comparan los modelos en términos de balance entre sensibilidad y especificidad.

---

## 🔎 Análisis de Variables Relevantes

- En Regresión Logística se analizan los coeficientes.
- En Random Forest se grafican las variables más importantes por ganancia de información.

---

## 📈 Conclusiones Estratégicas

- Clientes con **contratos mensuales**, sin **pago automático** y con **soporte técnico deficiente** son más propensos a cancelar.
- **Random Forest** ofrece mejor desempeño general, pero Regresión Logística entrega mayor interpretabilidad.
- La empresa puede:
  - Incentivar contratos a largo plazo.
  - Promover el pago automático con descuentos.
  - Mejorar el soporte técnico.
  - Usar este modelo en su CRM para identificar clientes en riesgo.

---

## 🛠 Herramientas Utilizadas

- Python (Google Colab)
- Pandas, Numpy
- Scikit-learn
- Seaborn, Matplotlib
- imbalanced-learn (SMOTE)

---

## 🚀 Autor

Proyecto realizado por Marcela Arce como parte del desafío de aprendizaje de análisis de datos para **Telecom X** – Etapa 2: Predicción.

