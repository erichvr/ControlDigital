# Clase #1 - Introducción al control digital
Existen señales analógicas y señales digitales, se debe tener en cuenta que se cuenta con señales continuas que pueden tomar cualquier valor en el dominio del tiempo sin dejar de lado que tienen dos posibles valores o estados.

![image](https://github.com/user-attachments/assets/cf1ffdd2-b683-4207-91e0-7b33be5e9daf)

Figura 1. Señal analógica


## 1. Definiciones

>🔑 *MUESTREO:* Da la opción de medir valores de voltaje cada cierto tiempo, se mide como el número de veces que se logra en 1 segundo por lo tanto las unidades son en HZ, más, sin embargo, el tiempo de muestreo se reparte con la frecuencia de muestreo. Se tiene presente que entre más alta sea la tasa de muestreo, más información se está procesando y si la tasa es muy baja se puede perder bastante información. El muestreo puede ser periódico (único) de tasa múltiple o aleatoria.

>🔑 *CUANTIZACIÓN:* La señal análoga se convierte en una serie de valores que corresponden a cada una de las medidas tomadas en el muestreo.

![image](https://github.com/user-attachments/assets/d5f56f24-9d13-41c4-a994-476908ec6e7c)

Figura 2. Sistema lazo cerrado

## 2. TIEMPO DE MUESTREADOR – RETENEDOR
### 2.1. Ta (TIEMPO DE ADQUISICIÓN): 
Es el tiempo que transcurre desde que se da la orden de muestreo hasta que se retiene dentro de cierto margen de tolerancia.
### 2.2. Tp (TIEMPO DE APERTURA):
Es el tiempo que transcurre desde que se inicia la retención hasta que abre el muestreador.
### 2.3. Ts (TIEMPO DE ESTABLECIMIENTO): 
El movimiento del interruptor puede crear una capacitancia parásita, la cual a su vez puede producir un transitorio.

![image](https://github.com/user-attachments/assets/047a26d5-eea5-4dd9-a178-79249492b4af)

![image](https://github.com/user-attachments/assets/5587ffa2-b009-450a-84ff-34822580d910)


## 4. Ejemplos
💡Ejemplo:
• Señal analógica: [0,3] V
• Bits representación: 2 bits
• 22 = 4 posibles símbolos
• Rango analógico: 3-0 = 3V
• Representación: 3/4 = 0,75𝑉


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
