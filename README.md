# Hateful-Memes

Tercer Proyecto de la materia de 'Proyecto integrador de tecnologías emergentes' impartida por el profesor Daniel Cabrera

Equipo #3

María Fernanda Mendoza A01745728 <br />
Carolina Obregon A01251983 <br />
Isabel Navarro A00823132 <br />
Jaime Montemayor A01176573 <br />
Gustavo De Los Ríos Alatorre A01410922

## Introducción
El internet es una gran herramienta que nos permite comunicarnos en segundos con las personas que queremos. También nos permite compartir ideas por medio de imágenes, textos, videos, etc. Algunas de estas ideas que en los últimos años ha ido creciendo exponencialmente es el uso de los memes con fines humorísticos en las diferentes redes sociales. Sin embargo, algunos memes pueden llegar a ser ofensivos contra algún sector de la población o contra un individuo en particular causando daños morales y pudiendo incluso a dañar la salud mental por el acoso excesivo. Es por esto que decidimos utilizar inteligencia artificial para desarrollar un modelo que pueda detectar memes ofensivos encontrados en las imágenes.


## Requerimientos
**Se debe de ejectuar el código en Google Colab para asegurar su funcionamiento adecuado.**
  
## Uso del código
Este proyecto está dividido en tres partes, las cuales se pueden ver en los siguientes archivos
- TextClassificationFP.ipynb (clasificador de texto)
- EmotionDetection.ipynb (clasificador de emociones)
- OCR.ipynb (extracción de texto)

Al realizar el clone al repositorio se obtienen todos los archivos, en caso de no hacerlo, verificar que se tengan todos los archivos de los datos para su correcto funcionamiento.

## Clonado del repositorio
```
git clone https://github.com/carooobregon/Hateful-Memes.git
```
## Base de datos
Está compuesta de imágenes tanto ofensivas como no ofensivas, con el propósito de entrenar el modelo y sepa distinguir entre estas. Dichas imágenes fueron obtenidas del desafío para la detección para memes de Facebook, los cuales fueron compilados con el propósito de desarrollar modelos multimodales para su respectiva clasificación.

Para el procesamiento de texto se utilizó el dataset del repositorio de Thomas Davidson "Automated Hate Speech Detection and the Problem of Offensive Language", el cual divide tweets entre ofensivos (19190), de odio (1430) y ninguno (4163).

## Descripción y entrenamiento de los modelos
Utilizamos una red convolucional para la detección de rostros, clasificación de género y clasificación de emociones. También se utiliza un clasificador de texto, sin embargo no se utiliza el método de ensamble.

Para realizar el proceso de extracción de textos, recurrimos a técnicas de OCR (Optic Character Recognition). Combinamos la biblioteca EasyOCR de Pytorch con procesamiento de imágenes en OpenCV. Se le aplicaron diferentes transformaciones a las imágenes, esperando obtener los mejores resultados posibles.

Una vez que los textos de cada imagen se extraen, son guardados en un documento tipo csv para poder procesarlos y clasificarlos en mensaje ofensivo o de odio y mensaje neutral.

En cuanto al reconocimiento de emociones en imágenes se utilizó la librería PAZ (Perception for Autonomous Systems) el cual propone una arquitectura de red neuronal convolucional y back-propagation para evaluar los pesos y las características aprendidas. Esta librería está implementada utilizando Keras y OpenCV.

Primero se realizó un reconocimiento de las caras y se dibujan bounding boxes en estas. Posteriormente, se realiza un corte y se hace la clasificación para reconocer emociones.

## Páginas consultadas
[1] Kiela, D., Firooz, H., Mohan, A., Goswami, V., Singh, A., Ringshia, P., & Testuggine, D. (2020). The hateful memes challenge: Detecting hate speech in multimodal memes. arXiv preprint arXiv:2005.04790.  <br />
[2] Arriaga, O., Valdenegro-Toro, M., & Plöger, P. (2017). Real-time convolutional neural networks for emotion and gender classification. arXiv preprint arXiv:1710.07557.

