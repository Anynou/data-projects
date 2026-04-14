# Análisis de reseñas de clientes en Google y Tripadvisor

Este proyecto analiza reseñas reales de un restaurante recolectadas de **Google Maps** y **Tripadvisor** para estudiar el **sentimiento y la experiencia de los clientes**.  
El objetivo es transformar texto libre en información estructurada que ayude a mejorar carta, servicio y percepción del restaurante.

---

## Motivo del proyecto

- Practicar **procesamiento de texto y análisis de sentimientos** con datos reales de un restaurante.  
- Aprender a:  
  - limpiar datos de reseñas,  
  - integrar reseñas de dos fuentes distintas (Google + Tripadvisor),  
  - clasificar el tono (positivo / negativo / neutro) y encontrar temáticas clave.  

---

## Objetivo de negocio

Ayudar a un restaurante real a entender:

- Qué aspectos de la experiencia gustan más o menos (comida, servicio, ambiente, precio, etc.).  
- Cuáles son las principales críticas repetidas.  
- En qué áreas podría mejorar la carta o el servicio para aumentar la satisfacción y la reputación online.

El resultado se puede usar como mini‑informe de “feedback de clientes” para el dueño del restaurante.

---

## Flujo de trabajo

### 1. Fuente de datos

- Reseñas de **Google Maps** del restaurante.  
- Reseñas de **Tripadvisor** del mismo restaurante.  
  - En el proyecto cada reseña se trata como una fila con:  
    - comentario,  
    - rating (1–5),  
    - fecha,  
    - fuente (Google / Tripadvisor).


---

### 2. Limpieza, preprocesamiento

- Limpiar comentarios
- Añadir sentimiento

---

### 3. Análisis exploratorio (EDA)

- Distribución de reseñas por estrellas y por fuente (Google vs Tripadvisor).  
- Distribución de sentimiento
- Evolución del sentimiento en el tiempo
- Términos positivos y negativos