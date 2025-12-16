# 📚 README: Tarea de Limpieza y Preprocesamiento de Datos (Data Wrangling Challenge)

Este repositorio contiene la solución para una tarea de **limpieza y preprocesamiento de datos**, donde se simuló el ciclo completo de creación, suciedad, limpieza y análisis de un conjunto de datos.

La tarea se realizó en dos roles: **Data Creator** (creador de datos sucios) y **Data Cleaner** (limpiador y analista de datos).

---

## 🚀 Estructura del Repositorio

El repositorio sigue la estructura de entrega requerida:

.
├── datacleaner/
│   ├── clean_dataset.csv             # ⬅️ Dataset limpiado por el estudiante
│   ├── cleaner.ipynb                 # ⬅️ Notebook con los pasos de limpieza y análisis
│   └── recieved_dirty_dataset.csv    # ⬅️ Dataset sucio recibido del compañero
└── datacreator/
    ├── dirty_dataset.csv             # ⬅️ Dataset sucio creado por el estudiante
    ├── enshitificator.ipynb          # ⬅️ Notebook explicando cómo se introdujeron los 10 errores
    └── source_clean_dataset.csv      # ⬅️ Dataset original de partida

## I. Rol: Data Creator (Creación de Dataset Sucio)

* **Dataset Original:** `source_clean_dataset.csv` (Dataset de ventas de videojuegos, 16.598 filas).
* **Dataset Modificado:** `dirty_dataset.csv` (Muestra de 200 filas + 40 duplicados con **errores introducidos**).

El notebook `datacreator/enshitificator.ipynb` explica detalladamente las modificaciones realizadas al dataset original para cumplir con los 10 tipos de errores requeridos por el enunciado.

### 🎯 Lista de Errores Introducidos

Se introdujeron los siguientes 10 tipos de errores:

1.  **Datos Faltantes:** Valores `np.nan`, `'Unknown'`, `""` y `'N/A'` en las columnas `Year` y `Publisher`.
2.  **Filas Duplicadas:** Se añadieron duplicados exactos (**20%** del dataset base).
3.  **Outliers:** Valores extremos en `Global_Sales`, `NA_Sales` (`9999.0`, `5000.0`) y `Year` (`2050.0`).
4.  **Inconsistencias de Formato/Unidad:** Multiplicación por **1000** en el **2%** de `EU_Sales`.
5.  **Errores Tipográficos:** Reemplazo de `'Sports'` por `'Sprots'` en la columna `Genre`.
6.  **Categorías Extranormales:** Introducción de valores de ruido en `Publisher` (ej: `'PERROSANXE'`).
7.  **Tipo de Dato Incorrecto:** Conversión de `Rank` (entero) a *string* con sufijo ordinal (ej: `'1491st'`).
8.  **Problemas de Codificación:** Inserción de caracteres acentuados (`ó`, `é`) en la columna `Name`.
9.  **Encabezados Incorrectos:** Inconsistencias de formato y puntuación en los nombres de columna (`Rank_`, `Name_`, `platform!!!!!!!!!!!`).
10. **Símbolos de Puntuación Extra:** Inserción del símbolo de moneda (**¥**) y conversión a *string* en el **30%** de `EU_Sales`.

---

## II. Rol: Data Cleaner (Limpieza y Análisis)

* **Dataset Recibido:** `datacleaner/recieved_dirty_dataset.csv` (Dataset sucio enviado por el compañero).

El notebook `datacleaner/cleaner.ipynb` detalla todo el proceso de limpieza, corrección de errores y el análisis básico posterior.

### 🛠️ Tareas de Limpieza Realizadas

* **Corrección de Encabezados** y estandarización de nombres de columna.
* **Manejo de Datos Faltantes** (`NaN`, `Unknown`, `N/A`, *strings* vacíos) mediante imputación, eliminación o conversión a un formato estándar.
* Detección y eliminación de **Duplicados**.
* **Corrección de Tipos de Datos** (ej: conversión de *strings* a numérico en `Rank` y `EU_Sales`).
* **Estandarización de Unidades y Formatos** (ej: eliminación del símbolo `¥` en `EU_Sales`, corrección de la escala en `EU_Sales`).
* **Corrección de Errores Tipográficos** y consolidación de categorías (ej: corrección de `'Sprots'`).
* Identificación y manejo (o justificación de manejo) de **Outliers** en variables de ventas y año.
* Asegurar la correcta **Codificación** para el manejo de caracteres especiales.

### 📊 Análisis Básico

Tras la limpieza, se realizó un análisis básico que incluye:

* **Estadísticas de Resumen** (Media, Mediana, Moda) para las columnas de Ventas.
* **Recuento de Frecuencias** para variables categóricas (`Genre`, `Platform`, `Publisher`).
* **Visualizaciones Clave** (Histogramas, Gráficos de Barras, Boxplots) para entender la distribución y las relaciones de los datos.