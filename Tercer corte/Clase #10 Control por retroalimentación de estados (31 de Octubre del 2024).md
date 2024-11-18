# Control por retroalimentación de estados

La retroalimentación de estados es una técnica avanzada en control multivariable que permite modificar el comportamiento de un sistema mediante la realimentación de sus variables de estado. Se enfoca en dos conceptos clave: controlabilidad y observabilidad, esenciales para determinar si un sistema es controlable desde cualquier estado inicial y si se pueden estimar sus variables internas a partir de sus salidas.

Se tiene una forma general de las matrices en el espacio de estados, tal como:

$$X(k + 1) = **A**X(k) + **B**u(k)$$
$$Y(k) = **C**X(k) + **D**u(k)$$


## 1. Controlabilidad
De la que **A,B,C** y **D** son matrices de coeficientes, teniendo esto en cuenta es posible construir la matriz de controlabilidad

$$U = [BㅤABㅤAABㅤAAABㅤ...ㅤAA...B]$$

Para saber sí un sistema es controlable, se debe hallar su determinante y este valor debe ser diferente de 0

💡**Ejemplo 1:**

| $X_1(k+1)$ | ‎‎ㅤ|‎ㅤ 3ㅤ1ㅤ|| $X_1(k)$ |ㅤ| 1 |

| $X_2(k+2)$ | = |‎ㅤ 2ㅤ1ㅤ|| $X_2(k)$ | + | 1 | $U(k)$


ㅤㅤ ㅤㅤㅤㅤㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤ4ㅤ2ㅤ|| $X_2(k)$ |

$U = [BㅤAB]$

$B =$ ‎‎|‎ㅤ1ㅤ|

ㅤ ㅤ |‎ㅤ1ㅤ|


$AB =$ ‎‎|‎ㅤ3ㅤ1ㅤ||‎ㅤ1ㅤ| = |‎ㅤ4ㅤ|

ㅤ ㅤ |‎ㅤ2ㅤ1ㅤ||‎ㅤ1ㅤ| = |ㅤ3ㅤ|


$U =$ ‎‎|‎ㅤ1ㅤ4ㅤ|

ㅤ ㅤ|‎ㅤ1ㅤ3ㅤ|

Cálculo del determinante:
(Para este ejemplo, A,B,C y D seran coeficientes)

$U =$ ‎‎|‎ㅤAㅤBㅤ|ㅤㅤAD - CB $≠ 0$

ㅤ ㅤ|‎ㅤCㅤDㅤ|

$U =$ ‎‎|‎ㅤ1ㅤ4ㅤ| ㅤㅤ3-4 ≠ 0 **El sistema es controlable**

ㅤ ㅤ|‎ㅤ1ㅤ3ㅤ|

## 2. Observabilidad

Partiendo del mismo modelo
$$X(k + 1) = **A**X(k) + **B**u(k)$$
$$Y(k) = **C**X(k) + **D**u(k)$$

Se obtiene la matriz de observabilidad

$V =$ ‎‎|‎ㅤㅤCㅤ ㅤ|

ㅤ ㅤ|‎ㅤ ㅤCAㅤ|

ㅤ ㅤ|‎ㅤㅤCAAㅤ|

ㅤ ㅤ|‎ㅤㅤ...ㅤㅤ|

ㅤ ㅤ|‎ㅤCAA...ㅤ|

Para saber sí un sistema es controlable, se debe hallar su determinante y este valor debe ser diferente de 0

💡**Ejemplo 2:**

| $X_1(k+1)$ | ‎‎ㅤ|‎ㅤ 3ㅤ1ㅤ|| $X_1(k)$ |ㅤ| 1 |

| $X_2(k+2)$ | = |‎ㅤ 2ㅤ1ㅤ|| $X_2(k)$ | + | 1 | $U(k)$



ㅤㅤ ㅤㅤㅤㅤㅤㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤ4ㅤ2ㅤ|| $X_2(k)$ |

$V =$ ‎‎|‎ㅤㅤCㅤ ㅤ|

ㅤ ㅤ|‎ㅤ ㅤCAㅤ|


$C =$ ‎‎|‎ㅤ4ㅤ2ㅤ|

$CA =$ ‎‎|‎ㅤ4ㅤ2ㅤ||‎ㅤ3ㅤ1ㅤ| = |‎ㅤ16ㅤ6ㅤ| 

ㅤㅤㅤ ㅤㅤㅤ ㅤ|‎ㅤ2ㅤ1ㅤ|


$V =$ ‎‎|‎ㅤ4ㅤ2ㅤ|

ㅤ ㅤ|‎ㅤ16ㅤ6ㅤ|

Determinante: $4x6 - 2x16 = -8$ **Es observable**

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
[1] "Controladores por retroalimentación de estados" Curso Control Digital
