# **PREDICCIÓN DE LA DEMANDA DE ENERGÍA ELÉCTRICA EN ANTIOQUIA**

- [Resumen](#resumen)
- [Descripción del repositorio](#descripción-del-repositorio)
  - [data](#data)
  - [notebooks](#notebooks)
  - [docs](#docs)
  - [init.py](#initpy)
- [Forma de usar los notebooks](#forma-de-usar-los-notebooks)

---

# **Resumen**

Este repositorio contiene los notebooks, data y documentos relacionados con el proyecto de monografía de la especialización en analítica y ciencia de la Universidad de Antioquia.

---

# **Descripción del repositorio**

## **data**

En esta carpeta se encuentran todos los datos utilizados en este proyecto, dicha información está organizada de la siguiente forma:

- `consumo`: En esta carpeta se encuentra la información del consumo o demanda de energía eléctrica horaria en la región de Antioquia, esta información fue extraída del API de XM, el ente regulador del mercado de energía eléctrica. Eesta información se encuentra en un archivo llamado `demanda_comercial.csv`.

- `temperatura`: En esta carpeta se encuentra la información de las temperaturas promedio, maxima y mediana horaria del departamento de Antioquia, esta información fue extraída del API de Socrata, que se conecta con la plataforma de datos abiertos del gobierno Colombiano (<https://www.datos.gov.co/>). Esta información se encuentraun archivo llamado `temperaturas.csv`.

- `data_procesada.csv`: Este es el resultado del proceso de limpieza y preparación de datos realizado en el notebook `1_extraccion_procesamiento_y_limpieza_datos.ipynb`, en donde se unieron las bases de datos antes mencionadas.

## **notebooks**

En esta carpeta se encuentran los notebooks usados en el proyecto.

- `1_extraccion_procesamiento_y_limpieza_datos.ipynb`: En este notebook se realiza el proceso de extración de los datos de la APIs de XM y Socrata, y la posterior unión de las bases de datos. Además, se realiza un proceso de limpieza de datos eliminando datos atipicos, imputación de datos faltantes, etc.

- `2_analisis_series_tiempo.ipynb`: En este notebook se realiza un el analisis de datos, en donde se usan metodos de analisis de datos de series de tiempo, como graficos de autocorrelacion, desomposición estacional, etc.

- `3_predicción_serie_tiempo_iniciales.ipynb`: En este notebook se realizan las primera iteraciones de los modelos de predicción, en este se encuentran modelos como ARIMA, SARIMAX, Linear Regressor Autorregresive, Random Forest Autorregresive y RNN LSTM.

- `4_predicción_serie_tiempo_ajuste_hiperparametros.ipynb`: En este notebook se realizan los ajustes de hiperparametros y predicciones de los modelos como ARIMA, SARIMAX, Random Forest Autorregresive y RNN LSTM.

## **docs**

En esta carpeta se encuentran los un archivo llamado `TorresAnderson_2023_PrediccionDemandaEnergiaElectrica.pdf` con el documento escrito con las explicaciones y resultados de los procesos y modelos para este trabajo de monografía.

## **init.py**

Este script fue creado con el objetivo de realizar la conexión del este repositorio con los notebooks, haciendo así que toda la información almacenada en la carpeta **data** sea importada a los notebooks de forma automática y sin la necesidad de depender de archivos externos.

---

# **Forma de usar los notebooks**

Lo primero que se debe mencionar, es que este proyecto de ejecutarse de forma obligatoria en `Google Colab`, debido a que se usan algunos comando de terminal que ejecutan en esta herramienta y haciendo que en otro tipo de herramientas tenga otra forma de uso.

Debido a la creación del archivo `init.py` en ninguno de los notebooks es necesaria la utilización de datos externos, ya que toda la data que se usa proviene de este mismo repositorio. Además, todas las librerías utilizadas que no se encuentran en el paquete nativo de Google Colab se instalan por medio de comandos de terminal.

En ambos notebooks mencionados anteriormente, solo es necesario dar, ejecutar todo y todo el flujo comenzará su ejecución. Sin embargo, se debe tener en cuenta que hay códigos en los notebooks que tiene tiempos de ejecución muy elevados (extracción de datos del API de Socrata, optimización de hiperparámetros de los modelos, etc.) y puede aumentar mucho el tiempo de espera. Por eso, dichos notebooks fueron pre cargados con todos los resultados de las ejecuciones de forma visible. Si se ejecuta todo, se debe tener paciencia por los altos tiempos de ejecución.
