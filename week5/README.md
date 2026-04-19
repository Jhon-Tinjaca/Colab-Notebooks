# week5
DIEGO ALEJANDRO RUIZ ALFONSO - ppmurcia@ucundinamarca.edu.co - Líder de métricas
PEDRO PASCUAL MURCIA VARGAS - ppmurcia@ucundinamarca.edu.co - Líder de documentación
JHON EDUARD TINJACA CRUZ - jetinjaca@ucundinamarca.edu.co - Líder de experimento
JULIAN DAVID SILVA GUZMAN - jdsilva@ucundinamarca.edu.co - Líder

## Objetivo
Comparar el efecto de hiperparámetros y técnicas de optimización en el entrenamiento de una red neuronal para clasificación binaria.

## Qué se comparó
1. **Tasa de aprendizaje** con Adam:
   - `learning_rate = 1e-3`
   - `learning_rate = 5e-4`

2. **Optimizador** manteniendo lo demás constante:
   - Adam
   - SGD

## Resultado principal
Adam con `learning_rate = 1e-3` mostró mejor equilibrio entre velocidad de convergencia, estabilidad y desempeño final. SGD fue más lento en converger bajo las mismas condiciones.

## Cómo ejecutar el notebook
1. Abrir `week5_hyperparameters_optimization.ipynb` en **Google Colab**.
2. Ejecutar las celdas en orden.
3. Revisar las tablas, métricas y gráficos para comparar las configuraciones.
