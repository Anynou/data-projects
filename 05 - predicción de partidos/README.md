# Predicción de resultado de partidos – Premier League

Este proyecto analiza el **historial de partidos de la Premier League** para predecir el **resultado de un partido**:  
- victoria local,  
- empate,  
- victoria visitante.

El objetivo es convertir datos de partidos reales en un modelo de clasificación multiclase que ayude a entender qué factores influyen en el resultado de un encuentro, tanto desde un punto de vista táctico como de análisis de cuotas.

---

## Motivo del proyecto

- Practicar **análisis de datos deportivos** usando una liga real (Premier League).  
- Aprender a trabajar con datasets de fútbol (marcador, cuotas, equipos, jugadores, etc.).  

---

## Objetivo de negocio

Ayudar a:

- un **club de fútbol** a entender qué factores (localía, momento de la temporada, diferencia de goles, etc.) correlacionan con ganar o perder.  
- un **analista deportivo / agencia de apuestas** a construir un modelo base de predicción de resultados para comparar con cuotas reales.

Este proyecto no pretende “ganar apuestas” de forma sistemática, sino mostrar un flujo de trabajo realista.

---

## Flujo de trabajo

### 1. Fuente de datos

- Dataset de datos de partidos de la **Premier League**
- Variables clave:
  - `date`  
  - `home_team` / `away_team`  
  - `home_goals`, `away_goals`  

---

### 2. EDA inicial

- Comprobar la distribución de resultados
- Qué equipos juegan más
- Qué días se juega más

---

### 3. Feature engineering

- Creamos variables para:
  - capturar forma
  - Eficiencia
  - Afectación del calendario

---

### 4. Limpieza

- Rellenamos nulos
- Seleccionamos solo variables numéricas
- Visualización de variables importantes

---

### 5. Modelado de resultado de partidos

- Tipo de problema:  
  - clasificación multiclase → `Home Win`, `Draw`, `Away Win`.  
- Modelos usados:  
  - `radientBoostingClassifier`  
  - `RandomForestClassifier`  


---

### 6. Interpretación de resultados

- Ejemplo de uso en un partido
