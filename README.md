# Machine Learning
Mi primer contacto con Machine Learning

### A través de este Git voy a enseñaros mi primer programa en mi introducción al Machine Learning. Es un ejemplo muy BÁSICO para empezar a entender conceptos.


Nuestro programa buscara patrones entre los datos introducidos, para ello usaremos Tree Classifier y lo alimentaremos con nuestros datos de prueba.

Nuestros datos de entrenamiento serán los siguientes :

| Peso  | Textura | Label |
| :----: | :----: |:-------: |
| 150g  | Rugosa  | Naranja |
| 170g  | Rugosa  | Naranja |
| 140g  | Lisa  |  Manzana |
| 130g  | Lisa  | Manzana |


````python
# Importamos de la librería de Machine Learning el módulo tree 
from sklearn import tree

# features serán los datos(características) de entrada para el clasificador
features = [[140, "lisa"], [130, "lisa"], [150, "rugosa"], [170, "Rugosa"]]

# labels será la salida que queremos como resultado
labels = ["manzana", "manzana", "naranja", "naranja"]
````



Scikit-learn usa real-valued features por lo que sustituiremos las palabras por valores

lisa será 1

rugosa será 0


manzana será 0

naranja será 1

El codigo quedaría de la siguiente manera:
````python
# Importamos de la librería de Machine Learning el módulo tree 
from sklearn import tree

# features serán los datos(características) de entrada para el clasificador
features = [[140, 1], [130, 1], [150, 0], [170, 0]]

# labels será la salida que queremos como resultado
labels = [0, 0, 1, 1]
````

Ahora crearemos un clasificador el cual alimentaremos con las cartacteristicas y el resultado esperado

````python
# creamos el clasificador
clf = tree.DecisionTreeClassifier()

# lo "alimentamos" con las caracteristicas y el resultado esperado.
# fit buscara patrones entre los datos 
clf = clf.fit(features, labels)
````

Ahora pasaremos nuevos datos al clasificador, el cual ya es capaz de predecir si es una manzana (0) o una naranja (1).

Pasaremos los datos 150g y rugosa (0). Si nos paramos a pensar y los comparamos con los datos de entrenamiento veremos que las características concuerdan con la descripción de una naranja (1).
````python
print(clf.predict([[150, 0]]))
````
#### Salida por consola del programa:
````console
[1]
````

El clasificador devuelve el resultado correcto. Ha reconocido los patrones en los datos introducidos y ha sido capaz de predecir que fruta es con esas características.


Código completo.
````python
# Importamos la librería de Machine Learning
from sklearn import tree

# features serán los datos(características) de entrada para el clasificador
features = [[140, 1], [130, 1], [150, 0], [170, 0]]

# labels será resultado esperado
labels = [0, 0, 1, 1]

# creamos el clasificador
clf = tree.DecisionTreeClassifier()

# lo "alimentamos" con las caracteristicas y el resultado esperado.
# fit buscara patrones entre los datos
clf = clf.fit(features, labels)


print(clf.predict([[150, 0]]))
````


