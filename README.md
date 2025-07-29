# 🌳 Análisis de la Deforestación en Argentina (2001–2020)

Este proyecto aplica ciencia de datos para analizar y modelar el comportamiento de la deforestación en Argentina entre los años 2001 y 2020. Se utilizaron herramientas de análisis exploratorio, visualizaciones, modelos predictivos y técnicas de machine learning para comprender el fenómeno desde una perspectiva territorial y temporal.

---

## 📌 Objetivo

Explorar, analizar y modelar los patrones de deforestación en distintas regiones del país. Evaluar la posibilidad de predecir la deforestación anual a partir de variables como el año y la región, y agrupar provincias según su comportamiento forestal.

---

## 🧹 Limpieza y preparación de los datos

- **Eliminación de columnas irrelevantes:** Se descartaron columnas como IDs y códigos que no aportaban valor analítico.
- **Revisión de nulos y duplicados:** No se detectaron valores nulos ni duplicados.
- **Renombrado de columnas:** Se estandarizaron los nombres en español y con mejor formato para facilitar la lectura.
- **Conversión de tipos de datos:** Se aseguraron los tipos adecuados (`year`: int, `deforestation`: float, `parent_region`: string).
- **Codificación de variables categóricas:** Se aplicó `LabelEncoder` a `parent_region`, creando la columna `parent_region_encoded`.

---

## 📊 Análisis exploratorio

Se realizaron visualizaciones clave para entender la distribución de la deforestación:

- Boxplots para detectar valores atípicos por año.
- Mapas de calor y gráficos de dispersión.
- Gráficos de tendencias por región.

```python
# Ejemplo de mapa de calor de correlaciones
import seaborn as sns
import matplotlib.pyplot as plt

corr = df.corr(numeric_only=True)
plt.figure(figsize=(8, 6))
sns.heatmap(corr, annot=True, cmap='YlGnBu')
plt.title('Mapa de calor de correlaciones')
plt.show()

## 🤖 Modelos aplicados

### 1. Random Forest Regressor (Modelo supervisado)

Se entrenó con un 80% de los datos y se evaluó con el 20% restante.

- **Variables usadas:** `year` y `parent_region_encoded`.

**Métricas del modelo:**
- MAE: 658.06  
- MSE: 8.625.511,13  
- R²: 0.29

📌 Este modelo sirvió como base para predecir la deforestación anual por región, aunque aún con margen de mejora.

---

### 2. KMeans Clustering (Modelo no supervisado)

Se agruparon provincias según su comportamiento de deforestación acumulada y promedio:

- **Cluster 1 – Alto impacto sostenido:** Chaco, Salta, Santiago del Estero.
- **Cluster 2 – Alto impacto con menos historial:** Menor cantidad de años registrados.
- **Cluster 0 – Bajo impacto:** Provincias con deforestación controlada.

📌 Este análisis permitió segmentar regiones y entender patrones comunes de forma automática.

---

## 🗂️ Estructura del repositorio

📁 data/ ...................... Datos originales y procesados
├── 📁 notebooks/ ................ Análisis exploratorio y modelos
├── 📄 README.md ................. Este archivo

## 🧠 Conclusiones

- La deforestación varía fuertemente por región y año.
- Hay regiones con impacto alto y sostenido que requieren atención prioritaria.
- Modelos como Random Forest permiten hacer predicciones iniciales, pero requieren más variables.
- El clustering ayuda a detectar patrones regionales sin intervención manual.

---

## 🛠️ Herramientas y tecnologías

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Jupyter Notebook

---

## 👤 Autor/a

Proyecto realizado por **Meli Ulloa – 2025**  
Para la entrega final del curso de Data Science en YPF.

---

## 📬 Contacto

Para consultas o sugerencias: [melinaulloa.github.io](https://github.com/melinaulloa)
