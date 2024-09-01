# TRANSFORMADA Z DE ADELANTOS Y ATRASOS
La transformada Z es una herramienta fundamental en el análisis y diseño de sistemas de control digital. Permite transformar ecuaciones en diferencias, que describen el comportamiento dinámico de un sistema en términos de sus entradas y salidas discretas, en el dominio Z. Esto facilita la resolución de dichas ecuaciones y la obtención de funciones de transferencia discretas, esenciales para analizar y entender el comportamiento de los sistemas en tiempo discreto. Además, la transformada Z es crucial en el estudio de adelantos y atrasos en las señales, lo que tiene aplicaciones directas en la mejora de la estabilidad y el rendimiento de sistemas de control digital.

## 1. FUNCIÓN EN TÉRMINOS DE MUESTRAS
$$ F(t) = F(kT) $$

>🔑 *T: Periodo de muestreo*

![image](https://github.com/user-attachments/assets/447ff947-f470-469c-8533-a486c6438ac1)

>Figura 1. Función en tiempo continuo y discreto

## 2. REPRESENTACIÓN MATEMÁTICA DE LOS SISTEMAS
### 2.1 Ecuación en diferencias

$$ B_n*U(k) + B_(n-1) * U_(k-1) + ... + B_o * U(k-n) = y(k)+a_(n-1)*y(k-1)+...+aoy_(k-n)$$

*	Donde “U” es la entrada y “Y” es la salida.
*	El sistema se representa a través de una combinación lineal.
*	Las ecuaciones en diferencias representan el comportamiento dinámico de un sistema en términos de sus señales de entrada y de salida.

### 2.2 CARACTERISTICAS ECUACIONES EN DIFERENCIAS 

Las ecuaciones en diferencias pueden ser homogéneas, lineales, invariantes en el tiempo.

* Lineal, invariante en el tiempo, no homogénea.

$$ y(k+2) + 0.8y(k+1) + 0.7y(k)U(k) = 0$$

* Lineal, variante en el tiempo, homogénea.

$$ y(k+4) + sen(0.4k)y(k+1) + 0.3y(k) = 0$$

* No lineal, invariante en el tiempo, homogénea.

$$ y(k+1) = -0.1*y(k)^2$$

Existen 2 soluciones para las ecuaciones en diferencias, estas son:

o	Métodos iterativos

o	Transformada Z

## 3. Transformada Z
### 3.1. Ecuación en diferencias

$$b_nu(k) + b_(n-1) u(k-1) +...+ b_0 u(k-n) = y(k) + a_(n-1)y(k-1) +...+ a_0 y(k-n)$$

* La solución numérica da los valores de “y” para un numero finito de muestras, sin embargo, no permite identificar características generales del funcionamiento del sistema.
* La solución por transformada Z permite obtener una expresión matemática para dar la solución de la ecuación en cualquier muestra.

![image](https://github.com/user-attachments/assets/04fadd6c-a139-4c3d-bc34-db2712121f8f)

>Figura 2. Transformada de Laplace y transformada Z

## 4. Relación Z y L

![image](https://github.com/user-attachments/assets/5b080757-e095-4e76-9c60-b32483e465eb)

>Figura 3. Demostración matemática del muestreo de una señal continua con la señal impulso

### 4.1 SOLUCIÓN DE ECUACIONES EN DIFERENCIAS POR TRANSFORMADA Z
Es un procedimiento similar a la solución de ecuaciones diferenciales en donde se le aplica si o si la transformada Z a la ecuación sin dejar de lado que se despeja la variable desconocida o la salida del sistema para así aplicar la transformada Z inversa de $$Z^(-1)$$.

### 4.2 TRANSFORMADA Z IMPORTANTES EN CONTROL
En las ecuaciones en diferencias tenemos términos del tipo:

$$𝑓(𝑘+𝑛) 𝑜 𝑓(𝑘-𝑛)$$

* Donde n es el número de muestra que se desplaza la función.
* Entonces la transformada Z de este tipo de términos son muy importantes en el área de control.

### 4.2.1 Atraso
![image](https://github.com/user-attachments/assets/7a5001b5-ada4-4173-8e5c-e56a27ac910f)


### 4.2.2 Adelanto

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
