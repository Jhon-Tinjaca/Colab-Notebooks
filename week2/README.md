# Práctica de Red Neuronal Básica

## Objetivo

Desarrollar e implementar una red neuronal básica en un cuaderno interactivo (Google Colab) para consolidar las bases del aprendizaje profundo. El enfoque se centra en entender la lógica de una neurona/perceptrón, el cálculo de puntaje z y la toma de decisiones por umbral.

## ¿Qué se implementó?

- Un perceptrón simple con entradas, pesos y sesgo (bias).
- Cálculo del puntaje z (suma ponderada más sesgo).
- Aplicación de una regla de activación (función escalón) para obtener salida binaria (0/1).
- Validación en Google Colab con ejemplos de clasificación.

## Pruebas realizadas

Se ejecutaron múltiples iteraciones con distintos conjuntos de entradas y pesos para verificar el comportamiento del perceptrón. Se documentó la salida 0/1 según la regla de activación y se observaron cambios al modificar los parámetros.

## Resultados principales

El perceptrón fue capaz de clasificar correctamente los ejemplos probados y mostró la influencia de los pesos y el sesgo sobre la salida.

## Cómo Ejecutar en Colab

### Opción 1: Cargar desde GitHub
1. Abre [Google Colab](https://colab.research.google.com/)
2. Selecciona **"Archivo"** → **"Abrir cuaderno"** → **"GitHub"**
3. Pega la URL del repositorio que contiene este notebook

### Opción 2: Cargar manualmente
1. Descarga el archivo `Practica 2.ipynb` de esta carpeta
2. Abre [Google Colab](https://colab.research.google.com/)
3. Selecciona **"Archivo"** → **"Subir cuaderno"**
4. Elige el archivo descargado

### Requisitos
- NumPy

