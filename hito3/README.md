# Estado de la Entrega 3 (Final)

En esta entrega final, el proyecto ha dado un salto técnico significativo: hemos evolucionado de un sistema de clasificación unitaria (detectar qué es *un* sonido) a un sistema de **detección y conteo de eventos continuos** (contar cuántos vehículos hay en un audio largo).

Sin embargo, para una implementación correcta, es necesario considerar las siguientes limitaciones y dependencias del contexto:

### Limitaciones Conocidas
1.  **Tamaño del Dataset:** El modelo actual presenta márgenes de error en el conteo debido a que fue entrenado con una cantidad limitada de audios. Como comentamos en clase, no encontramos bases de datos que incluyeran grabaciones de “autos pasando por una calle”. La mayoría de los datasets disponibles contienen sonidos de vehículos pequeños, medianos o grandes, pero corresponden a ruidos de motores estáticos y no a autos en movimiento. Por esta razón, tuvimos que construir nuestro propio dataset recopilando manualmente clips de vehículos de distintos tamaños pasando por una vía. Esta limitación reduce la capacidad del modelo para generalizar adecuadamente frente a variaciones sutiles en los sonidos reales.
2.  **Enmascaramiento Acústico:** En situaciones de tráfico denso, existe la posibilidad de que vehículos con motores más ruidosos opaquen o enmascaren el sonido de vehículos más pequeños o eléctricos, dificultando su detección. Esto ocurre principalmente cuando dos autos pasan de manera simultánea, ya que cuando lo hacen uno por uno el sistema logra identificarlos correctamente.
3.  **Calidad de Audio:** La precisión disminuye cuando la grabación presenta ruido de viento u otras interferencias no relacionadas con vehículos, ya que estos factores no fueron considerados durante el entrenamiento. También influye la ubicación del micrófono: no es lo mismo situarlo en un cruce que en una vía recta. En una vía recta es más sencillo que el sistema detecte los vehículos uno por uno, porque el sonido se aproxima desde el fondo, se vuelve muy notorio al pasar frente al micrófono y luego decae de forma clara. En cambio, en un cruce los sonidos provienen desde ángulos muy variados y generan patrones más caóticos. Además, la calidad del micrófono utilizado es un factor relevante que puede afectar el rendimiento del modelo.

###  Dependencia del Contexto
Para que el conteo sea preciso, el operador debe conocer el contexto de la grabación y ajustar los parámetros (`SEGMENT_DUR_SEC`, `OVERLAP_RATIO`) acorde a ello:
* **Velocidad de Tránsito:** Vehículos rápidos requieren ventanas de análisis más cortas.
* **Densidad Vehicular:** Una alta cantidad de vehículos requiere mayor solapamiento (overlap) para no perder eventos entre ventanas.

*Si los parámetros no se ajustan a la realidad de la vía grabada (ej. usar configuración de autopista en una calle residencial), el conteo tendrá errores.*






