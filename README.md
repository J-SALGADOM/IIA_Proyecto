# COM4402 Introducción a la Inteligencia Artificial - Proyecto Final
Integrantes: Kevin Fuentes N. y José Salgado M.

DEFINICIÓN DEL PROBLEMA

El presente proyecto tiene como objetivo poder predecir el precio de venta de un automóvil usado a partir de sus características, utilizando técnicas de Machine Learning vistas durante el curso. Esta problemática es perfecta para las personas que necesitan comprar o vender un auto, dado que en muchas ocasiones las circunstancias, condiciones o características afectan al valor y es difícil establecer un criterio. Para abordar esta problemática, seleccionamos una base de datos relacionada con el mercado automotriz de Estados Unidos, el cual presenta una gran variedad de marcas y modelos vehiculares.

Realizaremos un código que nos permita determinar el precio de vehículos a través de sus características. Sin embargo, existe la posibilidad de que el valor estimado no sea el más preciso, por lo que implementaremos distintos modelos de aprendizaje supervisado para determinar este. Además, evaluaremos el desempeño de estos modelos mediante métricas para comparar los resultados que se obtengan y, gracias a estas, poder descubrir qué modelo utilizado se ajusta de manera más adecuada a nuestra base de datos seleccionada.

PLAN DE ACCIÓN

Para la realización de este proyecto, se utilizará el dataset 'USA_cars_datasets.csv' (https://www.kaggle.com/datasets/doaaalsenani/usa-cers-dataset/data), el cual contiene 2499 registros de vehículos usados en venta en Estados Unidos. Los algoritmos de aprendizaje supervisado que se utilizaremos corresponden a modelos de regresión. Particularmente, se implementarán los siguientes algoritmos:

1. REGRESIÓN LINEAL: Es un modelo que permite predecir un valor numérico continuo a partir de un conjunto de variables independientes. Su característica principal es que asume una relación lineal entre las variables y la variable principal. Se entrena usando el método de Least Squares y se puede interpretar estadísticamente como una Maximum Likelihood Estimation si se asume que los errores tienen distribución normal. El motivo de seleccionar este modelo es porque es uno de los más fáciles de interpretar e implementar, sin embargo, presenta limitaciones cuando las relaciones entre variables no son lineales o cuando hay interacciones complejas.

2. RANDOM FOREST REGRESSOR: Es un modelo que utiliza múltiples Decision Trees para predecir una variable continua. Se utilizan varios árboles que se entrenan sobre un subconjunto de datos aleatorios del dataset usando la técnica de Bagging, lo que permite generar arboles con diversidad de datos, los cuales son menos propensos al overfitting. La predicción final del modelo la obtenemos promediando los resultados de todos los árboles ocupados o creados. Seleccionamos este modelo porque nos permite determinar las relaciones no lineales y manejar de forma robusta un dataset con atributos complejos. 

3. K-NEAREST NEIGHBORS REGRESSOR: Es un modelo que nos permite predecir un valor continuo en base a la similitud entre los datos del dataset. A diferencia de otros modelos, no construye una función durante el entrenamiento, sino que almacena los datos. Al momento de hacer una predicción, este modelo calcula la distancia entre la nueva instancia y todos los datos almacenados, seleccionando los k vecinos que estén más cercanos y promediando sus valores para entregar el resultado final. Seleccionamos este modelo por su capacidad de adaptarse a patrones complejos sin asumir relaciones lineales, pero puede verse afectado por el ruido o por la alta dimensionalidad de los datos.

JUSTIFICACIÓN DEL MODELO

Los modelos de regresión son herramientas estadísticas utilizadas para modelar relaciones entre variables numéricas, por lo que su uso en nuestro proyecto es adecuado para abordar problemas de predicción de precios gracias a su fácil implementación, simple interpretabilidad y bajo requerimiento computacional.

Es importante tener en cuenta que el dataset seleccionado podría afectar de cierta forma el buen entrenamiento de los modelos. Esto, debido a que hay un desbalance de los datos, lo que podría resultar en que los modelos se entrenen de mejor forma con ciertas variables por sobre otras. Este desbalance se podrá visualizar gráficamente durante el análsis exploratorio de datos (EDA).