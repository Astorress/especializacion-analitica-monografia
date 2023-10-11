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

- `consumo`: En esta carpeta se encuentra la información del consumo o demanda de energía eléctrica en las distintas regiones del país categorizadas por XM, esta información se encuentra en un archivo .xlsx.

- `temperatura`: En esta carpeta se encuentra la información de las temperaturas promedio del departamento de Antioquia en los últimos años, esta información se usó para poder incluir en las predicciones de la demanda de energía eléctrica la temperatura promedio diaria del departamento, esta información fue extraída del API de Socrata, que se conecta con la plataforma de datos abiertos del gobierno Colombiano (<https://www.datos.gov.co/>). Debido a que dicha API tiene un alto coste de tiempo de ejecución, para la extracción de los datos, se decidió guardar los mismos, en un formato .csv para agilizar los tiempos de ejecución de los notebooks.

- `data_procesada.csv`: Este es el resultado del proceso de limpieza y preparación de datos realizado en el notebook _`extraccion_procesamiento_y_limpieza_datos.ipynb`_, con el objetivo de separar el proyecto en dos notebooks, un destinado a la etapa de procesamiento de datos y otro a la etapa de análisis y generación de modelos, agilizando de esta forma los tiempos de ejecución en la etapa de análisis y generación de modelos.

## **notebooks**

En esta carpeta se encuentran los notebooks usados en el proyecto.

- `1_extraccion_procesamiento_y_limpieza_datos.ipynb`:

- `2_analisis_series_tiempo.ipynb`:

- `3_prediccion_series_tiempo_iniciales.ipynb`:

## **docs**

En esta carpeta se encuentran los dos archivos .pdf de las dos entregas realizadas en el proyecto de seminario para la monografía.

## **init.py**

Este script fue creado con el objetivo de realizar la conexión del este repositorio con los notebooks, haciendo así que toda la información almacenada en la carpeta **data** sea importada a los notebooks de forma automática y sin la necesidad de depender de archivos externos.

---

# **Forma de usar los notebooks**

Lo primero que se debe mencionar, es que este proyecto de ejecutarse de forma obligatoria en `Google Colab`, debido a que se usan algunos comando de terminal que ejecutan en esta herramienta y haciendo que en otro tipo de herramientas tenga otra forma de uso.

Debido a la creación del archivo `init.py` en ninguno de los notebooks es necesaria la utilización de datos externos, ya que toda la data que se usa proviene de este mismo repositorio. Además, todas las librerías utilizadas que no se encuentran en el paquete nativo de Google Colab se instalan por medio de comandos de terminal.

En ambos notebooks mencionados anteriormente, solo es necesario dar, ejecutar todo y todo el flujo comenzará su ejecución. Sin embargo, se debe tener en cuenta que hay códigos en los notebooks que tiene tiempos de ejecución muy elevados (extracción de datos del API de Socrata, optimización de hiperparámetros de los modelos, etc.) y puede aumentar mucho el tiempo de espera. Por eso, dichos notebooks fueron pre cargados con todos los resultados de las ejecuciones de forma visible. Si se ejecuta todo, se debe tener paciencia por los altos tiempos de ejecución.
