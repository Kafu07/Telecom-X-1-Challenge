# Telecom-X-1-Challenge
Telecom X 1 Challenge

# 📊 Telecom X - Análisis de Evasión de Clientes (Churn Analysis)

## 📌 Descripción del proyecto

Este proyecto tiene como objetivo analizar la **evasión de clientes (Churn)** en la empresa ficticia **Telecom X**.
La compañía enfrenta una alta tasa de cancelaciones de servicio y necesita comprender **qué factores influyen en que un cliente abandone el servicio**.

A través de un **Análisis Exploratorio de Datos (EDA)** realizado en Python, se identifican patrones y variables que podrían explicar el comportamiento de abandono de los clientes.

Este análisis sirve como base para el desarrollo posterior de **modelos predictivos de churn y estrategias de retención de clientes**.

---

# 🎯 Objetivos del análisis

* Analizar el comportamiento de los clientes que abandonan el servicio.
* Identificar variables asociadas al churn.
* Explorar patrones mediante visualización de datos.
* Generar insights que apoyen decisiones estratégicas de negocio.

---

# 🛠 Tecnologías utilizadas

* **Python**
* **Pandas** – Manipulación de datos
* **NumPy** – Operaciones numéricas
* **Matplotlib** – Visualización de datos
* **Plotly Express** – Visualizaciones interactivas
* **Requests** – Extracción de datos desde API

---

# 📂 Estructura del proyecto

```
TelecomX-Churn-Analysis/
│
├── TelecomX_LATAM.ipynb        # Notebook principal del análisis
├── README.md                   # Documentación del proyecto
└── images/                     # (Opcional) imágenes de gráficos para el README
```

---

# 🔄 Proceso de análisis de datos

El proyecto sigue el flujo clásico de análisis de datos:

## 1️⃣ Extracción de datos

Los datos se obtienen desde una API pública en formato JSON.

```python
import requests
import pandas as pd

url = "https://raw.githubusercontent.com/alura-cursos/challenge2-data-science-LATAM/main/TelecomX_Data.json"

response = requests.get(url)
data = response.json()

df = pd.json_normalize(data)
```

---

## 2️⃣ Transformación de datos (ETL)

Durante esta etapa se realizó:

* Normalización del JSON
* Limpieza de valores nulos
* Detección de duplicados
* Conversión de variables
* Traducción de variables al español
* Conversión de variables categóricas a binarias

Ejemplo de transformación:

```python
df['CargosTotal'] = pd.to_numeric(df['CargosTotal'], errors='coerce')
```

---

## 3️⃣ Análisis Exploratorio de Datos (EDA)

Se realizaron distintos análisis para identificar patrones en el abandono de clientes:

* Análisis de tasa de churn
* Relación entre churn y género
* Relación entre churn y tipo de contrato
* Relación entre churn y servicio de internet
* Relación entre churn y método de pago
* Análisis de cargos mensuales
* Antigüedad del cliente
* Matriz de correlación de variables numéricas

---

# 📊 Ejemplos de visualizaciones

### Abandono según tipo de contrato

Este gráfico permite observar cómo varía la tasa de abandono dependiendo del tipo de contrato del cliente.

```python
px.histogram(df, x="TipoContrato", color="Abandono")
```

Insight principal:

Los **clientes con contrato mensual presentan mayor probabilidad de abandono**.

---

### Abandono según meses de contrato

Permite observar si la antigüedad del cliente influye en la evasión.

Insight principal:

Los **clientes con menor antigüedad tienen mayor probabilidad de cancelar el servicio**.

---

### Distribución de cargos mensuales

Se analiza si el costo del servicio influye en el abandono.

Insight principal:

Clientes con **cargos mensuales más altos presentan mayor tasa de churn**.

---

### Matriz de correlación

Se analiza la relación entre variables numéricas del dataset.

```python
df.corr()
```

Variables como:

* **MesesContrato**
* **CargoMensual**
* **CargosTotales**

podrían ser relevantes para modelos de predicción de churn.

---

# 📈 Principales insights del análisis

A partir del análisis exploratorio se identificaron los siguientes patrones:

### 1️⃣ Alta tasa de churn

La tasa de abandono se encuentra aproximadamente entre **25% y 27%**, lo que representa un desafío importante para la empresa.

---

### 2️⃣ El tipo de contrato influye en el churn

Los clientes con **contratos mensuales presentan mayor probabilidad de abandonar el servicio**.

Los contratos de largo plazo tienden a generar mayor fidelización.

---

### 3️⃣ La antigüedad del cliente es un factor clave

Los clientes con **menos tiempo en la empresa presentan mayor probabilidad de cancelar el servicio**.

Esto sugiere que los primeros meses son críticos para la retención.

---

### 4️⃣ El cargo mensual puede influir en el abandono

Se observa que los clientes con **cargos mensuales más altos presentan mayor tendencia a abandonar**.

Esto podría estar relacionado con la percepción de valor del servicio.

---

### 5️⃣ El método de pago muestra diferencias en churn

Algunos métodos de pago presentan **mayores tasas de abandono**, especialmente aquellos que no son automáticos.

---

# 💡 Recomendaciones estratégicas

A partir de los resultados obtenidos, Telecom X podría considerar:

* Incentivar **contratos de largo plazo** (anuales o bianuales).
* Mejorar la **experiencia del cliente durante los primeros meses**.
* Promover **métodos de pago automáticos**.
* Crear **paquetes de servicios (bundles)** para aumentar fidelización.
* Desarrollar **modelos predictivos de churn** para identificar clientes en riesgo.

---

# 🚀 Próximos pasos

Como continuación de este análisis se recomienda:

* Construir un **modelo de Machine Learning para predecir churn**.
* Realizar **segmentación de clientes**.
* Implementar **estrategias de retención personalizadas**.
* Analizar el impacto económico del churn.

---

# 👤 Autor

**Nicolás Yáñez**

Proyecto desarrollado como parte de práctica de **Análisis de Datos y Exploración de Datos con Python**.

---
