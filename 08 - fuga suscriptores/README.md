# Predicción de fuga de suscriptores de servicio de streaming

Este proyecto analiza un dataset de suscriptores de un servicio de streaming de música para predecir el **riesgo de abandono (churn)** de cada usuario, usando **XGBoost** y **SHAP** para explicar las decisiones del modelo.

El objetivo es convertir datos de comportamiento de usuarios en un sistema de **detección de churn** orientado a negocio, con un enfoque similar a detección de fraude: detectar la minoría de usuarios que abandonan con alta sensibilidad, aunque aceptando algunos falsos positivos.

---

## Motivo del proyecto

- Practicar **análisis de churn** en un contexto de negocio muy típico: servicios de streaming de música.  
- Aprender a manejar datasets desbalanceados y usar métricas orientadas a “fraud‑like” (AUC, Precision‑Recall AUC, recall de la clase minoritaria).  
- Aplicar **XGBoost** y **SHAP** para explicar decisiones de riesgo de churn por usuario.  

---

## Objetivo de negocio

Ayudar a una plataforma de streaming de música a:

- Identificar usuarios con **alto riesgo de churn**.  
- Entender qué variables influyen en el abandono:  
  - inactividad,  
  - horas de escucha,  
  - playlists creadas,  
  - skips,  
  - engagement con recomendaciones,  
  - antigüedad de la suscripción,  
  - tipo de plan, etc.  

---

## Flujo de trabajo

### 1. Fuente de datos

- Dataset de suscriptores de streaming de música.
- Variable objetivo `churn` se construye combinando señales de inactividad y bajo engagement (no solo una columna flag), para evitar data leakage.

---

### 2. Limpieza y preprocesamiento

- Convertir `signup_date` en `days_since_signup` como proxy de antigüedad.  
- Definir `churn` combinando:
  - nivel de inactividad (`months_inactive`),  
  - baja escucha semanal,  
  - y/u otras condiciones de comportamiento.  
- Eliminar o adaptar columnas que implicarían data leakage (por ejemplo, flags directos de churn si se usan como features).  
- Codificar variables categóricas (`country`, `subscription_type`, `favorite_genre`, `primary_device`, etc.) con `LabelEncoder` o similares.  
- Dividir entrenamiento / test de forma estratificada (`stratify=y`) para mantener proporción de churn.

---

### 3. Modelo XGBoost

- Tipo de problema: clasificación binaria → `churn = 1` (abandona) / `0` (permanece).  
- Modelo usado: `XGBClassifier`.  

---

### 4. Enfoque “fraud‑like” en churn

- El enfoque prioriza **encontrar la mayor parte de los churn reales**, aunque haya algunos falsos positivos.  
- En términos de negocio:  
  - `recall` de churn alto → se detecta la mayoría de abandonos.  
  - `precision` de churn moderado → algunas alertas de alto riesgo resultan usuarios que finalmente no se van, pero eso es asumible si evita perder clientes sin acción.  
- La métrica de **Precision‑Recall AUC** es especialmente relevante aquí porque el dataset es muy desbalanceado.

---

### 5. Explicabilidad con SHAP

- Usar `shap.TreeExplainer` para calcular SHAP values sobre el test set.  
- Esto permite explicar el modelo en lenguaje de negocio:
  - “Este usuario lleva varios meses con poca escucha y no crea playlists, por eso el modelo le da 85 % de riesgo de abandonar”.
