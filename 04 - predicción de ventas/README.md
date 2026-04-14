# Predicción de ventas

Este proyecto analiza el dataset **Store Sales – Time Series Forecasting** de Kaggle, correspondiente a las ventas diarias de múltiples tiendas de una cadena de supermercados, para predecir las **ventas futuras** usando técnicas de **series temporales**.

El objetivo es convertir un dataset de ventas históricas en un flujo de trabajo completo de:
- limpieza y análisis de datos  
- modelado de series temporales  
- evaluación y despliegue de resultados  
- interpretación para la toma de decisiones de negocio.

---

## Motivo del proyecto

- Practicar **predicción de ventas** en un contexto realista de retail.  
- Aprender a trabajar con series temporales diarias, estacionalidad y eventos externos (vacaciones, feriados, promociones).  

---

## Objetivo de negocio

Ayudar a una cadena de supermercados a:

- Predecir las **ventas diarias por familia de productos y por tienda**.  
- Anticipar picos de demanda y reducir el exceso de inventario o la falta de stock.  
- Apoyar la planificación de aprovisionamiento, turnos de personal y promociones.

---

## Flujo de trabajo

### 1. Fuente de datos

- Dataset de Kaggle: **Store Sales – Time Series Forecasting**  

---

### 2. EDA inicial

- Revisar ventas totales en el tiempo y por día de la semana

---

### 3. Feature engineering

- Crear variables para holidays y calendario

---

### 4. Preparar training

---

### 5. Importancia de las variables

- Ordenar las variables con mayor importancia

---

### 6. Entrenar modelo

- Modelo utilizado: `GBMRegressor`

---

### 7. Hacer predicciones

