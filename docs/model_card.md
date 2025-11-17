# Model Card: Pipeline ETL de Demanda de Taxis v1.0

## Descripción del Pipeline
Este pipeline ETL procesa datos históricos de viajes Yellow Taxi NYC para identificar zonas y horas de alta demanda.
Incluye extracción desde la nube, limpieza, transformaciones, optimización y generación de métricas agregadas.

- Tecnología: PySpark 3.x
- Infraestructura: AWS S3 / Google Cloud Storage
- Formato de salida: Parquet particionado

## Datos Procesados

- Volumen estimado: 12–20 millones de registros por mes (según año)
- Período analizado: Año 2023 (o el que especifiques)
- Variables: 20–30 columnas originales + variables derivadas
- Fuente: NYC Yellow Taxi 
- Más detalles: ver data_dictionary.md

## Limitaciones Conocidas

- No incluye modelo predictivo (solo análisis descriptivo).
- No detecta anomalías complejas (necesitaría ML).
- Sensible a coordenadas erróneas en versiones antiguas del dataset.

## Uso recomendado
       
