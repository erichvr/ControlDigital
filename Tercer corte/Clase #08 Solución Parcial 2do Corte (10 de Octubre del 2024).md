# Solución del parcial del segundo corte

Esta clase fue destinada para socializar los resultados del parcial del segundo corte y mostrar la solución correcta del ejercicio propuesto sobre métodos algebráicos. A cada grupo se le propuso un método diferente, por lo que a continuación se mostrará el ejercició que nos correspondió.

Primeramente, se presentarán unas generalidades que serán de ayuda para identificar cada parte del ejercicio

- Función de transferencia lazo abierto:   $$G(z) = \frac{N(z)}{D(z)}$$
- Controlador del sistema:                 $$C(z) = \frac{A(z)}{B(z)}$$
- Función de transferencia lazo cerrado:   $$G_o(z) = \frac{N_o(z)}{D_o(z)}$$
- Función con retroalimentación unitaria en lazo cerrado:

$$G_o(z) = \frac{C(z)G(z)}{1 + C(z)G(z)}$$

$$G_o(z) = \frac{\frac{A(z)}{B(z)} \frac{N(z)}{D(z)}}{1 + \frac{A(z)}{B(z)} \frac{N(z)}{D(z)}}$$

$$G_o(z) = \frac{A(z)N(z)}{B(z)D(z) + A(z)N(z)}$$

## Obtención del sistema discreto en lazo cerrado
Se tiene la siguiente planta en tiempo discreto. Teniendo en cuenta los polos dados para la función en lazo cerrado, se debe obtener el controlador por el método de igualación de coeficientes:

$$ G(z) = \frac{1.61 \cdot 10^{-7} z^2 + 6.25 \cdot 10^{-7} z + 1.53 \cdot 10^{-7}}{z^3 - 2.87z^2 + 2.75z - 0.88} $$

>🔑 *Método de igualación de coeficientes:* Consiste en igualar los coeficientes de las variables de grados comunes de dos funciones.

💡**Ejemplo 1:**

$R = 4z + 2$

$P = ez + 2 + u$

Igualar coeficientes

$4 = e$

$2 = 2 + u; u = 0$

A partir de los siguientes polos, se debe hallar el polinomio característico del denominador de la función en lazo cerrado. El cual, será de ayuda para obtener el controlador de la planta.

$$ P_1 = -100$$
$$ P_2 = -100$$
$$ P_3 = -100$$
$$ P_4 = -2 + 2.73j$$
$$ P_5 = -2 - 2.73j$$

Para ello, se crea una expresión que de lugar a esos polos.

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

Y reemplazando en la ecuación que obtiene la función en lazo cerrado

$$G_o(z) = \frac{A(z)N(z)}{B(z)D(z) + A(z)N(z)} = \frac{(A_0 + A_1z + A_2z^2)(1.61 \cdot 10^{-7} z^2 + 6.25 \cdot 10^{-7} z + 1.53 \cdot 10^{-7})}{(B_0 + B_1z + B_2z^2)(z^3 - 2.87z^2 + 2.75z - 0.88) + (A_0 + A_1z + A_2z^2)(1.61 \cdot 10^{-7} z^2 + 6.25 \cdot 10^{-7} z + 1.53 \cdot 10^{-7})}$$

Un código de matlab para resolver esta multiplicación más tarde...

$$\left( \frac{2890088287516223}{18889465931478580854784}A0 - \frac{22}{25}B0 \right) + \left( \frac{5902958103587057}{9444732965739290427392}A0 + \frac{2890088287516223}{18889465931478580854784}A1 + \frac{11}{4}B0 - \frac{22}{25}B1 \right)z + \left( \frac{6082408029936103}{37778931862957161709568}A0 + \frac{5902958103587057}{9444732965739290427392}A1 + \frac{2890088287516223}{18889465931478580854784}A2 - \frac{287}{100}B0 + \frac{11}{4}B1 - \frac{22B2}{25} \right)z^2 + \left(\frac{6082408029936103A1}{37778931862957161709568} + \frac{11B2}{4} - \frac{287B1}{100} + \frac{5902958103587057}{9444732965739290427392}A2 + B0 \right)z^3 + \left( \frac{6082408029936103}{37778931862957161709568}A2 + B1 - \frac{287}{100}B2 \right)z^4 + B2z^5$$

Simplificado

$$(B2)z^5 + (1.61·10^{-7}A2 + B1 - 2.87B2)z^4 + (1.61·10^{-7}A1 + 2.75B2 - 2.87B1 + 6.25·10^{-7}A2 + B0)z^3 + (1.61·10^{-7}A0 + 6.25·10^{-7}A1 + 1.53·10^{-7}A2 - 2.87B0 + 2.75B1 - 0.88B2)z^2 + (6.25·10^{-7}A0 + 1.53·10^{-7}A1 + 2.75B0 - 0.88B1)z + (1.53·10^{-7}A0 - 0.88B0)$$


Recordando el denominador $D_o(z)$ y usando el método de igualación de coeficientes es posible obtener el valor de las incógnitas $A0, A1, A2, B0, B1$ y $B2$.

$$D_o(z) = (z^5 + 304z^4 + 31211.4529z^3 + 1123435.87z^2 + 4343587z + 11452900) $$

$$1 = B2$$
$$304 = 1.61·10^{-7}A2 + B1 - 2.87B2$$
$$31211.4529 = 1.61·10^{-7}A1 + 2.75B2 - 2.87B1 + 6.25·10^{-7}A2 + B0$$
$$1123435.87 = 1.61·10^{-7}A0 + 6.25·10^{-7}A1 + 1.53·10^{-7}A2 - 2.87B0 + 2.75B1 - 0.88B2$$
$$4343587 = 6.25·10^{-7}A0 + 1.53·10^{-7}A1 + 2.75B0 - 0.88B1$$
$$11452900 = 1.53·10^{-7}A0 - 0.88B0$$

💡**Código para obtener el denominador de lazo cerrado con coeficientes de controlador de esta función:**
```
clc
clear all
close all

% Define the symbolic variable
syms z;

% Define the symbolic coefficients for A(z) and B(z)
A0 = sym('A0');
A1 = sym('A1');
A2 = sym('A2');

B0 = sym('B0');
B1 = sym('B1');
B2 = sym('B2');

% Define N(z) and D(z)
N = 1.61e-7 * z^2 + 6.25e-7 * z + 1.53e-7;  % N(z)
D = z^3 - 2.87 * z^2 + 2.75 * z - 0.88;  % D(z)

% Expression for G_o(z)
G_o = expand((A0 + A1 * z + A2 * z^2) * N / ((B0 + B1 * z + B2 * z^2) * D + (A0 + A1 * z + A2 * z^2) * N));

% Simplify the expression
G_o_simplified = simplify(G_o);

% Display the simplified expression in pretty format
pretty(G_o_simplified)

D_o = expand(((B0 + B1 * z + B2 * z^2) * D + (A0 + A1 * z + A2 * z^2) * N)) %Formula del denominador
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## 10. Conclusiones
Una vez presentada la solución del parcial, es posible reflexionar un par de puntos importantes:
- El orden, la clave de este ejercicio radica en organizar las expresiones de una manera legible y clara, que permita operar sin posibilidad de enredarse, ya que si se desea verificar el proceso sería muy dificil analizarlo.
- Las propiedades del método, en este caso la igualación de coeficientes tiene unas caracteristicas para construir el controlador, que al no tenerlas en cuenta se puede perder mucho tiempo multiplicando una expresión erronea.
- Este proceso puede ser verificado con Matlab y también se puede ejecutar en su totalidad de manera algebráica.

## 11. Referencias
[1] "Parcial Segundo Corte" Curso Control Digital.

[2] "Métodos algebráicos" Curso Control Digital.
