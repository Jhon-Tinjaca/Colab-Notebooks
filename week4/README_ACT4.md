# Actividad 4: Impacto de la Regularización L2 en Redes Neuronales

## Objetivo
Demostrar el efecto de la regularización L2 en el sobreajuste de una red neuronal multicapa (MLPClassifier) utilizando un dataset sintético no lineal de círculos concéntricos, comparando modelos con y sin penalización de pesos.

## Método(s) de Regularización Aplicado(s)
- Regularización L2: Implementada mediante el parámetro `alpha` en el MLPClassifier de scikit-learn, con valores de 0.0 (sin regularización) y 0.5 (con regularización).

## Comparación Realizada
Se compararon dos configuraciones de MLPClassifier idénticas en arquitectura (capas ocultas de 100 y 50 neuronas, activación ReLU, optimizador Adam) pero diferenciadas únicamente por el nivel de regularización L2 aplicado.

## Resultado Principal
La regularización L2 redujo significativamente la norma L2 de los pesos (de ~268.5 a ~54.1) y el gap de sobreajuste, mejorando la generalización del modelo sin comprometer excesivamente la precisión en el conjunto de prueba (ambos modelos alcanzaron 98% de accuracy en test), aunque requirió más iteraciones para converger.

## Cómo Ejecutar en Colab

### Opción 1: Cargar desde GitHub
1. Abre [Google Colab](https://colab.research.google.com/)
2. Selecciona **"Archivo"** → **"Abrir cuaderno"** → **"GitHub"**
3. Pega la URL del repositorio que contiene este notebook

### Opción 2: Cargar manualmente
1. Descarga el archivo `Actividad4.ipynb` de esta carpeta
2. Abre [Google Colab](https://colab.research.google.com/)
3. Selecciona **"Archivo"** → **"Subir cuaderno"**
4. Elige el archivo descargado

### Requisitos
- NumPy
- Matplotlib
- Scikit-learn (para generación de datos)

Todas estas librerías están preinstaladas en Google Colab.
