# Análisis Predictivo y Clasificación de Rendimiento y Calidad en Cultivos de Caña de Azúcar: Ingenio La Providencia

**Autores:** Eduardo José Avendaño Caicedo¹, Sebastián Dow Valenzuela¹
**Supervisión:** PhD. Milton Sarria-Paja²
**Institución:** ¹Maestría en Ciencia de Datos, ²Profesor - Universidad Icesi, Cali, Colombia
**Fecha:** Marzo 2024 (Revisado: Marzo 2025)

---

## Descripción General

Este repositorio contiene el trabajo realizado para el proyecto final de la Maestría en Ciencia de Datos de la Universidad Icesi. El estudio se centra en la aplicación de técnicas de análisis predictivo y clasificación sobre datos operativos del Ingenio La Providencia (Valle del Cauca, Colombia) [source: 3] para evaluar y predecir el rendimiento (Toneladas de Caña por Hectárea - TCH) [source: 4] y la calidad (% Sacarosa en Caña - %Sac.Caña) [source: 4] de los cultivos de caña de azúcar.

## Contexto

La optimización de la producción agrícola es vital para la industria azucarera [source: 8]. Este proyecto busca explorar cómo la ciencia de datos puede contribuir a mejorar la toma de decisiones en el Ingenio La Providencia mediante el análisis de sus datos históricos y agronómicos [source: 9, 10].

## Objetivos del Proyecto

1.  **Predicción (Regresión):** Desarrollar y evaluar modelos de regresión lineal múltiple para estimar los valores numéricos de TCH y %Sac.Caña [source: 12].
2.  **Clasificación:** Construir y evaluar modelos de clasificación (k-NN, Regresión Logística con regularización L1/L2) para categorizar los lotes ('suertes') en niveles de desempeño (Alto, Medio, Bajo) para TCH y %Sac.Caña, basados en percentiles (terciles) [source: 13, 23, 24].

## Datos

Se utilizaron dos conjuntos de datos principales proporcionados por el Ingenio La Providencia para este análisis [source: 14]:

1.  `HISTORICO_SUERTES.xlsx`: Datos históricos con $N=21027$ registros, usados principalmente para la regresión [source: 4].
2.  `BD_IPSA_1940.xlsx`: Datos con mayor detalle agronómico ($N=1940$), usados para la clasificación [source: 5, 18].

**Nota Importante:** Los archivos de datos originales (`.xlsx`) **no se incluyen** en este repositorio debido a la confidencialidad de la información del Ingenio La Providencia. El notebook requiere acceso a estos archivos para ser ejecutado completamente.

## Metodología

El flujo de trabajo implementado incluye las siguientes etapas:

1.  **Preprocesamiento de Datos:** Limpieza, manejo de valores nulos, codificación de variables categóricas (One-Hot Encoding) y escalado de variables numéricas (StandardScaler) [source: 20].
2.  **Análisis Exploratorio de Datos (EDA):** Análisis univariado y multivariado para entender las distribuciones, correlaciones y características de los datos [source: 21].
3.  **Modelado de Regresión:** Entrenamiento de modelos de Regresión Lineal Múltiple, diagnóstico de supuestos (Multicolinealidad (VIF), Normalidad de Residuos (Shapiro-Wilk), Homocedasticidad (Breusch-Pagan)) [source: 22].
4.  **Modelado de Clasificación:** Definición de clases (Bajo, Medio, Alto) usando terciles, entrenamiento de modelos k-NN y Regresión Logística (L1/L2) [source: 23, 24].
5.  **Evaluación:** Uso de Validación Cruzada (K-Fold y Estratificada) y métricas estándar como $R^{2}$, RMSE, MAE para regresión, y Accuracy, Matriz de Confusión, Reporte de Clasificación y Kappa de Cohen para clasificación [source: 26, 35].

## Estructura del Repositorio

* `analisis_ingenio_providencia.ipynb`: Jupyter Notebook que contiene todo el código Python para el preprocesamiento, EDA, modelado y evaluación.
* `Informe_ingenio_la_providencia.pdf`: Informe final del proyecto en formato PDF, detallando la metodología, resultados, discusión y conclusiones [source: doc].
* `README.md`: Este archivo, que describe el repositorio.

## Librerías Utilizadas

El análisis se realizó utilizando Python 3.x y las siguientes librerías principales [source: 48]:

* `pandas`
* `numpy`
* `scikit-learn`
* `matplotlib`
* `seaborn`
* `statsmodels`
* `scipy`

Se recomienda crear un entorno virtual e instalar las librerías (preferiblemente usando un archivo `requirements.txt` si se genera a partir del notebook).

## Resumen de Resultados

* **Regresión:** Los modelos lineales mostraron una capacidad explicativa limitada para TCH ($R^{2} \approx 0.21$) [source: 30, 37] y presentaron violaciones en los supuestos clave (multicolinealidad, normalidad de residuos, homocedasticidad) [source: 31, 32].
* **Clasificación:** La exactitud (Accuracy) promedio en validación cruzada para clasificar el desempeño fue modesta (aproximadamente 45%), con un coeficiente Kappa bajo ($\approx 0.17$), indicando dificultad para separar las clases definidas [source: 35, 37, 40]. La regularización L1 fue útil para reducir la dimensionalidad sin sacrificar rendimiento [source: 33, 42].
* **Visualizaciones:** Se generaron diversas visualizaciones (distribuciones, correlaciones, diagnósticos de residuos, matrices de confusión) que aportan valor al análisis [source: 6, 29, 34, 35, 44].

**Para un análisis detallado de los resultados y las visualizaciones, por favor consulte el archivo `Informe_ingenio_la_providencia.pdf`.** [source: doc]

## Conclusiones y Trabajo Futuro

El estudio establece una línea base cuantitativa para la predicción y clasificación en el contexto del Ingenio La Providencia [source: 45, 46]. Se identificaron limitaciones en los modelos lineales simples y en la definición actual de clases. Futuras líneas de investigación podrían incluir [source: 47]:

* Incorporación de variables adicionales (climáticas más granulares, espaciales, etc.).
* Exploración de modelos más avanzados (no lineales, ensambles, etc.).
* Revisión de la definición de las clases de desempeño.

