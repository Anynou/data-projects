# Análisis de fuga de clientes

Este proyecto analiza el dataset **Telco Customer Churn** de Kaggle, correspondiente a una empresa de telecomunicaciones, para predecir la **probabilidad de fuga de clientes (churn)** y entender qué factores influyen en que un cliente deje de usar el servicio.

El objetivo es convertir un dataset de negocio realista (Telco) en un caso de estudio completo de:
- limpieza de datos  
- análisis exploratorio  
- ingeniería de variables  
- modelado de churn  
- interpretación de resultados para la toma de decisiones.

---

## Motivo del proyecto

- Practicar **análisis de fuga de clientes (churn)** en un contexto de negocio muy típico (telecomunicaciones).  
- Aprender a trabajar con un dataset estructurado, mixto (categórico + numérico) y realista.  

---

## Objetivo de negocio

Ayudar a una empresa a:

- Identificar qué clientes tienen **alto riesgo de abandono**.  
- Entender qué variables explican el churn:  
  - tipo de contrato,  
  - servicios adicionales,  
  - pagos automáticos,  
  - facturación electrónica, etc.  
- Proponer acciones de retención (por ejemplo, ofertas, descuentos, seguimiento personalizado) para reducir la fuga de clientes.

---

## Flujo de trabajo

### 1. Fuente de datos

- Dataset de Kaggle: **Telco Customer Churn**   
- Variables clave:  
  - `customerID`  
  - `gender`, `SeniorCitizen`  
  - `tenure` (meses como cliente)  
  - `Contract`, `PaperlessBilling`, `PaymentMethod`  
  - `TotalCharges`, `MonthlyCharges`  
  - `PhoneService`, `MultipleLines`, `OnlineSecurity`, `TechSupport`, `StreamingTV`, `StreamingMovies`  
  - `Churn` (variable objetivo).

---

### 2. Limpieza y preprocesamiento

- Visualizar variables clave
- Feature engineering ( crear variables útiles ) 
- Dividir el dataset en entrenamiento y prueba (`train/test split`).
- Preprocesado 

---

### 3. Modelado de churn

- Tipo de problema:  
  - clasificación binaria → `Churn = 0` (no se va) / `1` (se va).  
- Modelos usados:  
  - `LogisticRegression`  
  - `LightGBM`  
 
- Métricas:  
  - AUC‑ROC  
  - matriz de confusión.

---

### 4. Interpretación de resultados

- Matriz de confusión:  
  - cuántos falsos positivos (clientes tratados como “alto riesgo” que no se van)  
  - cuántos falsos negativos (clientes que se van sin ser detectados).  
- Importancia de variables (feature importance) para ver qué factores más influyen en el churn.  
- Interpretación en lenguaje de negocio:
  - Motivos del "Churn"
