# ⚽ Data-Driven Scouting: Análisis Predictivo de Talento en Fútbol Europeo

## 👤 Autor
Paul Handley Viggiano  

---

# 📌 1. Contexto del Problema

En el fútbol profesional, la identificación de talento es una de las decisiones estratégicas más costosas y determinantes para el rendimiento deportivo y financiero de un club.

Tradicionalmente, el scouting se ha basado en observación subjetiva. Este proyecto propone un enfoque **data-driven**, utilizando analítica descriptiva, predictiva y prescriptiva para:

- Identificar patrones asociados al rendimiento de jugadores.
- Estimar el nivel general de un jugador (`overall_rating`).
- Detectar talento potencialmente infravalorado en el mercado.

---

# 📊 2. Conjunto de Datos

Se trabajó con una base de datos SQLite compuesta por múltiples tablas relacionadas con jugadores europeos.

### 🔎 Granularidad del dataset

El dataset contiene registros por:

> Jugador – Fecha de evaluación

Esto implica que un mismo jugador puede aparecer múltiples veces en distintas fechas.

- Registros totales procesados: ~181.000  
- Variables finales utilizadas: +20  
- Unidad de análisis: evaluación individual por jugador en una fecha determinada  

---

# 📚 3. Data Dictionary (Variables Clave)

| Variable | Descripción |
|----------|------------|
| overall_rating | Evaluación general del jugador en esa fecha |
| potential | Potencial estimado de desarrollo futuro |
| reactions | Capacidad de reacción y toma de decisiones |
| age | Edad del jugador en la fecha del registro |
| brecha | Diferencia entre potential y overall_rating |

### 📌 Definición de “Brecha”

```python
brecha = potential - overall_rating
```

Interpretación:

- Brecha positiva alta → jugador con margen de crecimiento  
- Brecha cercana a 0 → jugador cercano a su techo  
- Brecha negativa → caso poco frecuente (inconsistencias o regresión)  

---

# 🛠 4. Metodología

El proyecto sigue tres niveles de analítica:

## 4.1 Análisis Descriptivo

- Limpieza de edades anómalas.
- Eliminación de registros inconsistentes.
- Análisis de correlaciones.
- Identificación de variables más asociadas al `overall_rating`.

Se observó una asociación fuerte entre:
- `reactions`
- `potential`
- `overall_rating`

---

## 4.2 Análisis Predictivo

Se entrenó un modelo de **Regresión Lineal** para estimar el `overall_rating`.

### División de datos
- Train/Test split
- Validación fuera de muestra

### Métricas obtenidas:
- **R²:** 0.85  
- **RMSE:** 2.68 puntos  

Interpretación:

El modelo explica aproximadamente el 85% de la variabilidad del `overall_rating` dentro de este dataset.

⚠ Importante:  
El modelo identifica relaciones estadísticas, no relaciones causales.

---

## 4.3 Análisis Prescriptivo – “Joyas Ocultas”

Se desarrolló un criterio para identificar jugadores potencialmente infravalorados:

- Brecha > 30 puntos  
- Edad dentro de rango competitivo  
- Buen nivel en variables clave (`reactions`, `potential`)  

Esto genera una lista accionable para scouting.

---

# 📈 5. Dashboard Operativo (Power BI)

Se desarrolló un dashboard interactivo que permite:

- Filtrar por jugador
- Visualizar relación `Reactions` vs `Overall`
- Explorar ranking de “joyas ocultas”
- Analizar métricas agregadas

Se recomienda interpretar los KPIs en términos de:
- Media
- Distribución
- Jugadores únicos (no registros totales)

---

# 🚀 6. Reproducibilidad

## 6.1 Requisitos

Python 3.11+

Instalar dependencias:

```bash
pip install -r requirements.txt
```

## 6.2 Estructura del Proyecto

```
DataProject_Final/
│
├── Data/
│   ├── Raw/
│   └── Processed/
│
├── Notebooks/
│   └── FinalProject.ipynb
│
├── README.md 
├── .gitignore
└── requirements.txt
```

## 6.3 Flujo de Ejecución

1. Colocar la base de datos `.sqlite` en `Data/Raw`
2. Ejecutar el notebook `FinalProject.ipynb`
3. Se generará el dataset final en:
   `Data/Processed/recomendaciones_scouting.csv`
4. Ese archivo alimenta el dashboard de Power BI

---

# 🧭 7. Implicaciones para la Toma de Decisiones

Un director deportivo podría utilizar este modelo para:

- Priorizar jugadores con alto margen de crecimiento.
- Reducir riesgo en fichajes.
- Identificar perfiles subvalorados.
- Comparar jugadores dentro de segmentos específicos.

Este análisis no reemplaza el scouting tradicional, sino que lo complementa con evidencia cuantitativa.

---

# ⚠ 8. Limitaciones

- Múltiples registros por jugador en distintas fechas.
- `potential` es una estimación subjetiva del proveedor del dataset.
- No se consideran variables tácticas o contexto del equipo.
- Dataset histórico (no en tiempo real).

---

# 🔮 9. Próximos Pasos

- Segmentación por posición.
- Validación cruzada.
- Modelos no lineales.
- Automatización de selección por última fecha disponible.
- Incorporar variables de mercado (valor transferencia).

---

# 🎯 Conclusión

Este proyecto demuestra cómo la analítica de datos puede estructurar un proceso de scouting basado en evidencia, transformando datos históricos en recomendaciones estratégicas accionables.