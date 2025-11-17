# Diccionario de datos

## Tabla: yellow_tripdata
| Campo                   | Tipo      | Descripción                                        | Ejemplo             | Restricciones                      |
| ----------------------- | --------- | -------------------------------------------------- | ------------------- | ---------------------------------- |
| `tpep_pickup_datetime`  | timestamp | Fecha y hora de inicio del viaje                   | 2023-01-15 08:45:30 | NOT NULL                           |
| `tpep_dropoff_datetime` | timestamp | Fecha y hora de finalización del viaje             | 2023-01-15 09:02:10 | NOT NULL                           |
| `passenger_count`       | int       | Número de pasajeros                                | 2                   | >= 0                               |
| `trip_distance`         | float     | Distancia del viaje en millas                      | 3.45                | > 0                                |
| `pickup_longitude`*     | float     | Longitud del punto de recogida                     | -73.985             | Dentro del rango geográfico de NYC |
| `pickup_latitude`*      | float     | Latitud del punto de recogida                      | 40.758              | Dentro del rango geográfico de NYC |
| `dropoff_longitude`*    | float     | Longitud del punto de destino                      | -73.971             | —                                  |
| `dropoff_latitude`*     | float     | Latitud del punto de destino                       | 40.764              | —                                  |
| `fare_amount`           | float     | Tarifa básica del viaje                            | 12.5                | >= 0                               |
| `extra`                 | float     | Cargos adicionales                                 | 0                   | >= 0                               |
| `mta_tax`               | float     | Impuesto MTA                                       | 0.5                 | >= 0                               |
| `tip_amount`            | float     | Propina                                            | 3.25                | >= 0                               |
| `tolls_amount`          | float     | Peajes                                             | 0                   | >= 0                               |
| `total_amount`          | float     | Total del viaje                                    | 18.25               | >= 0                               |
| `payment_type`          | int       | Método de pago (1=Credit 2=Cash...)                | 1                   | 1–5                                |
| `ratecodeid`            | int       | Código de tarifa                                   | 1                   | 1–6                                |
| `store_and_fwd_flag`    | string    | Si el viaje fue almacenado antes de enviarse (Y/N) | N                   | ('Y', 'N')                         |


## Variables derivadas
| Feature                 | Fórmula                                               | Descripción                       |
| ----------------------- | ----------------------------------------------------- | --------------------------------- |
| `trip_duration_minutes` | `(tpep_dropoff_datetime - tpep_pickup_datetime) / 60` | Duración total del viaje          |
| `pickup_hour`           | `HOUR(tpep_pickup_datetime)`                          | Hora del día (0-23)               |
| `pickup_day`            | `DAYOFWEEK(tpep_pickup_datetime)`                     | Día de la semana (1-7)            |
| `pickup_month`          | `MONTH(tpep_pickup_datetime)`                         | Mes del viaje                     |
| `is_night_trip`         | `pickup_hour >= 22 OR pickup_hour < 5`                | Viaje nocturno                    |
| `tip_percentage`        | `(tip_amount / fare_amount) * 100`                    | % de propina                      |
| `demand_bucket`         | Clasificación según cantidad de viajes por zona       | Se usa para clustering o insights |
| `weekend_flag`          | `(pickup_day = 1 OR pickup_day = 7)`                  | Si el viaje fue sábado/domingo    |
