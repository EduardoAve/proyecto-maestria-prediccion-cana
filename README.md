# Análisis Predictivo y Clasificación de Rendimiento y Calidad en Cultivos de Caña de Azúcar: Ingenio La Providencia

**Autores:** Eduardo José Avendaño Caicedo¹, Sebastián Dow Valenzuela¹
**Supervisión:** PhD. Milton Sarria-Paja²
**Institución:** ¹Maestría en Ciencia de Datos, ²Profesor - Universidad Icesi, Cali, Colombia
**Fecha:** Marzo 2024 (Revisado: Marzo 2025)

---

## Descripción General

Este repositorio contiene el código y el informe final del proyecto de Maestría en Ciencia de Datos (Universidad Icesi), enfocado en aplicar técnicas de Machine Learning para analizar, predecir y clasificar el rendimiento (TCH) y la calidad (% Sacarosa) de la caña de azúcar, utilizando datos operativos del Ingenio La Providencia (Valle del Cauca, Colombia).

## Objetivos

* **Predicción:** Estimar los valores de TCH (Toneladas de Caña/Hectárea) y %Sac.Caña usando modelos de regresión.
* **Clasificación:** Categorizar el desempeño de los lotes (Alto, Medio, Bajo) para TCH y %Sac.Caña mediante algoritmos de clasificación.

## Datos

El estudio se basa en conjuntos de datos históricos y agronómicos proporcionados por el Ingenio La Providencia.

**Nota Importante:** Por motivos de confidencialidad, los archivos de datos originales **no se incluyen** en este repositorio. El código del notebook requiere acceso a estos archivos para su ejecución.

## Metodología Resumida

El flujo de trabajo consistió en:
1.  Preprocesamiento de los datos.
2.  Análisis Exploratorio de Datos (EDA).
3.  Entrenamiento y evaluación de modelos de Regresión Lineal.
4.  Entrenamiento y evaluación de modelos de Clasificación (k-NN, Regresión Logística L1/L2).
5.  Diagnóstico y evaluación rigurosa usando validación cruzada y métricas estándar.

**La metodología completa, incluyendo detalles del preprocesamiento, modelos y evaluación, se encuentra en el informe PDF adjunto.**

## Estructura del Repositorio

* `analisis_ingenio_providencia.ipynb`: Jupyter Notebook con todo el código Python del análisis.
* `Informe_ingenio_la_providencia.pdf`: Informe final del proyecto con la descripción detallada, metodología, resultados y conclusiones.
* `README.md`: Este archivo.

## Tecnologías Utilizadas

* Python 3.x
* Scikit-learn
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Statsmodels

## Resumen de Hallazgos Clave

Los modelos de regresión lineal mostraron una capacidad predictiva moderada y ciertas limitaciones relacionadas con los supuestos del modelo. Los modelos de clasificación presentaron dificultades para distinguir claramente entre las categorías de desempeño definidas. La regularización L1 demostró ser útil para la selección de características.

**Para un análisis exhaustivo de los resultados, métricas detalladas, diagnósticos y visualizaciones, por favor consulte el informe `Informe_ingenio_la_providencia.pdf`.**

## Cómo Utilizar

El notebook `analisis_ingenio_providencia.ipynb` documenta el proceso de análisis. Para ejecutarlo se requiere:
1.  Un entorno Python con las librerías listadas.
2.  Acceso a los archivos de datos originales del Ingenio La Providencia (no proporcionados aquí).

---
