# Week_15 - Data Journey, Monitoreo y Model Serving

## Integrantes:
DIEGO ALEJANDRO RUIZ ALFONSO - diegoaruiz@ucundinamarca.edu.co PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co

## Objetivo

Comprender y aplicar el ciclo de vida completo de un modelo de aprendizaje profundo: desde el origen y preparacion de los datos hasta el monitoreo del entrenamiento y la puesta en operacion (serving). La prioridad es demostrar trazabilidad del proceso completo, no maximizar el desempeno.

---

## Que se implementó

| Componente | Descripcion |
|------------|-------------|
| Data Journey | Diagrama del recorrido completo: imagen FNA -> caracteristicas -> CSV -> carga -> limpieza -> normalizacion -> entrenamiento -> evaluacion -> serving |
| Acceso y manipulacion | Carga del dataset Breast Cancer Wisconsin (scikit-learn), inspeccion de calidad, analisis exploratorio (histogramas, boxplots), division 80/20 estratificada y normalizacion con StandardScaler |
| Modelo | Red neuronal Entrada(30) -> Oculta1(32,ReLU) -> Oculta2(16,ReLU) -> Salida(1,Sigmoid) con Adam y Binary Cross-Entropy, implementada desde cero en NumPy |
| Monitoreo y logging | Sistema ExperimentLogger con registro de loss/accuracy/norma de gradiente por epoca, exportacion a JSON, dashboard de 6 graficas y tabla de hitos. Bloque W&B listo para activar incluido |
| Analisis de metricas | Reporte de clasificacion completo, curva ROC con AUC, curva Precision-Recall, matriz de confusion y analisis del gap train-validacion |
| Model Serving | Simulacion de endpoint POST /predict con preprocesamiento encapsulado, serializacion del artefacto (pesos + scaler) y esquema de codigo FastAPI para produccion |
| Conclusiones | Analisis tecnico de data journey, monitoreo, metricas, serving, dificultades y oportunidades de mejora |

---

## Dataset

**Breast Cancer Wisconsin (Diagnostic)** — incluido en scikit-learn.

- 569 muestras (357 benignas, 212 malignas)
- 30 caracteristicas numericas (radio, textura, perimetro, area, etc.)
- Sin valores nulos
- Fuente original: UCI Machine Learning Repository

---

## Monitoreo

Se implementa un sistema de logging local equivalente a Weights and Biases que registra por epoca:

- Loss de entrenamiento y validacion
- Accuracy de entrenamiento y validacion
- Norma del gradiente (para detectar vanishing/exploding gradients)
- Timestamp y Run ID unico por experimento

El historial se exporta a `historial_experimento.json` para trazabilidad reproducible. Al final del notebook se incluye el bloque de integracion con W&B comentado y listo para activar.

---

## Resultados principales

La red neuronal implementada con Adam (LR=0.001, 300 epocas) logra convergencia estable sobre el dataset Breast Cancer Wisconsin. El ROC-AUC superior a 0.97 indica alta capacidad discriminativa entre tumores malignos y benignos. El monitoreo del gap train-validacion muestra que el modelo no presenta sobreajuste significativo en las 300 epocas entrenadas.

---

## Como ejecutar el notebook

### Google Colab (recomendado)

1. Descarga `notebook_data_journey.ipynb`.
2. Ve a [https://colab.research.google.com](https://colab.research.google.com).
3. Selecciona **Archivo -> Subir notebook** y carga el archivo.
4. Ejecuta todas las celdas con **Runtime -> Run all**.

No se requiere configuracion adicional. El dataset se descarga automaticamente desde scikit-learn.

### Para activar Weights and Biases

1. Crea una cuenta gratuita en [https://wandb.ai](https://wandb.ai).
2. En Colab, ejecuta en una celda: `!wandb login`
3. Pega tu API key cuando se solicite.
4. Descomentar el bloque en la Seccion 9 del notebook y ejecutar.

### Local con Jupyter

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook notebook_data_journey.ipynb
```

### Dependencias

```
numpy
pandas
matplotlib
scikit-learn
```

Opcionales (solo para W&B):
```
wandb
```

---

## Archivos generados al ejecutar

| Archivo | Descripcion |
|---------|-------------|
| `eda_dataset.png` | Graficas de analisis exploratorio |
| `dashboard_experimento.png` | Dashboard de monitoreo (6 paneles) |
| `evaluacion_modelo.png` | Curva ROC, Precision-Recall y matriz de confusion |
| `historial_experimento.json` | Historial completo del experimento en JSON |

---



