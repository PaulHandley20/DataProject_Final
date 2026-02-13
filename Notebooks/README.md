# ⚽ Análisis de Datos y Predicción de Talento - Fútbol Europeo

## 👤 Autor
*Lucas Ezequiel Bianchi*  
Ingeniero en Sistemas / IT Engineer

---

## 📋 Descripción del Proyecto
Este proyecto consiste en un análisis integral de una base de datos de fútbol europeo utilizando técnicas de *Data Science*. El objetivo es transformar datos brutos de jugadores en información estratégica para el scouting deportivo, siguiendo el flujo de analítica Descriptiva, Predictiva y Prescriptiva.



## 🛠️ Tecnologías Utilizadas
* *Lenguaje:* Python 3.11.9
* *Entorno:* Virtual Env (venv) y Jupyter Notebooks (.ipynb)
* *Base de Datos:* SQLite 3
* *Librerías principales:* * pandas & numpy (Procesamiento)
    * seaborn & matplotlib (Visualización)
    * scikit-learn (Machine Learning)

---

## 📂 Estructura del Repositorio
| Carpeta | Descripción |
| :--- | :--- |
| Data/Raw | Base de datos original (.sqlite) |
| Data/Processed | Datasets limpios y recomendaciones (.csv) |
| Notebooks | Archivo principal del análisis (FinalProject.ipynb) |
| venv | Entorno virtual con dependencias aisladas |

---

## 🚀 Metodología Aplicada

### 1. Análisis Descriptivo
Limpieza de más de *181,000 registros. Identificamos que las variables con mayor correlación con el éxito del jugador son las **Reacciones* y el *Potencial* ($0.77$).

### 2. Análisis Predictivo
Desarrollamos un modelo de *Regresión Lineal* para estimar el overall_rating.
* *Precisión ($R^2$):* $0.8523$
* *Error ($RMSE$):* $2.68$ puntos

### 3. Análisis Prescriptivo
Generación de una lista de *"Joyas Ocultas"*, identificando jugadores subestimados por el mercado con alto margen de crecimiento (brechas de talento > 30 puntos).

---

## 📈 Conclusiones
El proyecto demuestra cómo la analítica de datos permite optimizar la toma de decisiones estratégicas, permitiendo a los clubes identificar talento de manera objetiva y eficiente.