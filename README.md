# Optimización de un Modelo k-NN para Clasificación

## Descripción del Proyecto

Este repositorio contiene el proceso completo de optimización y evaluación de un modelo de clasificación basado en k-Nearest Neighbors (k-NN). El modelo fue entrenado utilizando el conjunto de datos de análisis de personalidad del cliente, disponible en Kaggle, y se optimizó a través de técnicas como GridSearch y RandomizedSearch.

El objetivo principal fue construir un modelo eficiente y simple para predecir la respuesta de los clientes a una campaña de marketing.

---

## Contenido del Repositorio

- `data/`: Carpeta que contiene el conjunto de datos original descargado de Kaggle.
- `notebook/`: Archivos Jupyter Notebook con el análisis, optimización y evaluación del modelo.
- `models/`: Modelos entrenados guardados como archivos `.pkl`.
- `README.md`: Este archivo, que describe el proyecto y los resultados obtenidos.
- `requirements.txt`: Lista de bibliotecas necesarias para ejecutar el código.
- `main.py`: Script principal para entrenar y evaluar el modelo.

---

## Datos Utilizados

### Descripción del Conjunto de Datos

El conjunto de datos utilizado proviene de [Kaggle: Customer Personality Analysis](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis). Este dataset contiene información demográfica y de consumo de los clientes, utilizada para analizar patrones de comportamiento y respuesta.

### Variables Seleccionadas
Se eligieron las siguientes variables como características relevantes:
- **Income**: Ingreso anual del cliente.
- **MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts, MntGoldProds**: Gastos en distintas categorías de productos.
- **NumDealsPurchases, NumWebPurchases, NumCatalogPurchases, NumStorePurchases, NumWebVisitsMonth**: Comportamiento de compra.

**Variable Objetivo**:
- **Response**: Respuesta del cliente a la campaña de marketing (1: Sí, 0: No).

---

## Modelo Seleccionado

Tras evaluar múltiples configuraciones, se seleccionó el modelo más **simple** con los siguientes hiperparámetros óptimos:

- **n_neighbors**: 13
- **weights**: `distance`
- **metric**: `manhattan`
- **p**: 1

---

## Resultados

### Métricas del Modelo en el Conjunto de Prueba

| Métrica            | Clase 0 | Clase 1 | Promedio Ponderado |
|--------------------|---------|---------|---------------------|
| **Precisión**      | 0.87    | 0.79    | 0.87                |
| **Recall**         | 0.99    | 0.16    | 0.87                |
| **F1-Score**       | 0.93    | 0.27    | 0.83                |

- **Precisión General**: 87%
- **Soporte Total**: 444 instancias
  - Clase 0: 377
  - Clase 1: 67

---

## Cómo Ejecutar el Código

1. **Clonar el Repositorio**:
   ```bash
   git clone <url-del-repositorio>
   cd <nombre-del-repositorio>
