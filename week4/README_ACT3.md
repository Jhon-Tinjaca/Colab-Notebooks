# Actividad 3 - Análisis comparativo de optimizadores para MLP

## Objetivo
Comparar el rendimiento de cuatro configuraciones de redes neuronales (optimización `adam` y `sgd`, con tasas de aprendizaje baja/alta) sobre un problema de clasificación sintético (`make_moons`).

## Técnica(s) comparada(s)
- MLPClassifier (`sklearn.neural_network`) con solver `adam`
- MLPClassifier con solver `sgd`

## Configuración base
Entrenamiento en `make_moons` (1000 muestras, ruido=0.2) con arquitectura de capas ocultas `(100, 50)`, `relu`, y `max_iter=1000`.

## Resultado principal
`adam` alcanza alta precisión  y converge más rápido, mientras `sgd` es más sensible a learning rate (LR baja puede no converger en 1000 iteraciones). En `sgd` LR alta mejora mucho la precisión.

- Adam es más eficiente: El optimizador Adam, incluso con una tasa de aprendizaje más alta, logró una convergencia rápida y un rendimiento superior o comparable al mejor SGD, con menos iteraciones.
- La tasa de aprendizaje es crítica para SGD: Para SGD, una tasa de aprendizaje demasiado baja puede llevar a una no convergencia efectiva dentro de un número razonable de épocas, mientras que una tasa más alta puede mejorar drásticamente el rendimiento, aunque aún puede ser más lenta que Adam.
- Sobreajuste/Convergencia temprana (Adam alta LR): Aunque Adam con LR alta convergió muy rápido, su pérdida final fue peor que Adam con LR baja. Esto podría indicar que la LR alta fue un poco agresiva, aunque no afectó negativamente la precisión en el conjunto de prueba, o que se detuvo antes debido al criterio de parada anticipada.
- Compensación Velocidad-Estabilidad: La tasa de aprendizaje es un hiperparámetro clave que afecta directamente la velocidad a la que el modelo aprende y la estabilidad de ese aprendizaje. Adam parece manejar esta compensación de manera más efectiva que SGD en este dataset.

## Cómo ejecutar
1. Abrir `week4/Actividad3.ipynb` en Jupyter/Colab.
2. Ejecutar celdas en orden desde la preparación de datos hasta el análisis comparativo.
3. Revisar curvas de pérdida y métricas impresas (accuracy).

