# Solución del parcial del segundo corte

Esta clase fue destinada para socializar los resultados del parcial del segundo corte y mostrar la solución correcta del ejercicio propuesto sobre métodos algebráicos. A cada grupo se le propuso un método diferente, por lo que a continuación se mostrará el ejercició que nos correspondió.

Primeramente, se presentarán unas generalidades que serán de ayuda para identificar cada parte del ejercicio

- Función de transferencia lazo abierto:    $G(z) = \frac{N(z)}{D(z)}$
- Controlador del sistema:                  $C(z) = \frac{B(z)}{A(z)}$
- Función de transferencia lazo cerrado:    $G_o(z) = \frac{N_o(z)}{D_o(z)}$
- Función con retroalimentación unitaria en lazo cerrado:
  $$G_o(z) = \frac{C(z)G(z)}{1 + C(z)G(z)}$$
  $$G_o(z) = \frac{\frac{B(z)}{A(z)} \frac{N(z)}{D(z)}{1 + \frac{B(z)}{A(z)} \frac{N(z)}{D(z)}$$

## Obtención del sistema discreto en lazo cerrado
Se tiene la siguiente planta en tiempo discreto. Teniendo en cuenta los polos dados para la función en lazo cerrado, se debe obtener el controlador por el método de igualación de coeficientes:

$$ G(z) = \frac{1.61 \cdot 10^{-7} z^2 + 6.25 \cdot 10^{-7} z + 1.53 \cdot 10^{-7}}{z^3 - 2.87z^2 + 2.75z - 0.88} $$

A partir de los siguientes polos, se debe hallar el polinomio característico del denominador de la función en lazo cerrado. El cual, será de ayuda para obtener el controlador de la planta.

$$ P_1 = -100$$
$$ P_2 = -100$$
$$ P_3 = -100$$
$$ P_4 = -2 + 2.73j$$
$$ P_5 = -2 - 2.73j$$

Entonces, lo primero que se debe hacer es obtener el denominador de la función en lazo cerrado que obtiene esos polos.

$$ D_o(z) = (z+100)(z+100)(z+100)(z + 2 - 2.73j)(z + 2 + 2.73j) $$

$$ D_o(z) = (z^3 + 300z^2 + 3*10^4z + 10^6)(z^2 + 4z + \frac{114529}{10^4}) $$

$$ D_o(z) = (z^5 + 304z^4 + \frac{312114529}{10^4}z^3 + \frac{112343587}{100}z^2 + 4343587z + 11452900) $$

>🔑 *Clave:* Existen herramientas como *_MATLAB_* o calculadoras como *_CALCES_* que facilitan el proceso de multiplicación y simplicación, puede ser útil para ahorrar tiempo.

A continuación, se desea obtener el controlador que permite que la función $G(z)$ logre la respuesta requerida.
Por lo tanto, se plantea un controlador con las siguientes propiedades:
- Orden $n-1$ inferior al grado mayor del denominador (Esto se verifica sumando el mayor grado de $G(z)$ y $C(z)$, ya que tiene que tener el mismo grado que el denominador caracteríztico $D_o(z)$ ).
- Bipropio, esto indica que tanto el numerador como el denominador sean del mismo grado.

Identificando que el sistema $G(z)$ tiene en su denominador el grado $3$, su controlador será de grado $2$ y resultando así:

$$ C(z) = \frac {A_0 + A_1z + A_2z^2}{B_0 + B_1z + B_2z^2} $$






## 2. Definiciones
Utilice el símbolo '>' para crear bloques de texto. En la presente plantilla estas cajas están reservadas para resaltar las definiciones, las cuales deben ser breves, y la palabra o frase que se está definiendo debe estar en letra itálica. El inicio del bloque de texto debe realizarse con el emoji 🔑 .
>🔑 *Definición:* descripción precisa y clara del significado de una palabra, término, concepto o fenómeno. Es una explicación que establece los límites y el alcance de aquello que se está definiendo, aclarando su naturaleza, características esenciales y, en algunos casos, su relación con otros conceptos.

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
