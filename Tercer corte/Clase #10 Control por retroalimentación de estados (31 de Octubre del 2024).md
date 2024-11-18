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


ㅤㅤ ㅤㅤㅤㅤㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤ4ㅤ2ㅤ|| $X_2(k)$ |

$V =$ ‎‎|‎ㅤㅤCㅤ ㅤ|

ㅤ ㅤ|‎ㅤ ㅤCAㅤ|

$C =$ ‎‎|‎ㅤ4ㅤ2ㅤ|

$CA =$ ‎‎|‎ㅤ4ㅤ2ㅤ||‎ㅤ3ㅤ1ㅤ| = |‎ㅤ3ㅤ1ㅤ| 

ㅤㅤㅤㅤㅤㅤ ㅤ|‎ㅤ2ㅤ1ㅤ|ㅤ ㅤ|‎ㅤ2ㅤ1ㅤ|



## 3. Subsecciones
Las subsecciones pueden utilizarse para sub dividir ciertos temas que se tienen en clases, por ejemplo si se está trabajandolos conversores D/A, puede ser necesario subdividir este en circuito de resistencias ponderadas y circuito de escalera R2R. 
### 3.1. Título de subsecciones
Para la creación de estas subsecciones debe utilizar un tamaño de letra más pequeño, por lo tanto utilice la etiqueta '###' 
### 3.2. Numeración de subsecciones
Siga la numeración de la sección seguida de un punto y luego el número de la subsección.

## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
