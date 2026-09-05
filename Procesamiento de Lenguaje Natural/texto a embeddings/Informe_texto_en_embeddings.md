# Informe_Texto_en_Embeddings

## Integrante:
Jhon Eduard Tinjaca Cruz - jetinjaca@ucundinamarca.edu.co

# Embeddings para Procesamiento de Lenguaje Natural

Este ejercicio transforma textos en representaciones numéricas utilizando tres técnicas fundamentales de procesamiento de lenguaje natural: TF-IDF, Word2Vec y embeddings aprendidos con TensorFlow/Keras. También compara las representaciones mediante la similitud de coseno y utiliza visualizaciones para facilitar su interpretación.

## Contenido
1. **Preprocesamiento de texto**: Normalización, limpieza y tokenización de un corpus en español.
2. **TF-IDF**: Representación estadística basada en la importancia de las palabras dentro de cada documento.
3. **Word2Vec**: Representación densa basada en el contexto de las palabras.
4. **TensorFlow/Keras**: Uso de una capa de `Embedding` para generar vectores aprendibles.
5. **Visualización**: Nube de palabras, mapa de calor TF-IDF y proyección PCA de Word2Vec.
6. **Similitud de coseno**: Comparación de documentos usando embeddings de TF-IDF y Keras.

## Resultados

- Se limpió un corpus de cuatro frases relacionadas con tecnología y gastronomía italiana.
- Se generó una matriz TF-IDF con el vocabulario obtenido del corpus.
- Se entrenó un modelo Word2Vec con un tamaño de vector de 10 dimensiones.
- Se proyectaron los vectores de Word2Vec en dos dimensiones mediante PCA.
- Se obtuvieron embeddings de palabras con una capa de TensorFlow/Keras de cuatro dimensiones.
- Se calcularon similitudes de coseno entre la primera frase y las demás.
- Se comprobó que TF-IDF mide principalmente coincidencias literales, mientras que Word2Vec busca relaciones contextuales.
- Se observó que los embeddings de Keras sin entrenamiento producen valores aleatorios y no representan todavía relaciones semánticas confiables.

## Cómo ejecutar
1. Abrir el archivo `Texto_en_Embeddings.ipynb` en Google Colab o Jupyter Notebook.
2. Ejecutar las celdas de instalación de dependencias (`gensim` y `wordcloud`).
3. Ejecutar las celdas de importación y preprocesamiento.
4. Construir las representaciones TF-IDF, Word2Vec y TensorFlow/Keras.
5. Ejecutar las celdas de visualización y comparación de similitud.
6. Revisar las gráficas y los valores impresos en cada etapa.

## Archivos Generados

- Nube de palabras del corpus limpio.
- Mapa de calor con los valores TF-IDF de cada documento.
- Gráfico de dispersión PCA con las palabras del modelo Word2Vec.
- Gráfico de barras con la similitud de coseno respecto a la primera frase usando TF-IDF.
- Gráfico de barras con la similitud de coseno usando embeddings de Keras.

## General del Código

El flujo de trabajo de este notebook se divide en cinco etapas principales:

1. **Instalación e importación de librerías**:
   * Se utilizan NumPy y Pandas para el manejo de datos.
   * Scikit-Learn proporciona `TfidfVectorizer`, PCA y el cálculo de similitud de coseno.
   * Gensim proporciona el modelo Word2Vec.
   * TensorFlow/Keras se utiliza para crear la capa de embeddings.
   * Matplotlib, Seaborn y WordCloud permiten visualizar los resultados.

2. **Preprocesamiento de texto**:
   * Se convierten las frases a minúsculas.
   * Se eliminan caracteres especiales y números mediante expresiones regulares.
   * Se separan las palabras en tokens.
   * Se preparan dos formatos del corpus: texto separado por espacios para TF-IDF y listas de tokens para Word2Vec.

3. **Generación de representaciones numéricas**:
   * TF-IDF asigna pesos a las palabras según su frecuencia en cada documento y su presencia en el resto del corpus.
   * Word2Vec aprende vectores densos a partir del contexto de las palabras.
   * Keras convierte los tokens en índices y los pasa por una capa `Embedding`.

4. **Visualización**:
   * La nube de palabras muestra la frecuencia de los términos.
   * El mapa de calor representa la importancia de cada palabra en cada frase.
   * PCA reduce los vectores de Word2Vec de 10 dimensiones a dos para poder observarlos en un plano.

5. **Comparación de similitud**:
   * Se utiliza la similitud de coseno para comparar la primera frase con las demás.
   * En los embeddings de Keras se promedian los vectores de las palabras para obtener un único vector por frase.

## En la ejecución del código, podemos evidenciar varios puntos clave sobre el comportamiento de las representaciones de texto:

**Preprocesamiento y normalización**: La función `limpiar_texto` permite trabajar con un corpus uniforme. Al convertir las frases a minúsculas y eliminar signos de puntuación, se evitan diferencias artificiales entre palabras equivalentes.

**Importancia estadística con TF-IDF**: Las palabras particulares de un documento reciben valores altos cuando ayudan a distinguirlo de los demás. Las palabras comunes tienen menor capacidad para diferenciar frases.

**Limitaciones de TF-IDF**: La similitud de coseno con TF-IDF depende de las palabras exactas que comparten dos documentos. Por este motivo, dos frases semánticamente relacionadas pueden obtener una similitud baja si utilizan vocabularios diferentes.

**Representación contextual con Word2Vec**: Word2Vec genera vectores densos para las palabras y coloca cerca aquellas que aparecen en contextos semejantes. Sin embargo, el corpus utilizado es muy pequeño, por lo que las agrupaciones observadas mediante PCA pueden ser inestables o poco representativas.

**Embeddings de Keras**: La capa `Embedding` inicia sus valores de forma aleatoria. Para que los vectores aprendan relaciones semánticas útiles, deben optimizarse durante el entrenamiento de un modelo orientado a una tarea específica.

**Comparación mediante similitud de coseno**: Esta medida permite cuantificar el ángulo entre dos vectores. Una puntuación cercana a 1 indica direcciones similares, mientras que una puntuación cercana a 0 indica poca coincidencia en la representación usada.

## Conclusiones

- TF-IDF es una técnica sencilla y útil cuando la coincidencia de palabras clave es importante, pero no comprende el significado de las palabras.
- Word2Vec puede capturar relaciones semánticas entre palabras, aunque necesita un corpus amplio para producir representaciones robustas.
- Los embeddings de Keras son flexibles porque se aprenden junto con una tarea de aprendizaje profundo, pero sus valores iniciales no deben interpretarse como relaciones semánticas antes del entrenamiento.
- La similitud de coseno funciona como una herramienta común para comparar documentos representados mediante vectores.
- La combinación de métricas numéricas y visualizaciones facilita el análisis de las diferencias entre representaciones dispersas y densas.

## Cómo Ejecutar en Colab

### Opción 1: Cargar desde GitHub
1. Abre [Google Colab](https://colab.research.google.com/)
2. Selecciona **"Archivo"** → **"Abrir cuaderno"** → **"GitHub"**
3. Pega la URL del repositorio que contiene este notebook

### Opción 2: Cargar manualmente
1. Descarga el archivo `Week14_14_GANs.ipynb` de esta carpeta
2. Abre [Google Colab](https://colab.research.google.com/)
3. Selecciona **"Archivo"** → **"Subir cuaderno"**
4. Elige el archivo descargado

### Requisitos
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-Learn
- Gensim
- NLTK
- WordCloud
- TensorFlow
- Keras
