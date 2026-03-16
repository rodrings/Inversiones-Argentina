# Predicción de Rentabilidad de Inversiones en Argentina utilizando Machine Learning

Este proyecto corresponde al trabajo final del curso de Data Science realizado en Coderhouse. El objetivo de la investigación es analizar distintas alternativas de inversión en Argentina y estudiar, a partir de datos históricos, si es posible predecir su rentabilidad real y su capacidad para superar la inflación.

Argentina presenta un contexto económico caracterizado por alta inflación, volatilidad financiera e incertidumbre macroeconómica. En este escenario, muchas personas enfrentan dificultades al momento de decidir qué hacer con sus ahorros, debido tanto a la desconfianza en la moneda local como a la falta de información clara sobre las distintas alternativas de inversión disponibles.

A partir de esta problemática, el proyecto busca analizar el comportamiento histórico de distintos instrumentos financieros y aplicar modelos de Machine Learning para identificar patrones y realizar predicciones sobre su desempeño futuro.

## Objetivos del proyecto

El objetivo principal es evaluar diferentes instrumentos financieros disponibles en Argentina y analizar su capacidad para generar rentabilidad real positiva, es decir, superar la inflación.

En particular, el proyecto busca:

- Analizar el comportamiento histórico de distintas inversiones.
- Comparar su rentabilidad real frente a la inflación.
- Estudiar la relación entre variables macroeconómicas y el rendimiento de los activos.
- Construir modelos de Machine Learning que permitan predecir si una inversión superará la inflación.
- Estimar la rentabilidad real de distintos activos para el mes siguiente.

## Dataset

El análisis se basa en un dataset con información mensual desde 2015 hasta 2024. Los datos incluyen variables macroeconómicas y la rentabilidad de distintos instrumentos financieros relevantes para el mercado argentino.

Las variables principales del dataset incluyen:

- Inflación mensual
- Rentabilidad del plazo fijo
- Rentabilidad de fondos comunes de inversión (FCI)
- Variación del dólar blue
- Rentabilidad de Bitcoin
- Variación del índice Merval
- Rentabilidad real de cada uno de los instrumentos
- Riesgo país

El repositorio incluye el archivo:

rentabilidad_inversiones_argentina_con_riesgo_pais.csv

## Hipótesis de investigación

A lo largo del proyecto se analizan distintas hipótesis relacionadas con el comportamiento de las inversiones en Argentina.

En primer lugar, se analiza si es posible predecir, a partir de datos históricos, si una inversión determinada logrará superar la inflación. Utilizando modelos de clasificación binaria, se busca determinar si existen patrones en los datos que permitan anticipar este comportamiento.

También se estudia si mantener ahorros en dólares resulta más rentable que invertir en instrumentos tradicionales en pesos. El análisis muestra que esto depende del contexto económico, aunque en muchos períodos el dólar ha presentado una rentabilidad real superior a la de las inversiones en moneda local.

Otra hipótesis plantea que muchas inversiones tradicionales en pesos tienen dificultades para superar la inflación mensual, mientras que activos dolarizados o internacionales tienden a mantener una rentabilidad real más elevada.

Finalmente, se analiza la relación entre el riesgo país y el rendimiento de los distintos activos, evaluando si en períodos de mayor incertidumbre económica las inversiones dolarizadas presentan mejores resultados.

## Análisis Exploratorio de Datos

El proyecto comienza con un análisis exploratorio del dataset para comprender su estructura y evaluar la calidad de los datos.

En esta etapa se realizaron:

- Revisión de la estructura del dataset y tipos de datos
- Análisis de estadísticas descriptivas
- Verificación de valores faltantes
- Visualización de distribuciones mediante histogramas
- Detección de posibles valores atípicos mediante boxplots
- Análisis de correlaciones entre variables mediante matrices de correlación

El análisis inicial mostró que el dataset se encuentra completo, sin valores faltantes ni inconsistencias relevantes, lo que permitió avanzar con el modelado.

Además, se realizaron distintas visualizaciones para analizar la relación entre la inflación y las inversiones, así como la posible influencia del riesgo país sobre la rentabilidad de los distintos activos.

## Feature Engineering

Para mejorar el desempeño de los modelos se realizó un proceso de ingeniería de características.

Se generaron nuevas variables a partir de la información original, incluyendo:

- Lags temporales de las rentabilidades de los activos
- Cambios porcentuales mensuales (momentum)
- Medias móviles de corto y mediano plazo
- Medidas de volatilidad
- Indicadores de tendencia
- Variables de interacción entre distintos activos

Estas transformaciones permitieron incorporar información temporal y mejorar la capacidad predictiva de los modelos.

## Modelos de Machine Learning

El proyecto utiliza dos enfoques principales de modelado.

### Modelos de clasificación

Se construyeron modelos de clasificación binaria cuyo objetivo es predecir si una inversión superará la inflación en un determinado período.

La variable objetivo se define como:

supera_inflacion = 1 si la rentabilidad real del activo es positiva  
supera_inflacion = 0 en caso contrario

Para este problema se utilizó un modelo Random Forest Classifier, implementado dentro de un pipeline que incluye escalado de variables y optimización de hiperparámetros mediante GridSearchCV y validación cruzada.

### Modelos de regresión

Además del problema de clasificación, se desarrollaron modelos de regresión con el objetivo de estimar directamente la rentabilidad real de cada activo para el mes siguiente.

Para esta tarea se utilizó RandomForestRegressor, optimizado mediante búsqueda de hiperparámetros y evaluado utilizando métricas como:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Coeficiente de determinación (R²)

Los modelos obtuvieron valores positivos y relativamente altos de R², lo que indica que logran capturar una parte significativa de la variabilidad presente en los datos.

## Resultados

Los resultados obtenidos muestran que es posible construir modelos capaces de identificar patrones en los datos históricos y utilizarlos para estimar el comportamiento futuro de distintos instrumentos financieros.

Los modelos de clasificación lograron predecir con buen desempeño si una inversión superará la inflación, mientras que los modelos de regresión permitieron estimar la rentabilidad real esperada para el mes siguiente.

Es importante destacar que, debido a la naturaleza incierta de los mercados financieros y al tamaño limitado del dataset, estos resultados deben interpretarse como un ejercicio de análisis de datos y modelado predictivo, y no como una herramienta definitiva de predicción financiera.

## Tecnologías utilizadas

El proyecto fue desarrollado en Python utilizando principalmente las siguientes librerías:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

Estas herramientas se utilizaron para el procesamiento de datos, visualización, construcción de modelos y evaluación de resultados.

## Estructura del repositorio

El repositorio contiene los siguientes archivos principales:

rentabilidad_inversiones_argentina_con_riesgo_pais.csv  
Dataset con la información histórica utilizada en el análisis.

InversionesArgentina final.ipynb  
Notebook que contiene todo el proceso de análisis exploratorio, modelado y evaluación de los resultados.

README.md  
Documento de descripción del proyecto.

## Aclaración

Este proyecto tiene fines educativos y forma parte de un trabajo académico dentro de un curso de Data Science. Los resultados presentados no constituyen asesoramiento financiero ni recomendaciones de inversión.

## Autor

Rodrigo García Solá
