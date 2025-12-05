# Estado de la Entrega 3 (Final)

En esta entrega final, el proyecto ha dado un salto técnico significativo: hemos evolucionado de un sistema de clasificación unitaria (detectar qué es *un* sonido) a un sistema de **detección y conteo de eventos continuos** (contar cuántos vehículos hay en un audio largo).

Sin embargo, para una implementación correcta, es necesario considerar las siguientes limitaciones y dependencias del contexto:

### Limitaciones Conocidas
1.  **Tamaño del Dataset:** El modelo actual presenta márgenes de error en el conteo debido a que fue entrenado con un volumen limitado de audios. Esto afecta la capacidad del modelo para generalizar ante variaciones sutiles de sonido.
2.  **Enmascaramiento Acústico:** En situaciones de tráfico denso, existe la posibilidad de que vehículos con motores más ruidosos "opaquen" o enmascaren el sonido de vehículos más pequeños o eléctricos, impidiendo su detección.
3.  **Calidad de Audio:** La precisión decae si la grabación presenta mucho ruido de viento o interferencias no vehiculares que no fueron contempladas en el entrenamiento.

### 🔧 Dependencia del Contexto
Este **no es un sistema de "caja negra" universal**. Para que el conteo sea preciso, el operador debe conocer el contexto de la grabación y ajustar los parámetros (`SEGMENT_DUR_SEC`, `OVERLAP_RATIO`) acorde a ello:
* **Velocidad de Tránsito:** Vehículos rápidos requieren ventanas de análisis más cortas.
* **Densidad Vehicular:** Una alta cantidad de vehículos requiere mayor solapamiento (overlap) para no perder eventos entre ventanas.

*Si los parámetros no se ajustan a la realidad de la vía grabada (ej. usar configuración de autopista en una calle residencial), el conteo tendrá errores.*



