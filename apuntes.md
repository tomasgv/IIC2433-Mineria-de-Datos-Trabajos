# Association Rules

## Algoritmo Apriori
Soporte, Confianza y Lift

### Problemas
- Consume mucha memoria
- Probar combinaciones a posibles candidatos puede ser muy lento

## FP-Tree

todo todo todo


# PCA
**Reducción de dimensionalidad depende de los datos.**
Nos quedamos con aquellos de mayor varianza. Siempre se pierde información, pero eso no significa que la info perdida sea valiosa o no.

Se buscan k vectores ortogonales, con k < d (d las dimensiones del dataset)

Usando método de Lagrange se llega a
$S v_1 = \lambda_1 v_1$

Con $v_1$ vector unitario y $\lambda_1$ es un escalar.

Notamos que $\lambda_1$ es valor propio de $S$ y $v_1$ es vector propio asociado.

**Finalmente, las primeras k componentes principales de X corresponden exactamente a los vectores propios de la matriz de covarianza S ordenados por sus valores propios de mayor a menr. Más aún, los valores propios son exactamente iguales a la varianza del conjunto de datos a través de esa dimensión.**

Para reducir la dimensionalidad de los datos, se genera la matriz de tranfsormación $W$ de tamaño $d \times k$, compuesta por los vectores propios de la matriz de covarianza ordenados de mayor a menor.

Luego los datos transformados se generan proyectando el conjunto de datos en la matriz de transformación:

$y=WX^T$

Donde $X$ es de $d \times n$, e $y$ resulta ser de $k\times n$.

- $n =$ número de filas
- $k =$ número de componenetes
- $d =$ número de dimensiones

**El algortimo en resumen:**
- Se toma el conjunto de datos usando las $d$ dimensiones
- Se calcula la media para cada dimensión
- se calcula la matriz de covarianza del conjunto de datos
- Se calculan la matriz de vectores propios y sus correspondientes valores propios de la matriz de covarianza
- Se ordenan los vectores propios de forma decreciente en cuanto al valor propio asociado
- Se escogen los $k$ vectores propios con mayor valor propio de forma de dejar una matriz de tamaño $d \times k$ que llamaremos $W$
- Se utiliza esta matriz $W$ para transformar nuestros datos de $n \times d$ a $n \times k$.