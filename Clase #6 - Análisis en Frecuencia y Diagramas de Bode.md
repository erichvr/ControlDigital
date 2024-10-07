# Análisis en Frecuencia y Diagramas de Bode

El análisis en frecuencia es crucial para evaluar el comportamiento de un sistema de control ante variaciones en la frecuencia de entrada, utilizando señales senoidales para observar cambios en la salida. Los diagramas de Bode, que representan gráficamente la ganancia y el desfase del sistema en función de la frecuencia, son herramientas fundamentales en este análisis. Estos diagramas permiten identificar la estabilidad y el rendimiento del sistema, aunque es importante considerar que, en sistemas discretos, la eficacia de los compensadores puede disminuir a frecuencias altas. En conjunto, estos enfoques ofrecen una visión clara del funcionamiento del sistema, facilitando su diseño y optimización.

---

## 1. Análisis en frecuencia:
Se verifica su comportamiento en la salida a partir de cambios en la frecuencia de entrada, se realiza aplicando señales seno $$R = Asen (wkT+0)$$ suponiendo que el sistema tiene un comportamiento lineal. Para finalizar se realizan variaciones en la frecuencia de entrada, se producen variaciones en amplitud y fase en la señal de salida.

### 1.1. Cambios que se producen
- Salida sinusoidal con amplitud proporcional
- Armónicos igual a la frecuencia que a la entrada
- Variaciones en amplitud y frecuencia

| $$A_1 < \phi_1$$                     | $$A_2 < \phi_2$$                       |
|-----------------------------------------|------------------------------------------|
| $$A_1 \cdot \sin(w_1 K T + \phi_1)$$ | $$A_2 \cdot \sin(w_2 K T + \phi_2)$$  |
|                                         |                                          |
| $$G(s) = \frac{A_2 < \phi_2}{A_1 < \phi_1} = M < \phi$$ |                             |
| $$M = \frac{A_2}{A_1} \quad \phi = \phi_2 - \phi_1$$ | $$\text{No depende de la frecuencia}$$ |

Tabla 1. Relación entre Amplitudes, Fases y Ganancia en Sistemas Dinámicos.

### 1.2. Expresar la función de transferencia en términos de la frecuencia
Se sabe que $$S = j\omega$$ y que la equivalencia de mapeo de polos y ceros es $$z = e^{s t}$$; por lo tanto, para poner la variable $$z$$ en términos de la frecuencia se obtendría:

$$z = e^{j\omega t}$$.

### 1.3. Diagramas de frecuencia:

Para cualquier función de transferencia se puede separar la parte real e imaginaria, entonces es posible hallar la magnitud y la fase en el dominio de la frecuencia, por lo tanto, esto podría ser graficado en un plano para observar su comportamiento.

1. Magnitud y fase con respecto a la frecuencia.
2. Escala lineal.  
3. Escala logarítmica **DECIBELIOS**.
4. Magnitud con respecto a la fase. 
5. Coordenadas polares.

| IMAGENES                    | TITULO DE LA IMAGEN                     |
|---------------------------------------------------|------------------------------------------|
| ![image](https://github.com/user-attachments/assets/456a8cda-494c-4b2b-888d-29b2529d1721)| TITULO DE LA IMAGEN                     |

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


---

### 2.3 Función De Transferencia Nuevo Controlador:
Los coeficientes obtenidos para el controlador son:

$$ A_1 = 1 $$

$$ B_0 = -12.99 $$

$$ A_0 = -0.911 $$

$$ B_1 = 14.23 $$

**El Controlador Sería:**

$$C(z) = \frac{B_0 + B_1 z}{A_0 + A_1 z} = \frac{-12.99 + 14.23 z}{-0.911 + z}$$

## 3. Conclusiones
Es posible modelar cualquier respuesta en lazo cerrado a través de los métodos algebraicos, aunque las soluciones satisfacen matemáticamente, por otro lado, no siempre son realizables desde el punto de vista de control.

Por otro lado, en el método de igualación de modelos se modela completamente la función de transferencia, en el método de igualación de coeficientes no se tiene control de los ceros del sistema y para finalizar la igualación de coeficientes se puede simplificar por medio de las ecuaciones diafánticas.

## 4. Referencias
[1] "Métodos algebráicos" Curso Control Digital.

