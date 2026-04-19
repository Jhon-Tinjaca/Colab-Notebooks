# Actividad 6 - Comparación de Regularización en Redes Neuronales
DIEGO ALEJANDRO RUIZ ALFONSO - ppmurcia@ucundinamarca.edu.co - Líder de métricas
PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co - Líder de documentación
JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co - Líder de experimento
JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co - Líder

## Objetivo
Comparar el rendimiento de dos configuraciones de redes neuronales en un problema de clasificación binaria (`make_moons`): una sin regularización y otra con técnicas de regularización (L2 y Dropout) para evaluar su impacto en la prevención del sobreajuste.

## Técnica(s) comparada(s)
- Modelo Base: Red neuronal sin mecanismos de regularización
- Modelo Regularizado: Red neuronal con regularización L2 y Dropout (30%)

## Configuración base
Entrenamiento en `make_moons` (1000 muestras, ruido=0.2) con arquitectura de dos capas ocultas de 64 neuronas cada una, activación `relu`, `sigmoid` en salida (clasificación binaria), optimizador `Adam`, tasa de aprendizaje 0.01, `EPOCHS=100` y `BATCH_SIZE=32`.

## Resultado principal
La regularización L2 + Dropout reduce significativamente el sobreajuste manteniendo las curvas de pérdida de entrenamiento y validación más cercanas. El modelo regularizado presenta una **norma L2 de pesos mucho menor**, indicando pesos más controlados y una mejor generalización. Los límites de decisión del modelo regularizado son más suaves, reduciendo la memorización del ruido del dataset.

### Puntos clave:
- **Prevención de Overfitting**: El modelo base muestra divergencia entre pérdida de entrenamiento y validación, mientras que el modelo regularizado mantiene ambas más cercanas.
- **Magnitud de pesos controlada**: La regularización L2 penaliza pesos grandes, reduciendo la dependencia excesiva en pocos atributos.
- **Generalización mejorada**: El modelo regularizado produce fronteras de decisión más suaves y genera predicciones más robustas ante datos nuevos.
- **Trade-off robustez-precisión**: Sacrifica ligeramente precisión en entrenamiento por mejor desempeño en validación, asegurando estabilidad en producción.

## Cómo Ejecutar en Colab

### Opción 1: Cargar desde GitHub
1. Abre [Google Colab](https://colab.research.google.com/)
2. Selecciona **"Archivo"** → **"Abrir cuaderno"** → **"GitHub"**
3. Pega la URL del repositorio que contiene este notebook

### Opción 2: Cargar manualmente
1. Descarga el archivo `Actividad6.ipynb` de esta carpeta
2. Abre [Google Colab](https://colab.research.google.com/)
3. Selecciona **"Archivo"** → **"Subir cuaderno"**
4. Elige el archivo descargado

### Requisitos
- NumPy
- Matplotlib
- TensorFlow/Keras
- Scikit-learn (para generación de datos)

Todas estas librerías están preinstaladas en Google Colab.

