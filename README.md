Telecom X — Predicción de Cancelación (Churn) · Parte 2
Descripción del proyecto

Este proyecto implementa un sistema de predicción de cancelación de clientes (churn) para la empresa Telecom X.
El objetivo es identificar de forma anticipada a los clientes con alta probabilidad de cancelar sus servicios, permitiendo a la compañía aplicar estrategias de retención más efectivas y focalizadas.

Objetivos cumplidos

Preparación y tratamiento de datos: limpieza, codificación y normalización de variables.

Control de multicolinealidad: análisis VIF y eliminación de variables redundantes.

Balanceo de clases: aplicación de SMOTE/SMOTENC únicamente sobre el set de entrenamiento.

Entrenamiento de modelos: Regresión Logística, SVM lineal, Random Forest y KNN.

Evaluación de desempeño: métricas de precisión, recall, F1 y ROC-AUC, además de análisis visual.

Interpretación de variables clave: análisis de coeficientes e importancias para comprender los factores que impulsan la cancelación.

Informe final con conclusiones y recomendaciones de negocio.

Dataset

Variable objetivo: Churn (Yes / No)

Principales variables predictoras:

Tenencia (tenure)

Cargos mensuales y totales (Charges.Monthly, Charges.Total)

Tipo de contrato (Contract_*)

Tipo de servicio de internet (InternetService_*)

Soporte técnico, streaming y servicios adicionales (TechSupport_Yes, StreamingTV_Yes, StreamingMovies_Yes)

Métodos de pago (PaymentMethod_*)

Resultados principales

Mejores modelos para discriminación de churn:

Regresión Logística y SVM lineal con ROC-AUC ≈ 0.845 y recall ≈ 0.79 para clientes que cancelan.

Útiles cuando la prioridad es maximizar la captura de clientes en riesgo.

Random Forest: mayor accuracy (0.79) pero recall menor (0.463) para la clase de cancelación.

KNN: desempeño global correcto (ROC-AUC ≈ 0.794) pero con recall bajo para churn.

Factores clave identificados

Mayor riesgo de cancelación:

Contratos de corto plazo o mensuales.

Servicio de internet de fibra óptica o sin internet.

Altos cargos mensuales.

Pago mediante cheque electrónico.

Ausencia de soporte técnico o servicios adicionales.

Menor riesgo:

Contratos de dos años.

Mayor tiempo de permanencia (tenure).

Servicios adicionales activos (tech support, streaming).

Recomendaciones estratégicas

Incentivar contratos de mayor duración (1-2 años) mediante descuentos o beneficios.

Mejorar la experiencia temprana en clientes nuevos (< 12 meses) con soporte proactivo.

Ofrecer paquetes de servicios que incluyan soporte técnico y streaming sin coste adicional inicial.

Revisar tarifas y promociones para clientes con cargos mensuales altos.

Migrar métodos de pago a opciones más estables (ej. tarjeta automática).
