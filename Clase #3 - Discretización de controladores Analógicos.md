# Discretización de controladores Analógicos
## ¿Qué es la discretización de señales analógicas?
Se trata de la transformación de una señal de tiempo continuo a tiempo discreto, con el objetivo de muestrear una señal, obtener sus valores en intervalos constantes de tiempo que permitan su procesamiento. Esto resulta como una señal digital.
Se utiliza para decirle a un controlador que acciones hacer sobre una señal recibida.
Para control, esto se logra buscando la equivalencia entre el espacio de Laplace y el espacio Z

![image](https://github.com/user-attachments/assets/52a6df84-4531-4adf-9283-799bf1829133)
![image](https://github.com/user-attachments/assets/39480da1-eeea-472d-82de-2c6700f6a89c)

>Figura 1 y 2. Discretización de una señal en tiempo continuo, muestreada y digitalizada.

## ¿Qué métodos se utilizan para la discretización de señales analógicas?
### *Método de invarianza al pulso*
>🔑 A una señal cualquiera se le aplica una señal impulso, deseando que el comportamiento en dicho momento sea el mismo para la señal continua y discreta.

![image](https://github.com/user-attachments/assets/c21898ec-7306-43c5-bd04-ecef6c640340)

![image](https://github.com/user-attachments/assets/a5c589cb-a600-452b-9793-a3f88a3a46e1)

>Figura 3 y 4. Aplicación del impulso y transformada Z de la función.

Al tratarse de discretizar una señal, buscamos obtener su equivalente en el espacio Z.
1. Se obtiene la equivalencia en tiempo continuo a la señal en el dominio de Laplace.
2. Se traslada la función de tiempo continuo a tiempo discreto.
3. Se aplica transformada Z para obtener la función de transferencia en términos de Z.

*De acuerdo a la forma de la FT en el Dominio de Laplace, es posible obtener su equivalencia en el Dominio Z mediante las transformadas rápidas.

>🔑 *¿Para qué sirve la función de transferencia?*
Sirve para relacionar la salida del sistema con respecto a las variables de entrada que nos permita controlar un sistema. Es decir, obtiene el comportamiento dinámico del sistema para así controlarlo.


💡*Ejemplo:*

![image](https://github.com/user-attachments/assets/8ca56560-b6c3-4d6f-8c15-2687fb190da9)

>Figura 5. Ejercicio de invarianza al pulso.

### *Método de invarianza al paso*
Para este caso, lo que se opta por hacer es aplicar a nuestra señal discretizada y sin discretizar, un escalón unitario. Sí la respuesta es la misma para ambas señales, entonces la señal es invariable en el tiempo.

$$u(t)c(t); \frac{1}{s} c(s); \frac{z}{z-1} c(z)$$

![image](https://github.com/user-attachments/assets/d2a46060-e3b2-4044-b05e-6839979fbb2c)

>Figura 6. Transformadas necesarias para obtener la FT en dominio Z.

![image](https://github.com/user-attachments/assets/9686737b-4c9b-4adc-87b7-cc8035848922)


Esta igualdad se debe cumplir, obteniendo la FT en el dominio Z a partir de:
1. Aplicarle a la función de transferencia en el dominio S un escalón.
2. Obtener la función en tiempo continuo y se traslada a tiempo discreto (Esto se hace indirectamente al aplicar Transformada Z a la transformada inversa de Laplace).
3. Aplicar transformada para obtener la equivalencia en el dominio z.
4. Revertir el escalón unitario multiplicando por el inverso.
5. Esto nos debe dar la equivalente en el espacio z de la FT original, demostrando la condición de invariabilidad en el tiempo.

💡*Ejemplo:*

![image](https://github.com/user-attachments/assets/5c89d2ce-98db-481e-9f37-c96264055822)

>Figura 7. Ejercicio de invarianza al paso.

### *Método Euler Adelante*
Se tiene como aproximación de la derivada lo siguiente:

![image](https://github.com/user-attachments/assets/e9735e29-6ed3-4a15-ab39-8cc56e404526)

>Figura 8. Diferencial de la muestra futura y actual.

Esto nos relaciona la distancia entre la amplitud de la siguiente muestra (predicha) con la amplitud de la muestra actual de nuestra señal, sobre el tiempo de muestreo T. Esto calcula la derivada a partir de la predicción de la señal y su comportamiento actual con respecto al tiempo de muestreo.
	
Según las propiedades de la transformada de Laplace, la transformada de la derivada de una función es:

![image](https://github.com/user-attachments/assets/365aefeb-3ffa-4536-8ee7-a863f51a40e4)

>Figura 9. Equivalencia de la derivada en Laplace.

Al aplicar la transformada Z a la derivada discreta, obtenemos:

![image](https://github.com/user-attachments/assets/07684900-b7a3-454a-9ac7-83e09e2c8552)

Asumiendo que el comportamiento de la función en el dominio de Laplace y en el dominio de Z es el mismo, se puede aproximar su equivalencia así:

$$sX(s) ≈ \frac{z-1}{T} X(z)$$

$$s ≈ \frac{z-1}{T}$$

### *Método Euler Atrás*
Para este método, se tiene en cuenta la muestra anterior a la actual. Es decir, un sistema con memoria. Definiendo la derivada así:

![image](https://github.com/user-attachments/assets/8a73d5fb-fabb-4713-b342-23840f5adfce)

>Figura 10. Diferencial de la muestra actual y anterior.

Del mismo modo, aplicamos transformada Z:

![image](https://github.com/user-attachments/assets/332cd934-91f2-466d-bf52-8fe88875eb16)

Entonces, igualamos nuevamente dominio de Laplace y dominio Z:

$$sX(s) ≈ \frac{z-1}{Tz} X(z)$$

$$s ≈ \frac{z-1}{Tz}$$

### *Método Trapezoidal*
Para este método, ya se plantea una igualdad entre el dominio s y el dominio z, así:

$$s = \frac{\frac{2}{T} (z-1)}{z+1} $$

$$z = \frac{1+ \frac{Ts}{2}}{1- \frac{Ts}{2}}$$

Con estas equivalencias, es posible discretizar una función de Laplace a Z.

## 9. Ejercicios
*Los ejemplos de los métodos también son ejercicios ya que se desarrollan paso a paso.
📚 Ejercicio invarianza al pulso:

![image](https://github.com/user-attachments/assets/1b41b7b1-26dd-4abd-a534-f59cc8b9a6bc)

>Figura 11. Ejercicio invarianza al pulso.

## 10. Conclusiones
Discretización de Señales: La discretización de señales analógicas convierte una señal continua en una señal discreta mediante diferentes métodos, permitiendo su procesamiento digital y el control en sistemas discretos.

Métodos de Discretización: Los métodos como la invarianza al pulso, invarianza al paso, Euler adelante y atrás, y el método trapezoidal son fundamentales para transformar modelos continuos en discretos, asegurando que el comportamiento dinámico del sistema se preserve en el dominio digital.

## 11. Referencias
[1] "Discretización de controladores," Repositorio Universidad de Ibagué, 2024. [Enlace: https://repositorio.unibague.edu.co/entities/publication/6b138ca4-3a0a-48bc-a629-51e40bcf1edd]

[2] J. A. Cortés Osorio, H. B. Cano Garzón y J. A. Chaves Osorio, "Fundamentos y aplicación del muestreo en señales ubicadas en las bandas altas del espectro," Scientia et Technica, vol. 14, no. 39, pp. 37-42, 2008.
