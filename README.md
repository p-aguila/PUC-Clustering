# PUC-Clustering
Foro 3 del curso Modelamiento Estadístico y Sistemas Recomendadores

## Instrucciones

Considere los datos `wholesale.csv`, que contienen información de 440 clientes de un distribuidor mayorista. La base de datos contiene información sobre el gasto anual de cada cliente en productos de las siguientes categorías: frescos (Fresh), lácteos (Milk), comestibles (Grocery), congelados (Frozen), detergentes/papel (Detergents_Paper) y rotisería (Delicassen).
En base a este conjunto de datos, realice las siguientes actividades:

## Actividades Preliminares
1. Cargue el conjunto de datos en la sesión de trabajo de `R` usando la función `read.table` . Utilizando la función `summary` determine el producto que generó la máxima venta, y el producto que mayor ingreso genera en promedio. Luego, considere y responda:
 a. ¿Son similares las distribuciones de venta de cada producto?
 b. ¿Cuál es la relación entre las medias y las desviaciones estándar de cada variable? Interprete este resultado.
 c. Adicionalmente, investigue qué producto representa la mayor parte de las ventas, y qué producto la menor. Comente e interprete estos resultados.
2. En lo que sigue, haremos análisis de conglomerados sobre los datos. ¿Qué utilidad podría tener este tipo de análisis desde el punto de vista del negocio para el distribuidor mayorista? Responda en el Foro dando ejemplos concretos.
3. Normalice los datos utilizando la función `scale`. Comente sobre el posible beneficio de realizar este pre-procesamiento en análisis de conglomerados.

## Conglomerados por k-medoids
4. Haciendo uso de la función `pam()` , incluida en la librería `cluster`, construya *k* conglomerados utilizando el método de *k-medoids*, para valores del parámetro *k* entre 2 y 10, y calcule el ancho de silueta promedio para cada valor de dicho parámetro. En base al ancho de la silueta, determine el número óptimo de conglomerados para agrupar los datos. Investigue la salida de la función `pam()` para poder obtener la silueta promedio. En el siguiente enlace encontrará información relevante sobre ella: https://en.wikipedia.org/wiki/Silhouette_(clustering). Repita el procedimiento para los datos normalizados. Comente sus resultados en el foro.
5. Agrupe los datos usando *k-medoids* con el valor de *k* determinado en el punto anterior, y genere una representación gráfica de los conglomerados generados utilizando la función `fviz_cluster`. Esta función reduce la dimensionalidad de los datos a dos dimensiones utilizando el algoritmo PCA, visto en la clase 1. ¿Qué diferencias puede observar entre los clusters generados por ambos conjuntos de datos? Comente sus resultados en el foro.
6. Utilizando los conglomerados generados en el punto anterior: ¿Qué observaciones son utilizadas como representantes de cada grupo? Repita el análisis para los datos normalizados, considerando si las observaciones representantes se mantienen o cambian. Comente su análisis en el foro.
7. Cree un gráfico de silueta utilizando la función `fviz_silhouette` y discuta una interpretación para el ancho de silueta promedio total, y dentro de cada uno de los conglomerados. ¿Cómo varía la cantidad de elementos por cluster?, ¿Cómo es la calidad del agrupamiento de los datos?. Repita el análisis para los datos normalizados y comente su análisis en el foro.

## Conglomerados Jerárquicos
8. Responda en el foro: ¿Qué utilidad podría tener un conglomerado jerárquico en los datos disponibles?.
9. Utilizando la función `hclust()` realice un análisis de conglomerados jerárquico aglomerativo. Grafique el dendograma obtenido para cada conjunto de datos y comente sus resultados en el foro. En el siguiente enlace encontrará información sobre este tipo de gráfico: https://en.wikipedia.org/wiki/Dendrogram.
10. Si se quedase con la misma cantidad de grupos que en la parte 1, ¿Se parece este agrupamiento al realizado con el método de *k-medoids*? Justifique su respuesta en el foro. Para obtener la agrupación en base a un número determinado de conglomerados puede utilizar la función `cutree()`. Repita el análisis para los datos normalizados y comente en el foro. 
11. Calcule el número de observaciones para cada uno de los *k* grupos, en base al conglomerado jerárquico aglomerativo obtenido en el punto anterior, con *k* entre 2 y 10. Repita el análisis para los datos normalizados. Comente los resultados en el foro.
