# Para la realización de este proyecto se utilizaron las siguientes herramientas/bibliotecas:

## Interprete
- python 3.7

## Librerias
- cvzone 1.5.6
- mediapipe 0.9.1.0
- opencv-python 4.5.4.60
- tensorflow 2.9.1

## Servidor en la nube
- teachable machine

# Explicación del codigo:

## datacollection.py

El código importa algunos módulos como cv2, numpy, math, time y HandDetector de la biblioteca cvzone. Luego, inicializa la cámara capturando un objeto de VideoCapture con índice 0 (la cámara predeterminada) y un detector de manos con un límite máximo de detección de una mano.

Se definen algunas variables como offset, imgSize y folder. El bucle while se ejecuta indefinidamente y en cada iteración, se lee un cuadro de la cámara y se detecta la mano utilizando el detector de manos.

Si se detecta una mano, se calcula el cuadro delimitador que encierra la mano. Se crea una imagen en blanco del tamaño especificado por imgSize y se ajusta la imagen recortada de la mano para que tenga la misma relación de aspecto que la imagen en blanco.

Si la relación de aspecto de la imagen recortada es mayor que 1, significa que la imagen es más alta que ancha. Por lo tanto, se redimensiona la imagen recortada para que tenga una altura de imgSize y se ajusta el ancho para mantener la relación de aspecto original. Si la relación de aspecto es menor que 1, se hace lo contrario.

La imagen redimensionada se coloca en el centro de la imagen en blanco. Se muestran la imagen recortada y la imagen en blanco en ventanas separadas. Si se presiona la tecla "s", se guarda la imagen en blanco en la carpeta especificada por folder con un nombre de archivo único basado en la hora actual. El contador se incrementa en uno y se muestra por pantalla.

## test.py

Este es un script de Python que utiliza la biblioteca OpenCV para capturar imágenes de video desde la cámara de la computadora, detectar una mano y predecir la letra que se muestra en la palma de la mano.

El código importa varios módulos de Python, incluidos cv2, numpy y math, y también importa dos módulos específicos para la detección de manos y clasificación de imágenes, llamados HandDetector y Classifier, respectivamente.

A continuación, se inicializa una instancia de HandDetector para detectar una mano en cada fotograma de video y una instancia de Classifier para predecir la letra que se muestra en la palma de la mano.

Luego, se define una serie de variables, incluidas offset, imgSize y folder. Estas variables se utilizan para redimensionar y recortar las imágenes de la mano.

El código luego entra en un bucle while infinito que captura continuamente fotogramas de video de la cámara y procesa la imagen para detectar la mano y predecir la letra.

En el bucle, se lee cada fotograma de video y se llama a detector.findHands() para encontrar la mano en la imagen. Si se detecta una mano, se recorta y redimensiona la imagen para que se ajuste al tamaño deseado y se llama a classifier.getPrediction() para predecir la letra que se muestra en la palma de la mano.

Finalmente, se dibujan cajas alrededor de la mano y se muestra la imagen procesada en una ventana de OpenCV. El bucle continúa hasta que el usuario presiona la tecla 'q' para salir del programa.
