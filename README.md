# TrabajoFinal2025 — Data Science : TaxiDataScienceGroup
Detección de zonas y horas con alta demanda en NYC usando PySpark
## Descripción
Pipeline ETL en PySpark para analizar la demanda de taxis en NYC y optimizar la redistribución de flota.

## Problema
Las empresas de taxi enfrentan el reto de posicionar sus vehículos en los lugares y horarios donde la demanda es más alta. Sin herramientas basadas en datos, la distribución de la flota tiende a ser ineficiente y reactiva.

## Solución
Este proyecto usa datos reales de NYC Taxi para identificar patrones de demanda y apoyar decisiones operativas.

Se construye un pipeline ETL en PySpark para procesar millones de registros y generar métricas que permitan detectar zonas y horas con mayor demanda de taxis.

## Características

- Visualizaciones dinámicas (gráficas, mapa)
- Indicadores clave: zonas criticas, horarios pico
- Dashboard

## Tecnologías Utilizadas

- Python 3.9+
- PySpark
- AWS S3 / Google Cloud Storage
- Parquet

## Estructura del proyecto
TrabajoFinal2025-Data-Scientists-TaxiDataScienceGroup/
│
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
│
├── notebooks/
│   ├── 01_exploracion_inicial.ipynb
│   ├── 02_limpieza_y_etl.ipynb
│   └── 03_metricas_demanda.ipynb
│
├── src/
│   ├── data/
│   │   ├── make_dataset.py
│   │   └── clean_data.py
│   ├── features/
│   │   └── build_features.py
│   └── visualization/
│       └── visualize.py
│
├── reports/
│   └── figures/
│
├── docs/
│   ├── project_charter.md
│   ├── data_dictionary.md
│   └── model_card.md
│
├── .gitignore
├── requirements.txt 
├── setup.py 
├── README.md 
└── LICENSE             

## Instalación

### Requisitos
- Python 3.13.3 o superior
- GIT

### Pasos de instalación
1. Clonar el repositorio
```bash
git clone https://github.com/LM-8941/TrabajoFinal2025-Data-Scientists-TaxiDataScienceGroup.git
cd TrabajoFinal2025-Data-Scientists-TaxiDataScienceGroup
```
2. Crear entorno virtual
```bash
python -m venv venv
source venv/Scripts/activate
```
3. Instalar dependencias
```bash
pip install -r requirements.txt
```
4. Ejecutar el job PySpark
```bash
spark-submit src/pipeline_etl.py
```

## Resultados
- Métricas de demanda por hora y zona
- Base para dashboards 
- Mapas y Gráficos

## Roadmap 
### Versión Actual (v1.0)

- Configuración del entorno PySpark
- Pipeline ETL básico (extracción → limpieza → transformación)
- Carga de datos desde S3
- Escritura optimizada en formato Parquet
- Métricas iniciales: viajes por hora y distancia

### Próximas Versiones
v1.1 — Optimización & Data Quality
- Implementación de particionamiento por fecha/hora
- Uso de caching y broadcast joins
- Validaciones de calidad de datos (outliers, nulos, rangos invalidos)
- Monitoreo básico del pipeline

v1.2 — Visualización
- Dashboard de zonas con mayor demanda
- Mapa geográfico interactivo

## Contribución
¡Las contribuciones son bienvenidas!
Si deseas mejorar el pipeline, agregar funciones o reportar errores, sigue estos pasos:
1. Haz un fork del repositorio
2. Crea una nueva rama
```bash
git checkout -b feature/TuNuevaFeature
```
3. Realiza tus cambios y haz commit
```bash
git commit -m "Descripción corta de la mejora"
```
4. Sube tu rama
```bash
git push origin feature/TuNuevaFeature
```
5. Abre un Pull Request con una descripción clara de tu contribución.


## Equipo

- ** Noemy Beltran **  - [@abigailviana] (https://github.com/abigailviana)
- ** Luis Menjivar **  - [@LM-8941] (https://github.com/LM-8941)

