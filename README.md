# MachineLearning
Mi primer contacto con Machine Learning

### A través de este Git voy a enseñaros mi primer programa en mi introducción al Machine Learning. Es un ejemplo muy básico para empezar a entender conceptos.




Nuestros datos de entrenamiento serán los siguientes :

| Peso  | Textura | Label |
| :-------------: | :-------------: |:-------------: |
| 150g  | Rugosa  | Naranja |
| 170g  | Rugosa  | Naranja |
| 140g  | Lisa  |  Manzana |
| 130g  | Lisa  | Manzana |


````python
# Importamos la librería de Machine Learning
import sklearn

# features serán los datos de entrada para el clasificador
features = [[140, "lisa"], [130, "lisa"], [150, "rugosa"], [170, "Rugosa"]]

# labels será la salida que queremos como resultado
labels = ["manzana", "manzana", "naranja", "naranja"]
````



scikit-learn usa real-valued features por lo que sustituiremos las palabras por valores
rugosa será 0
lisa será 1

manzana será 0
naranja será 1

````python
# Importamos la librería de Machine Learning
import sklearn

# features serán los datos de entrada para el clasificador
features = [[140, 1], [130, 1], [150, 0], [170, 0]]

# labels será la salida que queremos como resultado
labels = [0, 0, 1, 1]
````
