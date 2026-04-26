
# Actividad 8 - Comparación de Regularización en Redes Neuronales
DIEGO ALEJANDRO RUIZ ALFONSO - ppmurcia@ucundinamarca.edu.co 
PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co 
JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co 
JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co 

#### Objetivo
Evaluar y comparar el desempeño de una arquitectura de Red Neuronal Convolucional (CNN) diseñada a medida frente a una estrategia de **Transfer Learning** utilizando un modelo pre-entrenado de gran escala para la clasificación de dígitos manuscritos.

#### Técnica(s) Comparada(s)
*   **CNN desde Cero (Scratch):** Una red ligera optimizada específicamente para el dominio de MNIST.
*   **Transfer Learning (MobileNetV2):** Uso de una red entrenada en ImageNet (1,000 clases de objetos reales) adaptada para la tarea de dígitos mediante el congelamiento de sus capas base.

#### Configuración Base
*   **Dataset:** MNIST (60,000 imágenes de entrenamiento, 10,000 de prueba).
*   **Pre-procesamiento:**
    *   Normalización de píxeles (0-1).
    *   Para MobileNetV2: Redimensionamiento a 32x32 y conversión de 1 canal (gris) a 3 canales (RGB).
*   **Optimización:** Optimizador Adam y función de pérdida Sparse Categorical Crossentropy.

#### Resultado Principal
| Modelo | Precisión (Test) | Épocas | Observación |
| :--- | :--- | :--- | :--- |
| **CNN Base** | **~99.1%** | 10 | Alta precisión, ligera y rápida. |
| **Transfer Learning** | **~71.0%** | 5 | Desempeño inferior debido a la brecha de dominio (natural vs abstracto). |

#### Puntos Clave del Ejercicio
*   **Especialización vs Generalización:** Una red pequeña diseñada para un problema simple suele superar a un modelo gigante generalista.
*   **Importancia del Dominio:** Los pesos pre-entrenados en fotos reales (ImageNet) no son directamente transferibles con éxito total a dominios abstractos como dígitos en blanco y negro sin un ajuste fino (*fine-tuning*) profundo.
*   **Costo Computacional:** El Transfer Learning requiere mayor procesamiento previo (RGB/Resize) y memoria, lo que no siempre se justifica en tareas sencillas.
*   **Análisis de Errores:** La visualización de fallos es crucial para entender que incluso con alta precisión, existen ambigüedades humanas en los datos que el modelo hereda.

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
- Tensorflow
- Sklearn
- Pandas