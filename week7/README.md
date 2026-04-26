
# Actividad 7 - Comparación de Regularización en Redes Neuronales
DIEGO ALEJANDRO RUIZ ALFONSO - ppmurcia@ucundinamarca.edu.co 
PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co 
JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co 
JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co 


### Objetivo
Comprender y visualizar el impacto de los parámetros de convolución (padding y stride) en el tamaño de la salida y la preservación de la información, utilizando una convolución 2D manual.

### Técnica(s) Comparada(s)
Convolución 2D con un kernel de detección de bordes (Sobel vertical), comparando tres configuraciones:
1.  **Base**: Sin padding, stride 1.
2.  **Con Padding**: Padding de 1, stride 1.
3.  **Con Stride**: Sin padding, stride 2.

### Configuración Base
Se utiliza una imagen sintética de 10x10 píxeles con un cuadrado blanco y gris central. El kernel es un Sobel vertical de 3x3. La configuración base realiza la convolución sin relleno (`padding=0`) y con un paso normal (`stride=1`), resultando en una imagen de salida de 8x8.

### Resultado Principal
*   **Dimensiones de Salida**: La convolución **Base** reduce la imagen de 10x10 a 8x8. El uso de **Padding** permite mantener la dimensión original de 10x10. El uso de **Stride 2** reduce drásticamente la dimensión a 4x4.
*   **Preservación de Información (Norma L2)**: Las configuraciones **Base** y **Con Padding** mantienen la misma magnitud total de respuesta (Norma L2: 18.8680), indicando que detectan la misma cantidad de 'información' de bordes. La configuración **Con Stride 2** reduce la Norma L2 a la mitad (9.4340), confirmando una pérdida de detalle a cambio de eficiencia.

### Puntos Clave
*   **Padding**: Permite al kernel procesar los bordes de la imagen, evitando el encogimiento del mapa de características y preservando la resolución espacial. Es crucial para mantener la información en redes neuronales profundas.
*   **Stride**: Controla el tamaño del salto del kernel. Un stride mayor reduce significativamente las dimensiones del mapa de características, disminuyendo el costo computacional y 'comprimiendo' la información, pero con una pérdida de detalle fino.
*   **Mapas de Características**: Los colores (amarillo/brillante, púrpura/oscuro, verde/teal) indican la dirección y magnitud de los bordes detectados. La visualización de estos mapas demuestra cómo cada configuración afecta la representación visual del patrón detectado.

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
- time

