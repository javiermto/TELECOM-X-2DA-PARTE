# TELECOM-X-2DA-PARTE
Proyecto de Predicción de Churn de Clientes
Propósito del Análisis
El objetivo principal de este proyecto es desarrollar un modelo de aprendizaje automático capaz de predecir la cancelación (churn) de clientes. El análisis busca identificar patrones de comportamiento y características demográficas o de servicio que influyan en la decisión de un usuario de abandonar la compañía, permitiendo la implementación de estrategias de retención proactivas basadas en datos.

## **Estructura del Proyecto**
El repositorio está organizado de la siguiente manera:

notebooks/: Contiene el cuaderno principal (.ipynb) con todo el flujo de trabajo, desde el análisis exploratorio hasta la evaluación de modelos.

data/: Carpeta que aloja los archivos CSV con los datos crudos y tratados utilizados en el estudio.

visualizations/: Directorio con los gráficos exportados (matrices de confusión, importancia de variables y curvas de rendimiento).

README.md: Documentación general del proyecto.

## **Preparación de los Datos**

El proceso de limpieza y transformación se dividió en las siguientes etapas técnicas:

Clasificación de Variables
Variables Numéricas: Se identificaron variables como tenure, monthly_charges y total_charges para análisis estadístico y normalización.

Variables Categóricas: Se incluyeron factores como tipo de contrato, servicio de internet, método de pago y género.

Normalización y Codificación
Codificación: Se aplicó One-Hot Encoding a las variables categóricas para convertirlas en un formato numérico procesable por los modelos, estableciendo categorías de referencia para evitar la multicolinealidad.

Normalización: Las variables numéricas fueron escaladas para asegurar que todas las características contribuyan de manera equitativa a la función de coste de los modelos.

Separación de Datos
Los datos fueron divididos en un conjunto de entrenamiento (Train) y un conjunto de prueba (Test) utilizando una proporción estándar (generalmente 80/20 o 70/30) para validar la capacidad de generalización de los modelos sobre datos no vistos.

## **Modelización y Justificación**

Durante la fase de modelado se tomaron decisiones basadas en el rendimiento y la interpretabilidad:

Regresión Logística: Elegida por su alta capacidad de interpretación a través de coeficientes, permitiendo entender si una variable impulsa o previene el churn.

Random Forest: Implementado para capturar relaciones no lineales y jerarquías de importancia entre las variables.

Ajuste de Hiperparámetros: Se modificaron parámetros como la profundidad máxima y el balanceo de pesos (class_weight='balanced') para combatir el desbalanceo de clases y maximizar el Recall en la detección de fugas.

Análisis Exploratorio de Datos (EDA) e Insights
Durante el análisis inicial se obtuvieron los siguientes hallazgos clave:

Contratos: Los clientes con contratos mes a mes presentan una tasa de cancelación significativamente superior a aquellos con contratos anuales o bianuales.

Servicio de Internet: Los usuarios de fibra óptica muestran una mayor propensión al churn en comparación con los usuarios de DSL.

Antigüedad: Existe una correlación inversa entre la permanencia (tenure) y el riesgo de cancelación; los primeros 6 meses son críticos para la retención.

## **Instrucciones de Ejecución**

Requisitos Previos
Es necesario contar con un entorno de Python 3.x instalado. Se recomienda el uso de Google Colab o Jupyter Notebook.

Instalación de Bibliotecas
Ejecute el siguiente comando para instalar las dependencias necesarias:

Bash
pip install pandas numpy matplotlib seaborn scikit-learn plotly
Carga de Datos
Asegúrese de que el archivo CSV se encuentre en la ruta especificada en el cuaderno.

Cargue el archivo utilizando la biblioteca pandas:

Python
import pandas as pd
df = pd.read_csv('data/datos_tratados.csv')
Ejecute las celdas del cuaderno en orden secuencial para reproducir los resultados y las visualizaciones.
