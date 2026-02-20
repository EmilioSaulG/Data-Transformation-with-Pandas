# Data Transformation with Pandas

## Descripción del Proyecto

Este proyecto se centra en la transformación, normalización y preprocesamiento de datos utilizando Pandas. El objetivo principal es procesar datos estructurados y semi-estructurados provenientes de una base de datos en formato JSON para prepararlos para análisis y modelado.

El conjunto de datos contiene información relacionada con propiedades en renta, como comodidades, tamaño, ocupación en periodos determinados, reseñas y datos de precios. A través de un proceso sistemático de limpieza y generación de variables, el dataset transformado permite desarrollar un algoritmo de recomendación de tarifas diarias en periodos de alta demanda.

El enfoque principal del branch `main` es el manejo avanzado de datos con Pandas.

---

## Estructura del Proyecto

```
├── data/
│   └── properties.json
│
├── notebooks/
│   └── data_transformation.ipynb
│
├── src/
│   └── data_processing.py
│
├── README.md
└── requirements.txt
```

---

## Tecnologías Utilizadas

- Python 3  
- Pandas  
- NumPy  
- JSON  

---

## Fuente de Datos

El proyecto utiliza una base de datos en formato JSON que contiene información anidada sobre propiedades de renta, incluyendo:

- Características de la propiedad  
- Comodidades  
- Periodos de ocupación  
- Información de precios  
- Reseñas  
- Fechas de reservación  

---

## Proceso de Transformación de Datos

### 1. Normalización del JSON

- Uso de `pandas.json_normalize()` para aplanar estructuras anidadas.
- Conversión de datos jerárquicos en un DataFrame estructurado.
- Estandarización de nombres de columnas.

---

### 2. Limpieza de Datos

Se aplicaron múltiples procesos de limpieza:

- Eliminación de espacios y caracteres especiales en columnas de precio.
- Conversión de valores monetarios a tipo `float64`.
- Conversión de columnas numéricas a `int64` y `float64`.
- Reemplazo de valores nulos en columnas relacionadas con ocupación por `0` para representar periodos desocupados.
- Uso de `applymap()` para aplicar transformaciones elemento por elemento en el DataFrame.

---

### 3. Procesamiento de Texto

En las columnas de reseñas se realizaron los siguientes ajustes:

- Conversión de texto a minúsculas.
- Eliminación de caracteres especiales mediante expresiones regulares (`a-z`, `0-9`).
- Normalización básica del contenido textual.
- Tokenización mediante `str.split()`.

---

### 4. Transformación de Fechas

- Eliminación del formato con `/` en fechas.
- Conversión de columnas a tipo `datetime64`.
- Extracción de año y mes en columnas independientes.
- Generación de variables temporales derivadas para análisis de demanda.

---

## Ingeniería de Variables

Durante el proceso de transformación se generaron variables estructuradas como:

- Columnas de precio limpias en formato numérico  
- Indicadores de ocupación  
- Componentes temporales (año y mes)  
- Texto de reseñas procesado  
- Variables temporales para análisis estacional  

Estas transformaciones permiten estructurar los datos para el desarrollo de un algoritmo de recomendación de precios.

---

## Ramas Adicionales

### project_1

- Uso de dos bases de datos JSON adicionales.
- Aplicación de funciones similares de normalización y limpieza.
- Enfoque en reutilización de procesos de transformación.

### project_2

Proyecto enfocado en análisis financiero de pagos:

- Cálculo de diferencia entre fecha de pago esperada y fecha real.
- Medición del desfase en días de pago.
- Cálculo de la media de atraso.
- Análisis de comportamiento de cumplimiento de pago.

---

## Enfoque Técnico

Este proyecto demuestra competencias en:

- Limpieza y preprocesamiento de datos  
- Normalización de JSON  
- Tipado explícito de datos en Pandas  
- Manipulación de cadenas y expresiones regulares  
- Transformación y análisis temporal  
- Ingeniería de variables  
- Preparación de datos para modelado analítico  

---

## Próximos Pasos

- Implementar un modelo predictivo de recomendación de precios.
- Incorporar análisis de estacionalidad.
- Automatizar el pipeline de transforma
