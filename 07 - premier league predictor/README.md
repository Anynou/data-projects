# ⚽ Premier League Match Predictor (Poisson + XGBoost)

Proyecto de **predicción de resultados 1X2 de la Premier League** usando datos históricos de **Football-Data.co.uk** y un modelo combinado de **Poisson Regression** (goles esperados) + **XGBoost** (clasificación multiclase).

El objetivo es construir un pipeline completo de *data science* + una **aplicación Streamlit** desplegada en la nube para predecir partidos de la próxima jornada.

---

## 🧠 Objetivos del proyecto

- Descargar y procesar datos históricos de Premier League (goles, resultados, cuotas).
- Modelar goles esperados con **Poisson Regression** para entender la dinámica de anotación.
- Crear *features* de:
  - Forma reciente de cada equipo (últimos 5 partidos).
  - *Head-to-head* básico (histórico entre ambos equipos).
  - Cuotas de casas de apuestas (Bet365) como información de mercado.
- Entrenar un modelo **XGBoost** para predecir 1X2.
- Evaluar con **Accuracy**, **Log-Loss** y **Brier Score multiclase**.
- Exponer el modelo en una **Web App de Streamlit** para uso interactivo.

---

## 📂 Flujo 

```bash
1. EDA inicial
2. Calcular goles esperados
3. Feature engineering
4. Preprocesamiento
5. Modelos
6. Métricas
```

---

## 📊 Dataset

- Fuente: **Football-Data.co.uk** (CSV público).
- Ejemplo de descarga Premier League 23/24:


---

## 🌐 Aplicación

Se ha desplegado una aplicación de prueba que utiliza el modelo creado: https://premier-league-predictor-fget.onrender.com/
