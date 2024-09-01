# Clase #1 - Introducción al control digital
Existen señales analógicas y señales digitales, se debe tener en cuenta que se cuenta con señales continuas que pueden tomar cualquier valor en el dominio del tiempo sin dejar de lado que tienen dos posibles valores o estados.

![image](https://github.com/user-attachments/assets/cf1ffdd2-b683-4207-91e0-7b33be5e9daf)

Figura 1. Señal analógica


## 1. Definiciones

>🔑 *MUESTREO:* Da la opción de medir valores de voltaje cada cierto tiempo, se mide como el número de veces que se logra en 1 segundo por lo tanto las unidades son en HZ, más, sin embargo, el tiempo de muestreo se reparte con la frecuencia de muestreo. Se tiene presente que entre más alta sea la tasa de muestreo, más información se está procesando y si la tasa es muy baja se puede perder bastante información. El muestreo puede ser periódico (único) de tasa múltiple o aleatoria.

>🔑 *CUANTIZACIÓN:* La señal análoga se convierte en una serie de valores que corresponden a cada una de las medidas tomadas en el muestreo.

![image](https://github.com/user-attachments/assets/c941b183-82ed-4a82-a418-4850f445ac36)

Figura 2. Proceso de Cuantificación.

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

Tabla 1. Tabla de valores posbles

## 3. CONVERSOR DIGITAL / ANALÓGICO: 
Es un dispositivo que genera correspondencia uno a uno entre valores digitales y valores analógicos. Además, se tiene en cuenta para el rengo completo de la entrada digital, existen 2 valores analógicos correspondientes, diferentes incluyendo el cero (0).

![image](https://github.com/user-attachments/assets/d4fde933-3700-4cc9-9de4-14cd9ccbffd0)

Figura 5. Diagrama de bloques de un sistema de adquisición y procesamiento de datos.

## 4. RESOLUCIÓN DAC: 
La resolución depende de los bits de representación al igual que en los ADC, sin embargo, se entiende en voltaje o porcentaje del Fs (FONDO DE ESCALA) para Fs = 15v.

![image](https://github.com/user-attachments/assets/9e483466-f0f3-44de-b592-2adaeac2c5f6)

Tabla 2. Tabla de valores posibles para una resolución de 4 bits.

Se originan valores de tipo binario a cada uno de los valores de la cuantización, los valores a uso los define el diseñador de acuerdo con el tipo de información obtenida en la cuantización, se tiene presente y sin dejar de lado que para los métodos de conversión se tienen 2 métodos de gran uso como los resistores ponderados de fácil configuración, pero no muy exactos y por otro lado se cuenta con la red en escalera R – 2R el cual es un poco más complicado de configurar, pero es más exacto.

![image](https://github.com/user-attachments/assets/41bb0648-6ffd-4e92-ad71-811ceef336f0)

Tabla 3. Resolución DAC

![image](https://github.com/user-attachments/assets/fd2710ab-fe12-46e2-b659-a26fdd150360)

Tabla 3. Resistencia ponderada

## 5. Ecuaciones

Los resistores ponderados en un DAC son fáciles de configurar y económicos, pero tienen baja exactitud debido a la dependencia de la precisión de las re sistencias, lo que limita su uso en aplicaciones que requieren alta precisión.

$$E_0 = -R_f (\frac{V_a}{R} + \frac{V_b}{2R} + \frac{V_c}{4R}) $$

$$E_0 = -R_f (\frac{E_r}{R} + \frac{0}{2R} + \frac{0}{4R}) $$

$$E_0 = \frac{R_f*E_r}{R} $$

La red en escalera R-2R es un tipo de DAC más complicada de configurar que los resistores ponderados, pero ofrece mayor exactitud. Utiliza solo dos valores de resistencia (R y 2R), lo que mejora la precisi´on y la consistencia, reduciendo la dependencia de las tolerancias de los componentes.

$$V_0 = -(\frac{R_f}{R}) (\frac{V_0}{16} + \frac{V_1}{8} + \frac{V_2}{4} + \frac{V_3}{2}) $$

$$V_0 = -(\frac{R_f*V_ref}{R}) (\frac{B_0}{16} + \frac{B_1}{8} + \frac{B_2}{4} + \frac{B_3}{2}) $$

## 9. Ejercicios
📚 Ejercicio 1:
* Señal analógica: [0, 10] V
* Bits representación: 3 bits
* $$2^3 = 8 $$ posibles símbolos
* Rango analógico: $$ 10 - 0 = 10V $$
* Representación: $$ \frac{4}{8} * 10V = 5𝑉 $$
Realmente son: $$2^3 - 1 = 7 $$ posibles símbolos porque se gasta un símbolo representando el 0V.

📚 Ejercicio 2:
* Señal analógica: [0, 5] V
* Bits representación: 4 bits
* $$2^4 = 16 $$ posibles símbolos
* Rango analógico: $$ 5 - 0 = 5V $$
* Representación: $$ \frac{10}{16} * 5V = 3.125𝑉 $$
Realmente son: $$2^4 - 1 = 15 $$ posibles símbolos porque se gasta un símbolo representando el 0V.

## 10. Conclusiones
En esta primera clase de Introducción al Control Digital, se han abordado los conceptos fundamentales que distinguen las señales analógicas de las digitales, así como los procesos clave para convertir una señal continua en una señal digital útil para sistemas de control. Específicamente, se ha aprendido sobre el muestreo y la cuantización, dos procesos críticos en la digitalización de señales, que permiten transformar una señal analógica continua en una secuencia de valores discretos que pueden ser procesados por un controlador digital.

Se discutieron los tiempos involucrados en el muestreo, como el tiempo de adquisición (Ta), tiempo de apertura (Tp), y tiempo de establecimiento (Ts), que son fundamentales para entender cómo un sistema de adquisición de datos captura y procesa la información de una señal analógica.

Asimismo, se exploró la conversión entre señales digitales y analógicas, entendiendo la importancia de la resolución en un Convertidor Digital-Analógico (DAC) y cómo esta afecta la precisión y exactitud de la señal convertida. Se destacaron dos métodos para implementar DACs: los resistores ponderados y la red en escalera R-2R, cada uno con sus ventajas y limitaciones en términos de configuración y precisión.

## 11. Referencias
[1] "Sistemas causales y no causales," Blog ESPOL, 2016. [Enlace: http://blog.espol.edu.ec/telg1001/sistemas-causales-y-no-causales/]

[2] J. Pérez, Sistemas Causales y No Causales. Digitalia Publishing, 2022. [Enlace: https://www.digitaliapublishing.com/a/130029]

[3] "Métodos Iterativos," Scribd, 2018. [Enlace: https://es.scribd.com/document/390484476/Metodos-Iterativos]
