# 📱 Tech Use & Stress Wellness – Análisis y Modelado

## 1) Problema
Se busca entender cómo el uso de tecnología (tiempo de pantalla, redes sociales, etc.) se relaciona con los **niveles de estrés/bienestar** y construir un modelo que permita **predecir el nivel de estrés** a partir de variables de uso tecnológico y hábitos.

## 2) Dataset
- Origen: Kaggle (encuesta sobre uso tecnológico y bienestar).
- Estructura: variables numéricas y categóricas (tiempo de pantalla, uso de redes, hábitos, demografía, etc.).
- Objetivo (ejemplo): `stress_score` (valor continuo).

> Nota: el nombre exacto del objetivo puede variar; en el código se configura en `OBJETIVO`.

## 3) Estadísticas básicas
- **Valores faltantes:** se revisa cantidad por columna y se imputan numéricos con la **media** y categóricas con la **moda**.
- **Descriptivos numéricos:** `count, mean, std, min, 25%, 50%, 75%, max`.
- **Distribuciones:** histogramas y **boxplots** para detectar asimetrías/outliers.
- **Correlación:** matriz de correlación (solo numéricas) para detectar asociaciones con el objetivo.

## 4) Preparación
- Codificación de variables categóricas con **dummies** (solo categorías de baja cardinalidad).
- Escalado de variables numéricas con **StandardScaler** (útil para Regresión Lineal).
- División **train/test** (80/20) con `random_state=42`.

## 5) Modelos
Se comparan dos modelos vistos en clases:
- **Regresión Lineal** (base, interpretable).
- **Random Forest Regressor** (capta relaciones no lineales e interacciones).

**Métricas:** `MAE`, `MSE`, `RMSE`, `R²` sobre el conjunto de prueba.

## 6) Resultados
- Se reportan métricas de ambos modelos y se **selecciona el mejor** por **MSE**.
- Se muestra el gráfico **y_real vs y_pred** y la **distribución de residuales**.
- Se reportan **importancias de variables** (Random Forest) o **coeficientes absolutos** (Regresión Lineal).

## 7) Conclusiones
- Variables de uso tecnológico con mayor influencia en el estrés.
- Observaciones sobre patrones (por ejemplo, mayor tiempo de pantalla ↔ mayor estrés, si aplica).
- **Limitaciones:** tamaño muestral, datos auto-reportados, variables omitidas.
- **Mejoras:** recolectar más datos, probar regularización, explorar más modelos (p. ej., árboles de decisión, KNN), tuning de hiperparámetros.

## 8) Reproducibilidad
1. Clonar el repositorio.
2. Colocar el CSV en la carpeta raíz (ej.: `tech_stress.csv`).
3. Ejecutar el notebook / script `main.py` o `.ipynb`.

---
