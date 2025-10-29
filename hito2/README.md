# Hito 2: Prototipo Funcional - Detección de Vehículos

## Qué avances realizaron

* Se desarrolló un prototipo funcional del código capaz de procesar un audio y detectar la presencia de vehículos.
* El script implementa la clasificación de los vehículos detectados en tres clases principales:
* Motos, Autos y Camiones.

* Se realizó la búsqueda, recopilación y selección de un conjunto de datos (archivos de audio) que se utilizarán para el entrenamiento y
 se subio a Zenodo los audios para entrenar el programa.

## Qué falta por completar para Hito 3

Los siguientes pasos para la entrega final (Hito 3) son:

* Evaluar la precisión (métrica) del modelo y realizar ajustes (hiperparámetros) para mejorar su rendimiento.
* Integrar el modelo final en el script principal.
* Realizar el análisis de resultados y preparar la presentación final.

## Como ejecutar el codigo

El proyecto utiliza las siguientes librerias de Python:
* numpy
* librosa
* matplotlib
* soundfile
* joblib
* scikit-learn
* jupyter

### 2. Ejecución del Prototipo (Hito 2) 🚗

Para probar el prototipo, sigue estos pasos:

1. Inicia Jupyter en tu terminal:
   ```bash
   jupyter lab
2. Verificar los archivos: Asegúrate de tener los diguientes archivos en la misma carpeta:
* 02_Conteo_Aplicacion.ipynb (El notebook de esta demo).
* clasificador_vehiculos.joblib (El modelo entrenado. Si no lo tienes, debes ejecutar primero el notebook 01).
3. Prepara tu audio:
  * Opción A: Renombra tu archivo de audio a audio_random.wav y colócalo en la misma carpeta.
4. Ejecuta las celdas en orden para procesar un audio y ver la clasificación.
