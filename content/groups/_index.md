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
El **grupo simétrico de $n$ elementos** $S_n$ es el grupo simétrico del conjunto $\\{1,2, \cdots, n\\}$. Una manera concisa de representar una permutación de este conjunto es a través de una matriz con dos filas ($n=5$):
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
Con la notación matricial, la composición de permutaciones en $S_n$ se puede realizar como en el siguiente ejemplo. Consideramos
$$\sigma=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     2 & 1 & 3
                    \end{array}\right),
   \tau=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     2 & 3 & 1
                    \end{array}\right)\in S_3.$$
Para calcular $\sigma\circ\tau$ reordenamos las columnas de $\sigma$ de modo que su primera fila coincida con la segunda de $\tau$:
$$\sigma=\left(\begin{array}{ccc}
                     2 & 3 & 1\cr
                     1 & 3 & 2
                    \end{array}\right).$$
La matriz de $\sigma\circ\tau$ consiste en la primera fila de $\tau$ seguida de la segunda de la última representación de $\sigma$,
$$\sigma\circ\tau=\left(\begin{array}{ccc}
                     1 & 2 & 3\cr
                     1 & 3 & 2
                    \end{array}\right).$$
                    
Calculamos ahora $\tau\circ\sigma$,
$$
   \tau=\left(\begin{array}{ccc}
                     2 & 1 & 3\cr
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

Decimos que $\sigma\in \Sim(X)$ es un **ciclo** de **longitud** $r$, o un **$r$-ciclo**, si su soporte es un conjunto finito de $r$ elementos $$\sop (\sigma )=\\{ x_1,x_2,\ldots ,x_n\\}$$ y además
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

Un ejemplo de ciclo donde el soporte es el total:

![Un ciclo](../images/cycle.png)

Otro donde el soporte es un subconjunto propio:

![Otro ciclo](../images/cycle2.png)

Un ejemplo de trasposición entre elementos consecutivos:

![Un ciclo](../images/transposition.png)

Un ejemplo de trasposición entre elementos *no* consecutivos:

![Otro ciclo](../images/transposition2.png)


{{% watch %}}
La notación de ciclo no es única, por ejemplo $(x\_1 \; x\_2 \; x\_3)=(x\_3 \; x\_1 \; x\_2)=(x\_2 \; x\_3 \; x\_1)$. 
{{% /watch %}} 

{{% remark %}}
Dada una permutación $\sigma\in\Sim(X)$, al ser $\sigma\colon X\rightarrow X$ biyectiva, $\sigma(x)=y$ si y solo si $x=\sigma^{-1}(y)$, por tanto $\sigma$ y su inversa $\sigma^{-1}$ tienen el mismo soporte, $\sop(\sigma)=\sop(\sigma^{-1})$.
{{% /remark %}}

Cualquier notación bidimensional para los ciclos es intrínsecamente mala, lo ideal sería algo así:
![Ciclos circulares](../images/circular_cycle.png)

{{% proposition %}}
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

{{% proposition %}}
El orden de un ciclo coincide con su longitud.
{{% /proposition %}}

{{% proof %}}
Sea $\sigma=(x\_1\;\cdots\; x\_n)\in \Sim(X)$. Es fácil ver que $\sigma^k(x\_1)=x\_{1+k}\neq x\_1$ para todo $1\leq k<n$, así que $\sigma^k\neq 1\_X$, pero $\sigma^n=1\_X$.
{{% /proof %}}

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

Por construcción, $\sigma$ es el producto de los ciclos asociados a las órbitas no unitarias de la anterior relación de equivalencia. Es decir, por cada órbita no unitaria $\bar{x}$, el ciclo $(x\;\sigma(x)\;\dots\;\sigma^{m-1}(x))$ aparece en la factorización de $\sigma$, donde $m$ es el cardinal de $\bar{x}$. El orden de los factores de este producto no importa porque los ciclos son disjuntos, al ser sus soportes clases de una relacion de equivalencia. Hay una cantidad finita de órbitas no unitarias, ya que hemos visto que están contenidas en $\sop(\sigma)$, que es finito. La unicidad es obvia, pues las órbitas, y por tanto los ciclos, están determinados por $\sigma$ y la relación de equivalencia asociada.
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


<!--


### El grupo $S_n$

En este apartado vamos a estudiar las permutaciones de conjuntos finitos. Sea entonces el conjunto $X=\\{ 1,2,\ldots ,n\\}$, y denotemos por $S_n$ al grupo $\Sim(X)$ de permutaciones de estos $n$ elementos.

{{% definition %}}
{Orden de un grupo} {Sea $(G,\star)$ un grupo. Definimos su {\bf orden}, que notaremos por $|G|$, como el cardinal
del conjunto $G$.}
{{% /definition %}}

{{% theorem %}}
{Orden de $S_n$}
{El orden del grupo $S_n$ es $|S_n|=n!$}
{{% /theorem %}}

{{% proof %}}

Sea $\sigma$ una permutación cualquiera de $S_n$, podemos escribir
$$\sigma\colon\left(\begin{array}{cccccc}
                     1 & 2 & \cdots & n\\
                     i_1 & i_2 & \cdots & i_n
                    \end{array}\right) .$$
Hay $n$ posibles elecciones para $i_1$, pero solo $n-1$ posibilidades para $i_2$, pues $i_1$ no puede ser elegido de nuevo. Fijados $i_1$ e $i_2$ hay $n-2$ posibles elecciones para $i_3,\ldots$ y así sucesivamente hasta llegar a $i_n$, cuya elección ya está fijada por la de los elementos anteriores. Luego contando todas las posibilidades el número de permutaciones distintas de $S_n$ es
$$n(n-1)\cdots 1=n!$$
{{% /proof %}}

{{% example name="Ejemplo" %}}

Siguiendo el procedimiento anterior podemos dar la lista de todas las permutaciones de $S_3$:
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         1 & 2 & 3
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         1 & 3 & 2
        \end{array}\right) ,
$$
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         2 & 1 & 3
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         2 & 3 & 1
        \end{array}\right),
$$
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         3 & 2 & 1
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         3 & 1 & 2
        \end{array}\right) .
$$
Expresadas como productos de ciclos las permutaciones de $S_3$ son
$$S_3=\\{ (), (23), (12), (123), (13), (132)\\} .$$
{{% /example %}}

%{{% watch %}}

%En adelante para el conjunto $X=\\{ 1,2,\ldots ,n\\}$ notaremos $1_X=(1)$, como el ciclo que deja invariante al $1$ y a todos los demás elementos.
%{{% /watch %}}

Dado que $X=\\{ 1,2,\ldots ,n\\}$ es un conjunto finito, todas las permutaciones de $S_n$ tienen soporte finito y los resultados enunciados anteriormente se aplican a $S_n$, es decir,

{{% theorem %}}
{Descomposición en ciclos disjuntos y trasposiciones}
{Toda permutación de $S_n$ se descompone de manera única, salvo orden, como producto conmutativo de ciclos disjuntos. Además toda permutación de $S_n$ se puede expresar como producto de trasposiciones, esta vez {\bf no} de manera única.}
{{% /theorem %}}

### Explicación del juego inicial

Llegados a este punto podemos explicar cuál es la "magia" del juego de cartas. Teníamos cartas del mismo palo numeradas del 1 al 9 y las vamos "desordenando" hasta llegar a la posición inicial. Se trata por tanto de una combinación de permutaciones de $S_9$ que, "mágicamente", llegan a la identidad.

La {\bf separación de cartas} es la siguiente permutación\footnote{En realidad hay dos posibles separaciones, pues nosotros decidimos qué montón ponemos encima del otro, habría que estudiar varios casos que serían análogos a éste y que concluyen de igual forma.}:
$$\sigma\colon\left(\begin{array}{ccccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
                     9 & 4 & 8 & 3 & 7 & 2 & 6 & 1 & 5
                    \end{array}\right) .$$
Que es $\sigma =(195762438)$ un ciclo de longitud $9$. Si no cortáramos, separar dos veces es
$$\sigma^2=(156489723).$$
Y separar tres veces
$$\sigma^3=(174)(285)(396).$$

%Cortar una carta es la permutación
$$\kappa\colon\left(\begin{array}{ccccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
                     2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 1
                    \end{array}\right) .$$
Que en forma de ciclo es $\kappa =(123456789)$. Cortar dos cartas es igual a cortar una carta y luego otra, es decir,
$$\kappa^2=(135792468).$$
Y cortar varias cartas es:
$$\kappa^3=(147)(258)(369),\ \kappa^4=(159483726),\ \kappa^5=(162738495),$$
$$\kappa^6=(174)(285)(396),\ \kappa^7=(186429753),\ \kappa^8=(198765432)\mbox{ y }\kappa^9=().$$

\noindent {\bf Primer "hechizo mágico":} Separar tres veces seguidas es igual a cortar seis cartas\footnote{Es aquí donde sí tiene influencia relativa el hecho de poder decidir qué montón ponemos encima del otro. En cualquier caso, hagamos la elección que hagamos, separar tres veces es igual a cortar varias cartas.}.
$$\sigma^3=\kappa^6.$$

Sabemos que en el caso de las permutaciones el orden de los factores sí altera el producto. Cortar y separar no es lo mismo que separar y cortar:
$$\sigma\kappa =(147)(285),$$
$$\kappa\sigma =(258)(396).$$
Si embargo, cortar siete cartas y separar es
$$\sigma\kappa^7=(195762438)(186429753)=(258)(396)=\kappa\sigma .$$

\noindent {\bf Segundo "hechizo mágico":} Cortar siete cartas y separar es lo mismo que separar y después cortar una carta\footnote{Al igual que anteriormente, si al separar elegimos poner otro montón encima, siempre obtendremos una relación parecida en la que cortar varias cartas y separar equivale a separar y después cortar una carta.}.
$$\kappa\sigma =\sigma\kappa^7.$$
Por lo tanto, si bien es cierto que la composición no es conmutativa, sí tenemos ciertas reglas que nos permiten cambiar de posición "separar" y "cortar". En efecto:
$$\kappa^2\sigma =\kappa (\kappa\sigma )= \kappa \sigma \kappa^7 = (\kappa\sigma )\kappa^7=\sigma\kappa^7\kappa^7=\sigma\kappa^5.$$
$$\kappa^3\sigma =\kappa (\kappa^2\sigma )=\kappa \sigma \kappa^5=(\kappa\sigma )\kappa^5=\sigma\kappa^7\kappa^5=\sigma\kappa^3.$$
$$\kappa^4\sigma =\kappa (\kappa^3\sigma )=\kappa\sigma\kappa^3=(\kappa\sigma )\kappa^3=\sigma\kappa^7\kappa^3=\sigma\kappa.$$
$$\kappa^5\sigma =\cdots =\sigma\kappa^8.$$
$$\kappa^6\sigma =\cdots =\sigma\kappa^6.$$
$$\kappa^7\sigma =\cdots =\sigma\kappa^4 .$$
$$\kappa^8\sigma =\cdots =\sigma\kappa^2.$$

Ya tenemos las herramientas y "hechizos" necesarios para la explicación del juego. Inicialmente tenemos las $9$ cartas ordenadas y lo que hacemos en el juego es separar las cartas, cortar varias veces, separar otra vez las cartas, cortar varias veces y separar por tercera vez las cartas y cortar varias veces. Esto es:
$$(\kappa^r\sigma )(\kappa^q\sigma )(\kappa^p\sigma )= (\sigma\kappa^{r'})(\sigma\kappa^{q'})(\sigma\kappa^{p'})=\sigma (\kappa^{r'}\sigma )(\kappa^{q'}\sigma )\kappa^{p'}=$$
$$=\sigma (\sigma\kappa^{r"})(\sigma\kappa^{q"})\kappa^{p'} =\sigma^2(\kappa^{r"}\sigma )\kappa^{q"+p'}=\sigma^2(\sigma\kappa^{r"'})\kappa^{q"+p'}=\sigma^3\kappa^{r"'+q"+p'}=$$
$$=\kappa^6\kappa^{r"'+q"+p'}=\kappa^{6+r"'+q"+p'}.$$
Por tanto, después de realizar el juego lo que nos queda es {\bf un simple corte}. Al mirar la primera carta sabemos cuántas cartas tenemos que cortar para dejar nuestras nueve cartas ordenadas como al principio.

### Permutaciones pares e impares

Si $\sigma$ es una permutación de $S_n$ entonces $\sigma$ sustituye el orden natural de los enteros $1,2,\ldots ,n$ por el nuevo orden $\sigma (1),\sigma (2),\ldots ,\sigma (n)$. Así que la acción de $\sigma$ puede causar {\em inversiones} del orden natural.

{{% definition %}}
{Inversiones en una permutación}
{Se dice que un par $(i,j)$ es una {\bf inversión} de $\sigma\in S_n$, si
$$i<j \qquad y \qquad \sigma (i)>\sigma (j).$$}
{{% /definition %}}


{{% definition %}}
{Signo de una permutación}
{Si $\sigma\in S_n$ tiene un número par de inversiones, diremos que $\sigma$ es {\bf par}, y que $\signo(\sigma)=1$.


Si $\sigma\in S_n$ tiene un número impar de inversiones, diremos que $\sigma$ es {\bf impar}, y que $\signo(\sigma)=-1$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}

Las permutaciones pares de $S_3$ son $()$, $(123)$ y $(132)$, mientras que las impares son $(12)$, $(13)$ y $(23)$.
{{% /example %}}

Para decidir si una permutación (no demasiado grande) es par o impar es útil hacer un diagrama de cruces. Veamos esto con un ejemplo:

{{% example name="Ejemplo" %}}

?`Es la permutación
$$\sigma\colon\left(\begin{array}{ccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7\\
                     6 & 3 & 1 & 5 & 4 & 7 & 2
                    \end{array}\right) $$
par o impar?

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics{diagrama_inversiones.eps}
 }
 \caption{Inversiones de $\sigma$}
 \label{inversiones}
\end{figure}

Simplemente ponemos en dos filas los números del 1 al 7, y unimos el número $i$ de la fila superior al número $\sigma(i)$ de la fila inferior, teniendo cuidado de evitar intersecciones múltiples o innecesarias. Un cruce indica una inversión del orden natural.

Hay $11$ cruces, luego $\signo (\sigma )=-1$ y $\sigma$ es una permutación impar.
{{% /example %}}

El próximo resultado es es una propiedad significativa de las trasposiciones.

{{% proposition %}}
 Las trasposiciones son siempre impares.
{{% /proposition %}}

{{% proof %}}

Consideremos el diagrama de cruces (figura \ref{trasposicion-cruces}) para la trasposición $\tau =(ij)$ donde $i<j$. Contando obtenemos $2(j-i-1)+1$ cruces, que siempre es impar. Luego $\tau =(ij)$ es una permutación impar.
{{% /proof %}}

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics{diagrama_trasposicion.eps}
 }
 \caption{Diagrama de cruces de $\tau =(ij)$}
 \label{trasposicion-cruces}
\end{figure}

Las siguientes son propiedades básicas de la función $\signo$.

{{% proposition %}}

Sean $\sigma ,\tau\in S_n$. Se satisfacen las siguientes propiedades:
\begin{enumerate}
\item $\signo (\sigma\tau )=\signo (\sigma )\signo (\tau )$.
\item $\signo (\sigma^{-1})=\signo (\sigma )$.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}

\begin{enumerate}

\item Consideremos el diagrama que se obtiene dibujando el diagrama de cruces de $\tau$ encima del de $\sigma$. Este diagrama representa a la permutación $\sigma\tau$, aunque hay pares de líneas que se pueden cruzar dos veces (una en $\tau$ y otra en $\sigma$).

    Un par $(i,j)$ será una inversión de $\sigma\tau$ si y solo si las líneas correspondientes se cruzan solo en $\sigma$ o solo en $\tau$, pero no en ambas. Por tanto, para obtener el número de inversiones de $\sigma\tau$, solo hay que sumar los cruces del diagrama de $\sigma$ y los cruces del diagrama de $\tau$, y a continuación restar un número par de cruces (los que aparecen en los dos). Por tanto, el número de inversiones de $\sigma\tau$ tiene la misma paridad que la suma del número de inversiones de $\sigma$ y el número de inversiones de $\tau$. Así, $\sigma\tau$ es par si $\sigma$ y $\tau$ son ambos pares o ambos impares, y es impar en caso contrario. Esto equivale a decir que $\signo(\sigma\tau)=\signo(\sigma)\signo(\tau)$.

\item Esto se deduce de la propiedad anterior, tomando $\tau=\sigma^{-1}$, aunque se puede ver directamente: los diagramas de cruces de $\sigma$ y $\sigma^{-1}$ son simétricos, luego el número de cruces es el mismo en ambos diagramas. Por tanto $\sigma$ y $\sigma^{-1}$ tienen el mismo número de inversiones, y por ello el mismo signo.
\end{enumerate}
{{% /proof %}}

{{% corollary %}}

Una permutación $\sigma\in S_n$ es par (impar) si y solo si es producto de un número par (impar) de trasposiciones.
{{% /corollary %}}

{{% proof %}}

En efecto, si $\sigma =\tau_1\cdots\tau_r$ donde cada $\tau_i$ es una trasposición, entonces
$$\signo (\sigma )=\prod_{i=1}^r\signo (\tau_i)=(-1)^r.$$
{{% /proof %}}

Finalizamos esta sección con la fórmula de {\em Cauchy} que relaciona el signo de una permutación con su descomposición en ciclos disjuntos.

{{% theorem %}}
{Fórmula de Cauchy}
{Sea $\sigma\in S_n$ el producto de $c$ ciclos disjuntos entonces
$$\signo (\sigma )=(-1)^{m-c},$$
siendo $m=\#(\sop (\sigma ))$ el número de elementos del soporte de $\sigma$.}
{{% /theorem %}}

{{% proof %}}

Sea $\sigma =\sigma_1\cdots\sigma_c$ la descomposición de $\sigma$ en ciclos disjuntos, supongamos que cada $\sigma_j$ tiene longitud $\ell_j$. Sabemos que $\sigma_j$ es producto de $\ell_j-1$ trasposiciones. Luego $\signo (\sigma_j)=(-1)^{\ell_j-1}$ y
$$\signo (\sigma )=\prod_{j=1}^c\signo (\sigma_j)=\prod_{j=1}^c(-1)^{\ell_j-1}=(-1)^{m-c},$$
pues $\sum_{j=1}^c\ell_j=m$.
{{% /proof %}}

{{% watch %}}

En particular, el signo de un ciclo de longitud $m$ es $(-1)^{m-1}$. Luego la paridad del ciclo está cambiada respecto de su longitud: {\bf un ciclo de longitud par es impar y un ciclo de longitud impar es par}.
{{% /watch %}}

## Subgrupos. Teorema de Lagrange

{{% definition %}}
{Subgrupo} {Sea $(G,\star)$ un grupo. Un subconjunto $H$ de $G$ se dice que es un {\bf subgrupo} de
$(G,\star)$ si  $(H,\star)$ es un grupo. Es decir, si el conjunto $H$, y la operación definida en $G$, cumplen las propiedades de la definición de grupo.


Un subgrupo es, por tanto, un grupo dentro de otro grupo con la misma operación.}
{{% /definition %}}

{{% example name="Ejemplo" %}}

Veamos algunos ejemplos de subgrupos:
\begin{enumerate}
\item Vimos en el ejemplo \ref{ejemplo-grupos} que los conjuntos de números $\Z ,\Q ,\R$ y $\C$ son grupos abelianos con la suma. De hecho es una cadena de subgrupos $\Z\subset\Q\subset\R\subset\C$.
\item Lo mismo ocurre con los grupos $\Q^*=\Q\setminus\\{ 0\\}$, $\R^*=\R\setminus\\{ 0\\}$ y $\C^*=\C\setminus\\{ 0\\}$ con la multiplicación. Es también una cadena de subgrupos $\Q^*\subset\RR^*\subset\C^*$.
\item Sabemos que GL$(n,k)$, el conjunto de las matrices $n\times n$, con elementos en un cuerpo $k$ y determinante no nulo, es un grupo con la multiplicación de matrices. Sea $\text{SL}(n,k)$ el subconjunto de GL$(n,k)$ formado por las matrices con determinante igual a $1$. Comprobemos que $\text{SL}(n,k)$ es un subgrupo de GL$(n,k)$. En efecto, si $A,B\in \text{SL}(n,k)$ entonces $\det (AB)=\det (A)\det (B)=1$, luego $AB\in \text{SL}(n,k)$. La matriz identidad, $I_n$ tiene determinante igual a $1$, luego pertenece a $\text{SL}(n,k)$. Si $A\in \text{SL}(n,k)$, como $\det (A^{-1})=\det (A)^{-1}$ se tiene que $A^{-1}\in \text{SL}(n,k)$. Por último, como el producto en GL$(n,k)$ verifica la propiedad asociativa, en particular, también la satisface en $\text{SL}(n,k)$. Así que la multiplicación de matrices en $\text{SL}(n,k)$ es una operación  asociativa, con elemento neutro y cada matriz de $\text{SL}(n,k)$ tiene su inversa en el conjunto, luego es un grupo.
\item El subconjunto de $S_4$, $C=\\{ (), (1234), (13)(24), (1432)\\}$, es un subgrupo con la composición de permutaciones. Para comprobar que se satisfacen todas las propiedades de grupo, vamos a hacer la tabla de multiplicar de los elementos de $C$:
\begin{center}
 \begin{tabular}{|c||c|c|c|c|}
   \hline
   $\circ$ & $()$ & $(1234)$ & $(13)(24)$ & $(1432)$\\
   \hline\hline
   $()$ &  $()$ & $(1234)$ & $(13)(24)$ & $(1432)$\\
   \hline
   $(1234)$ & $(1234)$ & $(13)(24)$ & $(1432)$ & $()$\\
   \hline
   $(13)(24)$ & $(13)(24)$ & $(1432)$ & $()$ & $(1234)$\\
   \hline
   $(1432)$ & $(1432)$ & $()$ & $(1234)$ & $(13)(24)$\\
   \hline
 \end{tabular}
\end{center}
En la tabla se observa que la multiplicación es una operación de $C\times C \to C$, que está el elemento neutro $()$ y que cada elemento tiene un simétrico. Además, el producto en $C$ es asociativo, pues lo es en $S_4$. Luego es subgrupo. El hecho de que la tabla sea simétrica nos permite deducir que en este caso el subgrupo $C$ es conmutativo. Se da así la circunstancia de que un subgrupo de un grupo no conmutativo, como $S_4$, puede ser conmutativo.
\end{enumerate}
{{% /example %}}

{{% watch %}}

Si $G$ es un grupo y $H\subset G$ es finito, para comprobar que es subgrupo es suficiente hacer la tabla de multiplicar y razonar como en el ejemplo anterior. Si $H$ es infinito hay que demostrar que la operación entre elementos de $H$ está bien definida, que el elemento neutro pertenece a $H$ y que el simétrico de cada elemento de $H$ está también en $H$. En cualquier caso, la propiedad asociativa se "hereda" de $G$.
{{% /watch %}}

El siguiente resultado nos permite "ahorrarnos" verificar alguna propiedad a la hora de demostrar que un subconjunto es subgrupo.

{{% proposition %}}
{\label{subgrupo}}  Sean $(G,\star)$ un grupo y $H\subset G$ un subconjunto no vacío. Las condiciones siguientes son equivalentes:
 \begin{itemize}
  \item[$(1)$] $H$ es un subgrupo de $(G,\star)$.
  \item[$(2)$] Para cada par de elementos $x,y\in H$, tenemos que $x \inv{y}\in H$.
 \end{itemize}
{{% /proposition %}}

{{% proof %}}
 Veamos primero $(1)\Rightarrow (2)$. Sean $x,y\in H$. Como $H$ es subgrupo, contiene los simétricos de todos sus elementos. En particular $\inv{y}\in H$. De nuevo como $H$ es subgrupo la operación esta bien definida, de donde $x\inv{y}\in H$, como queríamos.



Probemos ahora $(2)\Rightarrow (1)$. Como $H \subset G$, los elementos
de $H$ verifican la propiedad asociativa. Como $H$ es no vacío, sea
$a\in H$. Aplicando (2) con $x=a$ e $y=a$, obtenemos
$$
a\inv{a}=e\in H,
$$
luego $H$ tiene un elemento neutro (el mismo que $G$).

Si $a\in H$, aplicando de nuevo (2) con $x=e$ e $y=a$, tenemos
$$
e \inv{a} =\inv{a}\in H,
$$
luego $H$ contiene los simétricos de todos sus elementos.

Sólo falta demostrar que la operación de $G$ es una operación en $H$. Sean
$a,b\in H$. Aplicando (2) esta vez con $x=a$ e $y=\inv{b}$ se tiene
$$
 a\inv{(\inv{b})}=a b\in H.
$$
Luego $H$ es subgrupo de $G$.
{{% /proof %}}

{{% watch %}}

Sea $(G,\star )$ un grupo y sea $x=x_1\cdots x_n$ un elemento de $G$, entonces el simétrico de $x$ es
$$\inv{x}=\inv{x_n}\cdots\inv{x_1}.$$
Así, si $\sigma =\rho_1\cdots\rho_n$ es una permutación, entonces su inversa es
$$\sigma^{-1}=\rho_n^{-1}\cdots\rho_1^{-1}.$$
Por otro lado, como el inverso de una trasposición es la misma trasposición, si $\delta =\tau_1\cdots\tau_m$ es una permutación producto de trasposiciones, su inversa es
$$\delta^{-1}=\tau_m\cdots\tau_1.$$
{{% /watch %}}

{{% theorem %}}
{El grupo alternado $A_n$}
{El conjunto $A_n$ de las permutaciones pares de $S_n$ es un subgrupo llamado {\bf grupo alternado}.}
{{% /theorem %}}

{{% proof %}}

Desde luego $()$ es una permutación par, luego $A_n$ es no vacío.
%Por otro lado, si la permutación $\sigma$ se escribe $\sigma =\tau_1\cdots\tau_r$ como producto de trasposiciones, entonces $\sigma^{-1}=\tau_r\cdots\tau_1$. Por tanto, la permutación inversa de una permutación par también es par.

Si $\sigma =\tau_1\cdots \tau_{2r}$ y $\rho=\pi_1\cdots \pi_{2s}$ son permutaciones pares, donde $\tau_i$ y $\pi_j$ son trasposiciones, entonces
$$\sigma\rho^{-1}=\tau_1\cdots \tau_{2r}\pi_{2s}\cdots\pi_1$$
es también una permutación par.

Luego por la proposición \ref{subgrupo} se concluye que $A_n$ es un subgrupo de $S_n$.
{{% /proof %}}

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

Si $\varphi (\sigma )=\varphi (\tau )$ entonces $\rho\sigma =\rho\tau$, multiplicando desde la izquierda por $\rho^{-1}$ obtenemos $\sigma =\tau$. Luego $\varphi$ es una aplicación inyectiva.

Por otro lado, si $\sigma\in I$, como $\rho^{-1}$ es impar, entonces $\rho^{-1}\sigma \in P$ y además $\varphi (\rho^{-1}\sigma )=\rho\rho^{-1}\sigma =\sigma$. Luego $\varphi$ es sobreyectiva.

Por tanto la aplicación $\varphi$ es biyectiva y hay tantas permutaciones pares como impares en $H$.
{{% /proof %}}

{{% corollary %}}

Si $n\geq 2$, el número de elementos de $A_n$ es $|A_n|=n!/2$, es decir, en $S_n$ hay tantas permutaciones pares como impares.
{{% /corollary %}}

{{% proof %}}

$S_n$ es un subgrupo de $S_n$ que, como $n\geq 2$, contiene a la permutación impar $(12)$. Luego podemos aplicar la proposición anterior para deducir que hay tantas permutaciones pares como impares.
{{% /proof %}}

{{% theorem %}}
{Subgrupo generado}
{Sean $(G,\star )$ un grupo y $A\subset G$ un subconjunto no vacío. Sea $\inv{A}=\\{\inv{x}\in G\mid x\in A\\}$ el conjunto de los elementos simétricos a los de $A$. Entonces el conjunto que se obtiene al operar sucesiones arbitrarias de elementos de $A$ y $\inv{A}$,
$$\langle A\rangle =\\{ x_1\cdots x_n\mid x_i\in A\cup \inv{A},n\geq 1\\} ,$$
es un subgrupo de $G$ llamado {\bf subgrupo generado por $A$}.}
{{% /theorem %}}

{{% proof %}}

Como $A\ne\varnothing$, entonces $\langle A\rangle$ también es no vacío.

Por otro lado, sean $x=x_1\cdots x_n$ e $y=y_1\cdots y_m$ dos elementos de $\langle A\rangle$, es decir, tales que $x_i,y_j\in A\cup \inv{A}$. Es evidente que cada $\inv{y_j}$ también pertenece a $A\cup \inv{A}$. Luego
$$x\inv{y}=(x_1\cdots x_n) \inv{(y_1\cdots y_m)}=x_1\cdots x_n \inv{y_m}\cdots \inv{y_1}$$
es un elemento de $\langle A\rangle$.
{{% /proof %}}

{{% example name="Ejemplo" %}}

En el grupo $S_4$ calcular todos los elementos del subgrupo $H=\langle (124),(12)\rangle$. Hay que ir operando los elementos $(123)$, $(12)$ y sus inversos, adjuntando a la lista los nuevos elementos que se obtengan. Hasta estar seguros de haberlos encontrado todos. Una buena forma de hacer esto es ir haciendo la tabla de multiplicar del conjunto, hasta que no se incorpore ningún nuevo elemento:
\begin{center}
\begin{tabular}{|c||c|c|c|c|c|c|}
\hline
$\circ$ & $()$ & $(124)$ & $(142)$ & $(12)$ & $(14)$ & $(24)$\\
\hline\hline
$()$ & $()$ & $(124)$ & $(142)$ & $(12)$ & $(14)$ & $(24)$\\
\hline
$(124)$ & $(124)$ & $(142)$ & $()$ & $(14)$ & $(24)$ & $(12)$\\
\hline
$(142)$ & $(142)$ & $()$ & $(124)$ & $(24)$ & $(12)$ & $(14)$\\
\hline
$(12)$ & $(12)$ & $(24)$ & $(14)$ & $()$ & $(142)$ & $(124)$\\
\hline
$(14)$ & $(14)$ & $(12)$ & $(24)$ & $(124)$ & $()$ & $(142)$\\
\hline
$(24)$ & $(24)$ & $(14)$ & $(12)$ & $(142)$ & $(124)$ & $()$\\
\hline
\end{tabular}
\end{center}
En este caso $H=\\{ (), (124), (142), (12), (14), (24)\\}$.

Claro que este método es operativo si el grupo no es demasiado grande. Por ejemplo, si calculamos los elementos de $\langle (123),(234)\rangle$, obtenemos el grupo alternado $A_4$. Este grupo tiene $12$ elementos, como hemos visto, luego su tabla de multiplicar tiene ¡$144$ entradas! Sin embargo, usando las propiedades que conocemos de permutaciones podemos ahorrar algunos cálculos. En este último caso sabemos que las permutaciones $(123)$ y $(234)$ son pares, así que lo serán también todas las permutaciones que calculemos a partir de ellas, esto quiere decir que el grupo $\langle (123),(234)\rangle$ tiene como mucho $12$ elementos. Así que en cuanto obtengamos $12$ distintos ya sabemos que hemos terminado.

Otra propiedad que podemos usar si es pertinente, aunque en este último ejemplo no, es que sabemos que si un grupo tiene elementos impares entonces tiene la misma cantidad de pares que de impares.
{{% /example %}}

{{% definition %}}
{Grupo cíclico} {Se dice que un grupo $G$ es {\bf cíclico} si existe $a\in G$ tal que
 $$
G=\langle a \rangle =\langle\\{ a\\}\rangle =\\{ a^m\mid m\in \Z\\} .
$$}
{{% /definition %}}

{{% example name="Ejemplo" %}}

El grupo $S_3$ no es cíclico, pues no existe ninguna permutación que genere todo el grupo. El grupo alternado $A_3=\\{ (),(123),(132)\\}$ es cíclico, pues $A_3=\langle (123)\rangle =\langle (132)\rangle$.

De hecho, para comprobar si un grupo finito de orden $m$ es o no cíclico, hay que verificar si existe o no en el grupo algún elemento de orden $m$. En $S_3$ no hay elementos de orden $6$ mientras que en $A_3$ hay un par de elementos de orden $3$,

El grupo de los enteros con la suma, $(\Z , +)$, es cíclico infinito, pues $\Z =\langle 1\rangle =\langle -1\rangle$.
{{% /example %}}

### El teorema de Lagrange

Para finalizar vamos a demostrar el teorema de Lagrange, que también puede ser de utilidad a la hora de calcular los elementos de un subgrupo de $S_n$, pues acota los posibles órdenes de los subgrupos de un grupo finito. Si $G$ es un grupo finito el teorema dice que el orden de cualquier subgrupo de $G$ divide al orden de $G$.

\begin{defn}{\label{relizq}} Sean $G$ un grupo y $H\subset G$ un subgrupo. Sobre $G$ definimos la relación
 $\sim_H$ de la manera siguiente: Dados $x,y\in G$,
$$
x\sim_H y \; \Leftrightarrow \; \inv{x} y\in H.
$$
\end{defn}

{{% proposition %}}
 En las condiciones de la definición anterior, las relación $\sim_H$ es de equivalencia.
{{% /proposition %}}

{{% proof %}}
 Se comprueba que la relación $\sim_H$ verifica las siguientes propiedades:
\begin{enumerate}
 \item Reflexiva: Para cada elemento $x\in G,\ x\sim_H x$ ya  que $\inv{x} x = e \in H$.
 \item Simétrica: Dados  $x,y\in G,\ x\sim_H y$ implica que $ y\sim_H x$, ya que $\inv{y} x = \inv{(\inv{x} y)} \in H$.
 \item Transitiva: Dados $x,y,z\in G$ si se tiene que $\ x\sim_H$  y que $y\sim_H z$, entonces se tiene que $x\sim_H z$. Esto se debe a que  $\inv{x} z = (\inv{x} y)(\inv{y} z)\in H$.
\end{enumerate}
{{% /proof %}}

{{% watch %}}

Lo usual es notar al conjunto cociente de $G$ por la relación de equivalencia $\sim_H$ como
$$G/H:=G/\sim_H.$$
Más adelante veremos que para algunos subgrupos $H$ (los {\em subgrupos normales}), la operación $\star$ de $G$ induce una operación $\bar{\star}$ que dota al conjunto cociente $G/H$ de estructura de grupo.
{{% /watch %}}

{{% proposition %}}
  Sean $G$ un grupo y $x\in G$. El conjunto
 $$
x H=\\{ x h\mid h\in H\\}
$$
es la clase de equivalencia de $x$ para la relación $\sim_H$.
{{% /proposition %}}

{{% proof %}}
 Sea $x\in G$ y llamemos $\bar{x}$ a su
clase de equivalencia por $\sim_H$, es decir,
$$
 \bar{x}=\\{ y\in G\mid x\sim_H y\\} =\\{ y\in G\mid \inv{x} y\in H\\} .
$$

Probaremos por doble inclusión que $\bar{x}=x H$. Si $y\in\bar{x}$,
entonces $\inv{x} y\in H$, es decir, existe $h\in H$ tal que $\inv{x} y=h$, de donde
$$
y=x h\in x H.
$$

Si $y\in x H$, existe $h\in H$ tal que $y=x h$, de donde
$$
\inv{x} y=h\in H\Rightarrow x\sim_H y.
$$
{{% /proof %}}

{{% watch %}}

Las clases de equivalencia para $\sim_H$, de la forma $xH$, se llaman {\it clases a izquierda}. Observemos que podríamos haber definido otra relación de equivalencia $\prescript{}{H}\sim$ de la siguiente forma:  
$$
  x \prescript{}{H}\sim y \Leftrightarrow yx^{-1}\in H.
$$ 
En este caso las clases de equivalencia son de la forma $Hx$, con $x\in G$, y se llaman {\it clases a derecha}.  En principio, las clases a izquierda no tienen por qué coincidir con las clases a la derecha (salvo en el caso evidente $1H=H1=H$). Cuando coinciden, se dice que el grupo $H$ es {\it normal}: esto se estudiará al final de este tema. 
{{% /watch %}}


{{% definition %}}
{\'Indice de un subgrupo} {Dado un grupo $G$ y un subgrupo $H\subset G$, el {\bf índice} de $H$ en $G$, denotado $|G:H|$, es el número de clases de equivalencia, en $G$, para la relación $\sim_H$. Es decir:
$$
    |G:H|=\#(G/H)
$$
}
{{% /definition %}}

{{% theorem %}}
 {Teorema de Lagrange} {Si $G$ es un grupo finito y
$H\subset G$ es un subgrupo, entonces $\vert H\vert$ divide a $\vert
G\vert$.}
{{% /theorem %}}

{{% proof %}}
 Consideremos la relación $\sim_H$
sobre $G$. Como $G$ es finito, habrá solo un número finito de
clases de equivalencia distintas. Sean éstas $a_1 H,\ldots,
a_r H$. Como $G$ es unión disjunta de estas clases, será
$$
 \vert G\vert =\# (a_1 H)+\cdots +\# (a_r H).
$$
Sea $H=\\{ h_1,\ldots ,h_n\\}$. Para todo $i=1,\ldots,r$, tendremos $a_i H = \\{a_i h_1, \dots, a_i h_n \\}$. Estos elementos son todos distintos, ya que si $a_i h_j=a_i h_l$, multiplicando desde la izquierda por el simétrico de $a_i$ se obtiene $h_j=h_l$. Por tanto $\#(a_i H)= n =\vert H\vert$ para todo $i=1,\ldots,r$. Luego $\vert G\vert=r\cdot n=r\cdot\vert
H\vert$.
{{% /proof %}}

Hemos visto que si $G$ es un grupo finito y $H$ es un subgrupo, las clases de equivalencia $aH$ tienen todas el mismo tamaño. Por tanto, tenemos:

{{% theorem %}}
 {\'Indice de un subgrupo en un grupo finito} {Si $G$ es un grupo finito y
$H\subset G$ es un subgrupo, entonces
$$
 |G:H|=\frac{|G|}{|H|}
$$}
{{% /theorem %}}



{{% corollary %}}

Sea $G$ un grupo finito y sea $x\in G$, entonces el orden de $x$ divide al orden de $G$.
{{% /corollary %}}

{{% proof %}}

El orden del elemento $x$ coincide con el del subgrupo $\langle x\rangle$, que a su vez divide al de $G$.
{{% /proof %}}

Del siguiente resultado dejamos la demostración como ejercicio.

{{% corollary %}}

Si $G$ es un grupo cuyo orden es un número primo, entonces $G$ es cíclico.
{{% /corollary %}}

{{% example name="Ejemplo" %}}

Volviendo al ejemplo en el que el subgrupo de $S_4$, $\langle (123),(234)\rangle$, resulta ser $A_4$, el teorema de Lagrange nos evita algún cálculo. Conforme van apareciendo nuevos elementos del subgrupo, en cuanto aparezca el noveno elemento, como el orden debe ser un divisor de $24$, sabemos que $\langle (123),(234)\rangle$ tiene 12 o 24 elementos. Al tratarse de permutaciones pares exclusivamente, se deduce que el subgrupo es $A_4$.

Es más, sabiendo que $\langle (123),(234)\rangle\subset A_4$, como el orden de $A_4$ es 12, basta con llegar al séptimo elemento para decidir que $\langle (123),(234)\rangle = A_4$
{{% /example %}}

{{% watch %}}
Terminamos el estudio del teorema de Lagrange proponiendo el ejercicio siguiente. Sabemos que el orden de cualquier subgrupo de $G$ divide a su orden. Recíprocamente, si $m$ divide a $|G|$, ?`existe algún subgrupo de $G$ de orden $m$? Te animamos a reflexionar esta cuestión en el grupo $S_4$ o en sus subgrupos.
{{% /watch %}}

## Homomorfismos de grupos

{{% definition %}}
{Homomorfismo de grupos}{
	Dados dos grupos $(G,\star)$ y $(H,\ast)$, un {\bf homomorfismo}
	\[f\colon (G,\star)\To (H,\ast)\]
	es una aplicación $f\colon G\to H$ que satisface
que para cada  $x_1,x_2\in G$, 
\[ f(x_1\star x_2)=f(x_1)\ast f(x_2).\]}
{{% /definition %}}

{{% watch %}}

Mientras no haya equívocos seguiremos usando la yuxtaposición para expresar la operación entre dos elementos. Aunque ahora intervienen dos grupos con operaciones que pueden ser distintas, normalmente por el contexto sabremos si los elementos que intervienen están en el primer grupo o en el segundo. Así, escribiremos por ejemplo
$$f(x_1 x_2)=f(x_1) f(x_2),\qquad  \text{ para cada } x_1,x_2\in G.$$
Igualmente, mientras no haya equívocos, se notará por $e$ tanto al elemento neutro de $G$ como al de $H$. Si hiciera falta distinguir, para evitar confusiones, se usará $e_G$ y $e_H$ respectivamente.
{{% /watch %}}

{{% example name="Ejemplo" %}}
\label{ejemplosdehomomorfismos}
	Ejemplos de homomorfismos:
	\begin{enumerate}
		\item La \emph{identidad}, $\id{G}\colon (G,\star)\to (G,\star)$.
		\item La inclusión de un subgrupo $K\subset G$, $i\colon (K,\star)\to (G,\star)$.
		\item El signo de una permutación, $\sign\colon\perm{n}\to\\{\pm1\\}$.
		\item La aplicación $f\colon \mathbb Z\to\mathbb Z$ definida como $f(x)=n\cdot x$ es un homomorfismo  $f\colon (\mathbb Z,+)\to (\mathbb Z,+)$ para todo entero $n$.
		\item Si $(G,\ast)$ es un grupo abeliano, la exponenciación $f\colon G\to G$, definida como $f(g)=g^n$ es un homomorfismo $f\colon (G,\ast)\to (G,\ast)$ para todo entero $n$.
		\item Si $\gl{n}{\mathbb R}$ es el grupo de matrices invertibles $n\times n$ de números reales, el determinante $\det\colon \gl{n}{\mathbb R}\to \mathbb R\setminus\\{0\\}$ es un homomorfismo (donde la operación en ambos grupos es la multiplicación).
		\item La aplicación exponencial $f\colon\mathbb R\to (0,+\infty)$, $f(x)=e^x$, es un homomorfismo $f\colon(\mathbb R,+)\to ((0,+\infty),\cdot)$.
        \item Dado un grupo $(G,\star)$ y un elemento $x\in G$, la aplicación $c_x\colon G\rightarrow G$ dada por $c_x(y)=x^{-1}yx$ es un homomorfismo, llamado {\it conjugación por $x$}.	\end{enumerate}
	Ejemplos de aplicaciones que no son homomorfismos:
	\begin{enumerate}
		\item Si $(G,\ast)$ no es abeliano, la exponenciación $f\colon G\to G$ definida en el anterior punto 5 no es un homomorfismo, al menos para $n=2$.
		\item La aplicación $f\colon \mathbb Z\to\mathbb Z$ definida como $f(x)=x^n$ no es un homomorfismo  $f\colon (\mathbb Z,+)\to (\mathbb Z,+)$ para ningún $n\geq 2$.
	\end{enumerate}
{{% /example %}}

Los homomorfismos preservan el elemento neutro y los simétricos.

{{% proposition %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un homomorfismo, entonces $	f(e)=e$, y además para cada $ x \in G$,
		$f(\inv{x})=\inv{f(x)}$.
{{% /proposition %}}

{{% proof %}}

	Como $e=e e$,
	\[f(e)=f(e e)=f(e) f(e).\]
	Cancelando un $f(e)$ de cada lado deducimos que $e=f(e)$.
%	Multiplicando por la izquierda por $\inv{f(e)}$ obtenemos
%	\[e=f(e)\ast\inv{f(e)}=f(e)\ast f(e)\ast\inv{f(e)}=f(e).\]

	Ahora que hemos probado la primera ecuación, deducimos la segunda de $e=x \inv{x}$ del siguiente modo,
	\[e=f(e)=f(x \inv{x})=f(x) f(\inv{x}).\]
	Despejando de aquí deducimos que $\inv{f(x)}=f(\inv{x})$.
%	Multiplicando por $\inv{f(x)}$ por la izquierda obtenemos,
%	\[\inv{f(x)}=\inv{f(x)}\ast e=\inv{f(x)}\ast f(x)\ast f(\inv{x})=f(\inv{x}).\]
{{% /proof %}}

La composición de dos homomorfismos es un homomomorfismo.

{{% proposition %}}

	Dados tres grupos y dos homomorfismos como en el siguiente diagrama,
	\[(G,\star)\stackrel{f}\To (H,\ast)\stackrel{g}\To (K,\bullet),\]
	la composición
	\[g\circ f\colon (G,\star)\To (K,\bullet)\]
	también es un homomorfismo.
{{% /proposition %}}

{{% proof %}}

	Basta observar que, aplicando las definiciones, dados $x_1,x_2\in G$,
	\begin{align*}
		(g\circ f)(x_1 x_2)&=g(f(x_1 x_2))\\
		&=g(f(x_1) f(x_2))\\
		&=g(f(x_1)) g(f(x_2))\\
		&=(g\circ f)(x_1) (g\circ f)(x_2).
	\end{align*}
{{% /proof %}}

{{% definition %}}
{Monomorfismos, epimorfismos e isomorfismos}{
	Decimos que un homomorfismo $f\colon (G,\star)\to (H,\ast)$ es un {\bf monomorfismo}, {\bf epimorfismo} o {\bf isomorfismo} si la aplicación $f$ es inyectiva, sobreyectiva o biyectiva, respectivamente. Los isomorfismos se denotan del siguiente modo
	 \[f\colon (G,\star)\stackrel{\cong}\To (H,\ast).\]}
{{% /definition %}}

{{% example name="Ejemplo" %}}

	De los homomorfismos del Ejemplo \ref{ejemplosdehomomorfismos}, 2 y 4 son  monomorfismos, 3 y 6 son epimorfismos y 1, 7 y 8 son isomorfismos. En general 5 no es un monomorfismo ni un epimorfismo.
{{% /example %}}

{{% proposition %}}

	La composición de dos isomorfismos es un isomorfismo.
{{% /proposition %}}

{{% proof %}}

	Se deduce de que ya sabemos que la composición de dos homomorfismos es un homomorfismo y que la composición de dos aplicaciones biyectivas es biyectiva.
{{% /proof %}}


{{% proposition %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un isomorfismo la aplicación inversa $f^{-1}\colon H\to G$ es un isomorfismo
	\[f^{-1}\colon (H,\ast) \To  (G,\star).\]
{{% /proposition %}}

{{% proof %}}

	Queremos demostrar que para cada $ y_1,y_2\in H$ se cumple que 
	\[f^{-1}(y_1 y_2)=f^{-1}(y_1) f^{-1}(y_2).\]
	Como $f$ es inyectivo, bastará comprobar que
	\[f(f^{-1}(y_1 y_2))=f(f^{-1}(y_1) f^{-1}(y_2)).\]
	Por un lado, por ser $f^{-1}$ la inversa de $f$,
	\[f(f^{-1}(y_1 y_2))=(f\circ f^{-1})(y_1 y_2)=y_1 y_2.\]
	Por otro lado, usando además que $f$ es un homomorfismo,
	\begin{align*}
	f(f^{-1}(y_1) f^{-1}(y_2))&=f(f^{-1}(y_1)) f(f^{-1}(y_2))\\
	&=(f\circ f^{-1})(y_1)(f\circ f^{-1})(y_2)\\
	&=y_1 y_2.
	\end{align*}
{{% /proof %}}

{{% example name="Ejemplo" %}}

	Los inversos de los isomorfismos 1, 7 y 8 del Ejemplo \ref{ejemplosdehomomorfismos} son, respectivamente, $\id{G}^{-1}=\id{G}$, el isomorfismo $f^{-1}\colon((0,+\infty),\cdot)\to(\mathbb R,+)$ definido por $f^{-1}(x)=\log(x)$, y el isomorfismo $(c_x)^{-1}=c_{x^{-1}}$ definido por $c_{x^{-1}}(y)=xyx^{-1}$.
{{% /example %}}

{{% definition %}}
{Grupos isomorfos}
{	Dos grupos $(G,\star)$ y $(H,\ast)$ son {\bf isomorfos} si existe un isomorfismo \[f\colon (G,\star)\stackrel{\cong}\To (H,\ast).\]}
{{% /definition %}}

{{% corollary %}}

	La relación de ser isomorfos es de equivalencia.
{{% /corollary %}}

{{% proof %}}

	Es reflexiva porque la identidad es un homomorfismo de todo grupo en sí mismo. Es transitiva porque la composición de dos isomorfismos es un isomorfismo. Es simétrica porque el inverso de un isomorfismo es un isomorfismo.
{{% /proof %}}

{{% definition %}}
{Núcleo de un homomorfismo}
{	Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, el {\bf núcleo} de $f$ es
	\[\ker(f)=\\{x\in G\,;\,f(x)=e\\}\subset G.\]}
{{% /definition %}}

{{% example name="Ejemplo" %}}

	El núcleo de $\sign\colon\perm{n}\to\\{\pm1\\}$ es el grupo alternado.
{{% /example %}}

La demostración de la siguiente propiedad la dejamos como ejercicio:

{{% proposition %}}

 Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, su núcleo $(\ker(f),\star)$ es un subgrupo de $(G, \star)$, y su imagen $(\im(f),\ast)$ es un subgrupo de $(H,\ast)$.
{{% /proposition %}}

{{% proposition %}}

	Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, se tiene:
\begin{enumerate}
  \item $f$ es inyectivo si y solo si $\ker(f)=\\{e\\}$.

  \item $f$ es sobreyectivo si y solo si $\im(f)=H$.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}

    La segunda propiedad es simplemente la definición de aplicación sobreyectiva, así que basta demostrar la primera propiedad.

	Supongamos que $f$ es inyectivo. En primer lugar, como $f(e)=e$ se tiene $\\{e\\}\subset \ker(f)$. Por otra parte, dado $x\in \ker f$ se tiene \[f(x)=e=f(e).\]
	Pero entones, como $f$ es inyectivo, se sigue que $x=e$. Por tanto $\ker(f)\subset \\{e\\}$, luego $\ker(f)=\\{e\\}$.

	Recíprocamente, supongamos que $\ker(f)=\\{e\\}$. Si $x, y\in G$ son tales que $f(x)=f(y)$ entonces, por ser $f$ un homomorfismo,
	\[f(x\inv{y})=f(x) f(\inv{y})=f(x) \inv{f(y)}=f(y) \inv{f(y)}=e.\]
	Luego $x\inv{y}\in \ker(f)=\\{e\\}$, es decir $x\inv{y}=e$. Multiplicando desde la derecha por $y$, obtenemos $x=y$. Por tanto $f$ es inyectiva.
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
