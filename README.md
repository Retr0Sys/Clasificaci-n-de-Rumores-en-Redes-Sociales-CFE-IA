# Modelo de Regresión Logística para la Detección de Falsedad en Mensajes de Redes Sociales
## Modelo de Machine Learning simple programado en Python (LogisticRegression)

----
Este proyecto presenta la implementación de un modelo de Aprendizaje Supervisado (Regresión Logística) desarrollado en Python para la predicción de la veracidad de rumores en plataformas de redes sociales. El objetivo es clasificar los mensajes de texto como rumor (1) o no rumor (0), mediante la identificación de patrones lingüísticos y características textuales correlacionadas con la propagación de información falsa.
----

<img src="https://github.com/user-attachments/assets/9c302335-2af0-4b20-9456-de0b698dd28a" alt="3de0b1c2cd036a5112ac231af2c5b7c6" width="600">

----

## 1. Preprocesamiento y Ingeniería de Datos
La fase inicial es crucial y se centra en la preparación y transformación del dataset para su posterior análisis mediante técnicas de Procesamiento del Lenguaje Natural (PLN).

### Proceso de Limpieza y Organización
Inspección Estructural: Se realiza una visualización inicial del conjunto de datos para comprender su conformación y la tipología de las variables.

Gestión de Valores Nulos: Se emplea la función .info() para diagnosticar la cantidad de datos faltantes.

La columna "topic" es eliminada del conjunto debido a su alta tasa de valores nulos y su baja relevancia predictiva para el objetivo de clasificación textual.

Los valores nulos remanentes en las variables "is_rumor" y "user.handle" son tratados mediante el remplazado por valores predeterminados para garantizar la integridad del dataset.

## 2. Desarrollo y Entrenamiento del Modelo
El modelo se entrena para establecer la relación probabilística entre el contenido del mensaje y su clasificación binaria.

### Variables Clave y Metodología
Variable Independiente: "text" (Contenido del mensaje).

Variable Dependiente: "is_rumor" (Etiqueta binaria: 1 = Rumor, 0 = No Rumor).

Para la validación interna del rendimiento, el conjunto de datos es dividido mediante la técnica de train_test_split, reservando una porción para el entrenamiento y otra para la prueba. Se utiliza el algoritmo de Regresión Logística debido a su eficiencia en problemas de clasificación binaria y su capacidad de interpretación en el ámbito del análisis de texto.

## 3. Evaluación y Validación Externa
La robustez del modelo se comprueba mediante la aplicación a un conjunto de datos ciego y una validación externa que simula un entorno real de competición.

### Proceso de Generación y Validación de Predicciones
Generación de Predicciones: El modelo entrenado se aplica al conjunto de datos de prueba externo (df_test_sin_etiqueta.csv), que carece de la columna "is_rumor". El modelo genera y asigna los valores predictivos a esta columna.

Validación Externa: El archivo resultante, que contiene las etiquetas predichas, es exportado y cargado en una plataforma de comprobación externa. Esta instancia verifica la eficiencia y precisión del modelo al contrastar las predicciones con los valores reales del ground truth.

## 4. Resultados
<img width="500" alt="Métrica de Desempeño del Modelo" src="https://github.com/user-attachments/assets/50cadafc-3031-4ad0-b520-3b6cbb4e7324" />
