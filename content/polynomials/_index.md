+++
title = "Polinomios"
weight = 40
+++

<!--

## Introducción




{{% definition %}}
{Polinomios con coeficientes en $A$}
{Sea $A$ un anillo. Llamaremos {\bf conjunto de polinomios con coe\-fi\-cien\-tes en $A$}, y lo denotaremos por $A[x]$, al conjunto de las expresiones de la forma
$$a(x)=a_mx^m+a_{m-1}x^{m-1}+\ldots+a_1x+a_0,$$
con los $a_i \in A$ y $m \in \N$.}
{{% /definition %}}

%Sea $k$ un cuerpo (por ejemplo, $\Q, \RR, \C, \F_p$). Denotaremos por $k[x]$ al conjunto de todas las expresiones de la forma
%$$a(x)=a_mx^m+a_{m-1}x^{m-1}+\ldots+a_1x+a_0,$$
%con los $a_i \in k$. De esta manera, $k[x]$ es el conjunto de todos los {\em{\bf polinomios con coeficientes en $k$}}. Dos polinomios son iguales si lo son coeficiente a coeficiente.

{{% definition %}}
{Grado}{
El {\em{\bf grado}} de un polinomio no nulo $a(x)$, notado $\mbox{grado}(a(x))$, es el mayor entero $n$ tal que $a_n\neq0$. El polinomio cuyos coeficientes son todos nulos se llama {\bf polinomio nulo} y se denota por $0$. Por convención, su grado es $\mbox{grado}(0)=-\infty$.}
{{% /definition %}}

{{% definition %}}
{Definiciones}{
Sea $a(x)=\sum_{i=0}^na_ix^i\in k[x]$ un polinomio no nulo con $a_n\neq0$ (de grado $n$). 

Llamaremos {\em{\bf término líder}} de $a(x)$ al término $a_nx^n$, {\em{\bf coeficiente líder}} a $a_n$ y {\em{\bf término constante}} a $a_0$. 

Un polinomio es {\em{\bf mónico}} si su coeficiente líder es $1$. Los polinomios se dicen {\em{\bf constantes}} cuando su grado es cero, así como el polinomio nulo.}
{{% /definition %}}

{{% watch %}}
 Los polinomios se pueden sumar y multiplicar, extendiendo las operaciones de $A$:

Si $a(x)=\sum_{i=0}^na_ix^i$, $b(x)=\sum_{i=0}^mb_ix^i$, suponiendo sin pérdida de generalidad que $m\geq n$, podemos definir la suma como
$$a(x)+b(x)=\sum_{i=0}^n(a_i+b_i)x^i+b_{n+1}x^{n+1}+\ldots+b_mx^m.$$
Cuando $m=n$, basta quedarnos con el primer sumando de la expresión anterior.

Tomando de nuevo $a(x)$ y $b(x)$, su producto está definido como:
$$d(x)=a(x)b(x)=\sum_{l=0}^{m+n}d_lx^l,\quad\text{donde}\quad d_l=\sum_{i+j=l}a_ib_j.$$

Estando así definidas las operaciones, es claro que extienden las de $A$; basta tomar $m=n=0$. Por otro lado, también es evidente que tenemos\footnote{Para ser estrictos, esto es cierto siempre y cuando asumamos que $-\infty<n$ y $-\infty+n=-\infty$ para cualquier $n\geq0$.} 
\begin{itemize}
\item $\mbox{grado}(a(x)+b(x))\leq\max\\{\mbox{grado}(a(x)),\mbox{grado}(b(x))\\}$, no dándose la igualdad solamente cuando $m=n$ y $a_m+b_n=0$.
\item $\mbox{grado}(a(x)b(x))\leq\mbox{grado}(a(x))+\mbox{grado}(b(x))$ (se da la igualdad cuando $A$ es dominio de integridad).
\end{itemize}
{{% /watch %}}

Es fácil comprobar que la suma y el producto de polinomios verifican las propiedades asociativa y distributiva, además de poseer la suma elemento neutro, elemento opuesto y ser conmutativa. En otras palabras:

{{% theorem %}}
{El anillo $A[x]$}
{El conjunto $A[x]$ con la suma y producto definidos anteriormente es un anillo. Además:
\begin{itemize}
\item Si $A$ es un anillo conmutativo, $A[x]$ es conmutativo.
\item Si $A$ es un anillo con elemento unidad, $A[x]$ tiene elemento unidad.
\item Si $A$ es dominio de integridad, $A[x]$ es dominio de integridad.
\end{itemize}
}
{{% /theorem %}}

{{% theorem %}}
{Unidades de $A[x]$}
{Si $A$ es un dominio de integridad, un polinomio de $A[x]$ es una {\bf unidad} si y sólo si es una constante y es una unidad en $A$. Es decir, el grupo multiplicativo $A[x]^*$ de las unidades de $A[x]$ es el grupo $A^*$ de las unidades de $A$.}
{{% /theorem %}}

## El anillo $k[x]$. Divisibilidad

En adelante consideraremos principalmente el anillo de polinomios $k[x]$, donde $k$ es un cuerpo (por ejemplo, $\Q, \RR, \C, \F_p$). Este anillo de polinomios es un dominio de integridad, conmutativo y unitario. Sus unidades son las de $k$, es decir, $k^*=k\setminus\\{ 0\\}$. El grado de los polinomios puede ser usado como una medida que, a modo del valor absoluto en los enteros, nos permite realizar la división euclídea. Veremos que ésta no es la única similitud con $\Z$.

{{% theorem %}}
{Teorema de división}
{Sean $f(x),g(x)\in k[x]$ dos polinomios, con $g(x)\neq0$. Entonces, existen dos únicos polinomios $q(x),r(x)\in k[x]$ tales que
$$f(x)=q(x)g(x)+r(x)$$
y $\mbox{grado}(r(x))<\mbox{grado}(g(x))$.}
{{% /theorem %}}
{{% proof %}}

La demostración es constructiva, indicando cómo se calculan cociente y resto de la división euclídea.\\
Si $\mbox{grado}(f(x))<\mbox{grado}(g(x))$ tomamos $q(x)=0$, $r(x)=f(x)$, y ya hemos terminado nuestra construcción.



Supongamos ahora que $\mbox{grado}(f(x))\geq\mbox{grado}(g(x))$ y sean $ax^m,bx^n$ los términos líder de $f(x),g(x)$ respectivamente. Escribamos
$$f_1(x)=f(x)-(a/b)x^{m-n}g(x);$$
así pues $f_1(x)$ es un polinomio de grado estrictamente inferior al de $f(x)$ y escogiendo $q_1(x)=(a/b)x^{m-n}$, tenemos que $f(x)=q_1(x)g(x)+f_1(x)$.

Aplicando el mismo razonamiento a $f_1(x)$ y así sucesivamente, logramos crear un conjunto finito de igualdades del tipo
$$\begin{array}{rcl}
f(x) & = & q_1(x)g(x)+f_1(x)\\
f_1(x) & = & q_2(x)g(x)+f_2(x)\\
\vdots & & \vdots\\
f_{t-1}(x) & = & q_t(x)g(x)+f_t(x),
\end{array}$$
donde
$$\mbox{grado}(f_1(x))>\mbox{grado}(f_2(x))>\ldots>\mbox{grado}(f_t(x))$$
y como vamos descendiendo al menos una unidad el grado en cada $f_i(x)$, o bien $f_t(x)=0$ o bien es de grado inferior al de $g(x)$, y de ahí la finitud del proceso. Poniendo
$$q(x)=\sum_{i=1}^t q_i(x), \; r(x)=f_t(x)$$
se tiene $f(x)=q(x)g(x)+r(x)$.



Hemos probado la existencia. Probemos ahora la unicidad. Consideremos pues dos expresiones para $f(x)$ que verifiquen las propiedades que establece el teorema de división:
$$f(x)=q(x)g(x)+r(x)=q'(x)g(x)+r'(x);$$
entonces
$$r(x)-r'(x)=(q'(x)-q(x))g(x),$$
con lo que $r(x)-r'(x)$ debe ser nulo, ya que todo múltiplo no nulo de $g(x)$ tiene que ser de grado mayor o igual que él.
{{% /proof %}}

\begin{metodocolor}{Algoritmo de división}
{Para calcular el cociente y el resto de la división entre $f(x)$ y $g(x)$, de grados respectivos $m$ y $n$.\\
Si $m\geq n$ tome
$$f_1(x)=f(x)-(a/b)x^{m-n}g(x)\text{ ,  }q_1(x)=(a/b)x^{m-n}.$$
Repita con $f_1(x)$ y $g(x)$ hasta que $\mbox{grado}(f_t(x))<\mbox{grado}(g(x))$. El cociente y el resto son
$$q(x)=q_1(x)+\ldots+q_{t-1}(x)\text{, }r(x)=f_t(x).$$
Si $m<n$, el cociente es 0 y el resto el propio $f(x)$.}
\end{metodocolor}

Veamos cómo funciona esto último con un ejemplo, que nos acompañará por nuestra lectura de las próximas secciones.

{{% example name="Ejemplo" %}}

Sean 
$$
f(x)=x^5-\frac{1}{2}x^3+2x^2-3x+3, \quad 
g(x)=2x^3-\frac{2}{3}x^2+3x-1
$$ 
dos polinomios de $\Q[x]$. Si queremos calcular el cociente y el resto de la división de $f(x)$ entre $g(x)$, tomamos en primer lugar
$$f_1(x)=f(x)-\frac{1}{2}x^2g(x)=\frac{1}{3}x^4-2x^3+\frac{5}{2}x^2-3x+3.$$
Como $\mbox{grado}(f_1(x))=4$, seguimos. Sea ahora
$$f_2(x)=f_1(x)-\frac{1}{6}xg(x)=-\frac{17x^3}{9}+2x^2-\frac{17x}{6}+3.$$
Tenemos que seguir, pues todavía no hemos bajado de grado 3, pero este será el último paso. Así,
$$f_3(x)=f_2(x)+\frac{17}{18}g(x)=\frac{37 x^2}{27}+\frac{37}{18}.$$
Ahora ya hemos terminado. El cociente y el resto de la división son
$$q(x)=\frac{1}{2}x^2+\frac{1}{6}x-\frac{17}{18}, \quad r(x)=\frac{37}{27}x^2+\frac{37}{18}.$$
{{% /example %}}



La división euclídea establece un paralelismo claro entre $k[x]$ y $\Z$ que tiene su reflejo más inmediato en el siguiente corolario.

{{% corollary %}}

Sea $I \subset k[x]$ un ideal. Entonces $I$ es un ideal principial. Eso es, existe $m(x) \in k[x]$ tal que 
$$
I = (m(x)) = \\{ f(x)m(x) \; | \; f(x) \in k[x] \\}.
$$
{{% /corollary %}}

{{% proof %}}

Queda como ejercicio, al ser similar a la equivalente para enteros.
{{% /proof %}}

Algunos otros resultados, circunscritos en este caso al anillo $k[x]$ son los suiguientes.

{{% corollary %}}
{\bf (Teorema del resto)}
Sea un polinomio $f(x)\in k[x]$, y sea un elemento del cuerpo $a\in k$. Entonces $f(a)$ es el
resto de dividir $f(x)$ por $x-a$.
{{% /corollary %}}
{{% proof %}}

Por el teorema de división,
$$f(x)=(x-a)q(x)+r(x)\text{, con }\mbox{grado}(r(x))<\mbox{grado}(x-a)=1.$$
Por tanto, $r(x)$ debe ser constante, digamos $r$, luego $f(a)=(a-a)q(a)+r=r$.
{{% /proof %}}

{{% definition %}}
{Raíz de un polinomio}
{Sea $f(x)\in A[x]$ un polinomio, se dice que $a\in A$ es una {\bf raíz de $f(x)$} si $f(a)=0$.}
{{% /definition %}}

{{% corollary %}}
{\bf (Teorema de la raíz)}
Sea un polinomio $f(x)\in k[x]$ de grado positivo. Entonces $f(x)$ tiene una {\em\bf{raíz}} $a\in k$ si y sólo si es divisible por $x-a$.
{{% /corollary %}}

{{% proof %}}

En efecto, podemos escribir $f(x)=q(x)(x-a)+r$ con $r\in k$. Así $f(a)=0$ si y sólo si $r=0$, lo que equivale a que $(x-a)|f(x)$.
{{% /proof %}}

{{% definition %}}
{Multiplicidad de una raíz}
{Sean $f(x)\in A[x]$ un polinomio y $a\in A$ una raíz. Se llama multiplicidad de $a$ al mayor entero positivo $m$ tal que $(x-a)^m$ divide a $f(x)$.}
{{% /definition %}}

{{% corollary %}}
{\bf (D'Alembert)}
Un polinomio no nulo $f(x)\in k[x]$ de grado $n$ tiene a lo sumo $n$ raíces distintas en $k$.
{{% /corollary %}}
{{% proof %}}

Lo probaremos por inducción en $n$, el grado de $f(x)$.



Si $\mbox{grado}(f(x))=0$, entonces $f(x)$ es un polinomio constante no nulo, luego no tiene raíces en $k$. Nuestra hipótesis de inducción es que si $h(x)$ es polinomio no nulo de grado $n-1$ con $r$ raíces distintas, entonces $r\leq n-1$.



Supongamos ahora que $f(x)$ es un polinomio de grado $n>0$ y que tiene $r$ raíces distintas $a_1,\ldots,a_r$ en $k$. Veamos que $r\leq n$.



Tenemos que $f(a_r)=0$, luego por el teorema de la raíz $f(x)=(x-a_r)g(x)$, con $\mbox{grado}(g(x))=n-1$. Para cada $i$ con $1\leq i\leq r-1$, $$
f(a_i)=0=(a_i-a_r)g(a_i).
$$ 
Como $a_i\neq a_r$, por fuerza $g(a_i)=0$. En consecuencia $a_1,\ldots,a_{r-1}$ son raíces de $g(x)$ y $\mbox{grado}(g(x))=n-1$. Por inducción, $r-1\leq n-1$, así que $r\leq n.$
{{% /proof %}}

{{% watch %}}

Hay que hacer notar que este corolario no implica el aserto de que todo polinomio posee tantas raíces como su grado. Este teorema es mucho más profundo e interesante y necesita conceptos que no veremos hasta más tarde.
{{% /watch %}}



## Máximo común divisor

Continuan los parecidos razonables entre $k[x]$ y $\Z$, pues al igual que cuando manejamos los enteros, con el teorema de división para polinomios podemos trabajar la divisibilidad de polinomios, el algoritmo de Euclides y la identidad de Bézout.

{{% definition %}}
{Máximo común divisor}{
Sean dos polinomios $f(x),g(x)\in k[x]$. Un polinomio $p(x)\in k[x]$ es un {\em{\bf máximo común divisor}} de $f(x)$ y $g(x)$ si verifica:
\begin{enumerate}
\item $p(x)|f(x)$ y $p(x)|g(x)$
\item Si $q(x)$ es otro polinomio que divide a $f(x)$ y a $g(x)$ entonces $q(x)|p(x)$.
\end{enumerate}}
{{% /definition %}}

{{% watch %}}

El máximo común divisor de dos polinomios no es único. Si $p(x)=\mbox{mcd}(f(x),g(x))$, entonces, para cualquier $a\in k\setminus\\{0\\}$, $ap(x)=\mbox{mcd}(f(x),g(x))$. Por eso cuando hablamos de un máximo común divisor, podremos acordar que estamos tomando un polinomio mónico y, en esas condiciones, sí que es único.
{{% /watch %}}

Como en los enteros, podemos calcular un máximo común divisor de dos polinomios usando el teorema de división. Consideremos para ello dos polinomios $f(x),g(x)\in k[x]$. Sabemos que existen $q(x),r(x)\in k[x]$ con $\mbox{grado}(r(x))<\mbox{grado}(g(x))$ tales que 
$$f(x)=q(x)g(x)+r(x).$$

{{% proposition %}}

Con las notaciones anteriores, se tiene que
$$\mbox{\em mcd}(f(x),g(x))=\mbox{\em mcd}(g(x),r(x))$$
{{% /proposition %}}
{{% proof %}}

Supongamos que
$$a(x)=\mbox{mcd}(g(x),r(x)), \; b(x)=\mbox{mcd}(f(x),g(x)).$$
Como $f(x)=q(x)g(x)+r(x)$, $a(x)$ no puede sino dividir a $f(x)$ y así $a(x)$ es un divisor común de $f(x)$ y $g(x)$, luego por ser $b(x)$ el máximo entre ellos, $a(x)|b(x)$.



Análogamente, como
$$r(x)=f(x)-q(x)g(x),$$
se tiene que  $b(x)|r(x)$ y así $b(x)$ es un divisor común de $g(x)$ y $r(x)$, luego $b(x)|a(x)$.
{{% /proof %}}

{{% theorem %}}
{Algoritmo de Euclides}
{Sean $f(x),g(x)\in k[x]$ dos polinomios no nulos, con $\mbox{grado}(f(x))>\mbox{grado}(g(x))$. Entonces, si haciendo divisiones sucesivas obtenemos
$$\begin{array}{lcl}
  f(x) &=& q(x)g(x)+r(x)\\
  g(x) &=& q_0(x)r(x)+r_1(x)\\
  r(x) &=& q_1(x)r_1(x)+r_2(x)\\
  & \vdots\\
  r_{n-2}(x) &=& q_{n-1}(x)r_{n-1}(x)+r_n(x)\\
  r_{n-1}(x) &=& q_n(x)r_n(x),
\end{array}$$
este proceso es finito y, con las notaciones anteriores, $\mbox{mcd}(f(x),g(x))=r_n(x)$.}
{{% /theorem %}}

{{% proof %}}

Consideremos la sucesión $\\{\mbox{grado}(r_i(x))\\}$, que es una sucesión estrictamente decreciente de enteros no negativos, pues el resto de la división polinómica es de menor grado que el divisor. Como el primer elemento es $\mbox{grado}(f(x))$, la sucesión puede tener a lo más $\mbox{grado}(f(x))+1$ elementos. Por tanto, existe un $n \geq 1$ tal que $r_{n+1}(x)=0$. Esto prueba la finitud del proceso.



Ahora queda preguntarse si realmente obtenemos el máximo común divisor de $f(x)$ y $g(x)$. Para la respuesta basta con aplicar el resultado anterior para obtener que
$$\mbox{mcd}(f(x),g(x))=\mbox{mcd}(g(x),r(x))=\ldots=\mbox{mcd}(r_{n-1}(x),r_{n}(x))=r_n(x).$$
{{% /proof %}}

Así pues, con este teorema hemos probado que el siguiente algoritmo es correcto:

\begin{metodocolor}{Algoritmo de Euclides}
{Para hallar el máximo común divisor de dos polinomios no nulos $f(x),g(x)\in k[x]$.\\
Efectúe la división $f(x)=q(x)g(x)+r(x)$ y tome $f_0(x)=f(x)$, $g_0(x)=g(x)$ y $r_0(x)=r(x)$. Mientras $r_i(x)\neq0$, repita con $f_{i+1}(x)=g_i(x)$ y $g_{i+1}(x)=r_i(x)$.\\
Si $r_{n+1}(x)=0$, $\mbox{mcd}(f(x),g(x))=r_n(x)$, notando $r_{-1}(x)=g(x)$.}
\end{metodocolor}

Como en la sección anterior, ilustremos el método de arriba con los mismos polinomios:

{{% example name="Ejemplo" %}}

Queremos hallar el máximo común divisor de 
$$
f(x)=x^5-\frac{1}{2}x^3+2x^2-3x+3, \quad g(x)=2x^3-\frac{2}{3}x^2+3x-1
$$ 
en $\Q[x]$. Siguiendo el algoritmo, dividimos el primero entre el segundo, y tomamos
$$f_0(x)=f(x)\text{,  }g_0(x)=g(x)\text{,  }r_0(x)=\frac{37}{27}x^2 +\frac{37}{18}.$$
Como $r_0(x)\neq0$, dividimos $g(x)$ entre $r_0(x)$, tomando
$$f_1(x)=g(x)\text{,  }g_1(x)=r_0(x)\text{,  }r_1(x)=0.$$
La división anterior era exacta de cociente $(18/37)(3x-1)$, con lo que $\mbox{mcd}(f(x),g(x))=r_0(x)$, o tomando el polinomio mónico asociado,
$$\mbox{mcd}(f(x),g(x))=x^2+\frac{3}{2}.$$
{{% /example %}}



Hemos demostrado la validez del algoritmo de Euclides. Como pasaba en la primera sección, a pesar de ser un resultado aparentemente trivial, esconde algunas aplicaciones, siendo la primera de ellas la identidad de Bézout.

{{% theorem %}}
{Identidad de Bézout}
{Sean $f(x),g(x)\in k[x]$ dos polinomios no nulos. Si denotamos $\mbox{mcd}(f(x),g(x))=d(x)$ entonces existen elementos $a(x),b(x)\in k[x]$ tales que
$$d(x)=a(x)f(x)+b(x)g(x).$$}
{{% /theorem %}}

{{% proof %}}

La demostración es consecuencia de aplicar el algoritmo de Euclides al revés.\\
En efecto, si con la notación del teorema, llamamos $r_n(x)=d(x)$, tendremos que
$$\begin{array}{rl}
r_n(x)=&r_{n-2}(x)-q_{n-1}(x)r_{n-1}=\\
      =&r_{n-2}(x)-q_{n-1}(x)(r_{n-3}(x)-q_{n-2}(x)r_{n-2}(x))=\\
       &\vdots\\
      =&\tilde{a}(x)r(x)+\tilde{b}(x)g(x)=\\
      =&\tilde{a}(x)f(x)+(\tilde{b}(x)-\tilde{a}(x)q(x))g(x).
\end{array}$$
Tomando $a(x)=\tilde{a}(x)$ y $b(x)=(\tilde{b}(x)-\tilde{a}(x)q(x))$, tenemos lo que queríamos.

Es posible dar una prueba distinta (no efectiva), siguiendo la expuesta en el tema anterior para los enteros, ya que solo se usa que todos los ideales del anillo son principales, y este es un hecho que también se verifica en $k[x]$.
{{% /proof %}}

{{% example name="Ejemplo" %}}

Sabemos que 
$$
\mbox{mcd} \left( x^5-\frac{1}{2}x^3+2x^2-3x+3, 2x^3-\frac{2}{3}x^2+3x-1 \right)=x^2+\frac{3}{2}. 
$$
?`Cuáles son los polinomios $a(x)$ y $b(x)$ de la identidad de Bézout para ellos? Siguiendo el algoritmo de Euclides realizado anteriormente para ellos,
$$d(x)=\frac{27}{37}f(x)-\frac{27}{37}\left(\frac{1}{2}x^2+\frac{1}{6}x-\frac{17}{18}\right)g(x),$$
luego 
$$
a(x)=\frac{27}{37}, \quad b(x)=-\frac{27}{37}q(x).
$$
{{% /example %}}



## Factorización. Factores múltiples

Continuando con las analogías con el anillo de los enteros, vamos a ver qué elementos juegan el papel en el anillo de polinomios $k[x]$ de los números primos, y una vez que los hayamos identificado, trabajaremos un poco con ellos y con la noción de factorización.

{{% definition %}}
{Polinomio irreducible}
{Un polinomio $p(x)\in k[x]$ es {\em{\bf irreducible}} si no es una constante, y si el que podamos escribir $p(x)=f(x)g(x)$ implica que uno de los dos factores sea una unidad (una constante).}
{{% /definition %}}

{{% proposition %}}

Sea $p(x)\in k[x]$ un polinomio irreducible. Si $f(x)$ es un polinomio que no es divisible por $p(x)$, entonces $\mbox{mcd}(f(x),p(x))=1$.
{{% /proposition %}}
{{% proof %}}

Sea $d(x)=\mbox{mcd}(p(x),f(x))$. Como $d(x)|p(x)$, existirá cierto polinomio $p_0(x)$ de modo que podamos escribir $p(x)=d(x)p_0(x)$. Ahora bien, por la definición de irreducibilidad, o bien $d(x)$ o bien $p_0(x)$ es constante. Si el polinomio constante es $d(x)$, tendríamos el resultado.\\
Veamos pues qué pasa cuando el que fuera constante fuera $p_0(x)$. En ese caso $p(x) |d(x),$ 
%$\mbox{grado}(d(x))=\mbox{grado}(p(x))>0$ y existiría un polinomio $f'(x)$ cumpliendo que $f(x)=d(x)f'(x)=p(x)(f'(x)/p'(x))$,
por lo que $p(x)$ dividiría a $f(x)$, que no es posible. Por consiguiente $d(x)$ no puede ser nada más que una constante.
{{% /proof %}}

Veremos a continuación algunos resultados que dejaremos sin demostrar, pues sus pruebas se pueden escribir de una manera completamente análoga a las de sus semejantes del ámbito de los enteros.

{{% proposition %}}
{\bf (Teorema de Euclides)}
Sea $p(x)\in k[x]$ un polinomio irreducible. Dados dos polinomios $f(x),g(x)\in k[x]$, si $p(x)|f(x)g(x)$, entonces $p(x)$ divide a alguno de los dos.
{{% /proposition %}}

{{% theorem %}}
{Descomposición en factores irreducibles}
{Cualquier polinomio no constante de $k[x]$ es irreducible o factoriza en producto de polinomios irreducibles. Este producto es único en tanto que si tenemos dos factorizaciones de $f(x)$ en producto de polinomios irreducibles en $k[x]$ de la forma 
$$
f(x)=p_1(x)\cdots p_s(x)=q_1(x)\cdots q_t(x)
$$ 
necesariamente $s=t$ y existe una correspondencia uno a uno entre los factores $p_1(x),\ldots,p_s(x)$ y $q_1(x),\dots,q_t(x)$ donde si $p_i(x)$ se corresponde con $q_j(x)$, existe un $\alpha\in k\setminus\\{0\\}$ tal que $p_i(x)=\alpha q_j(x)$.}
{{% /theorem %}}

{{% proposition %}}

Sea $I = (f(x)) \subset k[x]$ un ideal. Entonces son equivalentes las siguientes condiciones:
\begin{enumerate}
\item $I$ es maximal.
\item $I$ es primo.
\item $f(x)$ es irreducible.
\end{enumerate}
{{% /proposition %}}

Vamos a presentar una herramienta específica y útil de los polinomios, que no tiene paralelismo en los enteros: la derivada (formal), que coincide con el concepto usual de análisis.



Usaremos la notación habitual:
\begin{itemize}
\item $f'(x)$ es el polinomio que se obtiene al derivar $f(x)$; \\
\item $D:k[x]\rightarrow k[x]$ es la función que a cada polinomio le asocia su derivada. Esto es, $D(f(x)) = f'(x).$
\end{itemize}



{{% definition %}}
{Derivada de un polinomio}
{La {\em{\bf derivada}} de un polinomio $f(x)$ viene definida por las siguientes reglas:
\begin{enumerate}
\item Si $f(x)=ax^n$ con $a\in k$, entonces $D(ax^n)=nax^{n-1}$. (Si $n=0$, $D(a)=0$.)
\item Si $f(x)=g(x)+h(x)$, entonces $D(f(x))=D(g(x))+D(h(x))$. Esto es, la derivada es un homomorfismo de grupos aditivos.
\end{enumerate}}
{{% /definition %}}

{{% proposition %}}

Para cualesquiera polinomios $f(x),g(x)\in k[x]$ y para todo natural $s>1$ se verifica que:
\begin{enumerate}
\item $D(f(x)g(x))=f(x)D(g(x))+g(x)D(f(x)).$
\item $D(f(x)^s)=sf(x)^{s-1}D(f(x)).$
\end{enumerate}
{{% /proposition %}}
{{% proof %}}

La prueba es puramente efectiva.
%Sean $f(x)=\sum_{i=0}^na_ix^i$ y $g(x)=\sum_{j=0}^mb_jx^j$. Sabemos que $f(x)g(x)=\sum_{l=0}^{m+n}d_lx^l$, donde los coeficientes últimos vienen dados por $d_l=\sum_{i+j=l}a_ib_j$. Así, usando la definición,
%$$D(f(x)g(x))=\sum_{l=1}^{m+n}ld_lx^{l-1}.$$
%Por otro lado,
%$$f(x)D(g(x))+g(x)D(f(x))=\sum_{i=0}^na_ix^i\sum_{j=1}^mjb_jx^{j-1}+\sum_{i=0}^nia_ix^{i-1}\sum_{j=0}^mb_jx^j=$$
%$$=\sum_{l=1}^{m+n}\left(\sum_{i+j=l}ja_ib_j+ia_ib_j\right)x^{l-1},$$
%y ambas expresiones son iguales.
%
%
%
%La segunda afirmación se obtiene de la primera aplicando el principio de inducción en $s$. Si $s=1$, el resultado es una identidad trivial, así que supongamos como hipótesis de inducción que el resultado es cierto cuando $s=k$, y probémoslo para $s=k+1$.\\
%Por lo visto anteriormente, $D(f(x)^{k+1})=f(x)D(f(x)^k)+D(f(x))f(x)^k$. Por la hipótesis de inducción, esta expresión es igual a $f(x)kf(x)^{k-1}D(f(x))+D(f(x))f(x)^k=(k+1)f(x)^kD(f(x))$, como queríamos ver.
{{% /proof %}}

{{% theorem %}}
{Factores múltiples de un polinomio}
{Sea $f(x)\in k[x]$ un polinomio, donde $k \in \\{ \Q,\RR,\C\\}$. Entonces $f(x)$ tiene factores múltiples si y sólo si $f(x)$ y $f'(x)$ no son primos entre sí.}
{{% /theorem %}}
{{% proof %}}

Supongamos en primer lugar que $f(x)$ tiene algún factor múltiple, y sea por tanto $f(x)=p(x)^sq(x)$, con $s>1$. Entonces
$$f'(x)=p(x)^{s-1}[sp'(x)q(x)+p(x)q'(x)],$$
luego $p(x)$ es un factor común de $f(x)$ y $f'(x).$



Supongamos ahora que $d(x)=\mbox{mcd}(f(x),f'(x))$ es de grado mayor que cero, y sea $p(x)$ un factor irreducible de $d(x)$. Veamos que $p(x)$ es un factor múltiple de $f(x)$. Notemos que $p'(x) \neq 0$, al ser $p(x)$ irreducible.\\
En efecto, como $p(x)|f(x)$, tenemos $f(x)=p(x)g(x)$. Derivando esa expresión,
$$f'(x)=p'(x)g(x)+p(x)g'(x).$$
Como $p(x)|f'(x)$, $p(x)$ también divide al producto $p'(x)g(x)$, y, por ser $p(x)$ irreducible, divide a uno de los factores. Ahora bien, $p(x)$ no puede dividir a $p'(x)$ pues tiene grado estrictamente mayor y ambos son no nulos, luego $p(x)|g(x)$, y $g(x)=p(x)h(x)$, así que sustituímos y conseguimos la expresión $f(x)=p(x)^2h(x)$.
{{% /proof %}}

{{% watch %}}

La especificación de que el cuerpo de coeficientes es $\Q$, $\RR$ o $\C$ no es irrelevante. En efecto, en la segunda implicación hemos usado que un polinomio de grado mayor que $1$ no puede dividir a su derivada. Esto en cuerpos como $\F_p$ no es cierto ya que, por ejemplo, $f(x)=x^3+1$ es un polinomio irreducible de $\F_3[x]$ que verifica que $f'(x) =0$ y, por tanto $f(x)|f'(x)$.
{{% /watch %}}



## Congruencias. Teorema chino del resto

Trabajaremos con las congruencias para polinomios, definidas igualmente a las de los enteros y con propiedades similares, ya que son ejemplos del mismo caso general (el cociente de un anillo sobre un ideal). No nos extenderemos mucho por tanto en este punto; simplemente lo preciso.

{{% definition %}}
{Congruencia de polinomios}
{Sea $p(x)\in k[x]$ un polinomio. Dados dos polinomios $f(x),g(x)\in k[x]$, diremos que $f(x)$ y $g(x)$ son {\em{\bf congruentes módulo $p(x)$}}, y escribiremos
$$f(x)\equiv g(x)\; (\mbox{mod } p(x)),$$
si $p(x)$ divide a $f(x)-g(x)$.}
{{% /definition %}}

{{% proposition %}}

Si un polinomio $m(x)$ tiene grado $d$, cualquier clase de congruencia módulo $m(x)$ tiene un único representante $r(x)$ de grado estrictamente menor que $d$.
{{% /proposition %}}
{{% proof %}}

Sea un polinomio $f(x)\in k[x]$. Por el algoritmo de división tenemos que
$$f(x)=q(x)m(x)+r(x)\text{, con }\mbox{grado}(r(x))<\mbox{grado}(m(x))$$
y $f(x)\equiv r(x) \; (\mbox{mod } m(x))$. Como el resto de la división es único, es él el representante de menor grado buscado.
{{% /proof %}}

Dicho de otro modo, lo que esto prueba es que el conjunto de polinomios de $k[x]$ de grado estrictamente menor que el de $m(x)$ es un conjunto completo de representantes para $k[x]/(m(x))$.

{{% example name="Ejemplo" %}}

Sea $m(x)=x^2+1\in\Q[x]$. Por la proposición, cada elemento de $\Q[x]/(m(x))$ tiene un representante de grado menor o igual que 1. Como
$$x^2\equiv-1 \; (\mbox{mod } x^2+1),$$
multiplicando por $x$ tenemos que
$$x^3\equiv-x \; (\mbox{mod } x^2+1).$$
En general, es fácil ver por inducción en $n$ que
$$x^{2n}\equiv(-1)^n \; (\mbox{mod } x^2+1), \; \; x^{2n+1}\equiv(-1)^nx \; (\mbox{mod } x^2+1).$$



Como $\Q$ es un cuerpo infinito, existen infinitos polinomios de grado menor o igual que 1 en $\Q[x]$, y por tanto $\Q[x]/(x^2+1)$ es un conjunto infinito.



Si utilizáramos ahora $\F_3$ en lugar de $\Q$, por lo anterior tendríamos que
$$(\F_3)[x]/(x^2+1)=\\{\, 0,\, 1,\, 2,\, x,\, x+1,\, x+2,\, 2x,\, 2x+1,\, 2x+2\, \\}.$$
{{% /example %}}



{{% theorem %}}
{Teorema chino del resto}
{Sean $m_1(x),\ldots,m_n(x)\in k[x]$ polinomios primos entre sí dos a dos, y sean $a_1(x),\ldots,a_n(x)\in k[x]$ otros polinomios arbitrarios. Entonces existe $f(x)\in k[x]$ tal que:
$$\begin{array}{cc}
    f(x)\equiv a_1(x) & (\mbox{mod } m_1(x)) \\
    f(x)\equiv a_2(x) & (\mbox{mod } m_2(x)) \\
    \vdots & \vdots \\
    f(x)\equiv a_n(x) & (\mbox{mod } m_n(x))
  \end{array}$$
Además, para que el polinomio $\tilde{f}(x)\in k[x]$ sea otra solución es condición necesaria y suficiente que se verifique que
$$f(x)\equiv\tilde{f}(x) \; (\mbox{mod } m_1(x)m_2(x)\cdots m_n(x)).$$}
{{% /theorem %}}
{{% proof %}}

La demostración es análoga a la del teorema homónimo en el contexto entero.\\
Puesto que $m_i(x)$ y $m_j(x)$ son primos entre sí, para todo $i\neq j$, $m_i(x)$ es primo con el producto
$$l_i(x)=m_1(x)\cdots m_{i-1}(x)m_{i+1}(x)\cdots m_n(x).$$
Así pues, por la identidad de Bézout, existirán $\alpha_i(x),\beta_i(x)\in k[x]$ tales que
$$1=\alpha_i(x)m_i(x)+\beta_i(x)l_i(x)\text{ , para cualquier }i=1,\ldots,n.$$
Se tiene entonces que
$$\begin{array}{cl}
  \beta_i(x)l_i(x)\equiv1 & (\mbox{mod } m_i(x))\\
  \beta_i(x)l_i(x)\equiv0 & (\mbox{mod } m_j(x))\text{, para todo }i \not= j
\end{array}$$
Podemos tomar como solución entonces
$$f(x)=a_1(x)\beta_1(x)l_1(x)+a_2(x)\beta_2(x)l_2(x)+\ldots+a_n(x)\beta_n(x)l_n(x).$$



Vayamos a por el segundo aserto. Si 
$$
f(x)\equiv\tilde{f}(x) \; (\mbox{mod } m_1(x)\cdots m_n(x)),
$$ 
existirá un polinomio $q(x)$ tal que 
$$
f(x)-\tilde{f}(x)=q(x)m_1(x)\cdots m_n(x).
$$ 

Tomando en la anterior expresión clases de congruencia módulo $m_i(x)$, es claro que $f(x)\equiv\tilde{f}(x) (\mbox{mod } m_i(x))$ para todo $i$, y por tanto, es solución del problema.\\
Recíprocamente, si 
$$
f(x)\not\equiv\tilde{f}(x) \; (\mbox{mod } m_1(x)\cdots m_n(x)),
$$ 
es porque existen dos polinomios, que denominaremos $q(x)$ y $h(x)$, siendo $h(x)$ no divisible por $m_1(x)\cdots m_n(x)$, tales que 
$$
f(x)-\tilde{f}(x)=q(x)m_1(x)\cdots m_n(x)+h(x).
$$ 
Como alguno de los $m_i(x)$ no puede dividir a $h(x)$, alguna de las congruencias módulo $m_i(x)$ fallará, y por tanto $\tilde{f}(x)$ no será solución del problema.
{{% /proof %}}

\begin{metodocolor}{Sistemas lineales de congruencias}
{Para resolver el sistema
$$f(x)\equiv a_i(x) \; (\mbox{mod } m_i(x))\text{ ,  }i=1,\ldots,n,$$
siendo los $m_i(x)$ polinomios primos entre sí y los $a_i(x)$ polinomios cualesquiera.\\
Tome, para cada $i$, $l_i(x)=\left(\prod_{j=1}^nm_j(x)\right)/m_i(x)$. Aplique la identidad de Bézout a cada pareja $l_i,m_i$ para obtener la igualdad
$$1=\alpha_i(x)m_i(x)+\beta_i(x)l_i(x).$$
Las soluciones son
$$f(x)=a_1(x)\beta_1(x)l_1(x)+a_2(x)\beta_2(x)l_2(x)+\ldots+a_n(x)\beta_n(x)l_n(x),$$
y los polinomios congruentes con él módulo $\prod_{j=1}^nm_j(x)$.}
\end{metodocolor}

## Factorización en $\C[x]$ y en $\RR[x]$

A continuación enunciaremos un resultado del que hablaremos con más detalle en la última sección. Para lo que estamos tratando aquí, su importancia es que nos dice cómo son los polinomios irreducibles sobre $\C$. Ahora bien, su relevancia es mucho mayor, pero no adelantemos acontecimientos y centrémonos de momento en la factorización de polinomios.

{{% theorem %}}
{Teorema fundamental del álgebra}
{Todo polinomio $f(x)\in\C[x]$ de grado positivo tiene una raíz compleja.}
{{% /theorem %}}

{{% corollary %}}

Todo polinomio $f(x)\in \C[x]$ de grado positivo, digamos $n$, tiene $n$ raíces en $\C$, esto es, se puede escribir como
$$f(x)=\alpha\prod_{i=1}^n(x-\alpha_i),$$
donde $\alpha,\alpha_i\in\C$.
{{% /corollary %}}
%{{% proof %}}

%Por el teorema fundamental del álgebra, $f(x)$ tiene una raíz $\alpha_1$ en $\C$. Por tanto, por el teorema del resto podemos escribir $f(x)=(x-\alpha_1)f_1(x)$. Aplicando el mismo razonamiento a $f_1(x)$, y así sucesivamente, se llega, después de $n-1$ pasos, a una expresión de la forma
%$$f(x)=(x-\alpha_1)\cdots(x-\alpha_{n-1})f_{n-1}(x),$$
%donde $f_{n-1}(x)$ es un polinomio de primer grado. Como $f_{n-1}(x)$ se puede escribir $f_{n-1}(x)=\alpha x-\alpha\alpha_n$, se tiene el resultado.
%{{% /proof %}}

En virtud del corolario, el problema de dilucidar si un polinomio de $\C[x]$ es irreducible o no es tremendamente sencillo; tanto como mirar su grado, pues los únicos polinomios irreducibles en $\C[x]$ son los de grado $1$. En $\RR[x]$ no ocurre así, ya que, por ejemplo, los polinomios $x^2+1$ o $x^3-15x-4$ no se pueden factorizar en producto de polinomios de primer grado, aunque tampoco es que la cuestión de la factorización devenga complicada. Veamos cómo son los irreducibles en este otro anillo.

{{% proposition %}}

Todo polinomio de $\RR[x]$ de grado impar tiene una raíz en $\RR$. Todo polinomio se descompone en producto de polinomios de grados $1$ o $2$ (los cuales son irreducibles si y sólo si sus raíces son complejas no reales).
{{% /proposition %}}
{{% proof %}}

Sea $f(x)\in\RR[x]$ un polinomio de grado positivo, digamos $n$. A $f(x)$ lo podemos mirar con otros ojos, como elemento de $\C[x]$, así que aplicamos el teorema fundamental del álgebra para saber que $f(x)$ tiene $n$ raíces en $\C$. Sea
$$f(x)=a_nx^n+a_{n-1}x^{n-1}+\ldots+a_1x+a_0 \; , \; a_i\in\RR, i=0,1,\ldots,n,$$
y sea $\alpha=a+bi$ una raíz de $f(x)$. De
$$0=f(\alpha)=a_n(a+bi)^n+a_{n-1}(a+bi)^{n-1}+\ldots+a_1(a+bi)+a_0$$
se deduce, tomando conjugados, que
$$0=\overline{f(\alpha)}=f(\overline{\alpha})=a_n(a-bi)^n+a_{n-1}(a-bi)^{n-1}+\ldots+a_1(a-bi)+a_0.$$
En consecuencia, si $\alpha$ es una raíz de $f(x)$, también debe serlo $\overline{\alpha}$, luego las raíces no reales de $f(x)$ aparecen por pares de conjugadas. Si $n$ es impar, tiene que haber una raíz que coincida con su conjugada, es decir, que sea real. Con esto probamos el primer aserto.



En cuanto a la segunda afirmación, obramos como sigue. Si $\alpha=a+bi$  es una raíz compleja no real de $f(x)$, el polinomio
$$(x-\alpha)(x-\overline{\alpha})=x^2-2ax+(a^2+b^2)$$
divide a $f(x)$ y tiene coeficientes reales, con lo que podemos descomponer a $f(x)$ en producto de factores de grado 2 a lo sumo. La cuestión de si éstos se pueden descomponer a su vez en otros de grado 1 o son irreducibles es tan simple como el hecho de que sus raíces sean reales o no.
{{% /proof %}}



## Factorización en $\Q[x]$

Sea $f(x)\in k[x]$ un polinomio de grado $2$ o $3$. En ese caso, $f(x)$ es reducible si y sólo si tiene una raíz en $k$. En efecto, el hecho de que $f(x)$ sea reducible es equivalente a decir que tiene un divisor que es de grado $1$. Si éste es $ax-b$, entonces $b/a$ es una raíz de $f(x)$.



Naturalmente, lo anterior no funciona para grados mayores. Un polinomio de grado $4$ se puede descomponer, por ejemplo, en dos factores irreducibles de grado $2$, como $x^4+3x^2+2$ en $\Q$, luego no tiene por qué tener raíces en $k$. Con mayor razón ocurrirá esto en grados más altos. No obstante es bueno ver si un polinomio dado tiene o no raíces en $k$. Si las tiene, y es de grado mayor que $1$, es automáticamente reducible.



El problema de saber cuándo un polinomio de $\Q[x]$ es irreducible es algo intrincado si se pretende resolver de manera realmente efectiva. Sin embargo, el problema de la localización de raíces (que, como hemos notado en el párrafo anterior, es más simple), sí se puede atacar fácilmente, y es lo primero que haremos en esta sección.



Para empezar, notemos que si $f(x)\in\Q[x]$, es igual buscar sus raíces que las de $af(x)$, donde $a\in\Z$. En particular, podemos suponer que $f(x)$ está en realidad en $\Z[x]$ (esto es, todos sus coeficientes son enteros). En estas condiciones tenemos el siguiente resultado, también conocido como {\bf Regla de Ruffini}:

{{% proposition %}}

Sea el polinomio
$$f(x)=a_nx^n+a_{n-1}x^{n-1}+\ldots+a_1x+a_0 \; , \; a_i\in\Z, i=0,1,\ldots,n,$$
de grado $n>0$. Supongamos que $f(x)$ tiene una raíz racional $\alpha=a/b$ con $a$ y $b$ primos entre sí. Entonces $a|a_0$ y $b|a_n$.
{{% /proposition %}}
{{% proof %}}

En efecto, como $a/b$ es raíz de $f(x)$,
$$0=f(a/b)=a_n(a/b)^n+a_{n-1}(a/b)^{n-1}+\ldots+a_1(a/b)+a_0,$$
luego, previa multiplicación por $b^n$, tenemos que
$$0=a_na^n+a_{n-1}a^{n-1}b+\ldots+a_1ab^{n-1}+a_0b^n.$$
Como $a$ divide a todos los términos salvo al último y es primo con $b$, debe dividir a $a_0$. E igualmente, como $b$ divide a todos los términos salvo al primero y es primo con $a$, debe dividir a $a_0$.
{{% /proof %}}

Hemos visto que intentar localizar las raíces de los polinomios en $\Z[x]$ tiene algo más de futuro, o por lo menos es más abarcable, que en $\Q[x]$, así que seguiremos reduciéndonos al caso de los polinomios con coeficientes enteros, donde la factorización única de los coeficientes nos puede ser de ayuda.

{{% definition %}}
{Contenido de un polinomio}
{Dado un polinomio $f(x)\in\Z [x]$ no nulo, se llama {\em{\bf contenido de $f(x)$}} al máximo común divisor de sus coeficientes. Se denota por $c(f)$. Se dirá que $f(x)$ es {\em{\bf primitivo}} si su contenido es $1$.}
{{% /definition %}}

El siguiente resultado es conocido como lema de Gauss, como también se denomina del mismo modo a otros resultados en otros campos matemáticos. Al fin y al cabo, Gauss fue un matemático muy prolijo y no es de extrañar que varios lemas suyos hayan pasado a la historia con el mismo nombre. De hecho, se confunde incluso con un corolario suyo, pero el que presentamos es, en este contexto, el verdadero históricamente hablando, y aparece, con otras palabras, en el Artículo 42 de su gran obra \emph{Disquisitiones Arithmeticae}.

{{% theorem %}}
{Lema de Gauss}
{El producto de dos polinomios primitivos es primitivo.}
{{% /theorem %}}
{{% proof %}}

Sean
$$f(x)=a_mx^m+a_{m-1}x^{m-1}+\ldots+a_1x+a_0, \; a_i\in \Z, i=0,1,\ldots,m,$$
$$g(x)=b_nx^n+b_{n-1}x^{n-1}+\ldots+b_1x+b_0, \; b_j\in \Z, j=0,1,\ldots,n$$
dos polinomios primitivos. Para probar que $f(x)g(x)$ es primitivo basta ver que, fijado $p\in \Z$ irreducible, existe un coeficiente de $f(x)g(x)$ que no es divisible por él.



Fijemos pues $p$ irreducible. Sea $s$ (resp $t$) el entero $0\leq s\leq m$ (resp. $0\leq t\leq n$) tal que $p|a_i$ para todo $i>s$ (resp. $p|b_j$ para todo $j>t$), si se da el caso, y $p$ no divide a $a_s$ (resp. a $b_t$). El coeficiente de $x^{s+t}$ en $f(x)g(x)$ es
$$a_0b_{s+t}+\ldots+a_{s-1}b_{t+1}+a_sb_t+a_{s+1}b_{t-1}+\ldots+a_{s+t}b_0,$$
en el que se ve que $p$ divide a todos los sumandos salvo a $a_sb_t$. Así, $p$ no divide a la suma, lo que prueba el resultado.
{{% /proof %}}

{{% corollary %}}

Si $f(x),g(x)\in \Z [x]$ son polinomios no nulos, entonces
$$c(fg)=c(f)c(g).$$
{{% /corollary %}}
{{% proof %}}

Podemos escribir
$$f(x)=c(f)f_0(x), \; \; \; \; g(x)=c(g)g_0(x)$$
donde $f_0(x)$ y $g_0(x)$ son primitivos. Así
$$f(x)g(x)=c(f)c(g)f_0(x)g_0(x)$$
y, como $f_0(x)g_0(x)$ es primitivo por el lema de Gauss, debe ocurrir que $c(f)c(g)=c(fg)$.
{{% /proof %}}

El siguiente resultado es engañosamente sencillo, pero de una importancia extrema cuando se trata de factorizar polinomios, como comprobaremos más adelante.

{{% corollary %}}

Sea $f(x)\in\Z[x]$ un polinomio de grado positivo, digamos $n$, que se descompone en $\Q[x]$ en producto de dos polinomios de grados estrictamente menores que $n$. Entonces, se descompone en $\Z[x]$ en producto de dos polinomios de esos mismos grados.
{{% /corollary %}}
{{% proof %}}

Sea $f(x)=f_1(x)g_1(x)$, donde $f_1(x),g_1(x)\in\Q [x]$ con 
$$
\mbox{grado}(f_1(x))<n, \quad \mbox{grado}(g_1(x))<n.
$$ 

Multiplicando la anterior igualdad por un cierto
elemento $a\in\Z$ para quitarnos los denominadores de en medio del producto, se tendrá que
$$af(x)=g(x)h(x)\; , \; g(x),h(x)\in\Z[x].$$
De ahí se deduce que $ac(f)=c(gh)=c(g)c(h)$, luego $a|c(g)c(h)$. Por tanto, si tomamos $g(x)=c(g)g'(x)$, $h(x)=c(h)h'(x)$, entonces
$$f(x)=\frac{c(g)c(h)}{a}g'(x)h'(x),$$
y ésa es la descomposición buscada.
{{% /proof %}}

{{% corollary %}}

Sea $f(x)\in\Z[x]$ un polinomio de grado positivo, digamos $n$, y primitivo. Entonces $f(x)$ es reducible en $\Z[x]$ si y sólo si lo es en $\Q[x]$.
{{% /corollary %}}
{{% proof %}}

Muy simple; basta con releer el enunciado del corolario anterior.
{{% /proof %}}

Incluimos también un criterio muy general y útil de irreducibilidad de polinomios, aunque no concluyente al no poderse aplicar a todos los casos.

{{% proposition %}}
{\bf (Criterio de Eisenstein)}
Sea un polinomio de grado $n>0$
$$f(x)=a_nx^n+a_{n-1}x^{n-1}+\ldots+a_1x+a_0 \; , \; a_i\in \Z, i=0,1,\ldots,n.$$
Supongamos que existe un elemento irreducible $p\in\Z$ que divide a todos los coeficientes, salvo a $a_n$, y cuyo cuadrado $p^2$ no divide a $a_0$. Entonces $f(x)$ es irreducible en $\Q[x]$.
{{% /proposition %}}
{{% proof %}}

Se hará por reducción al absurdo. Supongamos que $f(x)$ fuese reducible en $\Q[x]$. En consecuencia se descompondría en $\Q[x]$ en producto de dos polinomios de grado estrictamente inferior. Por el corolario anterior se puede escribir
$$f(x)=(b_sx^s+b_{s-1}x^{s-1}+\ldots+b_1x+b_0)(c_tx^t+c_{t-1}x^{t-1}+\ldots+c_1x+c_0),$$
donde $b_i,c_j\in\Z$ para cualesquiera $i,j$ y $s,t<n$.



Por la segunda hipótesis, $p$ debe dividir a uno de entre $b_0$ y $c_0$, pero no a ambos. Supongamos pues sin pérdida de generalidad que $p|b_0$ y no divide a $c_0$. Como $p$ no divide a $a_n$, no puede dividir a todos los $b_i$. Sea $m$ el mínimo índice tal que $p$ no divide a $b_m$, que sabemos que es menor que $n$. El coeficiente del término en $x^{m}$ es
$$b_mc_0+b_{m-1}c_1+\ldots+b_0c_m=a_m,$$
que no es divisible por $p$ pues todos los sumandos lo son salvo el primero. Ahora bien, que $a_m$ con $m<n$ no sea divisible por $p$ es una contradicción, luego hemos terminado con la prueba.
{{% /proof %}}



### El método de los interpoladores de Lagrange



El método de los polinomios interpoladores de Lagrange, como su propio nombre indica, no es más que una adaptación a nuestro contexto del clásico método de interpoladores lineales de Lagrange del Cálculo Numérico. En la literatura también se le conoce como método de Kronecker.



Comencemos con el caso de un polinomio $f(x)\in\Z[x]$ de grado $n$ y sea $d=\lfloor n/2\rfloor$. Obviamente, salvo que $f(x)$ sea irreducible, alguno de sus factores irreducibles ha de tener grado menor o igual que $d$, por lo que basta buscar los posibles factores que verifican esta condición.



Para ello fijaremos $d+1$ enteros distintos (normalmente lo más cerca posible de $0$, por motivos de comodidad) $a_0,a_1,\ldots,a_d$ y hallaremos
$$n_i=f(a_i), \quad i=0,\ldots,d.$$
Ahora bien, si $g(x)$ es un factor del tipo que busco de $f(x)$, ha de verificar que $s_i=g(a_i)$ divide al $n_i$ correspondiente. Así pues, fijaremos una $(d+1)$-upla de divisores, de la forma
$$(s_0,s_1,\ldots,s_d)\mbox{ , donde }s_i|n_i, \; \; i=0,\ldots,d.$$
Recordemos que $g(a_i)$ es precisamente $g(x) (\mbox{mod } x-a_i)$. En ese caso, por el teorema chino del resto, $g(x)$ ha de ser entonces una solución al sistema
$$\begin{array}{cc}
    g(x) \equiv s_0 & (\mbox{mod } x-a_0) \\
    g(x) \equiv s_1 & (\mbox{mod } x-a_1) \\
         \vdots  &  \vdots \\
    g(x) \equiv s_d & (\mbox{mod } x-a_d)
\end{array}$$
Lo que hemos escrito en otras palabras y símbolos es la imposición de que $g(a_i)=s_i=s_i$ $(\mbox{mod } x-a_i)$ para todo $i$. Sabemos que este sistema tiene solución única (pues los $x-a_i$ son primos entre sí) de grado menor o igual que $d$. Así pues, fijado un vector de divisores, tenemos un posible divisor de $f(x)$. Como los posibles vectores de divisores son finitos, este procedimiento nos da una lista exhaustiva de todos los posibles divisores de $f(x)$ de grado menor o igual que $d$. Es más, podemos quedarnos con la mitad de vectores de divisores, pues la única solución asociada a $(-s_0,-s_1,\ldots,-s_d)$ será así el opuesto de la que verifique el sistema con $(s_0,s_1,\ldots,s_d)$.

\begin{metodocolor}{Polinomios interpoladores de Lagrange}
{Para factorizar un polinomio $f(x)\in\Z[x]$.\\
Sea $d=\lfloor n/2\rfloor$, tome $d+1$ enteros distintos $a_i$. Forme la $(d+1)$-upla $(f(a_i))$.\\
Forme todas las posibles $(d+1)$-uplas $(s_i)$ formadas por divisores de los $f(a_i)$, y resuelva el sistema
$g(x)\equiv s_i\text{ }(\mbox{mod } x-a_i)$, para todo $i$, y todas las $(d+1)$-uplas que no se diferencien en un signo.\\
Si $f(x)$ es reducible, de entre las soluciones no constantes, al menos dos serán un factor de $f(x)$.}
\end{metodocolor}

{{% example name="Ejemplo" %}}

Aprovechando que ya hemos factorizado algunos polinomios en, recuperemos uno de ellos para aplicarle el método que acabamos de detallar. Sea pues el polinomio $f(x)=x^4+x^3+x-1\in\Z[x]$, primitivo. Como tiene grado 4, elegimos 5 puntos cercanos al cero para evitarnos hacer cuentas más latosas. Calculamos los valores que toma $f(x)$ en esos puntos:
$$f(-2)=5\text{ ,  }f(-1)=-2\text{ ,  }f(0)=-1\text{ ,  }f(1)=2\text{ ,  }f(2)=25.$$
Podemos formar 768 $5$--uplas distintas, de las que nos quedamos con 384, la mitad. Evidentemente no vamos a comprobar todas ellas. No obstante, cualquier programa de cálculo efectuaría esos cálculos sin rechistar, y al fin y al cabo es por esa razón por la que se comenta este método aquí.



Una vez aclarado lo anterior, sigamos con el ejemplo y probemos con la $5$--upla $(1,-1,-1,1,5)$. Tenemos así el siguiente sistema de congruencias:
$$S:\left\\{\begin{array}{ll}
    g(x) \equiv 1 & (\mbox{mod } x+2) \\
    g(x) \equiv -1 & (\mbox{mod } x+1) \\
    g(x) \equiv -1 & (\mbox{mod } x) \\
    g(x) \equiv 1 & (\mbox{mod } x-1) \\
    g(x) \equiv 5 & (\mbox{mod } x-2)
\end{array}\right.,$$
que tiene como solución al polinomio $x^2+x-1$. Si dividimos $f(x)$ entre aquél, obtenemos como cociente $x^2+1$, que se conseguía al tomar la $5$--upla $(5,2,1,2,5)$. Por consiguiente, $f(x)$ es reducible, y como los de grado 2 que hemos obtenido son irreducibles sobre $\Q$, hemos terminado de calcular su descomposición.\\
Si hubiéramos seguido buscando factores, no habríamos obtenido más que los opuestos de los anteriores. Por ejemplo, la $5$--upla $(1,2,1,1,1)$ nos habría dado como resultado el polinomio 
$$
-\frac{x^4}{6}+\frac{x^3}{6}+\frac{2 x^2}{3}-\frac{2 x}{3}+1,
$$ 
que evidentemente no es factor de $f(x)$.
{{% /example %}}


## Factorización en $\F_p[x]$

Para ilustrar la importancia del problema de factorizar sobre $\F_p[x]$ de la que hablábamos antes veamos cómo podemos relacionar la irreducibilidad en $\Q$ y en $\F_p$, con $p$ primo. Sea
$$f(x)=a_nx^n+\ldots+a_1x+a_0\in\Z[x]$$
primitivo, sea $p$ un primo que no divida a $a_n$, y llamemos $\overline{f}(x)$ al polinomio
$$\overline{f}(x)=\overline{a}_nx^n+\ldots+\overline{a}_1x+\overline{a}_0\in\F_p[x],$$
siendo $\overline{a}_i=a_i \; (\mbox{mod } p)$, $0\leq i\leq n$.

{{% proposition %}}

Si $\overline{f}(x)$ es irreducible en $\F_p[x]$, entonces $f(x)$ es irreducible en $\Q[x]$.
{{% /proposition %}}
{{% proof %}}

Solo hay que tener en cuenta que para cualesquiera polinomios $f(x),g(x)$, $\overline{f(x)g(x)}=\overline{f}(x)\overline{g}(x)$ y escribir el contrarrecíproco del enunciado.
{{% /proof %}}

Veamos, con un ejemplo, cómo podemos usar el resultado anterior.

{{% example name="Ejemplo" %}}

Sea $f(x)=x^4-x^3+x^2-x+1\in\Z[x]$. Tomemos $p=2$. Entonces $\overline{f}(x)=x^4+x^3+x^2+x+1\in \F_2$. Ya que $\overline{f}(0)=1$ y $\overline{f}(1)=1$, $\overline{f}(x)$ no tiene raíces en $\F_2$.



Intentemos factorizar $f(x)$ de forma artesanal. Como en caso de ser reducible, ningún factor de la descomposición de $\overline{f}(x)$ sería de grado 1, pongamos por caso que
$$\overline{f}(x)=(x^2+ax+b)(x^2+cx+d).$$
Como otras veces, operando e igualando coeficientes obtenemos el sistema
$$S:\left\\{\begin{array}{ccl}
                 1 & = & a+c \\
                 1 & = & b+ac+d \\
                 1 & = & ad+bc \\
                 1 & = & bd
\end{array}\right.$$
La última ecuación nos dice que $b=d=1$, y sustituyendo en el resto nos quedamos con
$$S:\left\\{\begin{array}{ccl}
                 1 & = & a+c \\
                 1 & = & ac
\end{array}\right.,$$
que no tiene solución. Por tanto, $\overline{f}(x)$ es irreducible en $\F_2$ y así, por la proposición, $f(x)$ es irreducible sobre $\Q.$
{{% /example %}}



{{% watch %}}

Si bien en apariencia este procedimiento simplifica los cálculos a la hora de estudiar si un polinomio es o no irreducible sobre $\Q$, tiene un grave inconveniente. El recíproco de la proposición anterior es falso. Por ejemplo, el polinomio $x^2+2$ es irreducible sobre $\Q$, pero $\overline{f}(x)=x^2\in \F_2[x]$ es reducible, o el polinomio $x^2-x+1$, irreducible en $\Q$ y con $\overline{f}(x)$ reducible en $\F_3$.
{{% /watch %}}



### El algoritmo de Berlekamp



El algoritmo de Berlekamp para factorizar en $\F_p[x]$ data de 1967, fecha de publicación del artículo en donde se detallaba. Se basa en una idea sencilla, y gracias a eso y a su efectividad, ha sido desde entonces uno de los más utilizados, tanto para programar como para servir de ejemplo de algoritmo de factorización en característica positiva. La idea de la que hablábamos se presenta en el siguiente teorema.

{{% theorem %}}
{Teorema de Berlekamp}
{Sea $f(x)\in\F_p[x]$ de grado $n$, sin factores múltiples y mónico, y supongamos que existe un polinomio $g(x)$ tal que
$$f(x)|\left(g(x)^p-g(x)\right).$$
Entonces
$$f(x)=\prod_{s=0}^{p-1}\mbox{mcd}(f(x),g(x)-s),$$
aunque varios de estos factores pueden ser polinomios constantes.}
{{% /theorem %}}
{{% proof %}}

Del capítulo anterior, recordaremos que en $\F_p$ teníamos que, por el pequeño teorema de Fermat,
$$x^p-x=\prod_{s=0}^{p-1}(x-s),$$
lo cual en particular implica que
$$g(x)^p-g(x)=\prod_{s=0}^{p-1}(g(x)-s).$$
Hay que decir que todos estos factores son primos entre sí al diferenciarse en una constante.



Probemos entonces la igualdad que hemos enunciado. Por un lado, no es nada dificultoso ver que
$$\prod_{s=0}^{p-1}\mbox{mcd}(f(x),g(x)-s)|f(x),$$
pues todos los elementos de la izquierda dividen a $f(x)$ y como los $g(x)-s$ son primos entre sí también lo serán los divisores comunes.



En el otro sentido, si tomamos un factor irreducible de $f(x)$, pongamos $h(x)$, debe dividir a $g(x)^p-g(x)$, luego dividirá también a alguno de los $g(x)-s$ y, de igual modo a $\mbox{mcd}(f(x),g(x)-s)$.



En conclusión, los dos miembros de la igualdad se dividen mutuamente y al ser mónicos, son iguales.
{{% /proof %}}

A partir de aquí, la factorización de $f(x)\in\F_p[x]$ queda reducida por un lado a encontrar $g(x)$ de grado $r<n$ tal que
$$f(x)|(g(x)^p-g(x)),$$
y posteriormente a aplicar el algoritmo de Euclides $p$ veces. Notemos entonces que por estar en característica positiva y por el pequeño teorema de Fermat,
$$g(x)=\sum_{i=0}^{n-1}a_ix^i \; \Longrightarrow \; g^p(x)=\sum_{i=0}^{n-1}a_ix^{ip}.$$



Vamos entonces a buscar un tal polinomio $g(x)$ (concretamente, vamos a buscar sus coeficientes $a_0,\ldots,a_{n-1}$). Dividamos así los monomios $x^{ip}$ entre $f(x)$, que al tener grado $n$ obtendremos
\begin{eqnarray*}
x^{0p}&=&q_0(x)f(x)+r_0(x) \\
&=&q_0(x)f(x)+r_{00}+r_{10}x^1+\ldots+r_{n-1,0}x^{n-1}\\
x^{1p}&=&q_1(x)f(x)+r_1(x) \\ 
&=&q_1(x)f(x)+r_{01}+r_{11}x^1+\ldots+r_{n-1,1}x^{n-1}\\
& \vdots \\
x^{(n-1)p}&=&q_{n-1}(x)f(x)+r_{n-1}(x) \\
&=&q_{n-1}(x)f(x)+r_{0,n-1}+r_{1,n-1}x^1+\ldots+r_{n-1,n-1}x^{n-1}\\
\end{eqnarray*}
Por la unicidad de la división euclídea, el resultado de dividir $g^p(x)$ entre $f(x)$ es el dado por la expresión
$$g^p(x)=\sum_{i=0}^{n-1}a_ix^{ip}=\left(\sum_{i=0}^{n-1}a_iq_i(x)\right)f(x)+\sum_{i=0}^{n-1}a_ir_i(x),$$
y por el mismo motivo, el de dividir $g^p(x)-g(x)$ entre $f(x)$ es
$$g^p(x)-g(x)=\sum_{i=0}^{n-1}a_ix^{ip}-\sum_{i=0}^{n-1}a_ix^i=\left(\sum_{i=0}^{n-1}a_iq_i(x)\right)f(x)+\sum_{i=0}^{n-1}(a_ir_i(x)-a_ix^i).$$
Por consiguiente, $g(x)$ verifica lo que queremos si y sólo si
$$0=\sum_{i=0}^{n-1}(a_ir_i(x)-a_ix^i),$$
o escrito en forma matricial, tomando la matriz de orden $n\times n$ $R=(r_{ij})$, si y sólo si
$$(a_0,\ldots,a_{n-1})^t\text{ es solución del sistema }\left(R-I_n\right){\bf x}={\bf 0}.$$

Así, gracias al algoritmo de Berlekamp, factorizar en $\F_p[x]$ se reduce a resolver ciertos sistemas de ecuaciones lineales (problema elemental, gracias al álgebra lineal) y a aplicar el algoritmo de Euclides, operaciones ambas que se pueden realizar de manera muy eficiente.

\begin{metodocolor}{Algoritmo de Berlekamp}
{Para factorizar un polinomio $f(x)\in\F_p[x]$ de grado $n$.\\
Para cada $i=0,\ldots,n-1$, efectúe las divisiones de $x^{ip}$ entre $f(x)$ para obtener los restos
$$r(x)=r_{0i}+r_{1i}x^1+\ldots+r_{n-1,i}x^{n-1}.$$
Construya la matriz $R=(r_{ij})$, y plantee el sistema lineal
$$\left(R-I_n\right){\bf x}={\bf 0}.$$
Si el sistema no tiene solución, $f(x)$ es irreducible. Si tiene una solución $(a_0,\ldots,a_{n-1})^t$ que represente a un polinomio no constante, $f(x)$ se descompone como
$$\prod_{s=0}^{p-1}\mbox{mcd}\left(f(x),(a_0-s)+a_1x+\ldots+a_{n-1}x^{n-1}\right).$$}
\end{metodocolor}

{{% example name="Ejemplo" %}}

Ilustremos también este método con el mismo polinomio que el anterior ejemplo, pero considerado en $\F_3[x]$. Sea así $f(x)=x^4+x^3+x+2\in \F_3[x]$. Dividimos determinadas potencias de $x$ entre $f(x)$ y obtenemos:
\begin{eqnarray*}
1=q_0(x)f(x)+r_0(x)&=&0\cdot f(x)+1\\
x^{3}=q_1(x)f(x)+r_1(x)&=&0\cdot f(x)+x^3\\
x^{6}=q_1(x)f(x)+r_1(x)&=&q_2(x)f(x)+1+x+2x^2+x^3\\
x^{9}=q_1(x)f(x)+r_1(x)&=&q_3(x)f(x)+x
\end{eqnarray*}
Los cocientes no los hemos indicado todos porque sólo nos interesan los restos para formar la matriz. En nuestro caso,
$$R=\left(\begin{array}{cccc}
1&0&1&0\\
0&0&1&1\\
0&0&2&0\\
0&1&1&0
\end{array}\right).$$
El sistema lineal en $\F_3[x]$ que tenemos que resolver es
$$\left(\begin{array}{cccc}
0&0&1&0\\
0&2&1&1\\
0&0&1&0\\
0&1&1&2
\end{array}\right){\bf x}={\bf 0},$$
que tiene como solución cualquier vector de la forma ${\bf x}=(\alpha,\beta,0,\beta)^t$, donde $\alpha,\beta\in\F_3$. Si tomamos $\alpha=1,\beta=0$, obtenemos la constante 1, que obviamente cumple que $f(x)|1^3-1=0$. Escogiendo pues $\alpha=0,\beta=1$ conseguimos la descomposición
$$
\begin{array}{rcl}
f(x) &=& \mbox{mcd}(f(x),x^3+x) \cdot \mbox{mcd}(f(x),x^3+x+1) \cdot \mbox{mcd}(f(x),x^3+x+2)\\
&=& (x^2+1) \cdot (x^2+x+2)\cdot 1.
\end{array}$$
{{% /example %}}



## El teorema fundamental del álgebra



El contenido de esta sección está tomado del artículo {\em The Fundamental Theorem of Algebra and Linear Algebra}, de Harm Derksen, publicado en el American Mathematical Monthly {\bf 110} (2003), número 7, páginas 620-623. El objetivo que perseguimos es dar una prueba del teorema fundamental del álgebra con argumentos puramente algebraicos y a la vez asequible al lector que no tenga un conocimiento profundo de esta materia, pues solamente usa algunas nociones de álgebra lineal.

{{% theorem %}}
{Teorema fundamental del álgebra}
{Todo polinomio no constante de $\C[x]$ tiene una raíz en $\C$.}
{{% /theorem %}}

Si de algo no se puede quejar alguien que se acerque por primera vez al teorema que nos ocupa, es por falta de demostraciones. Existe una cantidad considerable de pruebas distintas, y usando técnicas variopintas. Desde la primera, elaborada por Gauss en su tesis doctoral de 1799 (aunque con algún fallo en el rigor matemático), hasta esta que aquí expondremos, existen pruebas topológicas, usando propiedades de la curva compleja que describe un polinomio, pruebas analíticas, que utilizan el teorema de Liouville de que toda función entera es acotada, pruebas algebraicas, basándose en la teoría de Galois entre otras herramientas, o incluso mixturas de los tres tipos anteriores.



Vayamos, sin más dilación, al desarrollo de la prueba. Para ello, definamos la propiedad $\mathcal{P}_{k,r}(d)$, donde $k$ es un cuerpo, $\RR$ o $\C$, y $r=1,2$. Su enunciado es el siguiente:



$\mathcal{P}_{k,r}(d)$: {\em Dados $r$ endomorfismos $A_i$ que conmuten entre todos de un $k$-espacio vectorial $V$ de dimensión $n$, no divisible por $d$, existe un autovector no nulo que es común a todos ellos.}



Para probar el teorema, bastaría con demostrar que se cumple la propiedad $\mathcal{P}_{\C,1}(2^r)$ para todo $r\in\mathbb{N}$. Así, para cualquier polinomio (que podemos suponer mónico sin problema) no constante $f(x)=x^n+a_{n-1}x^{n-1}+\ldots+a_0\in\C[x]$, se tiene que
$$f(x)=\det(xI_n-A)\text{, con }A=\left(
\begin{array}{ccccc}
0&0&\cdots&0&-a_0\\
1&0&\cdots&0&-a_1\\
\vdots&\vdots&\ddots&\vdots&\vdots\\
0&0&\cdots&1&-a_{n-1}
\end{array}\right)$$
Como $A$ representa a un endomorfismo de $\C$ y existe algún $r$ tal que $2^r$ no divide a $n$, $A$ tendría un autovector no nulo. Su autovalor asociado sería raíz de $f(x)$, y habríamos acabado.$\hfill\Box$



Así pues, para probar $\mathcal{P}_{\C,1}(2^r)$ seguiremos el camino marcado a través de diversos lemas, cada uno apoyándose en los anteriores. Como en la demostración de arriba, denotaremos por $A_i$ tanto a un endomorfismo como a su matriz asociada.



\begin{lema}
Si se tiene $\mathcal{P}_{k,1}(d)$, también se cumple $\mathcal{P}_{k,2}(d)$.
\end{lema}
{{% proof %}}

Sean $A_1$ y $A_2$ dos endomorfismos que conmutan de un $k$-espacio vectorial $V$ de dimensión $n$ no divisible por $d$. Vamos a probar por inducción en $n$ que tienen un autovector en común. Si $n=1$, cada $A_i$ no es más que la multiplicación por una constante, y todos los vectores de $V$ son propios, siendo trivial el aserto. Supongamos pues que también es cierto si $\dim V<n$, y veámoslo para $\dim V=n$.



Como $\mathcal{P}_{k,1}(d)$ se cumple, $A_1$ tiene un autovalor $\lambda\in k$. Sean $W$ y $Z$, respectivamente, el núcleo y la imagen del endomorfismo $A_2-\lambda I$. Como $A_1$ y $A_2$ conmutan, $W$ y $Z$ permanecen fijos por $A_1$.\\
Supongamos que $W\neq V$. Entonces, como $\dim W+\dim Z=\dim V$, $d$ no dividirá a al menos alguna de las dos dimensiones, y además ambas son menores que $n$. Por tanto, por la hipótesis de inducción, $A_1$ y $A_2$ compartirán un autovector no nulo directamente en $W$ o en $Z$.\\
Si $W=V$, cualquier vector propio de $A_1$ ${\bf v}$ cumple que $A_2{\bf v}=\lambda{\bf v}$, luego también tenemos la propiedad.
{{% /proof %}}

\begin{lema}
Si $k=\RR$, $\mathcal{P}_{k,r}(2)$ son ciertas para $r=1,2$.
\end{lema}
{{% proof %}}

Por el lema anterior bastaría probar que $\mathcal{P}_{\RR,1}(2)$ es cierta, esto es, que todo endomorfismo de un espacio vectorial sobre $\RR$ de dimensión impar tiene un autovector no nulo, pero eso es equivalente a que su polinomio característico $f(x)=\det(xI-A)$ tenga alguna raíz en $\RR$. Ahora bien, $f(x)$ es un polinomio de grado impar con coeficientes reales, y ya hemos visto que siempre tiene al menos una raíz real.
{{% /proof %}}

\begin{lema}
Todo endomorfismo de un $\C$-espacio vectorial de dimensión impar tiene un autovector no nulo, esto es, $\mathcal{P}_{\C,1}(2)$ se cumple.
\end{lema}
{{% proof %}}

Sea $A:\C^n\rightarrow\C^n$ un endomorfismo con $n$ impar, y sea $V=\text{Herm}_{n}(\C)$, el $\RR$-espacio vectorial de las matrices hermíticas (aquellas que $A^*=\overline{A}^t=A$) de orden $n\times n$. Consideremos los siguientes endomorfismos $\RR$-lineales de $V$ definidos como:
$$L_1(B)=\frac{AB+BA^*}{2}\text{ ,  }L_2(B)=\frac{AB-BA^*}{2i}.$$
Ver que $L_1$ y $L_2$ están bien definidos y conmutan es un cálculo bien sencillo y no lo escribiremos en estas líneas.



Sabemos que $\dim_{\RR}V=n^2$, que es impar. Entonces, por el lema anterior, $L_1$ y $L_2$ comparten un autovector no nulo al cumplirse $\mathcal{P}_{\RR,2}(2)$. Sea ${\bf B}$ ese autovector en $V$, cuyos valores propios asociados sean $\lambda$ y $\mu$ respectivamente. En ese caso,
$$(L_1+iL_2)({\bf B})=A{\bf B}=(\lambda+\mu i){\bf B},$$
luego cualquier columna no nula de ${\bf B}$ constituirá uno de los autovectores buscados para $A$.
{{% /proof %}}



Ya hemos acabado el ensamblaje de lemas previos al resultado que nos bastaba para probar el teorema fundamental del álgebra. No hemos usado más que algunas propiedades básicas de espacios vectoriales y matrices. Ahora demostremos la proposición siguiente.



{{% proposition %}}

Para todo $r\in\mathbb{N}$ se cumple $\mathcal{P}_{\C,1}(2^r)$.
{{% /proposition %}}
{{% proof %}}

Se hará por inducción en $r$. Si $r=1$ es el enunciado del lema anterior, así que supongamos como hipótesis de inducción que tenemos $\mathcal{P}_{\C,1}(2^l)$, con $l<r$.\\
Tomemos pues un endomorfismo $\C$-lineal $A:\C^n\rightarrow\C^n$, con $n$ divisible por $2^{r-1}$ pero no por $2^r$. Esto lo podemos asumir, puesto que si $n$ no fuera divisible por $2^{r-1}$ estaríamos en el caso de probar $\mathcal{P}_{\C,1}(2^{r-1})$. Sea $V=\text{Ant}_{n}(\C)$ el $\C$-espacio vectorial de las matrices antisimétricas con coeficientes complejos. Definamos dos endomorfismos de $V$, $L_1$ y $L_2$ como
$$L_1(B)=AB-BA^t\text{ ,  }L_2(B)=ABA^t.$$
De nuevo, no probaremos que están bien definidos ni que conmutan entre ellos, y queda para el lector.



Notemos que $2^{r-1}$ no divide a $\dim V$, que es igual a $n(n-1)/2$. Por tanto, por la hipótesis de inducción, existe un vector propio ${\bf B}$ común a $L_1$ y $L_2$. Sean sus autovalores asociados $\lambda$ y $\mu$, respectivamente. Así,
$$\mu{\bf B}=A{\bf B}A^t=A(A{\bf B}-\lambda{\bf B}),$$
es decir,
$$(A^2-\lambda A-\mu I){\bf B}={\bf 0}.$$
Sea ${\bf v}$ un vector columna de ${\bf B}$, y sean $\alpha$ y $\beta$ las dos raíces complejas del polinomio $x^2-\lambda x-\mu$, que sí que sabemos que tiene raíces en $\C$, porque es de grado 2. Si llamamos ${\bf w}=(A-\beta I){\bf v}$ y es no nulo, tenemos que $(A-\alpha I){\bf w}={\bf 0}$, y hemos terminado, siendo ${\bf w}$ el autovector que buscábamos. Si ${\bf w}={\bf 0}$ eso querría decir que $(A-\beta I){\bf v}={\bf 0}$, siendo ${\bf v}$ el vector propio buscado.
{{% /proof %}} 

-->
