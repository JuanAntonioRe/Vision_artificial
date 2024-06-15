# Vision artificial
Proyecto para poner en práctica la librería TensorFlow para la creación de un modelo de procesamiento de imágenes, el cual predice la edad de las personas que aparcen en cada imágen.

## Descripción del proyecto
El proyecto forma parte del curso de TrepleTen y la descripción del proyecto es:

A la cadena de supermercados Good Seed le gustaría explorar si la ciencia de los datos puede ayudarle a cumplir con las leyes sobre el alcohol, al asegurarse de no vender alcohol a personas menores de edad. Se tiene que tener en cuenta lo siguiente:

+ Las tiendas están equipadas con cámaras en el área de pago, las cuales se activan cuando una persona está comprando alcohol.
+ Los métodos de visión artificial se pueden usar para determinar la edad de una persona a partir de una foto.
+ La tarea, entonces, es construir y evaluar un modelo para verificar la edad de las personas.

## Objetivo
Entrenar un modelo que sea capaz de predecir la edad de una persona a través de una imagen. SE ha solicitado que el MAE tenga un valor menor a 8.

## Desarrollo del proyecto
### Carga de los datos
Se cargan los datos del dataset proporcionado por TripleTen. Se hace una búsqueda de datos duplicados o valores ausentes (preprocesamiento de datos)

### Análisis exploratorio de datos.
A través de un gráfico de de barras y un gráfico de caja se determina que las imágenes dentro del dataset si son pretenecientes a personas que tienen diferente edad, de 1 a 100 años.

Se observa que hay una mayor cantidad de imágenens de personas entre las edades de 20 a 40 años.

### Modelado
Se entrena un modelo de red neuronal convolucional de la librería TensorFlow. Para esto se crean 4 funciones:
* `load_train`: Se encarga de generar el conjunto de entrenamiento haciendo uso de `ImageDataGenerator`
* `load_test`: Se encarga de generar el conjunto de prueba haciendo uso de `ImageDataGenerator`
* `create_model`: Crea el modelo de TensorFlow con 3 capas y usando el optimizador "Adam"
* `train_model`: Entrena el modelo.

### Script
Se presenta un script que se coloca en la plataforma GPU de TripleTen. El script se coloca dentro de la plataforma y arroja un valor MAE de 6.90.

## Conclusiones
El modelo arroja un una valor MAE de 6.90, el cual es menor del valor solicitado de 8. Con esto decimos que nuestro modelo se equivoca en promedio por 7 años al momento de hacer una predicción de edad. Se concluye que nuestro modelo funciona.

## Tecnologías usadas
* Pandas
* matplotlib.pyplot
* Seaborn
* Numpy
* tensorflow.keras: 
    + preprocessing.image.ImageDataGenerator
    + applications.resnet.ResNet50
    + models.Sequential
    + layers.GlobalAveragePooling2D, Dense, Dropout, Flatten
    + optimizers.Adam
