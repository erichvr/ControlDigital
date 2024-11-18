# Sistemas inestables - Introducción al espacio de estados - Algunas operaciones con matrices

Para esta clase, se dividide el temario en 2 partes:
- **Identificación de la función $G_m(s)$ y sintonización del controlador.** Dónde mediante el método de procesos integrantes, se obtiene la función de transferencia en lazo abierto de un sistema que normalmente tiende a crecer indefinidamente. Esto ayuda a reducir esa tendencia a un valor finíto.
- a
  
## 1. **Identificación de la función $G_m(s)$ y sintonización del controlador.**
### 1.1 **Identificación de la función $G_m(s)$.**
Para lograr caracterizar una planta con comportamiento exponencial, se propone un método que permite obtener su comportamiento en lazo abierto con respecto a una entrada dada. Se conoce como **Caracterización de un proceso integrante**.

Entonces, a partir de la siguiente gráfica se determinan unos valores necesarios para armar el modelo del sistema:

![Respuesta dinámica de un proceso integrante](https://github.com/user-attachments/assets/4bb5d28f-c472-4d36-b406-f9a03319c10f)

Figura 1. Respuesta dinámica de un proceso integrante

Donde:
  - $O_1$ Es el estado bajo del sistema, muchas veces 0.
  - $O_2$ Es la magnitud de la señal en el tiempo $T_3$
    
  - $I_1$ Es el estado bajo del escalón, muchas veces 0.
  - $I_2$ Es el estado alto del escalón.
    
  - $T_1$ Es el tiempo donde el escalón cambia de estado bajo a alto.
  - $T_2$ Es el tiempo donde se cruza una línea continua del estado de reposo y una linea diagonal de la pendiente de la señal.
  - $T_3$ Es el tiempo donde la amplitud de la señal del sitema y la señal de entrada es el mismo.

Con estos valores, es posible calcular la ganancia estática del sistema o ganancia de integración $K_m$, que no es más que la pendiente de la curva.

$$K_m = \frac{O_2-O_1}{(I_2-I_1)(T_3-T_2)}$$

También, se puede obtener el tiempo muerto $T_m$

$$T_m = T_2 - T_1$$

Y así, obtener la expresión $G_m(s)$ también conocida como sistema de factor integrante más tiempo muerto.

$$𝐺_m(s) = \frac{K_m · e^{-T_m · s}}{s}$$

A partir de este punto, se puede identificar el controlador desea. El curso propone (Aparte de otros métodos como uso de relés) el uso de un **controlador PI o PID**

### 1.2 **Sintonización del controlador.**

El sistema en lazo cerrado requiere de la obtención de unos parametros de acuerdo al controlador escogido, tales como:
  - $K_c$ Ganancia proporcional.
  - $T_i$ Tiempo integral.
  - $T_d$ Tiempo derivativo.

![Sistema de control retroalimentado](https://github.com/user-attachments/assets/baf0b16a-919f-4fa0-838c-de682697cbb9)
Figura 2. Sistema de control retroalimentado

Estas magnitudes son obtenidas a partir de expresiones propuestas por cada autor y presentadas a continuación

- **Controlador PI**

| Método              | $K_c$                  | $T_i$     |
|---------------------|------------------------|-----------|
| Ziegler & Nichols   | $\frac{0.9}{K_mT_m}$   | $3.33T_m$ |
| Coon                | $\frac{1.0}{K_mT_m}$   | $0$       |
| Aström and Hägglund | $\frac{0.63}{K_mT_m}$  | $3.2T_m$  |
| Hay                 | $\frac{0.42}{K_mT_m}$  | $5.8T_m$  |
| Skogestad           | $\frac{0.404}{K_mT_m}$ | $7T_m$    |

Tabla 1. Sintonía del Controlador Proporcional - Integral

- **Controlador PID**

| Método              | $K_c$                                           | $T_i$      | $T_d$                             |
|---------------------|-------------------------------------------------|------------|-----------------------------------|
| Ford                | $$\frac{1.48}{K_mT_m}$$                           | $2T_m$     | $0.37T_m$                         |
| Coon                | $$\frac{0.4}{K_mT_m}$$                            | $3.2T_m$   | $0.8T_m$                          |
| Aström and Hägglund | $$\frac{0.94}{K_mT_m}$$                           | $2T_m$     | $0.5T_m$                          |
| Leonard             | $$\frac{0.74}{K_mT_m}$$                           | $12.2T_m$  | $0.41T_m$                         |
| Rotach              | $$\frac{1.21}{K_mT_m}$$                           | $1.6T_m$   | $0.48T_m$                         |
| Zou and Brigham     | $\frac{2}{K_m(𝜆 + 0.5T_m}$  $0.5T_m ≤ 𝜆 ≤ 3T_m$ | $2𝜆 + T_m$ | $\frac{𝜆 + 0.25T_m}{2𝜆 + T_m}T_m$ |

Tabla 2. Sintonía del Controlador Proporcional - Integral - Derivativo

## 2. **Algunas operaciones en el Espacio de estados**

Es posible usar la representación de estados como método para analizar y controlar un sistema, a continuación se presentará en qué consiste y como formar estas matrices.

Se tiene una función de transferencia discreta como:

$$G(z) = \frac{b_0z^n + b_1z^{n-1} +...+ b_{n-1}z + b_n}{z^n + a_1z^{n-1} +...+ a_{n-1}z + a_n}$$

## 1. Subtítulos
Agregue todos los subtítulos que considere necesarios para estructurar el contenido de la clase. Es importante que considere jerarquías de los temas para definir el orden de estos subtítulos. Cada subtítulo debe ir numerado como una sección, de la manera en que lo presenta esta plantilla

## 1. Subtítulos
Agregue todos los subtítulos que considere necesarios para estructurar el contenido de la clase. Es importante que considere jerarquías de los temas para definir el orden de estos subtítulos. Cada subtítulo debe ir numerado como una sección, de la manera en que lo presenta esta plantilla

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

[1] "" Curso Control Digital

[2] "" Curso Control Digital

[3] "" Curso Control Digital
