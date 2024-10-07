# Métodos algebraicos

Estos métodos emplean herramientas algebraicas para obtener un comportamiento deseado en el sistema en lazo cerrado. La base fundamental de estos métodos es modificar la función de transferencia del sistema en lazo cerrado de acuerdo con la respuesta deseada. Existen dos enfoques principales: **igualación de modelo** e **igualación de coeficientes**.

![Diagrama de bloques de un sistema de control discreto](https://github.com/user-attachments/assets/1cffeb00-64ad-406d-90fa-b0cc48ba9d35)

**Figura 1. Diagrama de bloques de un sistema de control discreto**

---

## 1. Igualación de modelo

Si se conoce la función de transferencia en lazo abierto \( G(z) \), y además se sabe la respuesta deseada, representada por la función de transferencia en lazo cerrado \( Go(z) \), entonces es posible determinar la función de transferencia del controlador \( C(z) \), que garantiza dicho comportamiento.

Si \( G(z) \) tiene polos fuera del círculo unitario o varios polos en \( z = -1 \), no se puede implementar una retroalimentación unitaria, ya que los controladores podrían ser **no implementables**.

### Consideraciones de implementación

- Los compensadores deben ser **causales**.
- El modelo objetivo debe ser **estable**.
- No deben resultar cancelaciones del tipo \( polo – zero \), es decir, \( r ≤ ro \).
- Los ceros (fase no mínima) de la planta serán retenidos en lazo cerrado.

---

## 2. Igualación de coeficientes

Si se conoce \( G(z) \) y la ubicación de los polos deseada, es posible expresar la respuesta en un **polinomio característico** y, a partir de allí, calcular la función de transferencia del controlador \( C(z) \) que asegura el comportamiento deseado.

Para ubicar los polos del sistema en lazo cerrado, se debe diseñar un controlador proporcional.

💡 **Ejemplo**:

Polos deseados:

$$ P_1 = 0.91 + j0.23 $$  
$$ P_2 = 0.91 - j0.23 $$

El polinomio característico deseado en lazo cerrado es:

$$ (z - 0.91 + j0.23)(z - 0.91 - j0.23) = z^2 - 1.82z + 0.881 $$

### 2.1. Consideraciones

Para calcular la función de transferencia en lazo cerrado con un controlador, se sabe que:

$$ G(z) = \frac{N(z)}{D(z)} $$

y

$$ C(z) = \frac{B(z)}{A(z)} $$

La función de transferencia en lazo cerrado es:

$$ Go(z) = \frac{G(z)C(z)}{1 + G(z)C(z)} = \frac{B(z)N(z)}{A(z)D(z) + B(z)N(z)} $$

**Dónde**:

- **\( G(z) \)**: Función de transferencia de la planta en el dominio Z.
- **\( C(z) \)**: Función de transferencia del controlador.
- **\( Go(z) \)**: Función de transferencia en lazo cerrado.

La multiplicación de \( A(z) \) y \( D(z) \) incrementa el orden del sistema en lazo cerrado. Además, la multiplicación de \( B(z) \) y \( N(z) \) implica que las funciones de la planta y del controlador deben ser propias.

La igualación se realiza en el **polinomio característico**, lo que significa que no se puede controlar la ubicación de los ceros del sistema. Finalmente, el orden de \( C(z) \) debe ser un grado menor que el de la planta en lazo abierto.

---

### 2.2. Realizando la igualación de coeficientes

El polinomio característico deseado sería:

$$ (z - 0.91 + j0.23)(z - 0.91 - j0.23)(z - 0.91) = z^3 - 2.73z^2 + 2.537z - 0.8017 $$

Para igualar correctamente, se necesita otro término en el polinomio \( B(z) \) para que haya el mismo número de ecuaciones que términos.

Al igualar:

$$ z^3 - 2.73z^2 + 2.537z - 0.8017 = A_1z^3 + (A_0 - 1.819A_1)z^2 + (0.8187A_1 - 1.819A_0)z + 0.8187A_0 + 0.0043B_0 $$

**Resultado**:

No se satisfacen todas las ecuaciones.

| \( A_1 = 1 \) |                  |
|---------------|------------------|
| \( A_0 - 1.819A_1 = -2.73 \)  \( A_0 = -2.73 \) | \( A_0 = -0.911 \) |
| \( 0.8187A_1 - 1.819A_0 = 2.537 \) |              |
| \( 0.8187A_0 + 0.0043B_0 = 0.8017 \) |            |

**Tabla 1. Ecuaciones resultantes**

---


Notamos que 
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
