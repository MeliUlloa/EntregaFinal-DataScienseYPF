🌳 Análisis de la Deforestación en Argentina (2001–2020) — Proyecto de Ciencia de Datos y Machine Learning
👥 Grupo 12
Integrantes:

Cruz Nicole

Ulloa Soto Melina Gimena

📘 Introducción
La deforestación es uno de los desafíos ambientales más importantes en Argentina y el mundo. Este proyecto busca analizar, visualizar y predecir el comportamiento de la deforestación entre 2001 y 2020 a través de técnicas de ciencia de datos y machine learning.

Aplicamos tanto modelos supervisados (como Random Forest) como no supervisados (como KMeans) para detectar patrones, hacer predicciones y agrupar provincias según su nivel de impacto. Todo con el objetivo de generar conocimiento que pueda contribuir al diseño de políticas públicas y estrategias de conservación.

🔄 Este proyecto está diseñado como una base sólida para futuras extensiones, incluyendo el análisis de reservas naturales, variables climáticas, socioeconómicas o el uso de imágenes satelitales.

🎯 Objetivos
Analizar la evolución de la deforestación en Argentina entre 2001 y 2020.

Detectar patrones temporales y espaciales de pérdida de cobertura vegetal.

Predecir la deforestación futura con modelos supervisados.

Agrupar provincias por comportamiento mediante modelos no supervisados.

Proveer herramientas de análisis que sirvan como base para políticas ambientales.

📂 Estructura del Repositorio
Copiar
Editar
├── README.md
├── datasets/
│   ├── Argentina_Deforestacion.csv
│   └── Dataset_Forest_ConservationAreas_Funding_inSouthAmerica_PAN2024.csv
├── notebooks/
│   ├── analisis_supervisado.ipynb
│   └── clustering_no_supervisado.ipynb
├── visualizaciones/
│   └── mapas, heatmaps, gráficos por región

📊 Datasets Utilizados
📌 Dataset 1 — Argentina_Deforestacion.csv
Fuente: Plataforma Trase

Filas: 2.381

Variables: Año, región, provincia (parent_region), hectáreas deforestadas

📌 Dataset 2 — Conservación de Bosques y Fondos PAN
Filas originales: 10.328

Aportó información adicional sobre regiones y años no presentes en el primero.

➡️ Se unificaron 11.417 observaciones, mejorando la calidad y cobertura del análisis.

🔄 Metodología General
1. Carga y limpieza de datos
Eliminación de columnas irrelevantes (IDs y códigos).

Revisión de nulos y duplicados (no se detectaron).

Renombrado de columnas al español.

Conversión de tipos (Año: int, Deforestación: float, Región: string).

Codificación de variables categóricas con LabelEncoder.

2. Análisis exploratorio
Boxplots, histogramas y líneas de tendencia para visualizar la evolución de la deforestación.

Análisis por provincia y región.

Aplicación de un heatmap de correlaciones para comprender la relación entre variables numéricas.

🤖 Modelos Aplicados
🧩 Aprendizaje Supervisado — Random Forest Regressor
Entrenamiento con: year, parent_region_encoded

Target: deforestation_hectares

División de datos: 80% entrenamiento, 20% prueba

Métricas finales:

MAE: 684.51

MSE: 8.568.047

R²: 0.29

✔️ Aunque el R² fue moderado, el modelo capturó bien los picos temporales de deforestación.

🧠 Aprendizaje No Supervisado — KMeans
Se construyó un dataset por provincia con:

total_deforestation

mean_deforestation

years_count

Normalización de datos con StandardScaler

KMeans con n_clusters = 3, definido mediante el método del codo.

📈 Resultados de Clustering
Cluster	Promedio Anual	Total Hectáreas	Descripción
0	~899 ha	~108.000 ha	Bajo impacto
1	~4.435 ha	~2.3 millones ha	Alto impacto sostenido
2	~4.710 ha	~1.15 millones ha	Impacto reciente, menor historial

📍 Principales Hallazgos
Provincias del norte como Chaco y Santiago del Estero concentran gran parte de la deforestación acumulada.

El período 2008–2012 mostró picos históricos en pérdida de bosques.

Los clusters permitieron distinguir regiones críticas con comportamientos distintos: impacto sostenido vs. impacto reciente.

La predicción futura es posible, pero mejoraría incluyendo más variables explicativas.

🛠️ Herramientas Utilizadas
Google Colab (para ejecución de notebooks)

Python + Pandas, NumPy, Seaborn, Matplotlib

Scikit-learn (para modelos de ML)

GitHub (gestión del proyecto)

🚀 Cómo Ejecutar el Proyecto
Clonar el repositorio:

bash
Copiar
Editar
git clone https://github.com/tu_usuario/deforestacion-argentina.git
cd deforestacion-argentina
Abrir los notebooks en Google Colab o Jupyter.

Instalar dependencias si lo ejecutás localmente:

bash
Copiar
Editar
pip install pandas numpy matplotlib seaborn scikit-learn
🌱 Futuro del Proyecto
Este trabajo sentó una base sólida para seguir profundizando en el análisis ambiental.

🔮 Posibles mejoras futuras:
Incluir variables climáticas, económicas o de uso del suelo.

Agregar imágenes satelitales (NDVI) o datos geoespaciales.

Analizar la relación con reservas naturales y áreas protegidas.

Aplicar modelos más complejos: XGBoost, LightGBM, redes neuronales.

Usar técnicas de reducción de dimensionalidad (PCA) y nuevos algoritmos de clustering (DBSCAN, Agglomerative).

📌 Conclusión
Este proyecto demostró cómo herramientas de ciencia de datos pueden aportar conocimiento valioso sobre procesos ambientales complejos. A través del análisis de datos abiertos y técnicas de machine learning, se lograron visualizar patrones, agrupar territorios y generar predicciones útiles.

🌎 La deforestación es un problema urgente. Entenderla es el primer paso para detenerla.

