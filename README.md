# COM4402 Introducción a la Inteligencia Artificial - Proyecto Final
Integrantes: Kevin Fuentes N. y José Salgado M.
Docente: Gabriel Cabas M.
Ayudante: Nairo Torres F.

## **DEFINICIÓN DEL PROBLEMA**

El presente proyecto tiene como objetivo poder predecir el precio de venta de un automóvil usado a partir de sus características, utilizando técnicas de Machine Learning vistas durante el curso. Esta problemática es perfecta para las personas que necesitan comprar o vender un auto, dado que en muchas ocasiones las circunstancias, condiciones o características afectan al valor y es difícil establecer un criterio. Para abordar esta problemática, seleccionamos una base de datos relacionada con el mercado automotriz de Estados Unidos, el cual presenta una gran variedad de marcas y modelos vehiculares.

Realizaremos un código que nos permita determinar el precio de vehículos a través de sus características. Sin embargo, existe la posibilidad de que el valor estimado no sea el más preciso, por lo que implementaremos distintos modelos de aprendizaje supervisado para determinar este. Además, evaluaremos el desempeño de estos modelos mediante métricas para comparar los resultados que se obtengan y, gracias a estas, poder descubrir qué modelo utilizado se ajusta de manera más adecuada a nuestra base de datos seleccionada.

## **PLAN DE ACCIÓN**

Para la realización de este proyecto, se utilizará el dataset 'USA_cars_datasets.csv' (https://www.kaggle.com/datasets/doaaalsenani/usa-cers-dataset/data), el cual contiene 2499 registros de vehículos usados en venta en Estados Unidos. Los algoritmos de aprendizaje supervisado que se utilizaremos corresponden a modelos de regresión. Particularmente, se implementarán los siguientes algoritmos:

1. REGRESIÓN LINEAL: Es un modelo que permite predecir un valor numérico continuo a partir de un conjunto de variables independientes. Su característica principal es que asume una relación lineal entre las variables y la variable principal. Se entrena usando el método de Least Squares y se puede interpretar estadísticamente como una Maximum Likelihood Estimation si se asume que los errores tienen distribución normal. El motivo de seleccionar este modelo es porque es uno de los más fáciles de interpretar e implementar, sin embargo, presenta limitaciones cuando las relaciones entre variables no son lineales o cuando hay interacciones complejas.

2. RANDOM FOREST REGRESSOR: Es un modelo que utiliza múltiples Decision Trees para predecir una variable continua. Se utilizan varios árboles que se entrenan sobre un subconjunto de datos aleatorios del dataset usando la técnica de Bagging, lo que permite generar arboles con diversidad de datos, los cuales son menos propensos al overfitting. La predicción final del modelo la obtenemos promediando los resultados de todos los árboles ocupados o creados. Seleccionamos este modelo porque nos permite determinar las relaciones no lineales y manejar de forma robusta un dataset con atributos complejos. 

3. K-NEAREST NEIGHBORS REGRESSOR: Es un modelo que nos permite predecir un valor continuo en base a la similitud entre los datos del dataset. A diferencia de otros modelos, no construye una función durante el entrenamiento, sino que almacena los datos. Al momento de hacer una predicción, este modelo calcula la distancia entre la nueva instancia y todos los datos almacenados, seleccionando los k vecinos que estén más cercanos y promediando sus valores para entregar el resultado final. Seleccionamos este modelo por su capacidad de adaptarse a patrones complejos sin asumir relaciones lineales, pero puede verse afectado por el ruido o por la alta dimensionalidad de los datos.

## **JUSTIFICACIÓN DEL MODELO**

Los modelos de regresión son herramientas estadísticas utilizadas para modelar relaciones entre variables numéricas, por lo que su uso en nuestro proyecto es adecuado para abordar problemas de predicción de precios gracias a su fácil implementación, simple interpretabilidad y bajo requerimiento computacional.

Es importante tener en cuenta que el dataset seleccionado podría afectar de cierta forma el buen entrenamiento de los modelos. Esto, debido a que hay un desbalance de los datos, lo que podría resultar en que los modelos se entrenen de mejor forma con ciertas variables por sobre otras. Este desbalance se podrá visualizar gráficamente durante el análsis exploratorio de datos (EDA).


# **CORRECCIONES POST RETROALIMENTACIÓN**

## **FEATURES**

Los atributos que contienen nuestro DataFrame son:
1. UNNAMED: 0   - NUMÉRICA   - ELIMINADA     - Índice del DataFrame, no aporta significancia para el entrenamiento de modelos.
2. PRICE        - NUMÉRICA   - NO CODIFICADA - Precio de venta del vehículo. Corresponde al target de nuestro proyecto.
3. YEAR         - NUMÉRICA   - NO CODIFICADA - Es el año en el cual se fabricó el vehículo.
4. BRAND        - CATEGÓRICA - CODIFICADA    - Es la marca del vehículo.
5. MODEL        - CATEGÓRICA - CODIFICADA    - Son los modelos de auto de las diferentes marcas.
6. MILEAGE      - NUMERICA   - NO CODIFICADA - Es el kilometraje del vehículo, es decir, la distancia conducida de este.
7. TITLE_STATUS - CATEGÓRICA - CODIFICADA    - Es la condición física del vehículo.
8. COLOR        - CATEGÓRICA - CODIFICADA    - Es el color del vehículo.
9. VIN          - CATEGÓRICA - ELIMINADA     - Es el código de identificación del vehículo, formada por caracteres.
10. LOT         - CATEGÓRICA - ELIMINADA     - Es el número de identificación del lote, para realizar un seguimiento.
11. STATE       - CATEGÓRICA - CODIFICADA    - Es el estado en el cual se encuentra el auto.
12. COUNTRY     - CATEGÓRICA - ELIMINADA     - Es el país donde se está realizando la venta del vehículo.
13. CONDITION   - CATEGÓRICA - CODIFICADA    - Es el tiempo de publicación restante para realizar la venta.

Decidimos eliminar algunas variables categóricas debido a que estas pueden afectar el desempeño de los modelos de regresión, pues estos se pueden volver demasiado complejos de interpretar y, consecuentemente, de realizar posterior análisis concluyente. Además, un modelo con demasiadas variables es propenso a sufrir overfitting.

## ¿EL MODELO PRESENTA UN DESBALANCE?

Al incio, habíamos determinado que el DataFrame presentaba un desbalance debido a las distribuciones que observamos en el Kaggle. Esto fue comprobado al visualizar gráficamente la distribución por medio de un histograma, donde nuevamente se evidenció que la mayoría de los vehículos son de la marca Ford. Por esto, determinamos una alta asimetría o sesgo en los datos del DataFrame.