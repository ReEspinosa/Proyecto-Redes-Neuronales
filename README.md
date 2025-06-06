# Red Neuronal para Clasificación de Géneros Musicales (GTZAN)

## Introducción
Este proyecto desarrolla una red neuronal convolucional (CNN) para clasificar fragmentos de canciones en diferentes géneros musicales utilizando el dataset GTZAN. El reto consiste en identificar el género musical a partir de espectrogramas extraídos de fragmentos de 20 segundos de audio. Aunque estos fragmentos pueden parecer insuficientes para que un humano reconozca el género, la red neuronal es capaz de aprender patrones y características relevantes que permiten una apreciable precisión en la clasificación.

## Lógica de Solución
1. **Preprocesamiento de Datos**
   - Se carga el dataset GTZAN, donde los archivos de audio están organizados por géneros: blues, classical, country, disco, hiphop, jazz, metal, pop, reggae y rock.
   - Cada archivo se procesa para extraer un espectrograma de Mel, transformando el audio en una representación visual que facilita la extracción de patrones mediante técnicas de visión computacional.

2. **Implementación del Modelo**
   - **Arquitectura de la Red:**  
     Se implementa una red neuronal convolucional (CNN) que incluye:
     - Capas convolucionales para identificar patrones locales en el espectrograma.
     - Batch Normalization para estabilizar y acelerar el entrenamiento.
     - MaxPooling para reducir la dimensionalidad espacial y mantener las características más importantes.
     - Dropout para prevenir el sobreajuste.
     - Capas densas finales que integran las características extraídas y realizan la clasificación final mediante una función softmax (implícita en la función de pérdida).
   - **Ciclo de Entrenamiento:**  
     Se definen funciones específicas para entrenar el modelo, evaluar su desempeño en conjuntos de validación y test, y realizar predicciones. Durante el entrenamiento se registran la pérdida y la precisión de entrenamiento y validación para ajustar el proceso de aprendizaje.

3. **Evaluación y Visualización**
   - El modelo se evalúa en un conjunto de prueba, calculando métricas como la pérdida y la precisión.
   - Se generan visualizaciones que incluyen:
     - Curvas de aprendizaje (pérdida y precisión a lo largo de las épocas).
     - Matriz de confusión para identificar los géneros que presentan mayor confusión.
     - Ejemplos visuales de espectrogramas con sus etiquetas reales y predichas.

## Librerías y Requisitos
Para ejecutar este proyecto es necesario contar con las siguientes librerías y entornos:
- Python 3.x
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- [Librosa](https://librosa.org/)
- [PyTorch](https://pytorch.org/)
- [Torchaudio](https://pytorch.org/audio/stable/index.html)
- [pandas](https://pandas.pydata.org/)
- [scikit-learn](https://scikit-learn.org/stable/)

Instala las dependencias utilizando pip:
```bash
pip install numpy matplotlib librosa torch torchaudio pandas scikit-learn
```

## Dataset
El proyecto utiliza el **GTZAN Genre Collection**, un dataset clásico en la clasificación de géneros musicales.  
- **Características:**  
  - 1000 archivos de audio de 30 segundos cada uno, organizados en 10 géneros: blues, classical, country, disco, hiphop, jazz, metal, pop, reggae y rock.
  - En este proyecto se utilizan fragmentos de 20 segundos.
- **Descarga:**  
  - Puedes descargar el dataset desde [este enlace](http://opihi.cs.uvic.ca/sound/genres.tar.gz) o buscarlo en [Kaggle](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification).
  - Descomprime el archivo y coloca la carpeta `genres` en el directorio del proyecto.

## Cómo Ejecutar el Proyecto
1. Clona el repositorio:
   ```bash
   git clone https://github.com/ReEspinosa/Proyecto-Redes-Neuronales.git
   ```
2. Navega al directorio del proyecto:
   ```bash
   cd Proyecto-Redes-Neuronales
   ```
3. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
   *(Si no se cuenta con un archivo `requirements.txt`, instala las librerías listadas en la sección de Librerías y Requisitos.)*
4. Descarga y descomprime el dataset GTZAN en la carpeta `./genres`.
5. Abre el notebook `ProyectoRN.ipynb` y ejecuta las celdas en orden para reproducir el entrenamiento y la evaluación del modelo.

## Miembros del Equipo
- Miembro 1: Espinosa Roque Rebeca (320326387)
- Miembro 2: Jose Ruben Alfaro Gonzalez (320516436)

## Conclusiones
Este proyecto demuestra el potencial de las redes neuronales en el análisis y clasificación automática de música. El modelo propuesto logra identificar patrones en los espectrogramas que le permiten clasificar fragmentos de audio en distintos géneros. Se plantean posibles mejoras como la optimización de hiperparámetros, el uso de arquitecturas más profundizadas, o la integración de técnicas avanzadas de preprocesamiento.
