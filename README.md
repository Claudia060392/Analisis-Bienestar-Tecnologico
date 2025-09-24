# 📱 Tech Use & Stress Wellness – Análisis y Modelado

## 1) Problema
Se busca entender cómo el uso de tecnología (tiempo de pantalla, redes sociales, etc.) se relaciona con los **niveles de estrés y bienestar**.  
El objetivo es construir un modelo que permita **predecir el nivel de estrés** a partir de variables de uso tecnológico y hábitos.

---

## 2) Dataset
- **Fuente:** Kaggle – encuesta sobre uso tecnológico y bienestar.  
- **Tamaño:** 5000 registros, 25 columnas.  
- **Variables:**  
  - Numéricas → edad, tiempo de uso de pantallas, horas de sueño, calidad del sueño, actividad física, consumo de cafeína, puntajes de ansiedad y depresión, etc.  
  - Categóricas → `gender`, `location_type`, `uses_wellness_apps`, `eats_healthy`.  
- **Variable objetivo:** `stress_level` (continua).

---

## 3) Estadísticas básicas
- **Valores faltantes:** no se detectaron.  
- **Distribución de género:** Male (2446), Female (2359), Other (195).  
- **Distribución por zona:** Urban (2480), Suburban (1477), Rural (1043).  
- **Uso de apps de bienestar:** Sí (2073) vs. No (2927).  
- **Alimentación saludable:** Sí (2514) vs. No (2486).  
- **Descriptivos numéricos:** Se calcularon `count, mean, std, min, 25%, 50%, 75%, max`.  
- **Visualizaciones:** histogramas, boxplots y matriz de correlación para explorar la relación entre variables.

---

## 4) Preparación
- Imputación → numéricas con la **media**, categóricas con la **moda**.  
- Codificación → **One-Hot Encoding** para variables categóricas de baja cardinalidad.  
- Escalado → **StandardScaler** aplicado a numéricas (para Regresión Lineal).  
- División → conjunto de entrenamiento (80%) y prueba (20%) con `random_state=42`.

---

## 5) Modelos aplicados
Se compararon dos modelos vistos en clases:

- **Regresión Lineal**  
  ✔️ Interpretable, sirve como baseline.

- **Random Forest Regressor (200 árboles)**  
  ✔️ Captura relaciones no lineales e interacciones.

**Métricas usadas:** MAE, MSE, RMSE, R².

---

## 6) Resultados obtenidos

### 📌 Regresión Lineal
- MAE = 0.4185  
- MSE = 0.2838  
- RMSE = 0.5327  
- R² = 0.9665  

### 📌 Random Forest
- MAE = 0.2145  
- MSE = 0.1232  
- RMSE = 0.3510  
- R² = 0.9854  

👉 **Mejor modelo:** Random Forest (menor error y mayor R²).

---

## 7) Importancia de variables
Top 5 variables más influyentes según **Random Forest**:

1. `social_media_hours` (principal factor, >90% del peso).  
2. `work_related_hours`.  
3. `mood_rating`.  
4. `mindfulness_minutes_per_day`.  
5. `entertainment_hours`.  

---

## 8) Conclusiones
- El **tiempo en redes sociales** es el predictor más fuerte del nivel de estrés.  
- Factores laborales, el estado de ánimo y prácticas de bienestar (ej.: mindfulness) también influyen.  
- Ansiedad y depresión semanales aparecen como variables secundarias pero relevantes.  
- El **Random Forest** ofrece mejor desempeño porque capta relaciones complejas entre hábitos y estrés.  

### Limitaciones
- Datos auto-reportados (posible sesgo).  
- Dataset limitado a un contexto específico (no necesariamente global).  

### Mejoras futuras
- Ajuste de hiperparámetros en Random Forest.  
- Inclusión de más variables contextuales (económicas, culturales).  
- Probar otros modelos (XGBoost, Redes Neuronales).  

---

## 9) Reproducibilidad
1. Clonar el repositorio.  
2. Guardar el dataset `tech_stress.csv` en la carpeta raíz.  
3. Ejecutar el notebook o script (`main.py` / `.ipynb`).  

---
