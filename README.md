# Predicción de sentimiento en comentarios NPS

Proyecto de Machine Learning y NLP para clasificar automáticamente comentarios de clientes en categorías **Detractor**, **Neutro** y **Promotor**, a partir de encuestas **NPS** de una procesadora de pagos.

## Descripción del proyecto

Las empresas que gestionan encuestas NPS suelen recibir miles de comentarios abiertos de clientes. Aunque la nota numérica resume el nivel de satisfacción, el valor real está en entender rápidamente el motivo detrás de cada calificación.

Este proyecto propone una solución de **Procesamiento de Lenguaje Natural (NLP)** para automatizar la clasificación de comentarios y transformar la voz del cliente en información accionable para el negocio.

## Objetivo

Desarrollar un modelo de clasificación multiclase que permita predecir automáticamente la categoría NPS de un comentario de cliente:

- **Detractor**: notas de 0 a 6
- **Neutro**: notas de 7 a 8
- **Promotor**: notas de 9 a 10

## Dataset

El dataset utilizado contiene información de encuestas NPS con las siguientes variables principales:

- `id`: identificador único de la encuesta o cliente
- `nota_nps`: calificación otorgada por el cliente
- `comentario`: texto abierto con la opinión del cliente
- `categoria_nps`: variable objetivo generada a partir de la nota NPS

### Características del dataset

- **Volumen original**: 50,000 registros
- **Problema**: clasificación multiclase supervisada
- **Tipo de datos**: texto libre + variable numérica derivada

## Metodología

El pipeline implementado incluye las siguientes etapas:

1. **Carga y exploración de datos**
2. **Limpieza y normalización de texto**
3. **Eliminación de duplicados exactos**
4. **Creación de la variable objetivo**
5. **Vectorización TF-IDF**
6. **Entrenamiento de modelos de clasificación**
7. **Evaluación y comparación con modelos baseline**
8. **Análisis de interpretabilidad**

## Modelos evaluados

Se compararon distintos enfoques de clasificación:

- **Red neuronal multicapa (MLP) en PyTorch**
- **Logistic Regression**
- **Random Forest**

### Modelo principal

El modelo principal utiliza:

- representación **TF-IDF**
- features numéricas auxiliares
- arquitectura densa en PyTorch
- capas ocultas de **128, 64 y 32 neuronas**
- activación **ReLU**
- regularización con **Dropout**
- función de pérdida **CrossEntropyLoss**

## Resultados

Los modelos evaluados obtuvieron un desempeño sobresaliente en el conjunto de prueba.

### Métricas principales

- **Accuracy**: 1.0000
- **Precision**: 1.0000
- **Recall**: 1.0000
- **F1-Score**: 1.0000

### Interpretación

Los resultados sugieren que el dataset presenta patrones lingüísticos muy marcados entre las clases. Sin embargo, antes de llevar la solución a producción, es recomendable validar el modelo con datos nuevos y más recientes para comprobar su robustez fuera de muestra.

## Estructura del repositorio

```bash
.
├── data/
│   └── README.md
├── figures/
├── notebooks/
├── report/
├── results/
├── src/
├── README.md
└── requirements.txt
