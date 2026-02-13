# ⚽ Análisis de Datos y Predicción de Talento - Fútbol Europeo

## 👤 Autor
*Paul Handley Viggiano*  

---

## 📋 Descripción del Proyecto
Este proyecto consiste en un análisis integral de una base de datos de fútbol europeo utilizando técnicas de *Data Science* and *Data Analityc*. El objetivo es transformar datos brutos de jugadores en información estratégica para el scouting deportivo, siguiendo el flujo de analítica Descriptiva, Predictiva y Prescriptiva.



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

Lecciones Aprendidas y Reflexión Técnica
El desarrollo de este proyecto representó un ciclo completo de aprendizaje en Ingeniería de Datos, dejando las siguientes lecciones clave:

La Integridad del Dato es Todo: Identificar anomalías (como registros de edad inconsistentes de 7 años) antes de entrenar el modelo fue vital para asegurar que el RMSE de 2.68 fuera un reflejo real del mercado y no un sesgo del dataset.

Gestión de Entornos en IT: Superar los conflictos de dependencias y la configuración de kernels en Visual Studio Code reforzó la importancia de trabajar con entornos virtuales (venv) para garantizar la reproducibilidad del software.

Simbiosis Tecnológica: La combinación de la potencia de procesamiento de Python (manejando con éxito 181.265 registros) con la capacidad visual de Power BI permitió transformar estadísticas frías en un Dashboard operativo y fácil de interpretar para la toma de decisiones.

Mentalidad de Solución: Más allá de la estética visual, la verdadera victoria fue lograr un modelo con un 85.2% de precisión, demostrando que la analítica predictiva es una herramienta indispensable en la industria moderna del deporte.