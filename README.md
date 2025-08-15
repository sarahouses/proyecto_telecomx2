🚀 Resumen del proyecto

Este repositorio contiene el pipeline completo de modelado de churn para Telecom X: preparación de datos, análisis de correlación, selección de variables, entrenamiento de modelos, evaluación y explicación de resultados.
Se prioriza recall de la clase 1 (churn) para detectar el mayor número posible de clientes en riesgo.

Hallazgos clave (de la corrida actual):

Modelos con mejor discriminación: Regresión Logística y SVM lineal → ROC-AUC ≈ 0.845, recall ≈ 0.79 (clase 1).

Random Forest: accuracy 0.79, ROC-AUC 0.828, recall 0.463 (más conservador; se le escapan churners).

KNN: ROC-AUC 0.794, recall 0.489 (baseline).

Factores que ↑ riesgo de churn: Charges.Monthly (precio mensual), InternetService_Fiber optic, PaymentMethod_Electronic check, PaperlessBilling_Yes, tenure bajo.
Factores protectores: Contract_One year, Contract_Two year, tenure alto, TechSupport_Yes, OnlineSecurity_Yes.

Estrategias sugeridas: ofertas de downgrade/paquetes a alto precio, incentivos para pasar de mes-a-mes a anual/bianual, onboarding proactivo en los primeros 90 días, migración de pagos a débito/tarjeta automática, y ajuste de umbral en Logística/SVM según presupuesto de retención.


📊 Resultados (corrida actual)

Logística / SVM lineal: ROC-AUC ≈ 0.845, recall ≈ 0.79 (mejor para detectar churners).

Random Forest: accuracy 0.79, ROC-AUC 0.828, recall 0.463.

KNN: ROC-AUC 0.794, recall 0.489.

Variables top (consenso): Charges.Monthly, tenure, Contract_One year, Contract_Two year, InternetService_Fiber optic, PaymentMethod_Electronic check, PaperlessBilling_Yes, OnlineSecurity_Yes, TechSupport_Yes.

🧭 Recomendaciones de negocio (retención)

Precio/valor: ofertas de downgrade/paquetes o descuentos temporales para alto Charges.Monthly (más si es fibra y tenure bajo).

Contratos: mover mes-a-mes → anual/bianual con incentivos (3–6 meses de beneficio).

Onboarding & soporte: foco en tenure < 3 meses; activar pruebas de TechSupport/OnlineSecurity.

Pagos: migrar Electronic check → automático (tarjeta/débito) y mejorar recordatorios/UX de facturación digital.

Operación del modelo: usar Logística/SVM; ajustar umbral según presupuesto y medir PR-AUC / recall@top-k.

🔁 Próximos pasos

Validación temporal (train en meses antiguos, test en recientes).

Calibración de probabilidades y threshold tuning por costo/beneficio.

Segmentos piloto de retención y medición de uplift.

Prueba de XGBoost/LightGBM y SHAP para explicabilidad.
