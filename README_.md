# Predicción de Churn de Clientes de Telecomunicaciones

## Descripción del proyecto

Interconnect, una empresa de telecomunicaciones, busca mejorar la retención de clientes identificando a aquellos con mayor probabilidad de cancelar sus servicios. El objetivo de este proyecto es desarrollar un modelo de Machine Learning que estime el riesgo de churn y proporcione información útil para orientar estrategias de retención.

## Objetivo de negocio

El modelo busca ayudar al equipo de marketing a priorizar a los clientes con mayor probabilidad de abandonar el servicio, en lugar de aplicar campañas de retención a toda la base de clientes.

El objetivo inicial de desempeño fue alcanzar un ROC-AUC mínimo de **0.75**, buscando superar **0.88**.

## Datos

El proyecto integra cuatro conjuntos de datos con información sobre:

- Contratos de clientes
- Información personal
- Servicios de Internet
- Servicios telefónicos

Después de integrar las fuentes, el conjunto final contiene **7,043 clientes**.

La variable objetivo es `Churn`:

- `0` — cliente activo
- `1` — cliente que canceló el servicio

Distribución de clases:

- Clientes activos: **5,174**
- Clientes que cancelaron: **1,869**

## Flujo del proyecto

1. Revisión de calidad y preparación de los datos
2. Integración de múltiples conjuntos de datos
3. Creación de la variable objetivo
4. Análisis exploratorio de datos
5. Preparación de variables
6. División estratificada en entrenamiento, validación y prueba
7. Codificación One-Hot de variables categóricas
8. Estandarización de variables numéricas
9. Entrenamiento y comparación de modelos
10. Ajuste de hiperparámetros
11. Evaluación final con el conjunto de prueba
12. Recomendaciones de negocio

## Modelos evaluados

Se compararon los siguientes modelos:

- Regresión Logística
- Random Forest
- Random Forest con balanceo de clases
- CatBoost

Las métricas utilizadas fueron:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

## Modelo final

El modelo seleccionado fue **CatBoost Classifier** después del ajuste de hiperparámetros.

### Resultados en el conjunto de prueba

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.8581 |
| Precision | 0.8021 |
| Recall | 0.6176 |
| F1-score | 0.6979 |
| ROC-AUC | **0.8985** |

El ROC-AUC obtenido en validación fue de **0.9056**, mientras que en el conjunto de prueba fue de **0.8985**, mostrando un desempeño estable frente a datos no utilizados durante el entrenamiento.

## Impacto de negocio

El modelo puede utilizarse como un sistema de alerta temprana para identificar clientes con mayor probabilidad de cancelar sus servicios.

Con un Recall cercano al **62%**, el modelo identifica una proporción importante de los clientes que finalmente cancelan. Al mismo tiempo, una Precision cercana al **80%** indica que la mayoría de los clientes clasificados como de alto riesgo realmente pertenecen a la clase de churn.

Una posible aplicación consiste en segmentar a los clientes en grupos de riesgo alto, medio y bajo utilizando la probabilidad estimada por el modelo. Las acciones de retención y el umbral de clasificación pueden ajustarse posteriormente de acuerdo con el costo de los incentivos y el costo asociado con perder a un cliente.

## Limitaciones y próximos pasos

Antes de una implementación en producción sería recomendable:

- Seleccionar el umbral de clasificación considerando los costos del negocio.
- Monitorear el desempeño del modelo a lo largo del tiempo.
- Reentrenar el modelo cuando cambie el comportamiento de los clientes.
- Incorporar validación cruzada o una estrategia sistemática de búsqueda de hiperparámetros.
- Evaluar el impacto financiero de las campañas de retención.

El modelo debe utilizarse como una herramienta de apoyo para la toma de decisiones y no como sustituto del criterio de negocio.

## Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- CatBoost
- Análisis exploratorio de datos
- Machine Learning
- Clasificación
- Ajuste de hiperparámetros
- Evaluación de modelos

## Estructura del repositorio

```text
Telecom_Customers_Churn/
├── README.md
├── telecom_churn_portafolio_.ipynb
└── requirements.txt
```

## Autor

**Jesús Adrián Jiménez Vázquez**

Geólogo Senior en transición hacia Data Science y Data Analytics.
