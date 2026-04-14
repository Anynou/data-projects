# Riesgo de lesión de jugadores de fútbol

Este proyecto analiza el dataset **European Soccer Database** de Kaggle, en formato **SQLite**, para predecir el **riesgo de lesión de jugadores** usando datos de partidos y atributos de futbolistas.

El objetivo es **convertir un problema de negocio** (reducir bajas médicas en un club) en un **problema de datos**: identificar jugadores con mayor riesgo de lesión basado en su carga de partidos, rachas y nivel de juego.

---

## Motivo del proyecto

- Practicar análisis de datos en una base de datos real y relacional (SQLite).  
- Aprender a transformar información de partidos y jugadores en variables de riesgo.  
- Publicar un notebook que muestre un flujo de trabajo que contenga:  
  - EDA  
  - feature engineering  
  - modelado  
  - evaluación e interpretación.

---

## Objetivo de negocio

Ayudar a un equipo de fútbol a:

- Detectar jugadores con **alto riesgo de lesión** por sobrecarga de partidos o rachas intensas.  
- Tomar decisiones de rotación, descansos y planificación de entrenamientos para reducir bajas médicas.  

---

## Enfoque técnico

1. **Fuente de datos**  
   - `database.sqlite` del dataset “European Soccer Database” (Kaggle).  
   - Tablas usadas: `Match`, `Player`, `Player_Attributes`.

2. **Ingeniería de variables**  
   - `matches_played`: número de partidos por jugador y temporada.  
   - `max_streak`: máxima racha de partidos seguidos en días cercanos.  
   - `matches_per_day`: densidad de partidos en la temporada.  
   - `overall_rating`: nivel del jugador.

3. **Etiqueta de lesión**  
   - Se simula una etiqueta `injury_risk` usando una heurística basada en carga de partidos y racha (no existe una columna oficial de lesiones en el dataset).

4. **Modelo**  
   - Clasificación binaria: `Bajo riesgo` vs `Alto riesgo`.  
   - Modelo: `RandomForestClassifier` con `accuracy`, `AUC` y matriz de confusión.

---

## Resultados principales

- Accuracy del modelo en el conjunto de test.  
- AUC de la curva ROC.  
- Importancia de `matches_played`, `max_streak`, `matches_per_day` y `overall_rating`.  
- Visualización de la matriz de confusión entre bajo y alto riesgo.
