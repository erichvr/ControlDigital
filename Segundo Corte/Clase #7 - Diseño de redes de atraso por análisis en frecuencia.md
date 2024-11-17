# Diseño de redes de atraso por análisis en frecuencia

El diseño de sistemas de control es crucial en la ingeniería para asegurar la estabilidad y rendimiento de procesos industriales. Utilizar el diagrama de Bode como herramienta visual permite a los ingenieros analizar el comportamiento del sistema frente a diferentes frecuencias, facilitando la identificación del error en estado estacionario y la evaluación de la estabilidad a través de los márgenes de ganancia y fase. Además, los controladores por análisis en frecuencia, como los compensadores de adelanto y las configuraciones de atraso-adelanto, mejoran el rendimiento del sistema. El control PID se destaca por su aplicabilidad y facilidad de sintonización en entornos industriales, estableciendo un marco efectivo para el diseño de controles robustos.

---

## 1. Ventajas del diseño por diagrama de Bode:
El diseño por diagrama de Bode ofrece una herramienta visual poderosa que permite a los ingenieros ver directamente el error de estado estacionario del sistema. Esta visualización directa facilita la comprensión inmediata del comportamiento del sistema sin necesidad de cálculos complejos adicionales.

![Diagrama de Bode de un Filtro Pasivo RC: Respuesta en Ganancia y Fase](https://github.com/user-attachments/assets/aacc414b-164c-4310-b954-2d059af2e899)

Figura 1. Diagrama de Bode de un Filtro Pasivo RC: Respuesta en Ganancia y Fase.

Existe una correlación directa entre la respuesta temporal del sistema y su representación en el diagrama de Bode, lo que permite predecir el comportamiento temporal a partir del análisis frecuencial. Además, los márgenes de estabilidad pueden medirse directamente en el diagrama, simplificando significativamente el proceso de evaluación de la estabilidad del sistema.

---

## 2. Controladores por análisis en frecuencia:
El compensador de adelanto de fase es útil cuando se necesita aumentar el rendimiento dinámico del sistema, mejorando el ancho de banda y los márgenes de estabilidad. Sin embargo, este beneficio viene con el costo potencial de una mayor susceptibilidad al ruido en altas frecuencias.

![Diagrama de Bloques de un Sistema de Control con Compensador de Adelanto de Fase](https://github.com/user-attachments/assets/426139a4-2de3-4687-ab85-4eef6d6ed7b3)

Figura 2. Diagrama de Bloques de un Sistema de Control con Compensador de Adelanto de Fase.

El compensador de atraso-adelanto de fase representa una solución intermedia que permite obtener los beneficios de ambos tipos de compensación. Esta combinación posibilita mejorar los márgenes de estabilidad y el ancho de banda mientras se mantiene un error en estado estacionario reducido, todo ello minimizando los problemas asociados con el ruido.

---

## 3. Control PID:
El control PID puede entenderse como un caso especial de una red de atraso-adelanto, donde la parte PD del controlador actúa en la región de alta frecuencia para mejorar la estabilidad del sistema. Esta estructura permite una comprensión más intuitiva de cómo cada componente del PID afecta al comportamiento del sistema.

![Diagrama de Bloques de un Controlador PID: Estructura y Función de sus Componentes](https://github.com/user-attachments/assets/13024185-7b97-4b91-ad33-3fa755ab9d9b)

Figura 3. Diagrama de Bloques de un Controlador PID: Estructura y Función de sus Componentes.

Aunque es posible sintonizar un controlador PID mediante análisis en frecuencia, en la práctica industrial se prefiere realizar la sintonización en el dominio del tiempo. Esta preferencia se debe a la simplicidad y efectividad de los métodos de sintonización temporal, que han demostrado ser más accesibles para los operadores en entornos industriales.

---

## 4. Margenes de estabilidad:
El margen de ganancia se define como el cambio necesario en la ganancia de lazo abierto para llevar al sistema al límite de la estabilidad, y se mide en decibeles (dB). Este margen se evalúa en el punto donde la fase del sistema cruza los -180 grados, proporcionando una medida cuantitativa de la robustez del sistema.

![Análisis de Márgenes de Ganancia y Fase en Sistemas de Control](https://github.com/user-attachments/assets/7494997a-9ffd-4986-a47f-048aa7d89129)

Figura 4. Análisis de Márgenes de Ganancia y Fase en Sistemas de Control.

El margen de fase, medido en grados, indica cuánto cambio en la fase puede tolerar el sistema antes de volverse inestable. Ambos márgenes, tanto de ganancia como de fase, deben ser positivos para garantizar la estabilidad del sistema en lazo cerrado, y se recomienda que sean tan grandes como sea posible para asegurar un comportamiento robusto.

---

## 5. Procedimiento de diseño:
El proceso comienza con la discretización de la planta analógica para obtener $$G(z)$$, seguida de su transformación a G(w). Esta secuencia de transformaciones permite aplicar las técnicas de análisis en frecuencia a sistemas discretos, manteniendo la familiaridad de los métodos continuos.

![Respuesta de una señal a diferentes valores de ganancia](https://github.com/user-attachments/assets/c86dc589-7afa-418c-a726-8818331a02ed)

Figura 5. Respuesta de una señal a diferentes valores de ganancia
Una vez diseñado el controlador $$C(w)$$, es necesario recuperar $$C(z)$$ para su implementación práctica en un sistema digital. Este paso final asegura que el diseño teórico pueda ser programado y aplicado efectivamente en un controlador real.

---

## 6. Metodología de diseño para red de atraso:
El proceso comienza calculando la ganancia proporcional $$Kp$$ necesaria para cumplir con los requisitos de error. Posteriormente, se miden los márgenes considerando esta ganancia, lo que proporciona una base para determinar qué ajustes adicionales son necesarios.

![Análisis del Lugar de las Raíces para la Estabilidad del Sistema de Control](https://github.com/user-attachments/assets/cd184abf-9e2f-4a82-b48a-adc3810bf5a1)

Figura 6. Análisis del Lugar de las Raíces para la Estabilidad del Sistema de Control.

La metodología continúa con el cálculo de la frecuencia necesaria para cumplir con el margen de fase deseado, seguido de la medición de la atenuación requerida. Finalmente, se calcula la constante de tiempo $$T1$$, que es un parámetro crítico para la implementación de la red de atraso.

---

## 7. Conclusiones

Visualización y Evaluación: El uso del diagrama de Bode como herramienta visual no solo facilita la comprensión del comportamiento del sistema en diferentes frecuencias, sino que también permite la evaluación directa de los márgenes de estabilidad, simplificando el proceso de diseño y ajuste de sistemas de control.

Flexibilidad en el Control PID: La estructura del controlador PID, considerada una red de atraso-adelanto, permite una sintonización intuitiva y eficaz, y aunque el análisis en frecuencia es viable, la preferencia por la sintonización en el dominio del tiempo en la práctica industrial resalta la importancia de métodos accesibles y efectivos en entornos reales.

## 8. Referencias
[1] "Diseño de redes de atraso por análisis en frecuencia" Curso Control Digital.
