# Sistemas inestables - Introducción al espacio de estados - Algunas operaciones con matrices

Para esta clase, se dividide el temario en 2 partes:
- **Identificación de la función $G_m(s)$ y sintonización del controlador.** Dónde mediante el método de procesos integrantes, se obtiene la función de transferencia en lazo abierto de un sistema que normalmente tiende a crecer indefinidamente. Esto ayuda a reducir esa tendencia a un valor finíto.
- **Algunas operaciones en el Espacio de estados** En la conversión de función de transferencia a espacio de estados, existen diversas operaciones que permiten obtener caracteristicas y relacionar variables. Tales como forma controlable, observable, etc.
  
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

Es posible usar la representación de estados como método para analizar y controlar un sistema, esto con el objetivo de relacionar el comportamiento de sistemas con multiples entradas y salidas. A continuación se presentará en qué consiste y como formar estas matrices.

Se tiene una función de transferencia discreta como:

$$G(z) = \frac{b_0z^n + b_1z^{n-1} +...+ b_{n-1}z + b_n}{z^n + a_1z^{n-1} +...+ a_{n-1}z + a_n}$$

A partir de sus coeficientes, se puede expresar en una matriz cuadrada del tamaño del grado mayor de su polinomio

El tamaño de la matriz debe ser cantidad de variables y cantidad de coeficientes. Es decir, sólo puede ser 2x2 o superior para considerarse espacio, una matriz cuadrada.
### 2.1 **Forma canónica Controlable**
💡**Ejemplo 1:** 
Se tiene la función:

$$\frac{Y(z)}{X(z)} = \frac{Az^3 + Bz^2 + Cz + D}{z^4 + Ez^3 + Fz^2 + Gz + H}$$

| $X_1(k+1)$ | ‎‎ㅤ|‎ㅤ 0ㅤ0ㅤ0ㅤ1ㅤ|| $X_1(k)$ |ㅤ| 0 |

| $X_2(k+2)$ | = |‎ㅤ 0ㅤ0ㅤ0ㅤ1ㅤ|| $X_2(k)$ | + | 0 |

| $X_3(k+3)$ | = |‎ㅤ 0ㅤ0ㅤ0ㅤ1ㅤ|| $X_3(k)$ | + | 0 | $u(k)$ 

| $X_4(k+4)$ | ‎ㅤ|ㅤ-H -Gㅤ-F -Eㅤ|| $X_4(k)$ |ㅤ| 1 |


ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤ ㅤㅤㅤ ㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤDㅤCㅤBㅤAㅤ|| $X_2(k)$ |

ㅤ ㅤㅤㅤㅤㅤㅤㅤㅤㅤ ㅤㅤ ㅤ| $X_3(k)$ |

ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤㅤ ㅤ ㅤㅤ| $X_4(k)$ |

### 2.2 **Forma canónica Observable**

💡**Ejemplo 2:** 
Se tiene la función:

$$\frac{Y(z)}{X(z)} = \frac{Az^3 + Bz^2 + Cz + D}{z^4 + Ez^3 + Fz^2 + Gz + H}$$

| $X_1(k+1)$ | ‎‎ㅤ|‎ㅤ 0ㅤ0ㅤ0ㅤ-Hㅤ|| $X_1(k)$ |ㅤ| D |

| $X_2(k+2)$ | = |‎ㅤ 1ㅤ0ㅤ0ㅤ-Gㅤ|| $X_2(k)$ | + | C |

| $X_3(k+3)$ | = |‎ㅤ 0ㅤ1ㅤ0ㅤ-Fㅤ|| $X_3(k)$ | + | B | $u(k)$ 

| $X_4(k+4)$ | ‎ㅤ|ㅤ 0ㅤ0ㅤ1ㅤ-Eㅤ|| $X_4(k)$ |ㅤ| A |


ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤ ㅤㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤ 0ㅤ0ㅤ0ㅤ1 ㅤ|| $X_2(k)$ |

ㅤ ㅤㅤㅤㅤㅤㅤㅤㅤㅤ ㅤ| $X_3(k)$ |

ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤㅤ ㅤ| $X_4(k)$ |

### 2.3 **Forma canónica diagonal**

💡**Ejemplo 3:** 
Se tienen los polos de la función:

$$\frac{Y(z)}{X(z)} = \frac{Az^3 + Bz^2 + Cz + D}{(z+E)(z+F)(z+G)(z+H) = \frac{k_1}{(z+E)} + \frac{k_2}{(z+F)} + \frac{k_3}{(z+G)} + \frac{k_4}{(z+H)} +}$$

$$P_1 = -E;P_2 = -F;P_3 = -G;P_4 = -H;$$

| $X_1(k+1)$ | ‎‎ㅤ|‎ㅤ -Eㅤ0ㅤ0ㅤ0ㅤ|| $X_1(k)$ |ㅤ| 1 |

| $X_2(k+2)$ | = |‎ㅤ 0ㅤ-Fㅤ0ㅤ0ㅤ|| $X_2(k)$ | + | 1 |

| $X_3(k+3)$ | = |‎ㅤ 0ㅤ0ㅤ-Gㅤ0ㅤ|| $X_3(k)$ | + | 1 | $u(k)$ 

| $X_4(k+4)$ | ‎ㅤ|ㅤ 0ㅤ0ㅤ0ㅤ-Hㅤ|| $X_4(k)$ |ㅤ| 1 |



ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤ ㅤㅤㅤ ㅤ| $X_1(k)$ |

$Y(k) =$ |ㅤ $k_1ㅤk_2ㅤk_3ㅤk_4$ ㅤ|| $X_2(k)$ |

ㅤ ㅤㅤㅤㅤㅤㅤㅤㅤㅤ ㅤㅤ ㅤ| $X_3(k)$ |

ㅤㅤ ㅤㅤㅤㅤㅤㅤㅤㅤㅤ ㅤ ㅤ| $X_4(k)$ |


## 10. Conclusiones
A partir de esta información, es posible empezar a diseñar un sistema de control. Muchos de estos métodos son algebráicos y requieren de cierta destreza junto con claridad para resolverlos. Contando con un paso a paso, es posible resolver muchos problemas.

El método de caracterización de una exponencia fue útil para obtener la curva de reacción de la planta trabajada en el proyecto final.

## 11. Referencias

[1] "Caracterización de sistemas integrantes" Curso Control Digital

[2] "Operaciones con espacio de estados" Curso Control Digital

[3] "Formas Canonicas de un Espacio de Estado" The Kelvin Talk Show Youtube https://www.youtube.com/watch?v=TuXAeY2V9ZA
