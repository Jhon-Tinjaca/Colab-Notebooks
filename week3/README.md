# Comparación de Redes Neuronales con Activación Sigmoid y ReLU


## Objetivo

El propósito de esta actividad es comprender cómo las funciones de activación afectan el aprendizaje y el rendimiento de una red neuronal. Mediante la comparación directa de Sigmoid y ReLU, se busca entender las ventajas y desventajas de cada una en el contexto de problemas de clasificación binaria.

---

## Qué se Implementó

- **Generación de datos sintéticos**: Creación de un conjunto de datos de dos clases para clasificación binaria.
- **Arquitectura de red neuronal**: Una red simple con:
  - Capa de entrada
  - Una capa oculta (con activación configurable)
  - Capa de salida (con activación Sigmoid para clasificación binaria)
- **Algoritmo de entrenamiento**: Implementación del algoritmo de retropropagación (backpropagation).
- **Visualización**: Gráficos de los límites de decisión aprendidos por cada modelo.
- **Evaluación**: Cálculo de pérdida y precisión en el conjunto de prueba.

---

## Activaciones Comparadas

Se compararon dos funciones de activación en la capa oculta:

1. **Sigmoid** ($\sigma(x) = \frac{1}{1 + e^{-x}}$)
   - Activación clásica que mapea valores a (0, 1)
   - Puede sufrir vanishing gradient en redes profundas

2. **ReLU** ($f(x) = \max(0, x)$)
   - Activación moderna, simple y eficiente computacionalmente
   - Menos susceptible al problema de vanishing gradient

---

## Resultados Principales

- Ambas redes logran clasificar correctamente los datos sintéticos, aunque con dinámicas de aprendizaje diferentes.
- ReLU generalmente converge más rápido, mientras que Sigmoid puede producir límites de decisión más suaves y curvados.

---

##  Cómo Ejecutar en Colab

### Opción 1: Cargar desde GitHub
1. Abre [Google Colab](https://colab.research.google.com/)
2. Selecciona **"Archivo"** → **"Abrir cuaderno"** → **"GitHub"**
3. Pega la URL del repositorio que contiene este notebook

### Opción 2: Cargar manualmente
1. Descarga el archivo `Actividad2.ipynb` de esta carpeta
2. Abre [Google Colab](https://colab.research.google.com/)
3. Selecciona **"Archivo"** → **"Subir cuaderno"**
4. Elige el archivo descargado

### Requisitos
- NumPy
- Matplotlib
- Scikit-learn (para generación de datos)

Todas estas librerías están preinstaladas en Google Colab.

