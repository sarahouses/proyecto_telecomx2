# 📡 Telecom X — Predicción de Cancelación de Clientes (Churn) · Parte 2

## 📌 Descripción del proyecto

Este proyecto desarrolla un sistema de **predicción de cancelación de clientes (churn)** para la empresa *Telecom X*.  
El objetivo es **identificar de forma anticipada a los clientes con mayor probabilidad de cancelar sus servicios**, permitiendo a la compañía implementar **estrategias de retención más efectivas, focalizadas y costo–eficientes**.

El enfoque del proyecto no se limita a maximizar métricas globales como *accuracy*, sino que prioriza métricas **alineadas a negocio**, particularmente la **detección temprana de clientes en riesgo (recall de churn)** y la **interpretabilidad del modelo**.

---

## 🎯 Objetivos alcanzados

- **Preparación y tratamiento de datos**  
  Limpieza, transformación, codificación de variables categóricas (one-hot encoding) y escalado de variables numéricas.

- **Control de multicolinealidad**  
  Análisis mediante *Variance Inflation Factor (VIF)* y eliminación de variables redundantes para mejorar estabilidad del modelo.

- **Manejo de desbalance de clases**  
  Evaluación de técnicas de balanceo (SMOTE) y selección final de `class_weight='balanced'` para preservar la distribución real de los datos.

- **Entrenamiento de modelos de Machine Learning**  
  - Regresión Logística  
  - SVM lineal  
  - Random Forest  
  - K-Nearest Neighbors (KNN)

- **Evaluación de desempeño**  
  Uso de métricas clave: *Recall*, *Precision*, *F1-score* y *ROC-AUC*, además de validación cruzada y análisis visual.

- **Interpretación del modelo**  
  Análisis de coeficientes y *Permutation Importance* para identificar los principales drivers de churn.

- **Optimización operativa**  
  Ajuste del **threshold de decisión** para balancear *recall* y *precision* según prioridades de negocio.

- **Informe final**  
  Conclusiones claras y **recomendaciones accionables** orientadas a retención de clientes.

---

## 📂 Dataset

- **Variable objetivo:**  
  `Churn` (Yes / No)

- **Principales variables predictoras:**
  - Antigüedad del cliente (`tenure`)
  - Cargos mensuales y totales (`Charges.Monthly`, `Charges.Total`)
  - Tipo de contrato (`Contract_*`)
  - Tipo de servicio de internet (`InternetService_*`)
  - Servicios adicionales (`TechSupport_Yes`, `OnlineSecurity_Yes`, `StreamingTV_Yes`, `StreamingMovies_Yes`)
  - Métodos de pago (`PaymentMethod_*`)
  - Facturación digital (`PaperlessBilling_Yes`)

---

## 📈 Resultados principales

### Modelos destacados

- **Regresión Logística (modelo final)**
  - ROC-AUC ≈ **0.84**
  - Recall (churn) ≈ **0.77**
  - Mejor equilibrio entre **capacidad predictiva, estabilidad e interpretabilidad**
  - Seleccionado como **modelo operativo final**

- **SVM lineal**
  - Desempeño similar a Regresión Logística en ROC-AUC
  - Menor interpretabilidad

- **Random Forest**
  - Mayor *accuracy* global
  - Recall significativamente menor para la clase churn
  - Útil como modelo complementario para capturar relaciones no lineales

- **KNN**
  - Desempeño aceptable en ROC-AUC
  - Bajo recall para churn, poco adecuado para objetivos de retención

---

## 🔎 Factores clave identificados

### 🔺 Mayor riesgo de cancelación
- **Tenure bajo** (clientes nuevos)
- **Altos cargos mensuales**
- **Servicio de internet por fibra óptica**
- **Método de pago: Electronic Check**
- **Facturación digital sin acompañamiento**

### 🔻 Factores protectores
- **Contratos de largo plazo (1–2 años)**
- **Mayor antigüedad del cliente**
- **Servicios adicionales activos** (Tech Support, Online Security)
- **Clientes sin servicio de internet (solo telefonía)**

> *Nota:* La importancia de variables no implica causalidad directa.  
> Algunos factores funcionan como **marcadores de fricción o perfil de cliente**, más que como causas únicas del churn.

---

## 🧠 Recomendaciones estratégicas

- **Fomentar contratos de mayor duración**  
  Incentivar la migración de contratos mensuales a planes anuales o bianuales mediante descuentos o beneficios.

- **Onboarding intensivo para clientes nuevos**  
  Enfocar esfuerzos de retención durante los primeros 60–90 días del ciclo de vida.

- **Estrategias de precio y bundles**  
  Ajustar planes o crear paquetes para clientes con cargos mensuales elevados, especialmente en fibra óptica.

- **Promoción temprana de servicios adicionales**  
  Ofrecer *Tech Support* y *Online Security* como herramientas de retención preventiva.

- **Optimización de métodos de pago**  
  Incentivar el uso de pagos automáticos y mejorar la experiencia de facturación digital.

---

## ⚙️ Reproducibilidad

El notebook fue ejecutado **de principio a fin en un entorno limpio**, utilizando:

```bash
jupyter nbconvert --to notebook --execute Proyecto_telecomx2.ipynb
).
