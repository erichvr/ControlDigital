# Clase #1 - Introducción al control digital
Existen señales analógicas y señales digitales, se debe tener en cuenta que se cuenta con señales continuas que pueden tomar cualquier valor en el dominio del tiempo sin dejar de lado que tienen dos posibles valores o estados.

![image](https://github.com/user-attachments/assets/cf1ffdd2-b683-4207-91e0-7b33be5e9daf)

Figura 1. Señal analógica


## 1. Definiciones

>🔑 *MUESTREO:* Da la opción de medir valores de voltaje cada cierto tiempo, se mide como el número de veces que se logra en 1 segundo por lo tanto las unidades son en HZ, más, sin embargo, el tiempo de muestreo se reparte con la frecuencia de muestreo. Se tiene presente que entre más alta sea la tasa de muestreo, más información se está procesando y si la tasa es muy baja se puede perder bastante información. El muestreo puede ser periódico (único) de tasa múltiple o aleatoria.

>🔑 *CUANTIZACIÓN:* La señal análoga se convierte en una serie de valores que corresponden a cada una de las medidas tomadas en el muestreo.

![image](https://github.com/user-attachments/assets/d5f56f24-9d13-41c4-a994-476908ec6e7c)

Figura 2. Sistema lazo cerrado

![image](https://github.com/user-attachments/assets/8d83e862-6bec-4aba-bedb-6e89006b7bd8)

Figura 3. Controlador Digital

## 2. TIEMPO DE MUESTREADOR – RETENEDOR
### 2.1. Ta (TIEMPO DE ADQUISICIÓN): 
Es el tiempo que transcurre desde que se da la orden de muestreo hasta que se retiene dentro de cierto margen de tolerancia.
### 2.2. Tp (TIEMPO DE APERTURA):
Es el tiempo que transcurre desde que se inicia la retención hasta que abre el muestreador.
### 2.3. Ts (TIEMPO DE ESTABLECIMIENTO): 
El movimiento del interruptor puede crear una capacitancia parásita, la cual a su vez puede producir un transitorio.

![image](https://github.com/user-attachments/assets/047a26d5-eea5-4dd9-a178-79249492b4af)

![image](https://github.com/user-attachments/assets/5587ffa2-b009-450a-84ff-34822580d910)

Figura 4. Tiempo de muestreador


💡Ejemplo:
* Señal analógica: [0,3] V
* Bits representación: 2 bits
* 2*2 = 4 posibles símbolos
* Rango analógico: 3-0 = 3V
* Representación: 3/4 = 0,75𝑉

Realmente son 2𝑟 − 1 posibles símbolos porque se gasta un símbolo representando el 0V
![image](https://github.com/user-attachments/assets/04d20d00-9ed8-4ee1-ae2c-6fabb033dbdd)

Figura 5. Tabla de valores posbles

## 3. CONVERSOR DIGITAL / ANALÓGICO: 
Es un dispositivo que genera correspondencia uno a uno entre valores digitales y valores analógicos. Además, se tiene en cuenta para el rengo completo de la entrada digital, existen 2 valores analógicos correspondientes, diferentes incluyendo el cero (0).

![image](https://github.com/user-attachments/assets/d4fde933-3700-4cc9-9de4-14cd9ccbffd0)

Figura 6. Diagrama de bloques de un sistema de adquisición y procesamiento de datos.

## 4. RESOLUCIÓN DAC: 
La resolución depende de los bits de representación al igual que en los ADC, sin embargo, se entiende en voltaje o porcentaje del Fs (FONDO DE ESCALA) para Fs = 15v.

![image](https://github.com/user-attachments/assets/9e483466-f0f3-44de-b592-2adaeac2c5f6)

Figura 7. Tabla de valores posibles para una resolución de 4 bits.

Se originan valores de tipo binario a cada uno de los valores de la cuantización, los valores a uso los define el diseñador de acuerdo con el tipo de información obtenida en la cuantización, se tiene presente y sin dejar de lado que para los métodos de conversión se tienen 2 métodos de gran uso como los resistores ponderados de fácil configuración, pero no muy exactos y por otro lado se cuenta con la red en escalera R – 2R el cual es un poco más complicado de configurar, pero es más exacto.

![image](https://github.com/user-attachments/assets/c941b183-82ed-4a82-a418-4850f445ac36)

Figura 8. Tabla de valores posibles para una resolución de 4 bits.

## 5. Ecuaciones

Los resistores ponderados en un DAC son fáciles de configurar y económicos, pero tienen baja exactitud debido a la dependencia de la precisión de las re sistencias, lo que limita su uso en aplicaciones que requieren alta precisión.

$$E_0$$

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
