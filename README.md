# Control Clásico

<iframe src="https://res.cloudinary.com/dp3gkrrd6/image/upload/v1741369402/02_Modelado_Matemático_de_Sistemas_de_Control_mw6pxa.pdf" width="100%" height="300px"></iframe>

[Ver PDF](https://res.cloudinary.com/dp3gkrrd6/image/upload/v1741369402/02_Modelado_Matemático_de_Sistemas_de_Control_mw6pxa.pdf)



# Unidad 02: Modelado Matemático de Sistemas de Control

## Actividades a realizar:

- **2.1** Introducción.  
- **2.2** Función de transferencia y de respuesta impulso.  
- **2.3** Sistemas de control automáticos.  
- **2.4** Modelado en el espacio de estados.  
- **2.5** Representación en el espacio de estados de sistemas de ecuaciones diferenciales escalares.  
- **2.6** Transformación de modelos matemáticos con MATLAB.  
- **2.7** Linealización de modelos matemáticos no lineales.  

## Tiempo empleado:

**20 minutos**

## Links y Lecturas:

- **Capítulo 2** – Katsuhiko Ogata, *Ingeniería de Control Moderna*, 5ta Edición.  
- **Capítulo 2** – Richard C. Dorf & Robert H. Bishop, *Sistemas de Control Moderno*, 10ma Edición.  
- **Diagramas de bloques – Parte 1** [Teoría del Control](https://www.youtube.com/watch?v=0x3UTw5iz4).  
- **Diagramas de bloques – Parte 2** [Teoría del Control](https://www.youtube.com/watch?v=MRQqnPCiTJE).  
- **Diagrama a bloques – Simplificación** [Teoría del Control](https://www.youtube.com/watch?v=dwprxT1ugM0).  

---

## Logro de la Unidad:

Al finalizar la **Unidad 02**, el estudiante será capaz de modelar sistemas dinámicos y analizar sus características.

---

## Definición de conceptos:

### Modelos matemáticos:

Los modelos matemáticos pueden adoptar muchas formas distintas. Dependiendo del sistema y de las circunstancias específicas, un modelo matemático puede ser más conveniente que otros.

### Simplicidad contra precisión:

Al obtener un modelo matemático se debe establecer un compromiso entre la **simplicidad** del mismo y la **precisión** de los resultados del análisis. Un modelo matemático simplificado a menudo ignora ciertas propiedades físicas inherentes al sistema.

### Sistemas lineales:

Un sistema se denomina **lineal** si se aplica el **principio de superposición**, el cual establece que la respuesta producida por la aplicación simultánea de dos funciones de entrada diferentes es la suma de las dos respuestas individuales.

---

# Sistemas Lineales Invariantes y Variantes en el Tiempo:

Una ecuación diferencial es **lineal** si sus coeficientes son constantes o dependen solo de la variable independiente.

- **Sistemas lineales invariantes en el tiempo (LTI):** Se describen mediante ecuaciones diferenciales con coeficientes constantes.  
- **Sistemas lineales variantes en el tiempo:** Se representan mediante ecuaciones diferenciales cuyos coeficientes varían con el tiempo.  

Ejemplo: Un sistema de control de naves espaciales es **variante en el tiempo**, ya que la masa de la nave cambia debido al consumo de combustible.

---

# 2.2 Función de Transferencia y Respuesta-Impulso

## Función de transferencia

La función de transferencia de un sistema descrito por una ecuación diferencial **lineal e invariante en el tiempo** se define como:

\[
G(s) = \frac{\mathcal{L}[\text{salida}]}{\mathcal{L}[\text{entrada}]}
\]

Bajo la suposición de que todas las condiciones iniciales son cero. Considérese la ecuación diferencial:

\[
a_0 y^{(n)} + a_1 y^{(n-1)} + \dots + a_{n-1} \dot{y} + a_n y = b_0 x^{(m)} + b_1 x^{(m-1)} + \dots + b_{m-1} x + b_m x
\]

Donde:

- \( y \) : Salida del sistema.  
- \( x \) : Entrada del sistema.  

La función de transferencia se expresa como:

\[
G(s) = \frac{b_0 s^m + b_1 s^{m-1} + \dots + b_{m-1} s + b_m}{a_0 s^n + a_1 s^{n-1} + \dots + a_{n-1} s + a_n}
\]

### Propiedades de la función de transferencia:

1. Es un modelo matemático que expresa la ecuación diferencial del sistema.  
2. Es una propiedad del sistema, independiente de la magnitud y naturaleza de la entrada.  
3. Incluye las unidades necesarias para relacionar entrada y salida, pero no describe la estructura física del sistema.  
4. Conociendo \( G(s) \), se puede analizar la respuesta del sistema ante diversas entradas.  
5. Si \( G(s) \) es desconocida, se puede determinar experimentalmente mediante pruebas con entradas conocidas.  

---

## Integral de Convolución:

Para un sistema **lineal e invariante en el tiempo**, la función de transferencia se expresa como:

\[
G(s) = \frac{Y(s)}{X(s)}
\]

Donde:

- \( X(s) \) es la transformada de Laplace de la entrada.  
- \( Y(s) \) es la transformada de Laplace de la salida.  

Si todas las condiciones iniciales son cero, la salida se expresa como:

\[
Y(s) = G(s) X(s)
\]

La multiplicación en el dominio complejo equivale a la **convolución en el dominio del tiempo**, por lo que la transformada inversa de Laplace se obtiene mediante la **integral de convolución**:

![Integral de convolución](https://storage.simpletex.cn/view/fuFWGnYqeswVzRHslOWilgzCfPCgWXxnZ)

---

## Respuesta-Impulso:

Se considera la salida del sistema cuando la entrada es un **impulso unitario** y las condiciones iniciales son cero.

Como la transformada de Laplace del impulso unitario es **1**, se obtiene:

\[
Y(s) = G(s)
\]

La transformada inversa de Laplace de \( G(s) \) se conoce como **respuesta-impulso** del sistema:

\[
\mathcal{L}^{-1} [G(s)] = g(t)
\]

- \( g(t) \) se denomina también **función de ponderación** del sistema.  
- La función de transferencia y la respuesta-impulso contienen la misma información sobre la dinámica del sistema.  
- Se puede obtener la dinámica del sistema excitándolo con un **impulso unitario** y midiendo su respuesta.  

---

## Linealización de Ecuaciones:

Si se linealizan las ecuaciones alrededor del estado de operación, se obtienen las siguientes **ecuaciones de estado y de salida linealizadas**:

![Ecuaciones linealizadas](https://storage.simpletex.cn/view/fZldeUEepAPVwzvtBGKCD3iixKpb28rNG)

Si las funciones del sistema son **invariantes en el tiempo**, las ecuaciones se simplifican a:

### **Ecuación de estado del sistema lineal invariante en el tiempo:**

\[
\dot{x}(t) = A x(t) + B u(t)
\]

### **Ecuación de salida:**

\[
y(t) = C x(t) + D u(t)
\]



![Ecuación de salida](https://storage.simpletex.cn/view/fWoIDOz3L9qVBWZkGCPZDXqTQAIslsyWx)
