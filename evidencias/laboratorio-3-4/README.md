
# Laboratorio 3.4: Formación del modelo XGBoost en Amazon SageMaker

## 1. Objetivo

Preparar los datos de la columna vertebral, almacenarlos en Amazon S3 y entrenar un modelo de clasificación utilizando XGBoost en Amazon SageMaker.

## 2. Desarrollo del laboratorio

### Evidencia 1. Acceso a Amazon SageMaker

**¿Qué hice?** Ingresé a AWS Academy y accedí al servicio Amazon SageMaker.

**¿Por qué?** Para utilizar el entorno necesario para desarrollar el laboratorio de aprendizaje automático.

![Acceso a Amazon SageMaker](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/01_acceso_sagemaker.png)

### Evidencia 2. Instancia MyNotebook

**¿Qué hice?** Identifiqué la instancia MyNotebook desde la consola de Amazon SageMaker.

**¿Por qué?** Para acceder al entorno de JupyterLab donde ejecuté el código.

![Instancia MyNotebook](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/02_instancia_mynotebook.png)

### Evidencia 3. Archivos de JupyterLab

**¿Qué hice?** Revisé los archivos disponibles y localicé el notebook de la actividad.

**¿Por qué?** Para abrir el archivo correcto y seguir las instrucciones del laboratorio.

![Archivos de JupyterLab](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/03_archivos_jupyterlab.png)

### Evidencia 4. Apertura del cuaderno

**¿Qué hice?** Abrí el notebook del laboratorio en JupyterLab.

**¿Por qué?** Para ejecutar las celdas de código y desarrollar la preparación de los datos y el entrenamiento.

![Apertura del cuaderno](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/04_apertura_cuaderno.png)

### Evidencia 5. Configuración e importación de bibliotecas

**¿Qué hice?** Importé las bibliotecas necesarias para procesar datos, utilizar pandas y trabajar con SageMaker y Amazon S3. También instalé las bibliotecas faltantes.

**¿Por qué?** Para contar con las herramientas necesarias para ejecutar el código.

![Configuración e importación de bibliotecas](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/05_configuracion_importacion_bibliotecas.png)

### Evidencia 6. Descarga y extracción de datos

**¿Qué hice?** Descargué el conjunto de datos de la columna vertebral y extraje los archivos para cargarlos en Python.

**¿Por qué?** Para disponer de la información que se utilizaría en el entrenamiento del modelo.

![Descarga y extracción de datos](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/06_descarga_extraccion_datos.png)

### Evidencia 7. Exploración y preparación de datos

**¿Qué hice?** Revisé la estructura del conjunto de datos y preparé la variable de clasificación.

**¿Por qué?** Para organizar la información antes de utilizarla en el entrenamiento.

![Exploración y preparación de datos](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/07_exploracion_y_division_datos.png)

### Evidencia 8. Exploración del conjunto de datos

**¿Qué hice?** Inspeccioné los registros y las variables del conjunto de datos.

**¿Por qué?** Para verificar la información disponible antes de continuar con el proceso.

![Exploración de datos](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/08_exploracion_de_datos.png)

### Evidencia 9. División de los conjuntos de datos

**¿Qué hice?** Dividí los datos en conjuntos de entrenamiento, prueba y validación con 248, 31 y 31 registros, respectivamente.

**¿Por qué?** Para entrenar el modelo y contar con datos separados para comprobar su comportamiento.

![División de conjuntos de datos](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/09_division_conjuntos_datos.png)

### Evidencia 10. Carga de datos en Amazon S3

**¿Qué hice?** Cargué los archivos de entrenamiento, prueba y validación en Amazon S3.

**¿Por qué?** Para almacenar los datos y permitir que SageMaker los utilizara durante el entrenamiento.

![Carga de datos en Amazon S3](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/10_carga_datos_amazon_s3.png)

### Evidencia 11. Entrenamiento del modelo XGBoost

**¿Qué hice?** Configuré y ejecuté el entrenamiento del modelo XGBoost y comprobé que el trabajo finalizara correctamente.

**¿Por qué?** Para construir un modelo de clasificación que posteriormente pudiera utilizarse para realizar predicciones.

![Entrenamiento del modelo XGBoost](https://raw.githubusercontent.com/Lindorti/laboratorio-sagemaker/main/evidencias/laboratorio-3-4/11_entrenamiento_modelo_xgboost_completado.png)

## 3. Conclusión

En este laboratorio preparé los datos, los almacené en Amazon S3 y entrené un modelo de clasificación con XGBoost en Amazon SageMaker. El ejercicio me permitió comprender las etapas básicas de preparación de datos y entrenamiento de un modelo de aprendizaje automático en la nube.
