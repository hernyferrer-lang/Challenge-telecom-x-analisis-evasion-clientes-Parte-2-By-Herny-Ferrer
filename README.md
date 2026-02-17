# 📊 TelecomX – Predicción de Cancelación de Clientes (Churn)

## 🎯 Objetivo del Proyecto

Desarrollar un modelo predictivo capaz de identificar clientes con alta probabilidad de cancelar sus servicios, permitiendo a TelecomX anticiparse y diseñar estrategias de retención más efectivas.

---

## 🧠 Problema de Negocio

La empresa presenta una tasa de cancelación aproximada del **26.5%**, lo que impacta directamente en ingresos y costos de adquisición de nuevos clientes.

El objetivo principal fue:

> Detectar la mayor cantidad posible de clientes que probablemente cancelen (maximizar Recall en la clase churn).

---

## 🛠️ Tecnologías Utilizadas

- Python  
- Pandas  
- NumPy  
- Scikit-Learn  
- Matplotlib / Seaborn  
- Google Colab  

---

## 🔎 Pipeline de Trabajo

### 1️⃣ Preparación de Datos

- Eliminación de valores nulos en la variable objetivo.
- Eliminación de variable identificadora (`customerID`).
- Codificación de variables categóricas con OneHotEncoder.
- Normalización de variables numéricas con StandardScaler.
- División estratificada en entrenamiento y prueba (70/30).

Distribución del dataset:

- 73% No churn  
- 27% Churn  

---

### 2️⃣ Modelos Entrenados

Se implementaron dos modelos de clasificación:

- Regresión Logística  
- Random Forest  

Ambos configurados con `class_weight='balanced'` para tratar el desbalance de clases.

---

## 📈 Resultados

| Modelo | Recall (Churn) | ROC-AUC | Accuracy |
|--------|---------------|----------|----------|
| Logistic Regression | **0.80** | **0.84** | 0.73 |
| Random Forest | 0.48 | 0.82 | 0.78 |

---

## 🏆 Modelo Seleccionado

Se seleccionó **Regresión Logística**, ya que:

- Detecta el **80% de los clientes que cancelan**.
- Presenta mejor capacidad de discriminación (ROC-AUC 0.84).
- Es interpretable y adecuada para una primera etapa productiva.

Aunque Random Forest obtuvo mayor accuracy, no cumple el objetivo estratégico de maximizar la detección de churn.

---

## 🔍 Principales Factores Asociados a Cancelación

El análisis de coeficientes indicó que la probabilidad de churn aumenta principalmente cuando:

- El contrato es mensual (Month-to-month).
- La antigüedad (tenure) es baja.
- Los cargos mensuales son elevados.
- Se utilizan ciertos métodos de pago electrónicos.
- No existe contrato a largo plazo.

En cambio, contratos anuales o mayor antigüedad reducen significativamente el riesgo de cancelación.

---

## 📌 Recomendaciones Estratégicas

En base a los resultados del modelo:

1. Implementar campañas de retención temprana para clientes con menos de 6 meses.
2. Incentivar contratos anuales o bianuales con descuentos.
3. Monitorear clientes con cargos mensuales elevados.
4. Crear un sistema de scoring automático para alertar clientes con alta probabilidad de churn.

---

## 🚀 Próximos Pasos (Mejoras Futuras)

- Ajuste del umbral de decisión para optimizar recall/precision.
- Validación cruzada.
- Optimización de hiperparámetros.
- Implementación de modelos más avanzados (XGBoost).
- Interpretabilidad avanzada con SHAP.
- Despliegue como API o dashboard.

---

## 📎 Conclusión

Se construyó un pipeline robusto de Machine Learning capaz de anticipar la cancelación de clientes con un alto nivel de detección (Recall 0.80), proporcionando a la empresa una herramienta accionable para mejorar la retención y reducir pérdidas.
