# Señales y Sistemas

+ > Una `señal` se puede pensar como si fuera una función matemática que lleva o que contiene información acerca del estado o comportamiento de de un cierto `sistema` físico {cite}`oppenheim99`.

+ > Aunque existen muchas maneras diferentes de `visualizar` una señal y la información que lleva, lo significativo es que dicha información, está contenida en ciertos tipos de `patrones` que pueden varíar {cite}`Morales`.

![Figura Señal2](Gabriel.png)

## Cómo se representa una señal?

+ > Las `señales` se representan matemáticamente como funciones de una o más variables independientes.

+ > En el caso de un sonido, la señal se representa como una función de una `sola variable`, que es el `tiempo`. Mientras que, en una imagen digital, estas se representan como una `función de dos variables`, $x(m,n)$, como se observa en la siguiente figura, donde $(m,n)$ representan las coordenadas espaciales y $x$ representa la intensidad (brillo) en ese pixel. 

![Figura Image](image.png)

+ > Es común, en el caso de sonido,  referirse a la variable independiente de la representación matemática de una señal como el `tiempo`. 

+ > En la representación matemática de una señal acústica, la variable independiente, puede ser `continua` o `discreta`.

+ > Las señales de tiempo continuo se refieren como `señales análogas`.

+ > Las señales de tiempo discreto se definen en `tiempos discretos` y en consecuencia la variable independiente toma valores discretos.

+ > Las `señales en tiempo discreto` se representan como secuencias de números.

+ > Una secuencia es simplemente una función cuyo dominio es el conjunto de los números enteros $\mathbb{Z}$.

+ > Formalmente, una secuencia de números $x$, en la que el `$n$-ésimo` número en la secuencia se denota como $x\,[\,n\,]$, donde $n$ es un entero, se escribe como:

$$
\begin{align*}
x&=\{x\,[\,n\,]\},\quad \quad -\infty < n < \infty 
\label{eq1}\tag{1}
\end{align*}
$$

```{note}
En la secuencia (o función), se usó $[\,]$ para encerrar a la variable independiente.
```

```{note}
En funciones de tiempo continuo, se usa $(\,)$ para encerrar a la variable independiente continua.
```
+ > A partir de un muestreo (`sampling`) de una señal continua $x_{c}(t)$, el valor numérico del $n$-ésimo número en la secuencia, es igual al valor de la señal continua $x_{c}(t)$ en el tiempo $nT_{s}$. Es decir,

$$
\begin{align*}
x\,[\,n\,]&=x_{c}\,(\,n\,T_{s}\,),\quad \quad -\infty < n < \infty 
\label{eq2}\tag{2}
\end{align*}
$$


```{note}
Representación gráfica de una señal en tiempo discreto
```

![Figura sampling](sampling.png)

## Secuencias fundamentales

+ > `Secuencia impulso unitario`: Esta señal se denota como $\delta[n]$ y se define como:

$$
\begin{align*}
\text{centrada en cero:}\quad \delta[n] &= \begin{cases}
1, & \text{para } n = 0 \\
0, & \text{otro caso}
\label{eq3}\tag{3}
\end{cases}
\end{align*}
$$

$$
\begin{align*}
{\it{Shifteada}:}\quad  \delta[n-k] &= \begin{cases}
1, & n = k \\
0, & n \neq k
\end{cases}
\label{eq4}\tag{4}
\end{align*}
$$

+ > Una propiedad muy importante de la secuencia $\delta[n]$, es que cualquier señal se podría  representar como una suma escalada de impulsos desplazados (*shifteados*):

$$
\begin{align*}
x\,[\,n\,] \, &=\, \sum_{k=-\infty}^{\infty}\, x\,[\,k\,]\cdot \delta[\,n\,-\,k\,]
\label{eq5}\tag{5}
\end{align*}
$$

+ > `Secuencia escalón unitario`:

$$
\begin{align*}
u[n] &= \begin{cases}
1, & \text{para } n \ge 0 \\
0, & n < 0
\label{eq6}\tag{6}
\end{cases}
\end{align*}
$$

+ > La secuencia $u[n]$ está relacionada a la secuencia impulso $\delta[n]$:

$$
\begin{align*}
u\,[\,n\,] \, &=\, \delta\,[\,n\,] + \delta\,[\,n-1\,]+ \delta\,[\,n-2\,]+\ldots 
\label{eq7a}\tag{7a}
\end{align*}
$$

+ > O bien,

$$
\begin{align*}
u\,[\,n\,]\, &=\, \sum_{k=0}^{\infty} \delta\,[\,n-k\,]
\label{eq7b}\tag{7b}
\end{align*}
$$

> + Además, la secuencia impulso unitario, se puede expresar como:

$$
\begin{align*}
\delta\,[\,n\,] \, &=\, u\,[\,n\,] - u\,[\,n-1\,]
\label{eq8}\tag{8}
\end{align*}
$$

# Sistemas

+ > Un `sistema` es un proceso que transforma una señal en otra señal.

+ > Al igual que en el caso de las señales, los `sistemas de tiempo continuo` son aquellos sistemas para los que la entrada y la salida son señales de tiempo continuo.

+ > Y los `sistemas de tiempo discreto` son aquellos sistemas para los que la entrada y la salida son señales de tiempo discreto.

+ > Se representa un sistema de manera gráfica en la forma de relaciones de `Entrada` y `Respuesta`.

![Figura Sistema](sistema.png)

```{note}
Por conveniencia, la señal de entrada se suele etiquetar como $x\,[\,n\,]$ mientras que la señal de salida, se etiqueta como $y\,[\,n\,]$.
```

## Propiedades de los sistemas

+ > `Aditividad:` Esto significa que cuando al sistema se le da la suma de diferentes señales de entrada, el resultado es la suma de las salidas de cada entrada por separado:

<img src="add.png" alt= “” width="1200" height="200">

+ > `Escalamiento:` Quiere decir que cuando uno multiplica por un escalar $c$ una señal de entrada a un sistema, la salida también se multiplica por el mismo escalar:

<img src="scaling.png" alt= “” width="400" height="100">

+ > `Sistema Lineal y Principio de Superposición:` Se refiere a que si las respuestas de un sistema son $y_1[n]$ e $y_2[n]$, cuando $x_1[n]$ y $x_2[n]$ son las entradas respectivas, entonces el sistema es `lineal` si y sólo si se cumplen las propiedades de aditividad y escalamiento, tal como se observa en las Ecs. (9) y (10):

$$
\begin{align*}
T\{x_1\,[\,n\,] + x_2\,[\,n\,]\} \, &=\, T\{x_1\,[\,n\,]\} \, + \, T\{x_2\,[\,n\,]\}
\label{eq9}\tag{9}
\end{align*}
$$

$$
\begin{align*}
T\{c\,\cdot x\,[\,n\,]\} \, &=\, c\,\cdot T\{x\,[\,n\,]\}
\label{eq10}\tag{10}
\end{align*}
$$

+ > Estas dos propiedades se pueden combinar en el `Principio de Superposición:`

$$
\begin{align*}
T\{c_1\,\cdot x_1\,[\,n\,] + c_2\,\cdot x_2\,[\,n\,]\} \, &=\, c_1\,\cdot T\{x_1\,[\,n\,]\} + c_2\,\cdot T\{x_2\,[\,n\,]\}
\label{eq11}\tag{11}
\end{align*}
$$

donde $c_1$ y $c_2$ son escalares arbitrarios.

+ > Este Principio de Superposición se puede generalizar a muchas entradas. Específicamente, si

$$
\begin{align*}
x\,[\,n\,]\, &=\, \sum_{k}^{} c_k \, x_k\,[\,n\,]
\label{eq12}\tag{12}
\end{align*}
$$

entonces:

$$
\begin{align*}
y\,[\,n\,]\, &=\, \sum_{k}^{} c_k \, y_k\,[\,n\,]
\label{eq13}\tag{13}
\end{align*}
$$

+ > `Invariancia en el tiempo:` Esta propiedad se refiere a que un sistema es `invariante en el tiempo` si cumple con que un cambio de tiempo arbitrario en la señal de entrada dada, va a producir el mismo cambio de tiempo en la salida. Si $y\,[\,n\,] \,=\, T\{x\,[\,n\,]\}$, entonces $y\,[\,n\,-\,n_0\,] \,=\, T\{x\,[\,n\,-\,n_0\,]\}$, donde $n_0$ es un corrimiento arbitrario de tiempo.

## Sistemas Lineales e Invariantes en el Tiempo

+ > Representan una clase de sistemas muy importantes en procesamiento de señales. Se dice que un sistema que posee las dos propiedades: `linealidad` e `invariancia en el tiempo`, es un sistema lineal e invariante en el tiempo. También se les identifica como o `sistemas LTI`.

+ > Los `sistemas LTI` siempre se consideran con respecto a la `respuesta de impulso unitario`. Esto quiere decir que cuando la entrada es la señal de impulso unitario, entonces la salida es la respuesta de impulso.

![Figura Sistema](h.png)

+ > En la figura, la entrada al sistema es una señal de impulso, $x\,[\,n\,] = \delta\,[\,n\,]$, y la salida es la respuesta del sistema al impulso:

$$
\begin{align*}
y\,[\,n\,]\, &=\, h\,[\,n\,]= T\{\delta\,[\,n\,]\}
\label{eq14}\tag{14}
\end{align*}
$$





<!---
## Learn more

This is just a simple starter to get you started.
You can learn a lot more at [jupyterbook.org](https://jupyterbook.org).
-->

