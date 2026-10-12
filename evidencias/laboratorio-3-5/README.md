# Laboratorio 3.5: Implementación y predicción con Amazon SageMaker

## 1. Introducción

En este laboratorio se continuó trabajando con el conjunto de datos de la columna vertebral utilizado en el laboratorio anterior. El objetivo fue implementar un modelo de aprendizaje automático con Amazon SageMaker, realizar predicciones individuales y procesar varios datos mediante una transformación por lotes.

Durante el desarrollo se utilizaron servicios de AWS, como Amazon SageMaker y Amazon S3, para entrenar el modelo, generar predicciones y almacenar los resultados.

## 2. Objetivo

Comprender cómo implementar un modelo de clasificación en Amazon SageMaker, realizar predicciones con datos nuevos y utilizar la transformación por lotes para procesar un conjunto de datos.

## 3. Desarrollo del laboratorio

### 3.1. Importación y configuración de los datos

Se instalaron las bibliotecas necesarias para ejecutar el código y se importó el conjunto de datos de la columna vertebral. Después, se organizaron los registros y se prepararon los conjuntos de entrenamiento, prueba y validación.

También se cargaron los archivos en Amazon S3, donde quedaron disponibles para el entrenamiento del modelo.

**¿Para qué se realizó?**

Para preparar la información y contar con los recursos necesarios para desarrollar el proceso de aprendizaje automático.

**Evidencia 1:** `01_importacion_y_configuracion_datos.png`

### 3.2. Entrenamiento del modelo XGBoost

Se configuró el algoritmo XGBoost con sus parámetros y se ejecutó el entrenamiento en Amazon SageMaker. El proceso finalizó correctamente y mostró el mensaje `ready for hosting!`, indicando que el modelo estaba listo para ser implementado.

**¿Para qué se realizó?**

Para crear un modelo capaz de analizar las características biomecánicas y generar predicciones sobre las categorías definidas en el conjunto de datos.

**Evidencia 2:** `02_entrenamiento_modelo_xgboost.png`

### 3.3. Implementación del modelo en un endpoint

Después de completar el entrenamiento, se implementó el modelo mediante un endpoint de SageMaker, utilizando una instancia `ml.m4.xlarge`. Este recurso permitió enviar datos al modelo y recibir las respuestas de las predicciones.

**¿Para qué se realizó?**

Para habilitar el uso del modelo mediante solicitudes individuales y comprobar que podía generar resultados a partir de nuevos datos.

**Evidencia 3:** `03_implementacion_modelo_endpoint.png`

### 3.4. Predicción individual y validación solicitada por el profesor

En esta parte se revisó el conjunto de prueba, que contenía 31 registros, y se seleccionó una fila para realizar una predicción individual.

Además, se desarrolló la prueba específica solicitada por el profesor, utilizando el endpoint `xgb_predictor` y la siguiente entrada:

**Datos de entrada:**

`63.0,12.5,45.0,50.5,125.0,3.0`

Para enviar los datos y obtener la respuesta se utilizó el siguiente código:

```python
entrada = "63.0,12.5,45.0,50.5,125.0,3.0"

resultado = xgb_predictor.predict(entrada)

print("Entrada:", entrada)
print("Resultado de la predicción:", resultado)
```

**Resultado obtenido:**

`0.01694011501967907`

**Interpretación del resultado**

El modelo devolvió una puntuación de probabilidad de aproximadamente 0,01694, equivalente al 1,69 %. Este resultado es inferior al umbral de 0,5, por lo que, si se utiliza ese umbral para convertir la puntuación en una clase binaria, la predicción corresponde a la clase **0 (Normal)**, según la codificación utilizada en el laboratorio.

Con esta prueba se comprobó que el endpoint recibió los seis valores indicados por el profesor y generó una respuesta. Es importante tener presente que se trata de una predicción del modelo y no de un diagnóstico médico.

**¿Para qué se realizó?**

Para comprobar el funcionamiento del endpoint y validar la respuesta del modelo utilizando exactamente los datos solicitados por el profesor.

**Evidencia 4:** `04_validacion_endpoint_datos_profesor.png`

### 3.5. Eliminación del endpoint

Una vez realizadas las predicciones individuales, se eliminó el endpoint mediante el siguiente código:

```python
xgb_predictor.delete_endpoint(
    delete_endpoint_config=True
)
```

La ejecución mostró los mensajes de eliminación de la configuración y del endpoint.

**¿Para qué se realizó?**

Para liberar los recursos utilizados para el alojamiento del modelo y evitar mantener una instancia de inferencia activa cuando ya no era necesaria.

**Evidencia 5:** `05_eliminacion_endpoint_transformacion_lotes.png`

### 3.6. Transformación por lotes

Después de eliminar el endpoint, se prepararon los datos de prueba para procesarlos por lotes. Se seleccionaron las características de entrada, se guardaron en un archivo CSV llamado `batch-in.csv` y se cargaron en Amazon S3.

Posteriormente, se configuró el transformador de SageMaker para procesar los datos y guardar las predicciones en una ubicación de salida dentro de Amazon S3.

El trabajo de transformación finalizó correctamente y tuvo una duración aproximada de seis minutos, según la consola de AWS.

**¿Para qué se realizó?**

Para obtener predicciones de varios registros en un solo proceso, sin tener que enviar cada dato individualmente al endpoint.

**Evidencia 6:** `06_resultados_transformacion_clasificacion_binaria.png`

### 3.7. Revisión e interpretación de los resultados

Cuando terminó la transformación por lotes, se descargaron los resultados desde Amazon S3 y se cargaron en un DataFrame de pandas para facilitar su revisión.

El modelo generó puntuaciones de probabilidad para los registros procesados. Después, se aplicó una función para convertir esas puntuaciones en clases binarias, utilizando un umbral de 0,65. De esta manera, las puntuaciones superiores a 0,65 se clasificaron como 1 y las demás como 0.

Los resultados se compararon con los registros originales del conjunto de prueba para observar las predicciones generadas por el modelo.

**¿Para qué se realizó?**

Para organizar los resultados, convertir las probabilidades en categorías y facilitar su comparación con los datos originales.

**Evidencia:** `06_resultados_transformacion_clasificacion_binaria.png`

## 4. Conclusiones

En este laboratorio se aprendió a implementar un modelo de aprendizaje automático en Amazon SageMaker y a utilizar un endpoint para realizar predicciones individuales. También se realizó la prueba solicitada por el profesor con la entrada específica y se interpretó la puntuación obtenida.

Finalmente, se utilizó la transformación por lotes para procesar varios registros, almacenar los resultados en Amazon S3 y convertir las probabilidades en clases binarias. La actividad permitió comprender mejor el funcionamiento de los modelos de aprendizaje automático en la nube y la importancia de revisar e interpretar sus resultados.
