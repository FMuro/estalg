+++
title = "Cuerpos"
weight = 30
+++

¿Sabías que es imposible construir un heptágono regular con una regla y un compás? ¿Sabías que también es imposible construir de este modo un cuadrado con la misma área que un círculo dado? Este último problema se conoce como la **cuadratura del círculo**. Fue planteado en la antigüedad y permaneció abierto hasta finales del siglo XIX.

Seguro que sabes que la única raíz de un polinomio de grado 1, $ax+b$, es

$$x=-\frac{b}{a}.$$

También sabes que las raíces de uno de grado 2, $ax^2+bx+c$, son

$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}.$$

Es menos conocido que las raíces de un polinomio de grado 3, $ax^3+bx^2+cx+d$, son 

$$
x=
\left\\{
\begin{array}{l}
S+T−\frac{b}{3a},\cr
-\frac{S+T}{2}−\frac{b}{3a}+\frac{i\sqrt{3}}{2}(S−T),\cr
-\frac{S+T}{2}−\frac{b}{3a}-\frac{i\sqrt{3}}{2}(S−T),
\end{array}
\right.
$$

donde

$$
\begin{array}{rcl}
S&=&\sqrt[3]{R+\sqrt{Q^3+R^2}},\cr
T&=&\sqrt[3]{R-\sqrt{Q^3+R^2}},\cr
Q&=&\frac{3ac-b^2}{9a^2},\cr
R&=&\frac{9abc-27a^2d-2b^3}{54a^3}.
\end{array}
$$

De aquí surge por tanto la siguiente cuestión natural: ¿Es posible expresar las raíces de un polinomio de cualquier grado a partir de sus coeficientes mediante sumas, multiplicaciones y raíces iteradas? Esto se denomina resolver una ecuación polinómica por **radicales**. Esta importante pregunta es también de origen antiguo y permaneció abierta hasta el siglo XIX, cuando fue resuelta por [Galois](https://en.wikipedia.org/wiki/%C3%89variste_Galois). La respuesta es sencilla, aunque llegar a ella no es fácil: hasta grado 4 sí, de grado 5 en adelante, en general, no. Un ejemplo de polinomio de grado 5 cuyas raíces no se pueden hallar por radicales es el siguiente, a pesar de su aparente sencillez,

$$x^5-16x+2.$$

A lo largo de este capítulo estudiaremos las matemáticas necesarias para resolver estas y otras cuestiones relacionadas.
