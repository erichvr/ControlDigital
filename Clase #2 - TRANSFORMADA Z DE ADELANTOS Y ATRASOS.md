# TRANSFORMADA Z DE ADELANTOS Y ATRASOS
La transformada Z es una herramienta fundamental en el análisis y diseño de sistemas de control digital. Permite transformar ecuaciones en diferencias, que describen el comportamiento dinámico de un sistema en términos de sus entradas y salidas discretas, en el dominio Z. Esto facilita la resolución de dichas ecuaciones y la obtención de funciones de transferencia discretas, esenciales para analizar y entender el comportamiento de los sistemas en tiempo discreto. Además, la transformada Z es crucial en el estudio de adelantos y atrasos en las señales, lo que tiene aplicaciones directas en la mejora de la estabilidad y el rendimiento de sistemas de control digital.

## 1. FUNCIÓN EN TÉRMINOS DE MUESTRAS
$$ F(t) = F(kT) $$

>🔑 *T: Periodo de muestreo*

![image](https://github.com/user-attachments/assets/447ff947-f470-469c-8533-a486c6438ac1)

>Figura 1. Función en tiempo continuo y discreto

## 2. REPRESENTACIÓN MATEMÁTICA DE LOS SISTEMAS
### 2.1 Ecuación en diferencias

$$ B_n*U(k) + B_(n-1) * U_(k-1) + ... + B_o * U(k-n) = y(k)+a_(n-1)*y(k-1)+...+aoy_(k-n)$$

*	Donde “U” es la entrada y “Y” es la salida.
*	El sistema se representa a través de una combinación lineal.
*	Las ecuaciones en diferencias representan el comportamiento dinámico de un sistema en términos de sus señales de entrada y de salida.

### 2.2 CARACTERISTICAS ECUACIONES EN DIFERENCIAS 

Las ecuaciones en diferencias pueden ser homogéneas, lineales, invariantes en el tiempo.

* Lineal, invariante en el tiempo, no homogénea.

$$ y(k+2) + 0.8y(k+1) + 0.7y(k)U(k) = 0$$

* Lineal, variante en el tiempo, homogénea.

$$ y(k+4) + sen(0.4k)y(k+1) + 0.3y(k) = 0$$

* No lineal, invariante en el tiempo, homogénea.

$$ y(k+1) = -0.1*y(k)^2$$

Existen 2 soluciones para las ecuaciones en diferencias, estas son:

o	Métodos iterativos

o	Transformada Z

## 3. Transformada Z
### 3.1. Ecuación en diferencias

Las ecuaciones en diferencias es el comportamiento dinámico de un sistema, similar a las ecuaciones diferenciales, pero utilizando señales discretas. En este contexto, ”u” representa la entrada del sistema y ”y” la salida. La dinámica del sistema se expresa mediante una combinación lineal de diferentes muestras de estas señales, lo que permite modelar cómo la salida depende de entradas actuales y pasadas.

$$b_nu(k) + b_(n-1) u(k-1) +...+ b_0 u(k-n) = y(k) + a_(n-1)y(k-1) +...+ a_0 y(k-n)$$

* La solución numérica da los valores de “y” para un numero finito de muestras, sin embargo, no permite identificar características generales del funcionamiento del sistema.
* La solución por transformada Z permite obtener una expresión matemática para dar la solución de la ecuación en cualquier muestra.

En sistemas de tiempo discreto, es posible obtener una representación de función de transferencia en el dominio z, análoga a la del tiempo continuo.
Esta representación ofrece ventajas significativas, como la capacidad de identificar el comportamiento del sistema a través de la identificación de parámetros. La función de transferencia pulso, en particular, describe la relación entre la salida y la entrada muestreadas de un sistema dinámico, proporcionando una herramienta valiosa para el análisis y diseño de sistemas discretos.

La transformada Z es la contraparte discreta de la transformada de Laplace, utilizada para analizar sistemas en tiempo discreto. A pesar de su similitud funcional, el espacio Z presenta características distintas al espacio de Laplace.
Estas diferencias se deben principalmente a la naturaleza discreta de las señales
que la transformada Z maneja, en contraste con las se˜ nales continuas de Laplace.

![image](https://github.com/user-attachments/assets/04fadd6c-a139-4c3d-bc34-db2712121f8f)

>Figura 2. Transformada de Laplace y transformada Z

## 4. Relación Z y L

![image](https://github.com/user-attachments/assets/5b080757-e095-4e76-9c60-b32483e465eb)

>Figura 3. Demostración matemática del muestreo de una señal continua con la señal impulso

### 4.1 SOLUCIÓN DE ECUACIONES EN DIFERENCIAS POR TRANSFORMADA Z
Es un procedimiento similar a la solución de ecuaciones diferenciales en donde se le aplica si o si la transformada Z a la ecuación sin dejar de lado que se despeja la variable desconocida o la salida del sistema para así aplicar la transformada Z inversa de $$Z^(-1)$$.

### 4.2 TRANSFORMADA Z IMPORTANTES EN CONTROL
En las ecuaciones en diferencias tenemos términos del tipo:

$$𝑓(𝑘+𝑛)$$ 𝑜 $$𝑓(𝑘-𝑛)$$

* Donde n es el número de muestra que se desplaza la función.
* Entonces la transformada Z de este tipo de términos son muy importantes en el área de control.

### 4.2.1 Atraso
![image](https://github.com/user-attachments/assets/7a5001b5-ada4-4173-8e5c-e56a27ac910f)
>Figura 4. Ilustración del atraso de una señal. 

![image](https://github.com/user-attachments/assets/86cbe15b-2428-41b6-8d6c-ea67bc01aa28)
![image](https://github.com/user-attachments/assets/93a5dc56-0415-4f49-9b85-b3207dd880b9)

>Figura 5. Transformada Z en un atraso

*	ATRASO = Negativo
*	ADELANTO = Positivo

### 4.2.2 Adelanto
![image](https://github.com/user-attachments/assets/24ae2384-0568-476c-a050-94605bd5e0fe)
>Figura 6. Ilustración del adelanto de una señal. 

![image](https://github.com/user-attachments/assets/59807c50-79c2-41f5-8487-244f3f832041)
![image](https://github.com/user-attachments/assets/e7412e22-e28b-47a0-8751-f963871ebed7)

>Figura 7. Transformada Z en un adelanto

## 5. Función de trasferencia discreta
### 5.1 Funciones de transferencia en el dominio z
Al igual que en tiempo continuo, en tiempo discreto es posible obtener una representación de función de transferencia en el dominio Z, teniendo en cuenta que tiene múltiples ventajas como poder identificar el comportamiento del sistema desde la identificación de parámetros.

![image](https://github.com/user-attachments/assets/c40786bc-ac43-4a0a-9725-e87438e9ad57)
>Figura 8. Diagrama de bloques de un sistema que st[a siendo muestreado cada T tiempo.
* Donde $$𝑥^*(𝑡)$$ 𝑦 $$𝑦^*(𝑡)$$ son las señales x(t) y y(t) muestreadas.

![image](https://github.com/user-attachments/assets/500615b1-9dc6-48f6-a3a5-6ee57d9a8005)
>Figura 9. Simplificación.

* Para dos sistemas en cascada:
  ![image](https://github.com/user-attachments/assets/290c9bf1-bc05-41fd-be4e-9d0040bcec1f)
  >Figura 10. Simplificación.
  
## 6. Ejemplos
>💡 Ejemplo 1:
Si se agrega un muestreador entre los dos sistemas.

![image](https://github.com/user-attachments/assets/f7ac8898-c925-42ab-941c-1d677bb66401)
![image](https://github.com/user-attachments/assets/f9db07c9-3d5c-4e18-afe8-f62b57ab7dd0)

>Figura 11. Obtención de la FT en dominio s

>💡 Ejemplo 2:
Dada la siguiente ecuación obtener la función de transferencia
$$3y(k) + 2y(k-1) - y(k-2) = 2u(k-1) - 3u(k-2)$$
>* Se aplica transformada Z
$$3Y(z) + 2z^(-1)(Y(z) - y(-1)z) -z^(-2)(Y(z) + y(-1)z + y(-2)z^2) = 2z^(-1)u(z) - 3z^(-2)u(z)$$

![image](https://github.com/user-attachments/assets/cf5e1d4a-c460-47de-8cac-eb27da2b1092)
>Figura 12. FT resultante

>💡 Ejemplo 3:
![image](https://github.com/user-attachments/assets/5e21a283-ba07-4a33-80ad-5007d63dcaf7)
![image](https://github.com/user-attachments/assets/f1a5bf28-6ed9-4af3-a122-17215d216cbd)
>Figura 13. Desarrollo y graficación ejercicio.

El sistema da respuesta solamente al haber aplicado una entrada teniendo en cuenta que si m > n la función de transferencia es propia la cual se le denomina un sistema causal.


## 7. TIEMPO MUERTO EN SISTEMAS DISCRETOS
El tiempo muerto es más fácil de medir en sistemas discretos comparando el grado de los polinomios de la función de transferencia.

$$EXCESO POLO - ZERO$$
$$R = M - N$$

Se sabe que el valor de r es la cantidad de muestras que hay de tiempo muerto, si r = 0 es sistema es bipropio.


## 8. Ejercicios
>📚Ejercicio 1: Ecuación en Diferencia
![image](https://github.com/user-attachments/assets/6859e88c-53bf-45d0-bdec-b80db9750cdb)
>Figura 14. Desarrollo ejercicio 1

>📚Ejercicio 2: Función de transferencia
![image](https://github.com/user-attachments/assets/f7a12e86-092a-49c6-a0e4-b9eae8f9f660)
>Figura 15. Desarrollo ejercicio 2


## 9. Conclusiones
La transformada Z es esencial en el análisis de sistemas de control digital, permitiendo la conversión de ecuaciones en diferencias a un formato que facilita su resolución y análisis. Esto es crucial para entender y mejorar la estabilidad y rendimiento de estos sistemas, especialmente en la manipulación de adelantos y atrasos en señales discretas. Además, permite obtener funciones de transferencia en el dominio Z, análogas a las de sistemas continuos, lo que es fundamental en el diseño y análisis de sistemas dinámicos discretos.

## 11. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
