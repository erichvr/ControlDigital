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

| IMÁGENES                                                                                                                                       | TÍTULO DE LA IMAGEN                                 |
|------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|
| <img src="https://github.com/user-attachments/assets/456a8cda-494c-4b2b-888d-29b2529d1721" alt="image" width="600"/>                  | **DIAGRAMAS DE BODE**                               |
| <img src="https://github.com/user-attachments/assets/5e7c3694-840c-4803-9cbf-69d2685a00eb" alt="image" width="600"/>                  | **DIAGRAMA POLAR**                                  |
| <img src="https://github.com/user-attachments/assets/fe07c182-a11a-4d0f-bfbc-b05836cb3d26" alt="image" width="600"/>                  | **ANALISIS FREENCIAL EN TIEMPO DISCRETO**           |
| <img src="https://github.com/user-attachments/assets/3ced2bdf-8d3c-4372-a095-8b8161db49de" alt="image" width="600"/>                  | **ANALISIS EN FRECUENCIA T = 0.1 SEG**              |
| <img src="https://github.com/user-attachments/assets/3bbf5f01-526d-437e-b7e3-27c5eb33d6b2" alt="image" width="600"/>                  | **ANALISIS EN FRECUENCIA T = 0.001 SEG**            |
| <img src="https://github.com/user-attachments/assets/26db4e3f-7d99-49f4-905f-568379317af9" alt="image" width="600"/>                  | **DIAGRAMAS DE BODE**                               |
| <img src="https://github.com/user-attachments/assets/ce9c625a-744e-4320-8132-95d912186613" alt="image" width="600"/>                  | **EFECTO DE LOS PARAMETROS**                        |

Tabla 2. Análisis de frecuencia y diagrama de bode de una señal

- Los decibelios dB no son una unidad física, se utilizan como una interpolación de algunas cantidades como ganancia o potencia.

  **En el caso de la ganancia** 
$$A_{dB} = 20 \log_{10}(A)$$


### 1.4. Análisis Frecuencial en Tiempo Discreto:

No es posible hacer análisis en frecuencia directamente en tiempo discreto, se aprovecha la transformación bilineal (TUSTIN) para aproximar al tiempo continuo.

$$ w = \frac{2}{T} \cdot \frac{z - 1}{z + 1} $$

$$ z = \frac{1 + \frac{wT}{2}}{1 - \frac{wT}{2}} $$

Reemplazando $$z = e^{j\omega T}$$ se obtiene 

$$ \omega = j \frac{2}{T} \tan\left(\frac{\omega T}{2}\right) $$

Sustituyendo $$\omega = jv$$ resulta en 

$$ v = \frac{2}{T} \tan\left(\frac{\omega T}{2}\right) $$


---

## 2. Diagramas de Bode:
Son gráficos obtenidos a partir de los cambios que tiene el sistema en la amplitud de su ganancia y su ángulo de desface frente a cambios en la frecuencia de la señal de entrada $$G(jv) y <G(jv)$$. Usualmente se presentan en escala logarítmica, en el caso de sistemas discretos es importante tener en cuenta que los compensadores que se diseñen pierden eficacia en frecuencias altas, debido a la transformada W, la aproximación de la transformada W es válida entre 0 y la frecuencia de Nyquist.

---

## 3. Ecuación de Overshoot:
$$
M_p = \frac{c_{(t_p)} - c_{(\infty)}}{c_{(\infty)}} = e^{-\frac{\pi \zeta}{\sqrt{1 - \zeta^2}}} = e^{-\frac{\pi}{\tan(\phi)}}
$$



$$
\phi = \tan^{-1}\left(\frac{\omega_d}{-\sigma}\right)
$$


## 4. Conclusiones
- RELACION DE LAS RESPUESTAS: A partir de lo anterior es posible obtener una relación entre la respuesta en frecuencia en lazo abierto con respecto a la respuesta temporal en lazo cerrado.
- Análisis en Frecuencia: Este análisis es clave para entender cómo un sistema de control reacciona ante cambios en la frecuencia de entrada. Al usar señales senoidales, se pueden observar las variaciones en la amplitud y la fase de la salida, lo que ayuda a diseñar y optimizar compensadores para mantener un buen rendimiento en diversas frecuencias.

- Diagramas de Bode: Estas gráficas muestran la relación entre la frecuencia de entrada y el comportamiento del sistema, revelando la ganancia y el desfase. Son esenciales para evaluar la estabilidad del sistema. Al utilizar escalas logarítmicas, permiten a los ingenieros analizar mejor las variaciones en un amplio rango de frecuencias, lo cual es crucial en sistemas discretos donde la eficacia a altas frecuencias puede verse afectada.

## 5. Referencias
[1] "Análisis en Frecuencia y Diagramas de Bode" Curso Control Digital.

