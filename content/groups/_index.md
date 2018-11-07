+++
title = "Grupos"
weight = 20
+++

## Definiciones básicas

{{% definition %}}
Un **grupo** es un par $(G, \star )$,
donde $G$ es un conjunto y $\star$ es una **operación binaria** en $G$, es decir una aplicación
$$
\begin{array}{rcl}
G\times G&\stackrel{\star}{\longrightarrow}&G,\cr
(x,y)&\mapsto&x\star y,
\end{array}
$$
que ha de satisfacer las propiedades siguentes:

* $(x\star y)\star z=x\star(y\star z)$ para todo $x,y,z\in G$ (**asociativa**).

* Existe un elemento $e\in G$  tal que $x\star e=x=e\star x$ para todo  $x\in G$ (**elemento neutro**).

* Para todo $x\in G$ existe $\inv{x}\in G$  tal que $x\star \inv{x}=e=\inv{x}\star x$ (elemento **simétrico** o **inverso**).
{{% /definition %}}

Cuando la operación $\star$ se sobreentienda por el contexto, el grupo $(G, \star )$ se denotará simplemente $G$. En este caso también es frecuente sustituir el símbolo $\star$ por una mera yuxtaposición de símbolos, es decir $x\star y=xy$. Observa que $e^{-1}=e$.

{{% example name="Ejemplos de grupos" %}}
Los siguientes son algunos grupos bien conocidos:

* $\Z$, $\Q$, $\mathbb{R}$ y $\mathbb{C}$ son grupos con la operación suma $+$. En este caso el elemento neutro es el **cero** $0$. El simétrico de un elemento $x$ es su **opuesto** $-x$. Esta notación se denomina **aditiva** frente a la usada en la definición de grupo, que es la **multiplicativa**.
  
* $\Q\setminus\\{ 0\\}$, $\mathbb{R}\setminus\\{ 0\\}$ y $\mathbb{C}\setminus\\{ 0\\}$
  son grupos  con la multiplicación. ¿Cuál es el elemento neutro?
  
* El conjunto $\\{ 1,-1\\}$ con el producto.

* El conjunto $\\{ 1,-1, i, -i\\}$ con el producto.
  
* El conjunto $GL(n,k)$ de las matrices $n\times n$ con entradas en un cuerpo $k$ y  determinante no nulo, con la multiplicación de matrices.

* El **grupo trivial** $\\{e\\}$, con el producto definido como $e\star e=e$, que es el único posible.
{{% /example %}}


{{% proposition %}}
El elemento neutro de un grupo $(G,\star)$ es único.
{{% /proposition %}}

{{% proof %}}
Si $e$ y $e'$ son elementos neutros de $(G,\star)$, entonces se tiene:
$$
   e = e\star e' = e',
$$
donde la primera igualdad es cierta por ser $e'$ un elemento neutro, y la segunda por serlo $e$.
{{% /proof %}}

{{% proposition %}}
El simétrico de un elemento de un grupo $x\in G$ es único.
{{% /proposition %}}

{{% proof %}}
Sea $x\in G$, y sean $y$, $z$ elementos simétricos de $x$, es decir, que satisfacen
$$
\begin{array}{rcl}
x\star y=e=y\star x,\cr
x\star z=e=z\star x.
\end{array}
$$
Entonces,
$$
\begin{array}{rcl}
y&=& y\star e\cr
&=& y \star (x \star z)\cr
&=& (y \star x) \star z\cr
&=& e \star z\cr
&=& z.
\end{array}
$$
{{% /proof %}}

Gracias al resultado anterior, podemos denotar  $x^{-1}$ al simétrico de $x$ sin ambigüedad, o $-x$ si estamos usando notación aditiva. Cuando estudiamos los conjuntos demostramos un resultado análogo para aplicaciones biyectivas. 

{{% proposition %}}
Si $x,y\in G$ son elementos de un grupo tales que $x\star y=e$, entonces $y=x^{-1}$ y $x=y^{-1}$.
{{% /proposition %}}

{{% proof %}}
A partir de $x\star y= e$,
$$
\begin{array}{rcl}
y&=&e\star y\cr
&=&x^{-1}\star x\star y\cr
&=& x^{-1}\star e\cr
&=&x^{-1}.
\end{array}
$$  
Análogamente,
$$
\begin{array}{rcl}
x&=&x\star e\cr
&=&x\star y\star y^{-1}\cr
&=&e\star y^{-1}\cr
&=&y^{-1}.
\end{array}
$$
{{% /proof %}}

{{% watch %}}
¡Ojo! El resultado análogo a la proposición anterior para aplicaciones es falso. Es posible encontrar aplicaciones $f\colon X\rightarrow Y$ y $g\colon Y\rightarrow X$ que no son biyectivas tales que $g\circ f=1_X$ pero $f\circ g\neq 1_Y$. En cambio, si $f$ o $g$ es biyectiva y $g\circ f=1_X$ es fácil probar que ambas son biyectivas, $f=g^{-1}$ y $g=f^{-1}$.
{{% /watch %}}

{{% corollary %}}
Todo elemento de un grupo $x\in G$ satisface $(x^{-1})^{-1}=x$.
{{% /corollary %}}

{{% proof %}}
Basta usar que $x\star x^{-1}=e$.
{{% /proof %}}

{{% proposition %}}
Dados dos elementos $x,y\in G$ en un grupo, $(x\star y)^{-1}=y^{-1}\star x^{-1}$.
{{% /proposition %}}

{{% proof %}}
Basta comprobar que
$$
\begin{array}{rcl}
(x\star y)\star(y^{-1}\star x^{-1})&=&
x\star (y\star y^{-1})\star x^{-1}\cr
&=&x\star e\star x^{-1}\cr
&=&x\star x^{-1}\cr
&=&e.
\end{array}
$$
{{% /proof %}}

También hemos probado con anterioridad una versión de la proposición anterior para aplicaciones biyectivas.

Los grupos poseen las siguientes **propiedades cancelativas** a izquierda y derecha.

{{% proposition %}}
Dados tres elementos de un grupo $x,y,z\in G$:

* Si $x\star y=x\star z$ entonces $y=z$.

* Si $y\star x=z\star x$ entonces $y=z$.
{{% /proposition %}}

{{% proof %}}
Si $x\star y=x\star z$ entonces 
$$
\begin{array}{rcl}
y&=&x^{-1}\star(x\star y)\cr
&=&x^{-1}\star(x\star z)\cr
&=&x.
\end{array}
$$
La otra propiedad se prueba de manera análoga.
{{% /proof %}}

Las **potencias** positivas de un elemento de un grupo $x\in G$ se definen como $$x^n=x\star\stackrel{n}{\cdots}\star x,\quad n>0.$$
Definimos además $x^0=e$ y $x^n=(x^{-n})^{-1}$ si $n<0$. Así definidas, las potencias satisfacen $x^mx^n=x^{m+n}$ y $(x^m)^n=x^{mn}$ para $m,n\in\mathbb{Z}$ cualesquiera. Además $x^{1}=x$ y $x^{-1}$ su inverso.


{{% definition %}}
Diremos que un elemento de un grupo $x\in G$ tiene **orden finito** si existe un entero positivo $n>0$ tal que $x^n=e$. En este caso, el **orden** de $x$, que denotaremos $o(x)$, es el menor entero positivo que cumple esta propiedad.
{{% /definition %}}

{{% example name="Elementos de orden finito" %}}
* En cualquier grupo, el elemento neutro es el único que tiene orden $1$.

* En el grupo $\\{1,-1,i,-i\\}$ con el producto, el orden de $-1$ es $2$, mientras que el orden de $i$ y de $-i$ es $4$.

* En $GL(n,\mathbb{Q})$, la siguiente matriz tiene orden $n$,
$$
\left(
\begin{array}{cccc}
0 & \cdots & 0 & 1 \cr
1 &        &   & 0 \cr
  & \ddots &   & \vdots \cr
  &        & 1 & 0
\end{array}
\right)
{=} 
\left(
\begin{array}{c|c}
0 & 1\cr
\hline
I_{n-1} & 0
\end{array}
\right).
$$
{{% /example %}}

{{% remark %}}
Cuando el grupo es aditivo, la notación exponencial se cambia por una multiplicativa, es decir,
$$n\cdot x=x+\stackrel{n}{\cdots}+ x,\quad n>0.$$
Definimos además $0\cdot x=0$ y $n\cdot x=-(-n)\cdot x$ si $n<0$. De este modo, se satisface $m\cdot x+n\cdot x=(m+n)\cdot x$ y $n\cdot(m\cdot x)=(n\cdot m)\cdot x$ para todo $m,n\in\mathbb{Z}$. Además $1\cdot x=x$ y $(-1)\cdot x=-x$.

Por tanto, en un grupo aditivo $x\in G$ tiene orden finito si $n\cdot x=0$ para cierto $n>0$ y el orden $o(x)$ es el mínimo.
{{% /remark %}}

{{% proposition %}}
Un elemento de un grupo $x\in G$ tiene orden infinito si y solo si todas sus potencias $x^k$ con $k\in \mathbb Z$ son distintas.
{{% /proposition %}}

{{% proof %}}
En lugar de demostrar $A\Leftrightarrow B$ probaremos NO $A$ $\Leftrightarrow$ NO $B$.

Si $x$ es de orden $n>0$ entonces $x^n=e=x^0$.

Si $x$ tiene dos potencias iguales, digamos $x^r=x^s$ con $r>s$, entonces 
$$
\begin{array}{rcl}
x^{r-s}&=&x^r\star x^{-s}\cr
&=&x^s\star x^{-s}\cr
&=&x^0\cr
&=&e.
\end{array}$$ 
Como $r-s>0$, esto prueba que $x$ tiene orden finito.
{{% /proof %}}

{{% corollary %}}
Si $G$ es un grupo finito, todo elemento tiene orden finito.
{{% /corollary %}}

{{% proposition %}}
Si $x\in G$ es un elemento de orden $o(x)=m$ en un grupo $G$, $x^n=e$ si y solo si $m$ divide a $n$.
{{% /proposition %}}

{{% proof %}}
$\Leftarrow$ Si $m$ divide a $n$ entonces $n=m\cdot k$ para cierto entero $k$, así que 
$$
\begin{array}{rcl}
x^n&=&x^{m\cdot k}\cr
&=&(x^m)^k\cr
&=&e^k\cr
&=&e.
\end{array}
$$


$\Rightarrow$ 
Si $n=0$ el resultado se tiene porque todo entero divide al $0$. Si no, podemos suponer que $n$ es positivo ya que el signo no afecta a la divisibilidad y además, si $n$ fuera negativo,  $x^{-n}=(x^n)^{-1}=e^{-1}=e$. 

Por definición de orden $n\geq m$. Sean $c$ y $r$ el cociente y el resto de la división de $n$ por $m$, $n=m\cdot c+r$. El resto satisface $0\leq r < m$. Basta probar que $r=0$. Por reducción al absurdo, si $r>0$ entonces
$$
\begin{array}{rcl}
x^r&=&x^{n-m\cdot c}\cr
&=&x^n\star (x^m)^{-c}\cr
&=&e\star e^{-c}\cr
&=&e.
\end{array}
$$
Como $0<r<m$, esto contradice $o(x)=m$.
{{% /proof %}}

{{% proposition %}}
Un elemento de un grupo $x\in G$ tiene orden finito si y solo si $\inv{x}$ también. En este caso $o(x)=o(\inv{x})$.
{{% /proposition %}}

{{% proof %}}
Si $o(x)=n$ entonces 
$$
\begin{array}{rcl}
(x^{-1})^n&=&x^{-n}\cr
&=&(x^n)^{-1}\cr
&=&e^{-1}\cr
&=&e.
\end{array}
$$
Por tanto $x^{-1}$ es de orden finito y además $o(x^{-1})\leq o(x)$.

Usando que $(x^{-1})^{-1}=x$, deducimos que $o(x)=o((x^{-1})^{-1})\leq o(x^{-1})$, con lo que se tiene la igualdad, y también la otra implicación.
{{% /proof %}}


{{% definition %}}
Un grupo $(G,\star)$ es **conmutativo** o **abeliano**  si $x\star y=y\star x$ para todo $x,y\in G$.
{{% /definition %}}


## El grupo simétrico

{{% definition %}}
Dado un conjunto $X$, una **permutación** de $X$ es una aplicación biyectiva $\sigma\colon X\to X$.
{{% /definition %}}

{{% proposition %}}
El conjunto $\Sim(X)$ de todas las permutaciones de un conjunto $X$ es un grupo para la composición de aplicaciones, denominado **grupo simétrico**.
{{% /proposition %}}

{{% proof %}}
Basta recordar que la composición de aplicaciones biyectivas es biyectiva. El elemento neutro es $1_X$. La existencia de inversas se probó también en el capítulo de conjuntos.
{{% /proof %}}

{{% remark %}}
El **grupo simétrico de $n$ elementos** $S_n$ es el grupo simétrico del conjunto $\\{1,2, \cdots, n\\}$. Este grupo posee $n!$ elementos. Una manera concisa de representar una permutación de este conjunto es a través de una matriz con dos filas ($n=5$):
$$
\left(\begin{array}{ccccccccc}
         1 & 2 & 3 & 4 & 5\cr
         1 & 5 & 4 & 2 & 3
        \end{array}\right)
$$
En la primera aparecen los números del $1$ al $n$. En la segunda fila, debajo de cada $i$ aparece $\sigma(i)$. En el ejemplo anterior $\sigma(1)=1$, $\sigma(2)=5$, $\sigma(3)=4$, etc. 

![Permutación](../images/permutation.png)

El orden de las columnas no importa, es decir, la siguiente matriz denota la misma permutación que la anterior
$$
\left(\begin{array}{ccccccccc}
         2 & 5 & 3 & 1 & 4\cr
         5 & 3 & 4 & 1 & 2
        \end{array}\right),
$$
si bien lo más común es que los números de la primera fila aparezcan ordenados, como en el primer caso.

La permutación identidad es la que tiene ambas fila iguales
$$
\left(\begin{array}{ccccccccc}
         1 & 2 & 3 & 4 & 5\cr
         1 & 2 & 3 & 4 & 5
        \end{array}\right).
$$
La permutación inversa se obtiene simplemente al intercambiar las filas
$$
\begin{array}{rcl}
\left(\begin{array}{ccccccccc}
         1 & 2 & 3 & 4 & 5\cr
         1 & 5 & 4 & 2 & 3
        \end{array}\right)^{-1}&=&
\left(\begin{array}{ccccccccc}
         1 & 5 & 4 & 2 & 3\cr
         1 & 2 & 3 & 4 & 5
        \end{array}\right)\cr
        &=&
        \left(\begin{array}{ccccccccc}
         1 & 2 & 3 & 4 & 5\cr
         1 & 4 & 5 & 3 & 2
        \end{array}\right).
\end{array}
$$
{{% /remark %}}


{{% example name="Composición de permutaciones" %}}
La composición de permutaciones se puede realizar de manera gráfica del siguiente modo,

![Composición](../images/composition.png)

Con la notación matricial, la composición en $S_n$ se puede llevar a cabo como en el siguiente ejemplo. Consideramos
$$\sigma=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     1 & 3 & 2
                    \end{array}\right),
   \tau=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     3 & 1 & 2
                    \end{array}\right)\in S_3.$$
Para calcular $\sigma\circ\tau$ reordenamos las columnas de $\sigma$ de modo que su primera fila coincida con la segunda de $\tau$:
$$\sigma=\left(\begin{array}{ccc}
                     3 & 1 & 2\cr
                     2 & 1 & 3
                    \end{array}\right).$$
La matriz de $\sigma\circ\tau$ consiste en la primera fila de $\tau$ seguida de la segunda de la última representación de $\sigma$,
$$\sigma\circ\tau=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     2 & 1 & 3
                    \end{array}\right).$$
                    
Calculamos ahora $\tau\circ\sigma$,
$$
   \tau=\left(\begin{array}{ccc}
                     1 & 3 & 2\cr
                     3 & 2 & 1
                    \end{array}\right),
$$
y entonces
$$
   \tau\circ\sigma=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     3 & 2 & 1
                    \end{array}\right).
$$

Observa que $\tau\circ\sigma\neq \sigma\circ\tau$. Esto demuestra que la composición de permutaciones no es conmutativa en general.

Este ejemplo se puede generalizar para demostrar que si $X$ tiene al menos tres elementos el grupo $\Sim(X)$ no es abeliano.
{{% /example %}}

## Ciclos y trasposiciones

{{% definition %}}
Dado un conjunto $X$ el **soporte** de una permutación $\sigma\colon X\rightarrow X$ es el subconjunto
$$\sop (\sigma )=\\{ x\in X\mid \sigma (x)\ne x\\} .$$

Decimos que $\sigma\in \Sim(X)$ es un **ciclo** de **longitud** $n$, o un **$n$-ciclo**, si su soporte es un conjunto finito de $n$ elementos $$\sop (\sigma )=\\{ x_1,x_2,\ldots ,x_n\\}$$ y además
$$
\left\\{
\begin{array}{ll}
\sigma(x\_i)=x\_{i+1},& 1\leq i<n,\cr 
\sigma (x\_n)=x\_1.
\end{array}\right.
$$
Este ciclo se denotará también $$\sigma=(x\_1\; x\_2\;\cdots\; x\_n).$$

Una **trasposición** es un ciclo de longitud 2.
{{% /definition %}}

Un ejemplo de ciclo $(1\; 2\; 3\; 4\; 5)$ donde el soporte es el total:

![Un ciclo](../images/cycle.png)

Otro $(1\; 3\; 4\; 5)$ donde el soporte es un subconjunto propio:

![Otro ciclo](../images/cycle2.png)

Otro ciclo más $(1\; 4\; 3\; 5\; 2)$ que ofrece un aspecto diferente debido al orden de sus entradas:

![Otro ciclo más](../images/cycle3.png)

¡El primer ejemplo de permutación que vimos también es un ciclo! Concretamente el $(2\; 5\; 3\; 4)$:

![Permutación](../images/permutation.png)

Un ejemplo de trasposición $(3\; 4)$ entre elementos consecutivos:

![Un ciclo](../images/transposition.png)

Un ejemplo de trasposición $(2\; 4)$ entre elementos *no* consecutivos:

![Otro ciclo](../images/transposition2.png)


{{% watch %}}
La notación de ciclo no es única, por ejemplo $(x\_1 \; x\_2 \; x\_3)=(x\_3 \; x\_1 \; x\_2)=(x\_2 \; x\_3 \; x\_1)$. 
{{% /watch %}} 

Cualquier notación para los ciclos que quepa en una línea es intrínsecamente mala, lo ideal sería algo así:
![Ciclos circulares](../images/circular_cycle.png)


{{% remark %}}
Dada una permutación $\sigma\in\Sim(X)$, al ser $\sigma\colon X\rightarrow X$ biyectiva, $\sigma(x)=y$ si y solo si $x=\sigma^{-1}(y)$, por tanto $\sigma$ y su inversa $\sigma^{-1}$ tienen el mismo soporte, $\sop(\sigma)=\sop(\sigma^{-1})$.
{{% /remark %}}


{{% proposition %}}
El orden de un ciclo coincide con su longitud.
{{% /proposition %}}

{{% proof %}}
Sea $\sigma=(x\_1\;\cdots\; x\_n)\in \Sim(X)$. Es fácil ver que $\sigma^k(x\_1)=x\_{1+k}\neq x\_1$ para todo $1\leq k<n$, así que $\sigma^k\neq 1\_X$, pero $\sigma^n=1\_X$.
{{% /proof %}}


{{% proposition label="cicletransp" %}}
Todo ciclo es producto de trasposiciones.
{{% /proposition %}}

{{% proof %}}
Es fácil comprobar que $(x\_1\;\cdots\; x\_n)=(x\_1\; x\_2)\cdots (x\_{n-1}\; x\_n)$.
{{% /proof %}}


{{% definition %}}
Dos permutaciones $\sigma ,\tau\in\Sim (X)$ son **disjuntas** si sus soportes son disjuntos, $\sop(\sigma)\cap \sop(\tau)=\varnothing$.
{{% /definition %}}

{{% lemma label="lem:soporte" %}}
Dada $\sigma\in\Sim (X)$, si $x\in\sop(\sigma)$ entonces $\sigma(x)\in\sop(\sigma)$.
{{% /lemma %}}

{{% proof %}}
En vez de $A\Rightarrow B$ probaremos NO $A$ $\Leftarrow$ NO $B$.

Si $\sigma(x)\notin\sop(\sigma)$ entonces $\sigma(\sigma(x))=\sigma(x)$. Como $\sigma$ es inyectiva, esto implica que $\sigma(x)=x$, con lo que $x\notin\sop(x)$.
{{% /proof %}}

{{% remark %}}
El soporte de una permutación $\sigma$, si no es vacío, ha de tener al menos dos elementos ya que si $\sop(\sigma)=\\{x\\}$, como $\sigma(x)\in\sop(\sigma)$ tendríamos que $\sigma(x)=x$, así que $x\notin\sop(\sigma)$, que es una contradicción. Por tanto los ciclos de soporte no vació tienen como poco longitud $2$. El ciclo de longitud $0$, denotado $()$, es la identidad. De hecho la identidad es la única permutación de soporte vacío.
{{% /remark %}}

{{% corollary label="cor:soporte" %}}
Dada $\sigma\in\Sim (X)$, si $x\in\sop(\sigma)$ entonces $\sigma^{n}(x)\in\sop(\sigma)$ para todo $n\in\mathbb{Z}$.
{{% /corollary %}}

{{% proof %}}
Para $n=0$ es obvio. Si $n>0$, es consecuencia del [lema anterior](#lem:soporte), por inducción. Si $n=-1$, se sigue también del lema anterior ya que $\sop(\sigma)=\sop(\sigma^{-1})$. De aquí se deduce también por inducción para todo $n<0$.
{{% /proof %}}

{{% proposition %}}
Si $\sigma,\tau\in\Sim (X)$ son permutaciones disjuntas entonces $\tau\sigma =\sigma\tau$.
{{% /proposition %}}

{{% proof %}}
Tenemos que demostrar que $\tau\sigma (x)=\sigma\tau (x)$ para todo  $x\in X$. 

Si $x\notin\sop (\sigma )\cup\sop (\tau )$ entonces $\sigma(x)=x=\tau(x)$, luego
$$
\begin{array}{rcl}
\tau\sigma (x)&=&\tau(x)\cr
&=&x\cr
&=&\sigma(x)\cr
&=&\sigma\tau (x).
\end{array}
$$

Si $x\in\sop (\sigma )$, como las permutaciones son disjuntas entonces $x\notin\sop (\tau )$, luego $\tau (x)=x$, así que $\sigma\tau (x)=\sigma(x)$. Es más, por el [lema anterior](#lem:soporte) $\sigma(x)\in\sop (\sigma )$, luego $\sigma(x)\notin\sop (\tau )$ y por tanto también $\tau\sigma (x)=\sigma(x)$.

Como los papeles de $\sigma$ y $\tau$ son intercambiables, el argumento anterior también demuestra que $\tau\sigma (x)=\sigma \tau(x)$ si $x\in\sop (\tau)$.
{{% /proof %}}

{{% watch %}}
El recíproco no es cierto.
{{% /watch %}}


{{% theorem %}}
Toda permutación con soporte finito se puede descomponer como producto de ciclos disjuntos. Esta descomposición es única salvo orden.
{{% /theorem %}}

{{% proof %}}
Sea $\sigma\in\Sim (X)$ una permutación. Definimos una relación de equivalencia $\sim$ en $X$ del siguiente modo: $x\sim y$ si existe $n\in\mathbb{Z}$ tal que $y=\sigma^n(x)$. Esta relación es de equivalencia: 

* Reflexividad: $x\sim x$ es cierto para todo $x\in X$ ya que $x=1_X(x)=\sigma^0(x)$.

* Simetría: $x\sim y\Leftrightarrow y\sim x$ pues $y=\sigma^n(x)$ es equivalente a $\sigma^{-n}(y)=x$.

* Transitividad: si $x\sim y\sim z$ entonces $y=\sigma^n(x)$ y $z=\sigma^m(y)$ para ciertos $n,m\in\mathbb{Z}$, luego $z=\sigma^m(\sigma^n(x))=\sigma^{m+n}(x)$, así que $x\sim z$.

Las clases de equivalencia de esta relación se denominan **órbitas**. La órbita de $x\in X$ es 
$$\overline{x}=\\{\sigma^n(x)\mid n\in\mathbb{Z}\\}.$$
Si $x\notin\sop (\sigma )$, entonces $\overline{x}=\\{ x\\}$. Si $x\in\sop (\sigma )$, entonces $\overline{x}\subset\sop (\sigma )$ por el [corolario anterior](#cor:soporte), y por tanto es un conjunto finito. 
Veamos que en general $\bar{x}=\\{x,\sigma(x),\dots,\sigma^{m-1}(x)\\}$ para cierto $m> 0$. Esto nos va a llevar la mayor parte de esta prueba.


Probemos que existe $m> 0$ tal que $\sigma^m(x)=x$. En efecto, como $\overline{x}=\\{\sigma^n(x)\mid n\in\mathbb{Z}\\}\subset\sop (\sigma)$, que es finito, todos los $\sigma^n(x)$ no pueden ser distintos, así que han de existir $p,q\in\mathbb{Z}$, $p\neq q$, tales que $\sigma^p(x)=\sigma^q(x)$. Podemos suponer sin pérdida de generalidad que $p < q$, así que, aplicando $\sigma^{-p}$ a la anterior igualdad deducimos que 
$$
\begin{array}{rcl}
x&=&\sigma^{-p}(\sigma^p(x))\cr
&=&\sigma^{-p}(\sigma^q(x))\cr
&=&\sigma^{q-p}(x),
\end{array}
$$
por tanto podemos tomar $m=q-p> 0$.

Sea $m> 0$ el mínimo tal que $\sigma^m(x)=x$. Los elementos de $\\{x,\sigma(x),\dots,\sigma^{m-1}(x)\\}$ son todos distintos. Lo veremos por reducción al absurdo. De lo contrario existirían $0\leq p<q<m$ tales que $\sigma^p(x)=\sigma^q(x)=\sigma^{p}(\sigma^{q-p}(x))$. La aplicación $\sigma^p$ es inyectiva por ser una permutación, así que esto implicaría que $x=\sigma^{q-p}(x)$, pero $0 < q-p < m$, lo que contradice la minimalidad de $m$.

Ahora tenemos que ver que, para todo $n\in\mathbb {Z}$, $\sigma^n(x)\in  \\{x,\sigma(x),\dots,\sigma^{m-1}(x)\\}$. 
Basta comprobar que, $\sigma^n(x)=\sigma^r(x)$ donde $r$ es el resto no negativo de la división de $n$ por $m$, $n=m\cdot c+r$, $0\leq r<m$. En efecto,
$$
\begin{array}{rcl}
\sigma^n(x)&=&\sigma^{r+m\cdot c}(x)\cr
&=&\sigma^r((\sigma^m)^c(x)).
\end{array}
$$
Como $\sigma^m(x)=x$, entonces $(\sigma^m)^c(x)=0$ si $c\geq 0$. Es más, $\sigma^m(x)=x$ también implica que $x=\sigma^{-m}(x)$, así que $(\sigma^m)^c(x)=0$ también si $c<0$. Por tanto, en efecto, $\sigma^n(x)=\sigma^r(x)$.

Hemos probado que $\sigma$ se comporta sobre cada órbita $\bar x=\\{x,\sigma(x),\dots,\sigma^{m-1}(x)\\}$ como un ciclo de longitud $m$, ya que $\sigma^m(x)=x$, de hecho $m$ era el menor entero positivo que satisfacía esta propiedad. Esto demuestra que $\sigma$ es el producto de los ciclos asociados a las órbitas no unitarias de la anterior relación de equivalencia. Es decir, por cada órbita no unitaria $\bar{x}$, el ciclo $(x\;\sigma(x)\;\dots\;\sigma^{m-1}(x))$ aparece en la factorización de $\sigma$, donde $m$ es el cardinal de $\bar{x}$. El orden de los factores de este producto no importa porque los ciclos son disjuntos, al ser sus soportes clases de una relacion de equivalencia. Hay una cantidad finita de órbitas no unitarias, ya que hemos visto que están contenidas en $\sop(\sigma)$, que es finito. La unicidad es obvia, pues las órbitas, y por tanto los ciclos, están determinados por $\sigma$ y la relación de equivalencia asociada.
{{% /proof %}}


{{% corollary %}}
Toda permutación con soporte finito puede descomponerse como producto de trasposiciones.
{{% /corollary %}}

{{% watch %}}
La descomposición de una permutación como producto de trasposiciones no satisface ninguna propiedad de unicidad.
{{% /watch %}}

{{% example name="Descomposición como producto de ciclos" %}}
Consideremos la permutación
$$\sigma=\left(\begin{array}{ccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7\cr
                     3 & 6 & 5 & 1 & 4 & 2 & 7
                    \end{array}\right)\in S_7 .$$
Las órbitas son:
$$\begin{array}{rcl}
\overline{1}&=&\\{ 1,3,5,4\\},\cr
\overline{2}&=&\\{ 2,6\\},\cr
\overline{7}&=&\\{ 7\\}.
\end{array}$$
Por tanto $\sigma =(1\;3\;5\;4)(2\;6)=(2\;6)(1\;3\;5\;4)=(1\;3)(3\;5)(5\;4)(2\;6)$.
{{% /example %}}

{{% proposition %}}
Si $\sigma\in S_n$ se descompone como producto de $c$ ciclos disjuntos de longitudes respectivas $l_1,\dots, l_c$ entonces el orden de $\sigma$ es el múltiplo común mínimo de $l_1,\dots, l_c$.
{{% /proposition %}}

{{% proof %}}
Sea $\sigma=\sigma_1\cdots\sigma_c$ la descomposición de $\sigma$ como producto de ciclos disjuntos, donde cada $\sigma_i$ es un ciclo de longitud $l_i$. Como las permutaciones disjuntas conmutan, 
$$\sigma^k=\sigma_1^k\cdots\sigma_c^k$$
para todo $k\geq 1$. Aquí estamos usando que el soporte de cada $\sigma_i^k$ está contenido en el de $\sigma_i$ pues si $\sigma_i(x)=x$ entonces $\sigma_i^k(x)=x$ para todo $k\geq 1$. Por tanto, la descomposición de $\sigma^k$ como producto de ciclos disjuntos se obtendrá descomponiendo cada $\sigma_i^k$ y haciendo el producto de todas estas descomposiciones. Por la unicidad de la descomposición de una permutación como producto de ciclos disjuntos, $\sigma^k=1$ si y solo si $\sigma_i^k=1$ para todo $i=1,\dots, c$. Si esto ocurre, es que $k$ es divisible por el orden de $\sigma_i$ para todo $i$, es decir $l_i|k$ para todo $i$. El mínimo valor de $k$ para el que esto pasa es, por definición, el múltiplo común mínimo de $l_1,\dots, l_c$.
{{% /proof %}}



## El signo de una permutación


{{% definition %}}
Un par $(i,j)$ de números $1\leq i,j \leq n$ es una **inversión** de $\sigma\in S_n$, si
$i < j$ pero $\sigma (i) > \sigma (j)$.
{{% /definition %}}

{{% example name="Inversiones" %}}
Las inversiones se corresponden con los cruces en la representación de la permutación como diagrama de flechas:

![Inversiones](../images/permutation_sign.png)

Las inversiones de esta permutación son $(2,3)$, $(2,4)$, $(2,5)$, $(3,4)$ y $(3, 5)$.

Esto es así siempre que dibujemos el diagrama respetando las dos reglas siguientes:

* Dos flechas se cruzan como máximo en un punto.

* En un prunto de cruce nunca concurren más de dos flechas.

Estas configuraciones prohibidas se comprenden mejor con diagramas que muestran lo que *no* puede pasar:

![Configuraciones prohibidas](../images/forbidden_permutations.png)

Siempre podemos evitarlas moviendo un poco las flechas.
{{% /example %}}


{{% definition %}}
El **signo** de una permutación $\sigma\in S_n$ se define como
$$
\signo(\sigma)=(-1)^{\text{nº de inversiones de }\sigma}.
$$
Decimos que $\sigma$ es **par** si $\signo(\sigma)=+1$ e **impar** si $\signo(\sigma)=-1$.
{{% /definition %}}

Obviamente, $\sigma$ es par si tiene un número par de inversiones, e igualmente en el caso impar. La permutación del ejemplo anterior es impar.


{{% example name="$S_3$" %}}
El grupo $S_3$ tiene $3!=6$ elementos, que son los siguientes:
$$
S_3=\\{(), (12), (13), (23), (123), (132)\\}.
$$
Las permutaciones pares de $S_3$ son $()$, $(123)$ y $(132)$ y las impares son $(12)$, $(13)$ y $(23)$.
![S3](../images/s3.png)
{{% /example %}}

{{% proposition %}}
Todas las trasposiciones son impares.
{{% /proposition %}}

{{% proof %}}
Las inversiones de una trasposición $(i\; j)\in S_n$ con $i<j$ son:
$$
\begin{array}{l}
(i,j),\cr
(i,i+1),\dots, (i, j-1),\cr
(i+1,j),\dots, (j-1, j).
\end{array}
$$
En total hay $1+2(j-i-1)$ inversiones, y este es un número impar.
![Inversiones de una trasposición](../images/transsign.png)
{{% /proof %}}

{{% proposition %}}
Dadas dos permutaciones  $\sigma ,\tau\in S_n$:

* $\signo (\sigma\tau )=\signo (\sigma )\signo (\tau )$.

* $\signo (\sigma^{-1})=\signo (\sigma )$.
{{% /proposition %}}

{{% proof %}}
Consideremos el diagrama de $\sigma\tau$ que se obtiene dibujando el diagrama de $\tau$ encima del de $\sigma$. Este diagrama representa a la permutación $\sigma\tau$, aunque haya pares de flechas que se crucen dos veces, una en la parte de $\tau$ y otra en la de $\sigma$.

![Composición](../images/composition.png)

Las inversiones de $\sigma\tau$ se corresponden con los cruces de flechas que se cruzan solo en la parte de $\sigma$ o solo en la de $\tau$, pero no en ambas. Por tanto, para obtener el número de inversiones de $\sigma\tau$, hay que sumar los cruces de los diagramas de $\sigma$ y $\tau$ y restarle el número par de cruces entre flechas que se cruzan dos veces, una en la parte de $\sigma$ y otra en la de $\tau$. Esto prueba que el número de inversiones de $\sigma\tau$ tiene la misma paridad que la suma del número de inversiones de $\sigma$ y de $\tau$. De aquí se deduce la primera fórmula.

La segunda fórmula es obvia porque el diagrama de $\sigma^{-1}$ se obtiene a partir del de $\sigma$ haciendo una simetría horizontal. El número de cruces es el mismo.
{{% /proof %}}

{{% corollary %}}
Una permutación $\sigma\in S_n$ es par si y solo si es producto de un número par de trasposiciones.
{{% /corollary %}}

{{% proof %}}
En efecto, si $\sigma =\tau\_1\cdots\tau\_r$ donde cada $\tau\_i$ es una trasposición, entonces
$$\signo (\sigma )=\signo (\tau\_1)\cdots\signo (\tau\_r)=(-1)^r.$$
{{% /proof %}}

Este corolario es también cierto cambiando *par* por *impar*.

{{% corollary %}}
El signo de un cliclo de longutud $l$ es $(-1)^{l-1}$.
{{% /corollary %}}

Este corolario, que es consecuencia de la descomposición de un ciclo como producto de trasposiciones [vista antes,](#cicletransp) nos dice que un ciclo de longitud par es impar y un ciclo de longitud impar es par.


{{% theorem name="Fórmula de Cauchy" %}}
Si $\sigma\in S_n$ se descompone como producto de $c$ ciclos disjuntos y $\sop(\sigma)$ tiene $s$ elementos entonces
$$\signo (\sigma )=(-1)^{s-c}.$$
{{% /theorem %}}

{{% proof %}}
Sea $\sigma =\sigma\_1\cdots\sigma\_c$ la descomposición de $\sigma$ como producto de ciclos disjuntos. Sea $l\_i$ la longitud del ciclo $\sigma\_i$, $i=1,\dots, c$. El número de elementos del soporte de $\sigma$ es $s=\sum\_{i=1}^{c}l\_i$ y 
$$
\begin{array}{rcl}
\signo(\sigma)&=&\signo(\sigma\_1)\cdots\signo(\sigma\_c)\cr
&=&(-1)^{l\_1-1}\cdots (-1)^{l\_c-1}\cr
&=&(-1)^{\sum\_{i=1}^{c}(l\_i-1)}\cr
&=&(-1)^{s-c}.
\end{array}
$$
{{% /proof %}}



## Subgrupos

{{% definition %}}
Un subconjunto $H\subset G$ de un grupo $G$ es un **subgrupo** de
$G$ si se dan las siguientes condiciones:

* $e\in H$, es decir, el elemento neutro de $G$ está en $H$.

* Si $x,y\in H$ entonces $xy\in H$.

* Si $x\in H$ entonces $x^{-1}\in H$.
{{% /definition %}}

{{% remark %}}
Un subgrupo $H\subset G$ es un grupo por derecho propio con la operación binaria heredada de $G$.
{{% /remark %}}

{{% example name="Ejemplo" %}}

* El subgrupo **trivial** $\\{e\\}\subset G$ y el **total** $G\subset G$.

* Los subgrupos aditivos $\Z\subset\Q\subset\mathbb{R}\subset\mathbb{C}$.

* Los subgrupos multiplicativos $\\{\pm 1\\}\subset\Q\setminus\\{ 0\\}\subset\mathbb{R}\setminus\\{ 0\\}\subset\mathbb{C}\setminus\\{ 0\\}$.

* $(0,+\infty)\subset\mathbb{R}\setminus\\{ 0\\}$.

* El subgrupo $SL(n,k)=\\{A\mid |A|=1\\}\subset GL(n,k)$ de matrices $n\times n$ sobre un cuerpo $k$ de determinante $1$.

* El subrgupo de Klein $\\{(), (1\;2)(3\;4), (1\;3)(2\;4), (1\;4)(2\;3)\\}\subset S_4$.
{{% /example %}}


{{% proposition %}}
Dado un grupo $G$, $H\subset G$ es un subgrupo si y solo si se satisfacen las dos condiciones siguientes:

* $H\neq\varnothing$ 

* Si $x,y\in H$ entonces $x^{-1}y\in H$.
{{% /proposition %}}

{{% proof %}}
$\Rightarrow$ Como $e\in H$, $H$ no es vacío. Si $x,y\in H$, tenemos que también $x^{-1}\in H$, así que $x^{-1}y\in H$.

$\Leftarrow$ Como $H\neq \varnothing$ ha de existir algún $z\in H$, así que $e=z^{-1}z\in H$. Dado $x\in H$, como $e\in H$ tenemos que $x^{-1}=x^{-1}e\in H$. Es más, dados $x,y\in H$, como también $x^{-1}\in H$ deducimos que $xy=(x^{-1})^{-1}y\in H$.
{{% /proof %}}

{{% definition %}}
Dado un grupo $G$ y un subconjunto $X\subset G$, si definimos $X^{-1}=\\{x^{-1}\mid x\in X\\}$, el **subgrupo generado por $X$** se define como
$$\langle X\rangle =\\{y\in G\mid \exists n\geq 0, x_1,\dots, x_n\in X\cup X^{-1}; y=x_1\cdots x_n\\}\subset G.$$
{{% /definition %}}

{{% proposition %}}
Para cualquier subconjunto $X\subset G$ de un grupo $G$, $\langle X\rangle\subset G$ es un subgrupo.
{{% /proposition %}}

{{% proof %}}
Tenemos que $e\in G$ ya que $e$ es el producto de una cantidad nula de elementos ($n=0$). Por otro lado, dados $y,\bar{y}\in \langle X\rangle$, tenemos que $y=x\_1\cdots x\_p$ e $\bar{y}=\bar{x}\_1\cdots \bar{x}\_q$ donde $x\_i,\bar{x}\_j\in X\cup X^{-1}$. Por definición, si $x\in X$ entonces $x^{-1}\in X^{-1}$. Es más, si $z\in X^{-1}$ entonces $z=x^{-1}$ para algún $x\in X$, por tanto $z^{-1}=(x^{-1})^{-1}=x\in X$. Esto prueba que los inversos de los elementos de $X\cup X^{-1}$ están también en $X\cup X^{-1}$, por tanto el elemento
$$
\begin{array}{rcl}
y^{-1}\bar{y}&=&(x_1\cdots x_p)^{-1}(\bar{x}\_1\cdots \bar{x}\_q)\cr
&=&x_p^{-1}\cdots x_1^{-1}\bar{x}\_1\cdots \bar{x}\_q
\end{array}
$$
también está en $\langle X\rangle$.
{{% /proof %}}

En general, $\langle\varnothing\rangle =\\{e\\}$ es el subgrupo trivial.

{{% example name="Generadores de $S_n$" %}}
$$
\begin{array}{rcl}
S_n&=&\langle \text{ciclos} \rangle\cr
&=&\langle \text{trasposiciones} \rangle\cr
&=&\langle (1\;2),\dots,(n-1\; n) \rangle\cr
&=&\langle (1\;2),\dots, (1\; n) \rangle\cr
&=&\langle (1\;2),(1\;\dots\; n) \rangle.
\end{array}
$$
Observa que hemos omitido las llaves en los conjuntos anteriores, es decir, no hemos escrito $\langle\\{ (1\;2),(1\;\dots\; n) \\}\rangle$. Lo hacemos para no sobrecargar la notación.
{{% /example %}}

{{% definition %}}
Un grupo $G$ es **cíclico** si existe $x\in G$ tal que $G=\langle x\rangle$.
{{% /definition %}}

{{% remark %}}
Observa que en general $\langle x\rangle=\\{x^n\mid n\in\mathbb{Z}\\}$. ¡Ojo! 
Si $x$ tiene orden infinito, todas estas potencias son distintas, luego $\langle x\rangle$ es infinito. Sin embargo, si $x$ tiene orden finito habrá potencias de $x$ con exponente distinto que sean iguales . En cualquier caso $\langle x\rangle$ es abeliano ya que $$x^px^q=x^{p+q}=x^{q+p}=x^qx^p.$$
{{% /remark %}}

{{% proposition %}}
Si $x\in G$ es de orden $n$ entonces $\langle x\rangle = \\{e,x,\dots, x^{n-1}\\}$ es un subgrupo de $n$ elementos.
{{% /proposition %}}

{{% proof %}}
Veamos por reducción al absurdo que todos los elementos de $\\{e,x,\dots, x^{n-1}\\}$ son diferentes. Supongamos que dos de ellos fueran iguales $x^p=x^q$, $p\neq q$. Podemos suponer sin pérdida de generalidad que $p > q$. Entonces 
$$
\begin{array}{rcl}
x^{p-q}&=&x^px^{-q}\cr
&=&x^qx^{-q}\cr
&=&e.
\end{array}
$$
Esto es imposible porque $1\leq p-q\leq n-1$ y $o(x)=n$.

La inclusión  $\langle x\rangle \supset \\{e,x,\dots, x^{n-1}\\}$ es obvia. Para probar la otra $\subset$, tomamos una potencia cualquiera $x^d$ y realizamos la división de $d$ por $n$, $d=cn+r$, $0\leq r<n$. Entonces
$$
\begin{array}{rcl}
x^d&=&x^{cn+r}\cr
&=&(x^n)^cx^r\cr
&=&e^cx^r\cr
&=&ex^r\cr
&=&x^r,
\end{array}
$$
y $x^r\in \\{e,x,\dots, x^{n-1}\\}$. Esto termina la demostración.
{{% /proof %}}


{{% example name="¿Es $S_n$ cíclico?" %}}
Tenemos que $S_2=\langle (1\; 2)\rangle$, pero $S_n$ no es cíclico para ningún otro $n>2$. Veámoslo. Todo elemento $\sigma\in S_n$ se puede descomponer como producto de $c$ ciclos disjuntos de longitud $l_1,\dots, l_c$. El número de elementos del soporte de $\sigma$ es $l_1+\cdots+l_c\leq n$. Es fácil pero tedioso ver que 
$$o(\sigma)=\operatorname{mcd}(l_1,\dots, l_c)\leq l_1\cdots l_c < n!$$
excepto si $n=2$, $c=1$ y $l_1=2$. Por tanto $|\langle\sigma\rangle|=o(\sigma) < n!=|S_n|$, así que la inclusión $\langle\sigma\rangle\subset S_n$ ha de ser siempre estricta si $n>2$.
{{% /example %}}

## El teorema de Lagrange

{{% definition %}} 
Dado un grupo  $G$ y un subgrupo $H\subset G$, definimos la siguiente relación en $G$:
$$
x\sim_H y \Leftrightarrow \inv{x} y\in H.
$$
{{% /definition %}} 

{{% proposition %}}
La relación $\sim_H$ es de equivalencia.
{{% /proposition %}}

{{% proof %}}

* Reflexiva: $x\sim_H x$ pues $x^{-1}x=e\in H$.

* Simétrica: si $x\sim_H y$ es porque $x^{-1}y\in H$, entonces $(x^{-1}y)^{-1}\in H$ y 
$$
\begin{array}{rcl}
(x^{-1}y)^{-1}&=&y^{-1}(x^{-1})^{-1}\cr
&=&y^{-1}x,
\end{array}
$$
luego $y^{-1}x\in H$, es decir $y\sim_H x$.

* Transitiva: si $x\sim_H y\sim_H z$ es porque $x^{-1}y, y^{-1}z\in H$, luego $x^{-1}z=(x^{-1}y)(y^{-1}z)\in H$, así que $x\sim_H z$.
{{% /proof %}}

{{% remark %}}
El conjunto cociente de $G$ por la relación de equivalencia $\sim_H$ se denota
$G/H:=G/\sim_H$.
{{% /remark %}}

{{% proposition %}}
Dado un grupo  $G$, un subgrupo $H\subset G$ y un elemento $x\in G$, la clase de equivalencia de $x$ para la relación $\sim_H$ es
$$
[x]=x H:=\\{ x h\mid h\in H\\}.
$$
{{% /proposition %}}

{{% proof %}}
$\supset$ Dado $xh\in xH$, como $x^{-1}(xh)=h\in H$, $x\sim_H xh$, luego $xh\in [x]$.

$\subset$ Dado $y\in[x]$, como $x\sim_H y$ tenemos que $x^{-1}y\in H$ así que $y=x(x^{-1}y)\in x H$.
{{% /proof %}}

{{% remark %}}
La clase de equivalencia $xH$ se denomina **clase a izquierda**. Podemos definir otra relación de equivalencia en $G$:
$$
  x\; {}\_H\\!\sim y \Leftrightarrow xy^{-1}\in H.
$$ 
En este caso las clases de equivalencia son de la forma $Hx=\\{hx\mid h\in H\\}$, $x\in G$, y se llaman **clases a derecha**. 
En general, las relaciones $\sim_H$ y ${}_H\\!\sim$ son diferentes, por tanto las clases a izquierda no tienen por qué coincidir con las clases a la derecha. Ambas relaciones son iguales si $G$ es abeliano, y en ese caso las clases a izquierda y a derecha de cada elemento de $G$ coinciden.
{{% /remark %}}


{{% definition %}}
El **orden** $|G|$ de un grupo $G$ es su número de elementos.

Dado un grupo $G$, el **índice** de un subgrupo $H\subset G$, denotado $[G:H]$, es el número de clases de equivalencia para la relación $\sim_H$, es decir, el número de elementos de $G/H$.
{{% /definition %}}

{{% theorem name="de Lagrange" %}}
 Si $G$ es un grupo finito y
$H\subset G$ es un subgrupo, entonces $\vert H\vert$ divide a $\vert
G\vert$ y $[G:H]=|G|/|H|$.
{{% /theorem %}}

{{% proof %}}
Como $G$ es finito, habrá solo un número finito de
clases de equivalencia $[G:H]=n$,  $$G/H=\\{x\_1 H,\ldots,
x\_n H\\}.$$ Al ser $G$ unión disjunta de estas clases, 
$$
 | G| = \\# (x\_1 H)+\cdots +\\# (x\_n H).
$$
Para cualquier $x\in G$, la aplicación $f\colon H\rightarrow xH$ definida como $f(h)=xh$ es biyectiva. En efecto, es sobreyectiva por definición de $xH$. Además es inyectiva porque si $f(h_1)=f(h_2)$ entonces $xh_1=xh_2$ y por la propiedad cancelativa $h_1=h_2$. Por tanto $\\# (xH)=|H|$ para todo $x\in G$, así que deducimos de la ecuación anterior que $|G|=n|H|$.
{{% /proof %}}


{{% corollary %}}
Dado un grupo finito $G$ y $x\in G$, el orden de $x$ divide al orden de $G$.
{{% /corollary %}}

{{% proof %}}
Como el orden de $x$ es el número de elementos del subgrupo $\langle x\rangle\subset G$, se deduce del teorema de Lagrange.
{{% /proof %}}


{{% corollary %}}
Si $G$ es un grupo cuyo orden es un número primo $p$, entonces $G$ es cíclico.
{{% /corollary %}}

{{% proof %}}
Sea $x\in G$ un elemento no trivial, como $\langle x\rangle\subset G$ no es el subgrupo trivial y $o(x)=|\langle x\rangle|$ divide a $|G|=p$, no queda más remedio que $o(x)=|\langle x\rangle|=p$, así que $\langle x\rangle =G$ ya que ambos tienen el mismo número de elementos.
{{% /proof %}}

{{% exercise %}}
Hemos visto que el orden de cualquier subgrupo de $G$ divide a $|G|$. Dado un divisor $n$ de $|G|$, ¿existe algún subgrupo de $G$ de orden $n$? Considera los casos $G=S_2, S_3, S_4$.
{{% /exercise %}}



## Homomorfismos

{{% definition %}}
Dados dos grupos $G$ y $H$, un **homomorfismo** $f\colon G\rightarrow H$ es una aplicación tal que $f(xy)=f(x)f(y)$ para todo $x,y\in G$.
{{% /definition %}}


{{% example name="Homomorfismos" label="homomorphisms" %}}

1. La **identidad** $\id{G}\colon G\rightarrow G$.

2. La **inclusión** de un subgrupo $H\subset G$, $i\colon H\hookrightarrow G$.

3. El **signo** de una permutación, $\sign\colon\perm{n}\to\\{\pm1\\}$.

4. El **determinante** $GL(n,k)\rightarrow k\setminus\\{0\\}$, $A\mapsto |A|$.

5. Dado un grupo $G$ y un elemento $x\in G$, la **conjugación** por $x$, $c_x\colon G\rightarrow G$, $c_x(y)=x^{-1}yx$.

6. Dado $n\in\mathbb Z$, la **multiplicación** por $n$, es decir, la aplicación $f\colon \mathbb Z\to\mathbb Z$ definida como $f(x)=n x$.

7. Si $G$ es un grupo abeliano multiplicativo, la **exponenciación** $f\colon G\to G$, $f(x)=x^n$, es un homomorfismo ya que $$f(xy)=(xy)^n=(xy)\stackrel{n}{\cdots}(xy)=x^ny^n=f(x)f(y).$$

8. La aplicación **exponencial** $f\colon\mathbb R\to (0,+\infty)$, $f(x)=e^x$, 
es un homomorfismo del grupo aditivo $\mathbb{R}$ en el grupo multiplicativo $(0,+\infty)$.
{{% /example %}}

Los homomorfismos preservan el elemento neutro y los simétricos.

{{% proposition %}}
Si $f\colon G\rightarrow H$ es un homomorfismo, entonces: 

* $f(e)=e$.

* $f(\inv{x})=\inv{f(x)}$ para todo $x\in G$.
{{% /proposition %}}

{{% proof %}}
Como $e=e e$,
\\[f(e)=f(e e)=f(e) f(e).\\]
Usando la propiedad cancelativa deducimos que $e=f(e)$.

Al ser $e=x \inv{x}$ deducimos que
\\[e=f(e)=f(x \inv{x})=f(x) f(\inv{x}),\\]
por tanto $f(\inv{x})=\inv{f(x)}$.
{{% /proof %}}

{{% corollary %}}
La imagen de un homomorfismo $f\colon G\rightarrow H$ es un subgrupo $\im f\subset H$.
{{% /corollary %}}

{{% proof %}}
Por definición de homomorfismo, el producto de dos elementos de $\im f$ está en $\im f$. Es más, por la proposición anterior $e\in\im f$ y el inverso de un elemento de $\im f$ están en $\im f$.
{{% /proof %}}

La composición de homomorfismos es un homomomorfismo.

{{% proposition %}}
Dados dos homomorfismos como en el siguiente diagrama,
\\[G\stackrel{f}\To H\stackrel{g}\To K,\\]
la composición
$g\circ f\colon G\rightarrow K$
es un homomorfismo.
{{% /proposition %}}

{{% proof %}}
Basta observar que, dados $x,y\in G$,
\begin{align*}
(g\circ f)(x y)&=g(f(x y))\\
&=g(f(x) f(y))\\
&=g(f(x)) g(f(y))\\
&=(g\circ f)(x) (g\circ f)(y).
\end{align*}
{{% /proof %}}

{{% definition %}}
Un **monomorfismo** $f\colon G\hookrightarrow H$ es un homomorfismo inyectivo. Un **epimorfismo** $f\colon G\twoheadrightarrow H$ es un homomorfismo sobreyectivo. Un **isomorfismo** 
$$f\colon G\stackrel{\cong}{\longrightarrow} H$$
es un homomorfismo biyectivo.
{{% /definition %}}

De los homomorfismos del [ejemplo](#homomorphisms) anterior,
son isomorfismos los siguientes: 1, 3 para $n=2$, 4 para $n=1$, 5 ya que $c\_x$ tiene inverso $c\_{x^{-1}}$, 6 y 7 si $n=\pm1$, y 8. Además, 2 es un monomorfismo, y 3 y 4 son epimorfismos para todo $n\geq 1$.


{{% proposition %}}
La composición de isomorfismos es un isomorfismo.
{{% /proposition %}}

{{% proof %}}
Se deduce de que ya sabemos que la composición de homomorfismos es un homomorfismo y que la composición de aplicaciones biyectivas es biyectiva.
{{% /proof %}}


{{% proposition %}}
Si $f\colon G\to H$ es un isomorfismo entonces la aplicación inversa $f^{-1}\colon H\to G$ también.
{{% /proposition %}}

{{% proof %}}
Dados $x,y\in H$ cualesquiera, hemos de probar que
\\[f^{-1}(x y)=f^{-1}(x) f^{-1}(y).\\]
Como $f$ es inyectivo, bastará comprobar que
\\[f(f^{-1}(x y))=f(f^{-1}(x) f^{-1}(y)).\\]
Por un lado, por ser $f^{-1}$ la inversa de $f$,
\\[f(f^{-1}(x y))=(f\circ f^{-1})(x y)=1_H(xy)=x y.\\]
Por otro lado, como $f$ es un homomorfismo,
$$\begin{array}{rcl}
f(f^{-1}(x) f^{-1}(y))&=&f(f^{-1}(x)) f(f^{-1}(y))\cr
&=&(f\circ f^{-1})(x)(f\circ f^{-1})(y)\cr
&=&1_H(x)1_H(y)\cr
&=&x y.
\end{array}$$
{{% /proof %}}

{{% example name="Isomorfismos inversos" %}}
Los inversos de los isomorfismos 1, 5 y 8 del [ejemplo](#homomorphisms) anterior son, respectivamente, $\id{G}^{-1}=\id{G}$, $(c\_x)^{-1}=c\_{x^{-1}}$, y el isomorfismo $f^{-1}\colon(0,+\infty)\to\mathbb R$ definido por $f^{-1}(x)=\log(x)$.
{{% /example %}}

{{% definition %}}
Dos grupos $G$ y $H$ son **isomorfos**, y lo denotamos $G\cong H$, si existe un isomorfismo $$f\colon G\stackrel{\cong}\To H.$$
{{% /definition %}}

{{% proposition %}}
La relación de ser isomorfos es de equivalencia.
{{% /proposition %}}

{{% proof %}}
Es reflexiva $G\cong G$ porque la identidad es un isomorfismo $1\_G\colon G\to G$. La simetría se sigue de que si $G\cong H$ es por que hay algún isomorfismo
$$f\colon G\stackrel{\cong}\To H.$$
El isomorfismo inverso
$$f^{-1}\colon H\stackrel{\cong}\To G$$
prueba que $H\cong G$. La transitividad es consecuencia de que si $G\cong H\cong K$ es porque hay isomorfismos
\\[G\mathop{\To}\limits^f\_\cong H\mathop{\To}\limits^g\_\cong K.\\]
Entonces la composición es un isomorfismo
\\[g\circ f\colon G\stackrel{\cong}\To K,\\]
así que $G\cong K$.
{{% /proof %}}

{{% definition %}}
Dado un homomorfismo $f\colon G\to H$, su **núcleo** es
\\[\ker f=\\{x\in G\mid f(x)=e\\}\subset G.\\]
{{% /definition %}}


{{% proposition %}}
El núcleo de un homomorfismo $f\colon G\to H$ es un subgrupo $\ker f\subset G$.
{{% /proposition %}}

{{% proof %}}
Como $f(e)=e$, $e\in \ker f$. Si $x,y\in\ker f$ entonces
$$f(xy)=f(x)f(y)=ee=e,$$
luego $xy\in\ker f$. Es más, si $x\in\ker f$ entonces
$$f(x^{-1})=f(x)^{-1}=e^{-1}=e,$$
así que $x^{-1}\in\ker f$.
{{% /proof %}}

{{% proposition %}}
Un homomorfismo $f\colon G\to H$ es inyectivo si y solo si $\ker f=\\{e\\}$.
{{% /proposition %}}

{{% proof %}}
$\Rightarrow$ La inclusión $\supset$ es obvia. Para ver $\subset$ tomamos $x\in\ker f$. Como $f(x)=e=f(e)$ y $f$ es inyectivo deducimos que $x=e$.

$\Leftarrow$. Sean $x,y\in G$ tales que $f(x)=f(y)$. Entonces
$$
\begin{array}{rcl}
f(x^{-1}y)&=&f(x^{-1})f(y)\cr
&=&f(x)^{-1}f(x)\cr
&=&e,
\end{array}
$$
es decir, $x^{-1}y\in\ker f=\\{e\\}$, por tanto $x^{-1}y=e$ y despejando vemos que $y=x$.
{{% /proof %}}

{{% remark %}}
Esta proposición demuestra que para probar que un homomorfismo $f\colon G\rightarrow H$ es inyectivo basta demostrar que si $f(x)=e$ entonces $x=e$.
{{% /remark %}}


## Cocientes


<!--

{{% example name="Ejemplo" %}}

Volviendo al ejemplo en el que el subgrupo de $S_4$, $\langle (123),(234)\rangle$, resulta ser $A_4$, el teorema de Lagrange nos evita algún cálculo. Conforme van apareciendo nuevos elementos del subgrupo, en cuanto aparezca el noveno elemento, como el orden debe ser un divisor de $24$, sabemos que $\langle (123),(234)\rangle$ tiene 12 o 24 elementos. Al tratarse de permutaciones pares exclusivamente, se deduce que el subgrupo es $A_4$.

Es más, sabiendo que $\langle (123),(234)\rangle\subset A_4$, como el orden de $A_4$ es 12, basta con llegar al séptimo elemento para decidir que $\langle (123),(234)\rangle = A_4$
{{% /example %}}

{{% watch %}}
Terminamos el estudio del teorema de Lagrange proponiendo el ejercicio siguiente. Sabemos que el orden de cualquier subgrupo de $G$ divide a su orden. Recíprocamente, si $m$ divide a $|G|$, ?`existe algún subgrupo de $G$ de orden $m$? Te animamos a reflexionar esta cuestión en el grupo $S_4$ o en sus subgrupos.
{{% /watch %}}



<!--



{{% theorem %}}
{El grupo alternado $A_n$}
{El conjunto $A_n$ de las permutaciones pares de $S_n$ es un subgrupo llamado {\bf grupo alternado}.}
{{% /theorem %}}


{{% proposition %}}

Sea $H\in S_n$ un subgrupo que tiene alguna permutación impar, entonces $H$ posee tantas permutaciones pares como impares.
{{% /proposition %}}

{{% proof %}}

Sean $P$ e $I$ los subconjuntos de $H$ formados por las permutaciones pares e impares, respectivamente. Sea $\rho\in H$ una permutación impar. Consideremos la aplicación
$$\begin{array}{rcl}
   \varphi\colon P&\to&I\\
   \sigma & \mapsto & \rho\sigma  .
  \end{array}$$
Efectivamente $\varphi$ es una aplicación bien definida, pues si $\sigma$ es una permutación par, como $\rho$ es impar, el producto $\rho\sigma$ es también impar.

Si $\varphi (\sigma )=\varphi (\tau )$ entonces $\rho\sigma =\rho\tau$, y por la propiedad cancelativa $\sigma =\tau$. Luego $\varphi$ es una aplicación inyectiva.

Por otro lado, si $\sigma\in I$, como $\rho^{-1}$ es impar, entonces $\rho^{-1}\sigma \in P$ y además $\varphi (\rho^{-1}\sigma )=\rho\rho^{-1}\sigma =\sigma$. Luego $\varphi$ es sobreyectiva.

Por tanto la aplicación $\varphi$ es biyectiva y hay tantas permutaciones pares como impares en $H$.
{{% /proof %}}

{{% corollary %}}

Si $n\geq 2$, el número de elementos de $A_n$ es $|A_n|=n!/2$, es decir, en $S_n$ hay tantas permutaciones pares como impares.
{{% /corollary %}}

{{% proof %}}

$S_n$ es un subgrupo de $S_n$ que, como $n\geq 2$, contiene a la permutación impar $(12)$. Luego podemos aplicar la proposición anterior para deducir que hay tantas permutaciones pares como impares.
{{% /proof %}}




## Subgrupos normales. Grupo cociente

Dado un grupo $(G,\star)$ y un elemento $x\in G$, recordemos el isomorfismo $c_x\colon G\rightarrow G$ que {\it conjuga por $x$} a los elementos de $G$, es decir, $c_x(y)=x^{-1}yx$ para todo $y\in G$.

Dado un subgrupo $K\subset G$, podemos aplicarle el isomorfismo $c_x$ a todos sus elementos y obtendremos un subgrupo de $G$ (el conjugado de $K$ por $x$):
$$
    c_x(K)=x^{-1}Kx =\\{x^{-1}yx;\ y\in K\\}.
$$
El grupo $x^{-1}Kx$ podría ser el propio $K$, o podría ser distinto. Diremos que $K$ es {\it normal en $G$} cuando obtenemos siempre el propio $K$, sea cual sea el elemento $x\in G$ escogido:


{{% definition %}}
{Subgrupos normales}
{	Dado un grupo $(G,\star)$ y un subgrupo $K\subset G$, decimos que $K$ es {\bf normal} en $G$ si para todo $x\in G$ se tiene que 
	\[\inv{x} K x\subset K.\]}
{{% /definition %}}



\begin{lema}
	Si $K\subset G$ es un subgrupo normal, la inclusión de la definición anterior es de hecho una igualdad.
\end{lema}

{{% proof %}}

    Fijemos un elemento cualquiera $a\in G$. Como $K$ es normal, tomando $x=a$ tenemos $a^{-1}Ka\subset K$. Pero también, tomando $x=a^{-1}$ tenemos $aKa^{-1}\subset K$. Esto quiere decir que dado cualquier $k\in K$ se tiene $aka^{-1}=k'\in K$, es decir, $k=a^{-1}k'a$, luego $k\in a^{-1}Ka$. Por tanto $K\subset a^{-1}Ka$, luego $a^{-1}Ka=K$. Como esto lo hemos hecho para todo $a\in G$, el resultado queda demostrado.
{{% /proof %}}

{{% watch %}}

Del lema anterior se deduce que un subgrupo $K$ es normal en $G$ si y solo si $aK=Ka$ para todo $a\in G$. En otras palabras, un subgrupo $K$ es normal en $G$ si y solo si las clases a izquierda (definidas para $K$) coinciden con las clases a derecha.
{{% /watch %}}

Es importante observar que la igualdad $x^{-1}Kx=K$ no implica que los elementos de $K$ quedan fijos al conjugarlos por $x$. Lo que queda fijo es el conjunto $K$, pero sus elementos pueden permutarse. Por tanto, $K$ es normal si y solo si conjugar $K$ por $x$ corresponde a una {\it permutación} de $K$, para todo $x\in G$.

Esta permutación puede ser trivial o no. En el siguiente caso, la permutación sí es trivial para todo $x$:


{{% proposition %}}

Si $(G,\star)$ es abeliano, todo subgrupo $K\subset G$ es normal.
{{% /proposition %}}

{{% proof %}}

	Si $G$ es abeliano, $x^{-1}kx=k$ para todo $k\in K$ y para todo $x\in G$. Por tanto, conjugar un subgrupo $K$ por un elemento $x$ induce la permutación trivial en $K$. Luego todo subgrupo de $G$ es normal en $G$.
{{% /proof %}}

{{% example name="Ejemplo" %}}

	Los subgrupos trivial y total $\\{e\\}$ y $G$, son normales en cualquier grupo $G$. El subgrupo $K=\\{\id{},(1\; 2)\\}\subset \perm{3}$ no es normal puesto que
	\[\inv{(1\;3)}(1\;2)(1\;3)=(1\;3)(1\;2)(1\;3)=(2\;3)\notin K.\]
{{% /example %}}

Hay una relación muy estrecha entre {\it subgrupos normales} de un grupo $G$ y {\it núcleos} de homomorfismos que parten de $G$. De hecho, todo núcleo es un subgrupo normal, y todo subgrupo normal es el núcleo de un homomorfismo. Veamos lo primero:

{{% proposition %}}

	El núcleo de un homomorfsimo $f\colon (G,\star)\to (H,\ast)$ es un subgrupo normal de $G$.
{{% /proposition %}}

{{% proof %}}

	Dado $x\in G$, veamos que $\inv{x} \ker(f) x\subset \ker(f)$. Dado un elemento del primer conjunto, será de la forma $x^{-1}yx$ con $y\in\ker(f)$. Y tendremos:
	\[f(\inv{x} y x)=f(\inv{x}) f(y) f(x)=\inv{f(x)} e f(x)=\inv{f(x)}  f(x)=e,\]
	luego $\inv{x} y x\in\ker(f)$.
{{% /proof %}}


La propiedad más importante de los subgrupos normales $K\subset G$ es que sirven para definir una operación de grupo, de la forma más natural posible, en el conjunto cociente $G/K$.


{{% theorem %}}
{Grupo cociente}
{	Si $(G,\star)$ es un grupo y $K\subset G$ es un subgrupo normal, entonces el conjunto cociente $G/K$ posee una única estructura de grupo $(G/K,\bar \star)$ tal que la proyección natural $p\colon G\to G/K$ es un homomorfismo
	\[p\colon (G,\star)\To (G/K,\bar \star).\]}
{{% /theorem %}}

{{% proof %}}

	Definimos el producto de dos clases como \[(x K)\bar\star(y K)=(x y) K.\]
	Tenemos que demostrar que $\bar{\star}$ está bien definido, es decir que esta definición de $\bar{\star}$ no depende de los representantes tomados. Para ello hemos de probar que si $x K=\tilde x K$ e $y K=\tilde y K$ entonces
	\[(x K)\bar\star(y K)=(\tilde x  K)\bar\star(\tilde y K).\]
Es decir, debemos probar que
	\[x y K=\tilde x \tilde y K,\]
  os lo que es lo mismo, que $y^{-1}x^{-1}\tilde x \tilde y\in K$.

	Por un lado, como $xK=\tilde xK$, tenemos $x^{-1}\tilde x = z_1 \in K$, y como $yK=\tilde yK$, tenemos $y^{-1}\tilde y = z_2 \in K$. Por otro lado, como $K$ es normal en $G$ y $z_1\in K$, se tiene $y^{-1}z_1 y\in K$. Por tanto,
   $$
      y^{-1}x^{-1}\tilde x \tilde y= y^{-1} x^{-1} x z_1 y z_2 = (y^{-1} z_1 y) z_2\in K,
   $$
  como queríamos demostrar.

	Con la definición anterior de $\bar{\star}$ es inmediato comprobar que $\bar{\star}$ es asociativo por serlo $\star$, que el elemento neutro del cociente es $e K$ y que el inverso de un elemento del cociente es $\inv{(x K)}=\inv{x} K$. Es más, $p$ es un homomorfismo puesto que dados $x_1,x_2\in G$,
	\[p(x_1 x_2)=(x_1 x_2) K=(x_1\ K)\bar{\star}(x_2 K)=p(x_1)\bar \star p(x_2).\]
	Además $\bar \star$ es el único producto que satisface esta propiedad puesto que la proyección natural $p$ es sobreyectiva.
{{% /proof %}}


Observemos que, en el grupo cociente $G/K$, el elemento neutro es la clase $eK$, es decir, el propio $K$. Además, el inverso del elemento $xK$ es el elemento $x^{-1}K$.


Como vimos antes, el núcleo de un homomorfismo es un subgrupo normal. Ahora ya podemos demostrar que todo subgrupo normal es núcleo de un homomorfismo.

{{% proposition %}}

	Sea $K$ un subgrupo normal en $G$. El núcleo de la proyección natural $p\colon (G,\star)\to (G/K,\bar \star)$ es precisamente $\ker(p)=K$.
{{% /proposition %}}

{{% proof %}}

	Basta observar que $p(x)=x K=e K$ si y solo si $x\in K$.
{{% /proof %}}

Hemos identificado entonces subgrupos normales con núcleos de homomorfismos. No podemos hacer lo mismo con las imágenes de homomorfismos:

{{% example name="Ejemplo" %}}

	Si $(G,\star)$ es un grupo y $F\subset G$ es un subgrupo \emph{cualquiera}, la imagen de la inclusión $i\colon (F,\star)\to (G,\star)$ es $\im(i)=F$, por tanto la imagen de un homomorfismo, en general, no es normal en el grupo de llegada.
{{% /example %}}

{{% theorem %}}
{Factorización canónica}
{	Todo homomorfismo $f\colon (G,\star)\to (H,\ast)$ factoriza como la composición $f=i\circ\bar f\circ p$ de un epimorfismo $p$,  un isomorfismo $\bar f$ y un monomorfismo $i$ del siguiente modo
	\[\xymatrix{(G,\star)\ar[r]^-{f}\ar[d]_-p& (H,\ast)\\
		(G/\ker(f),\bar \star)\ar[r]^-\cong_-{\bar f}& (\im(f),\ast)\ar[u]_-i}\]
	Aquí $p$ es la proyección natural sobre el cociente e $i$ es la inclusión del subgrupo imagen.}
{{% /theorem %}}

{{% proof %}}

	La factorización es la misma que la de una aplicación cualquiera. Ya sabemos que $p$ e $i$ son homomorfismos. Sabemos también que $p$ es sobreyectiva, $i$ es inyectiva y que $\bar f$, definida por ${\bar f}(x \ker(f))=f(x)$, es biyectiva. Basta por tanto ver que $\bar f$ es un homomorfismo. Por comodidad, llamaremos $K=\ker(f)$. Al ser $f$ un homomorfismo,
	\begin{align*}
		\bar f((x_1  K )\bar \star (x_2  K ))&= \bar f(x_1 x_2  K )\\
		&=f(x_1 x_2) \\
		&=f(x_1)\ast f(x_2) \\
		&=\bar f(x_1  K )\ast\bar f(x_2  K ).
	\end{align*}
	Luego $\bar f$ es también un homomorfismo.
{{% /proof %}}

{{% corollary %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un epimorfismo entonces $\bar f\colon (G/\ker(f),\bar \star)\to (H,\ast)$ es un isomorfismo.
{{% /corollary %}}

{{% corollary %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un monomorfismo entonces $\bar f\colon (G,\star)\to (\im(f),\ast)$ es un isomorfismo.
{{% /corollary %}}

{{% theorem %}}
{Teorema de Cayley}
{	Todo grupo $G$ es isomorfo a un subgrupo de un grupo de permutaciones. Si $G$ es finito de orden $n$, es isomorfo a un subgrupo de $S_n$.}
{{% /theorem %}}

{{% proof %}}

	Por el corolario anterior, basta construir un homomorfismo inyectivo $f\colon G\to\Sim (G)$.
	
	Dado $y\in G$ definimos $f(y)\in \Sim (G)$ como la aplicación $m_y\colon G\to G$ definida como $m_y(x)=y x$. Esta aplicación es biyectiva y su inversa es $m_y^{-1}=m_{y^{-1}}$. Así definido, $f$ es un homomorfismo pues dados $x,y,z\in G$,
	\[m_{zy}(x)=(zy) x=z (y x)=z m_y(x)=m_z(m_y(x))=(m_z\circ m_y)(x),\]
	luego $f(zy)=f(z)\circ f(y)$.
	
	Además $f$ es inyectivo pues si $f(y)=m_y=1$, la permutación identidad en $\Sim(G)$, entonces $y=ye=m_y(e)=1(e)=e$, luego $\ker(f)=\\{e\\}$.
	
	Si $G$ es finito de orden $n$, etiquetamos los elementos de $G=\\{ x_1,\ldots ,x_n\\}$ para identificar cada aplicación $m_{x_i}\in\Sim (G)$ con una permutación de los índices de los elementos de $G$.
{{% /proof %}}

Con esto vemos que los grupos simétricos no son un simple ejemplo particular de grupos, sino {\it el caso general}, puesto que todo grupo puede verse como subgrupo de un grupo de permutaciones.

-->
