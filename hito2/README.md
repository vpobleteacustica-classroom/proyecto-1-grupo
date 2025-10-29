# Hito 2: Prototipo Funcional - Detección de Vehículos

## Qué avances realizaron

* Se desarrolló un prototipo funcional del código capaz de procesar un audio y detectar la presencia de vehículos.
* El script implementa la clasificación de los vehículos detectados en tres clases principales:
* Grande, medio y pequeño.

* Se realizó la búsqueda, recopilación y selección de un conjunto de datos (archivos de audio) que se utilizarán para el entrenamiento, los cuales fueron subidos a Zenodo.

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

1. Verificar los archivos: Asegúrate de tener los diguientes archivos en la misma carpeta:
* 01_Entrenamiento_Modelo.ipynb (En la carpeta notebook de esta demo).
* 02_Conteo_Aplicacion.ipynb (Tambien en la carpeta notebook de esta demo).
* clasificador_vehiculos.joblib (El modelo entrenado. Si no lo tienes, debes ejecutar primero el notebook 01).
2. Prepara tu audio:
  *  Renombra tu archivo de audio a audio_random.wav y colócalo en la misma carpeta.
3. Iniciar Jupyter Lab:
* Abre tu terminal, navega a la carpeta del proyecto y ejecuta:
  ```bash
   jupyter lab
  ```
4. Ejecuta el Notebook:
   * En Jupyter Lab, abre el archivo 02_Conteo_Aplicacion.ipynb .
   * Ve al menú Kernel > Restart Kernel and Run All Cells... (o ejecuta las celdas una por una, desde el Bloque 1 hasta el 4).
5. Revisa el Resultado:
* EL resultado de la clasificación aparecerá al final, en la salida del Bloque 4. Verás un mensaje como:

    ```
    ===============================
          RESULTADO 
    ===============================
    El audio 'audio_random.wav' ha sido clasificado como:
     -> **PEQUENO**
    ===============================
    ```
