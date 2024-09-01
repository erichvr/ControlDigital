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
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
