# Proyecto5_Machine_Learning

![imagen](imag.jpg)

## OBJETIVO:
Tenemos como objetivo para este proyecto, encontrar el mejor modelo de aprendizaje automático (machine learning) para un conjunto de datos dado relacionado con características de diamantes. Además participaré en un concurso de la plataforma "Kaggle" para intentar que mi modelo sea el mejor obtenido.


## EJECUCIÓN:
Para conseguir dicho objetivo, voy a trabajar con un dataset de entrenamiento y otro de pruebas y el proceso que llevaré a cabo será el siguiente:
- TRAIN DATASET:
realizo limpieza del dataset, me valgo de matrices de correlación para poder eliminar las columnas que estén altamente correlacionadas.
A continuación exploro las variables categóricas para convertirlas en numéricas, para ello investigo sobre los datos proporcionados y doy valores a dichas categorías según corresponda cada nivel. Estas columnas son "cut", "color" y "clarity". Una vez tengamos los valores numéricos los relaciono con cada uno de sus valores de las columnas iniciales.
- TEST DATASET:
llevo a cabo con el cvs de test, los mismo métodos de limpieza aplicados en el dataset de train para poder relacionarlos correctamente.

Una vez tengo guardados mis nuevos csv de train y test limpios procedemos al entrenamiento del modelo:

- ENTRENAMIENTO:
    - Entreno varios modelos de regresión para poder elegir el más adecuado una vez obtenga los resultados.
    - Entreno los modelos con el 80% de los datos totales del dataset y hago la predicción con X_test, que es el 20% del dataset train, obteniendo el error cuadrático medio **RMSE**.
    - Nos quedamos con los 3 mejores modelos que serían los que tienen menor error cuadrático medio y los entrenos de nuevo pero en este caso en base al total de valores de train (X, y)
    - Hago la predicción con test para este segundo entrenamiento y me quedo con el modelo con menor RMSE calculado del total ("tree").
    - Ya cuento con un primera submission que puedi subir al concurso de Kaggle.


- MEJORAR MODELOS: para mejorar los modelos podemos usar los parámetros de cada uno. En este caso, intento mejorar el modelo de "tree" con el método grid, que elige los valores de los mejores hiperparámetros.
- Ya cuento con la segunda submission.


- ESTRUCTURA DEL PROYECTO: 
    - Una carpeta data que contiene:
        - el csv de train
        - el csv de test
        - el csv de la limpieza de train
        - el csv de la limpieza de test
        - el csv de submission
    - Una carpeta notebook que contiene:
        - documento jupyter de limpieza --> clean_diamond
        - documento jupyter de entrenamiento y prueba de diferentes modelos --> entrenamiento
  
    - Una carpeta gitignore

    - Un archivo ppt con una diapositiva explicativa del proceso seguido --> machine_learning

    - Un archivo Readme
    
CONCLUSIÓN FINAL: comparando los modelos especificados en base al error cuadrático medio, el mejor es **DecisionTreeRegressor**. Este se ha mejorado respecto a él mismo con dos métodos, en primer lugar con el método "grid" y en segundo lugar con el método "cross_validate".


## RECURSOS UTILIZADOS:
- [Kaggle data set](https://www.kaggle.com/c/diamonds-datamad1021-rev/leaderboard)

- He usado las siguientes librerías:
    - [Pandas](https://pandas.pydata.org/)
    - [Numpy](https://numpy.org/doc/)
    - [Sklearn](https://scikit-learn.org/)
    - [warnings](https://docs.python.org/3/library/warnings.html)
