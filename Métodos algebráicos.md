# Métodos algebráicos

Son métodos que utilizan herramientas algebraicas para obtener un determinado comportamiento en el sistema en lazo cerrado, la base fundamental de estos métodos es modificar la función de transferencia en lazo cerrado de acuerdo a una respuesta deseada. Existen dos enfoques: por igualación de modelo y por igualación de coeficientes.

![Diagrama de bloques de un sistema de control discreto](https://github.com/user-attachments/assets/1cffeb00-64ad-406d-90fa-b0cc48ba9d35)

Figura 1. Diagrama de bloques de un sistema de control discreto.

---

## 1. Igualación de modelo
Sabiendo que $$G(z)$$ es la función de lazo abierto y es conocida, entonces conociendo la respuesta que se desea obtener, representada en una función de transferencia de lazo cerrado  $$Go(z)$$ además es posible obtener la función de transferencia del controlador $$C(z)$$ que asegura dicho comportamiento.

Si $$G(z)$$ tiene polos fuera del circulo unitario o 2 o más en $$z = -1$$, entonces la retroalimentación unitaria no puede ser implementada, cualquier $$G(z)$$; debido a que los controladores podrían ser no implementables.

  ### Consideraciones de implementación
  Los compensadores deben ser causales, además de que el modelo objetivo debe ser estable, y no deben       resultar cancelaciones $$polo – zero =r≤ro$$ sin dejar de lado que los zeros (FASE NO MINIMA) de la planta serán retenidos en lazo cerrado.

---

## 2. Igualación de coeficientes
Sabiendo que $$G(z)$$ es la función de lazo abierto y es conocida entonces conociendo la ubicación de los polos que desea, a partir de la respuesta deseada, se puede representar en un polinomio característico en donde es posible obtener la función de transferencia del controlador $$C(z)$$ que asegura dicho comportamiento además se debe tener en cuenta que para aplicar una acción proporcional, se debe primero diseñar un controlador de acción proporcional para ubicar los polos del sistema en lazo cerrado en:

💡Ejemplo

$$P1=0.91+j0.23 $$

$$P2=0.91-j0.23 $$

Entonces el polinomio característico deseado en lazo cerrado es:

$$(z-0.91+j0.23)(z-0.91-j0.23)=z^2-1.82z+0.881$$

### 2.1. Consideraciones
Se sabe que para el lazo cerrado se debe calcular la función de transferencia en lazo cerrado aplicando un controlador.

Dado que:

$$ G(z) = \frac{N(z)}{D(z)} $$

y 

$$ C(z) = \frac{B(z)}{A(z)} $$

La función de transferencia en lazo cerrado es:

$$ Go(z) = \frac{G(z)C(z)}{1 + G(z)C(z)} = \frac{B(z)N(z)}{A(z)D(z) + B(z)N(z)} $$

Dónde:

- **$$G(z)**: Representa la función de transferencia del sistema o planta en el dominio Z.
- **C(z)**: Es la función de transferencia del controlador.
- **Go(z)**: Es la función de transferencia del sistema en lazo cerrado.

Se multiplican $$A(z)$$ y $$D(z)$$, por lo tanto, en lazo cerrado debe subir el orden del sistema. Luego, se multiplican $$B(z)$$ y $$N(z)$$, por lo tanto, las funciones de la planta y del controlador deben ser propias.

La igualación se realiza en el polinomio característico, lo que quiere decir que no hay control sobre la ubicación de los ceros del sistema. Finalmente, el orden de $$C(z)$$ debe ser un grado menor con respecto a la planta en lazo abierto.

### 2.2. Realizando la igualación de coeficientes
El polinomio deseado sería: 

$$(z-0.91+j0.23)(z-0.91-j0.23s)(z-0.91)=z-2.732+2.537z-0.8017$$

Se necesita otro término en el polinomio $$B(z)$$ para tener el mismo número de ecuaciones que de términos.

Al igualar:

$$z^3-2.73z^2+2.537z-0.8017 = A1z^3+(Ao-1.819A1)z^2+(0.8187A1-1.819Ao)z+0.8187Ao+0.0043Bo$$



Se puede ver que **NO SE SATISFACEN TODAS LAS ECUACIONES**

| $$A_1=1$$                           |            |
|-------------------------------------|------------|
| $$A_0-1.819A_1=-2.73$$ $$A_0=-2.73$$ | $$A_0=-0.911$$ |
| $$0.8187A_1-1.819A_0=2.537$$         |            |
| $$0.8187A_0+0.0043B_0=0.8017$$       |            |

Tabla 1. Lista de ecuaciones


Cuando el sistema es de tercer orden se deben ubicar 3 polos.

$$Z=0.91+j0.23$$

$$Z=0.91-j0.23$$

$$Z=0.91$$


