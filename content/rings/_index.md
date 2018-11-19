+++
title = "Enteros"
weight = 30
+++


## Anillos

{{% definition %}}
 Un **anillo** es un grupo abeliano aditivo \\(R\\) equipado con otra operación binaria, llamada *multiplicación* o *producto*,
 \\[
\begin{array}{rcl}
R\times R&\rightarrow& R,\cr
(a,b) &\mapsto& ab,
\end{array}
\\]
que satisface las siguientes propiedades, donde $a,b,c\in R$ son elementos cualesquiera:

* Asociativa: 
$$
a(bc)=(ab)c.
$$

* Distributiva:
$$
\begin{array}{rcl}
a(b+c)&=&ab+ac,\cr
(a+b)c&=&ac+bc.
\end{array}
$$

* Existencia de elemento neutro \\(1\in R\\) para el producto:
$$
1a=a=a1.
$$

Un anillo es **conmutativo** si además el producto satisface la siguiente propiedad.

* Conmutativa: 
$$
ab=ba.
$$
{{% /definition %}}

{{% remark %}}
En todo anillo, el elemento neutro del producto es único. Esto se demuestra igual que la unicidad del elemento neutro de un [grupo](../groups/#eunique). El producto en un anillo se denotará a veces $a\cdot b$, pero casi siempre lo haremos por yuxtaposición $ab$.
{{% /remark %}}

{{% watch %}}
El producto de un anillo no lo dota de estructura de grupo.
{{% /watch %}}

{{% example name="Clásicos" %}}
Los números enteros $\mathbb Z$, racionales $\mathbb Q$, reales $\mathbb R$ y complejos $\mathbb C$ son anillos, pero los naturales $\mathbb N$ no. 
{{% /example %}}

{{% example name="Polinomios" %}}
Dado un anillo conmutativo $R$, podemos considerar su anillo de **polinomios** $R[x]$ en una variable $x$, cuyos elementos $p(x)\in R[x]$ son de la forma $$p(x)=a_nx^n+\cdots+a_1x+a_0$$ con *coeficientes* $a\_i\in R$, $1\leq i\leq n$. En ocasiones los denotaremos como si fueran series $$p(x)=\sum\_{n\geq 0}a\_nx^n$$ dando por supuesto que *casi todos* los coeficientes son $0$. Esto facilita la definición de la suma y la multiplicación $$\sum\_{n\geq 0}a\_nx^n+\sum\_{n\geq 0}b\_nx^n=\sum\_{n\geq 0}(a\_n+b\_n)x^n,$$ $$\left(\sum\_{i\geq 0}a\_ix^i\right)\left(\sum\_{j\geq 0}b\_jx^j\right)=\sum\_{n\geq 0}\left(\sum\_{i+j=n}a\_ib\_j\right)x^n.$$ Los anillos de polinomios en varias variables se definen inductivamente $$R[x\_1,\dots, x\_{n-1},x\_n]=(R[x\_1,\dots, x\_{n-1}])[x\_n].$$ 
{{% /example %}}

{{% example name="Matrices" %}}
Dado un entero $n$ y un anillo conmutativo $R$, el conjunto $M(n, R )$ de las matrices $n\times n$ con entradas en $R$ es un anillo con la suma y el producto de matrices habituales. Para $n\geq 2$, este anillo no es conmutativo.
{{% /example %}}

{{% example name="El anillo trivial" %}}
El conjunto unitario $R=\\{0\\}$, dotado de las únicas operaciones suma y multiplicación posibles, es un anillo. Aquí obviamente $1=0$.
{{% /example %}}

{{% proposition %}}
En un anillo $R$, $1=0$ si y solo si $R=\\{0\\}$. 
{{% /proposition %}}

{{% proof %}}
$\Leftarrow$ Obvio.

$\Rightarrow$ Dado $a\in R$, $a=1a=0a=0$.  
{{% /proof %}}


{{% example name="Anillos de Boole" %}}
Dado un conjunto $X$, el conjunto $\mathcal P(X)=\\{A|A \subset X\\}$ formado por los subconjuntos de $X$ es un anillo, denominado **anillo de Boole**, donde la suma es la *diferencia simétrica*, 
$$A+B=(A\cup B)\setminus (A\cap B)$$ 
![symmetric_difference](../images/symmetric_difference.png) 
y el producto es la intersección, $$AB=A\cap B.$$ ¿Cuál es el $0$? ¿Y el $1$? ¿Y $-A$? ¿Y $A^2$? Dibuja $A+B+C$ para tres conjuntos en posición general.
{{% /example %}}

{{% proposition %}}
En un anillo cualquiera $R$ se cumplen las siguientes propiedades para todo $a\in R$:

* $0a=0=a0$.

* $(-1)a=-a=a(-1)$.
{{% /proposition %}}

{{% proof %}}
Como $0=0+0$, 
$$
\begin{array}{rcl}
a0&=&a(0+0)\cr
&=&a0+a0.
\end{array}$$ 
Cancelando un $a0$ de cada lado obtenemos que $0=a0$. La igualdad $0a=0$ se demuestra análogamente. 

Al ser $0=1+(-1)$ tenemos que 
$$
\begin{array}{rcl}
0&=&a0\cr
&=&a(1+(-1))\cr
&=&a1+a(-1)\cr
&=&a+a(-1).
\end{array}
$$ 
Despejando deducimos que $-a=a(-1)$. La igualdad $-a=(-1)a$ se prueba de un modo similar.
{{% /proof %}}

{{% definition %}}
Un subconjunto $S\subset R$ de un anillo $R$ es un **subanillo** si es un subgrupo aditivo y además:

* $1\in S$.

* $ab\in S$ para todo $a,b\in S$.
{{% /definition %}}


{{% remark %}}
Un subanillo $S\subset R$ es un anillo por derecho propio con la suma y la multiplicación heredadas de $S$. El total $R\subset R$ es obviamente un subanillo.
{{% /remark %}}

{{% watch %}}
El subconjunto $\\{0\\}\subset R$ no es un subanillo, a menos que sean iguales.
{{% /watch %}}

Ejemplos de subanillos son $\mathbb Z\subset \mathbb Q\subset \mathbb R\subset \mathbb C$ y $R\subset R[x]$.

{{% example name="Subanillos de $\mathbb{Q}$" %}}
Dado un entero primo $p\in\mathbb{Z}$, el subconjunto $$S=\left\\{\frac{a}{b}\in\mathbb{Q}\mid p\nmid b\right\\}\subset \mathbb{Q}$$ es un subanillo.
{{% /example %}}

{{% example name="Los complejos como matrices" label="complexesasmatrices" %}}
En $M(2,\mathbb{R})$, el siguiente subconjunto es un subanillo,
$$S=\left\\{\left(\begin{array}{rr}a&b\cr -b&a\end{array}\right)\mid a,b\in\mathbb{R}\right\\}.$$
Compruébalo.
{{% /example %}}


{{% definition %}}
Una **unidad** $u\in R$ es un elemento de un anillo tal que existe $u^{-1}\in R$, denominado **inverso** de $u$, de modo que $uu^{-1}=1=u^{-1}u$. Un **cuerpo** es un anillo conmutativo no trivial donde todos los elementos no nulos son unidades.
{{% /definition %}}


{{% remark %}}
El elemento inverso $u^{-1}$ de una unidad $u$ es único. Esto se demuestra igual que la unicidad de los inversos en un [grupo](../groups/#inverseunique). Si $u$ es una unidad entonces $u^{-1}$ también y $(u^{-1})^{-1}=u$. Dividir por una unidad es multiplicar por el elemento inverso $\frac{a}{u}=au^{-1}$. Los elementos $1$ y $-1$ son siempre unidades (no necesariamente distintas) cuyos inversos son ellos mismos. El subconjunto $R^{\times}\subset R$ formado por las unidades de un anillo $R$ es un grupo con la multiplicación. El grupo multiplicativo $R^\times$ es abeliano si el anillo $R$ es conmutativo.
{{% /remark %}}

Las unidades de $\mathbb{Z}$ son $\\{1,-1\\}$, mientras que $\mathbb{Q}$, $\mathbb{R}$ y $\mathbb{C}$ son cuerpos. Dado un cuerpo $k$, las unidades de $M(n,k)$ son el grupo $GL(n,k)$ de matrices $n\times n$ de determinante no nulo.



## Homomorfismos

Los homomorfismos de anillos son aplicaciones entre anillos que preservan la estructura, es decir, la suma, la multiplicación, el $0$ y el $1$.

{{% definition %}}
Dados dos anillos $R$ y $S$, un **homomorfismo** $f\colon R\rightarrow S$ es un homomorfismo entre los correspondientes grupos aditivos tal que, además, para todo $a,b\in R$, 
$$\begin{array}{rcl} 
f(ab)&=&f(a)f(b),\cr 
f(1)&=&1.
\end{array}$$ 
Un **monomorfismo** $f\colon R\hookrightarrow S$ es un homomorfismo inyectivo. Un **epimorfismo** $f\colon R\twoheadrightarrow S$ es un homomorfismo sobreyectivo. Un 
**isomorfismo** 
$$f\colon R\stackrel{\cong}\longrightarrow S$$
es un homomorfismo biyectivo.
{{% /definition %}}

La identidad $\operatorname{id}_R\colon R\rightarrow R$ es un isomorfismo. 

{{% example name="La inclusión" %}}
Si $R$ es un anillo y $S\subset R$ es un subanillo, la **inclusión** $i\colon S\hookrightarrow R$, $i(a)=a$, es un homomorfismo. ¿Qué diferencia a la inclusión de la identidad?
{{% /example %}}


{{% example name="La evaluación" %}}
Dado un anillo conmutativo $R$ y $a\in R$ está definido el homomorfismo de **evaluación** $ev\_a\colon R[x]\rightarrow R$ como $ev\_a(p(x))=p(a)$. 
{{% /example %}}


{{% example name="Los complejos como matrices" %}}
Si $S\subset M(2,\mathbb{R})$ es el subanillo del ejemplo [anterior](#complexesasmatrices), podemos definir un isomorfismo $f\colon\mathbb{C}\cong S$ como 
$$f(a+ib)=\left(\begin{array}{rr}a&b\cr -b&a\end{array}\right).$$
Compruébalo.
{{% /example %}}

{{% proposition %}}
Dado un homomorfismo $f\colon R\rightarrow S$, su imagen $\operatorname{im} f\subset S$ es un subanillo. 
{{% /proposition %}}

{{% proof %}}
Como $f$ es un homomorfismo entre los grupos aditivos subyacentes, $\operatorname{im} f\subset S$ es un subgrupo aditivo. Es más, 

* $1=f(1)\in \operatorname{im} f$.

* $f(a)f(b)=f(ab)\in \operatorname{im} f$ para todo $a,b\in R$.
{{% /proof %}}

{{% proposition %}}
Si $f\colon R\rightarrow S$ es un homomorfismo de anillos y $u\in R$ es una unidad, entonces $f(u)\in S$ es una unidad y $f(u^{-1})=f(u)^{-1}$.
{{% /proposition %}}

{{% proof %}}
Como $uu^{-1}=1=u^{-1}u$, aplicando el homomorfismo $f$ deducimos que 
$$
\begin{array}{rcl}
f(u)f(u^{-1})&=&f(uu^{-1})\cr
&=&f(1)\cr
&=&1\cr
&=&f(u^{-1}u)\cr
&=&f(u^{-1})f(u).
\end{array}
$$
El resultado se deduce de estas ecuaciones.
{{% /proof %}}

{{% corollary %}}
Todo homomorfismo de anillos $f\colon R\rightarrow S$ se restringe a un homomorfismo entre sus subgrupos multiplicativos de unidades $R^\times\rightarrow S^\times$.
{{% /corollary %}}

{{% proposition %}}
Dados dos homomorfismos de anillos $$R\stackrel{f}\longrightarrow S\stackrel{g}\longrightarrow T$$ 
la composición $g\circ f\colon R\rightarrow T$ también es un homomorfismo. Lo mismo es cierto para isomorfismos. 
{{% /proposition %}}

{{% proof %}}
Comenzamos probando la primera parte. 
La composición $g\circ f$ es un homomorfismo de grupos aditivos. Basta por tanto observar que 
$$
\begin{array}{rcl}
(g\circ f)(1)&=&g(f(1))\cr
&=&g(1)\cr
&=&1.
\end{array}
$$
Es más, dados $a,b\in R$,
$$
\begin{array}{rcl}
(g\circ f)(ab)&=&g(f(ab))\cr
&=&g(f(a)f(b))\cr
&=&g(f(a))g(f(b))\cr
&=&(g\circ f)(a)(g\circ f)(b).
\end{array}
$$

El enunciado para isomorfismos se deduce de que la composición de aplicaciones biyectivas es biyectiva.
{{% /proof %}}

{{% proposition %}}
Si $f\colon R\rightarrow S$ es un isomorfismo de anillos entonces la aplicación inversa $f^{-1}\colon S\rightarrow R$ también.
{{% /proposition %}}

{{% proof %}}
Sabemos que $f^{-1}\colon S\rightarrow R$ es biyectiva y un homomorfismo de grupos aditivos. Falta por ver que $f^{-1}$ preserva el elemento neutro para el producto y los productos. Como $f$ es inyectivo, para ver que $f^{-1}(1)=1$ basta comprobar que $f(f^{-1}(1))=f(1)$. Esto es cierto pues $$f(f^{-1}(1))=(f\circ f^{-1})(1)=\id{S}(1)=1$$
y además $f(1)=1$ por ser $f$ un homomorfismo de anillos. La demostración de que $f^{-1}$ preserva productos se hace igual que en el caso de [grupos](../groups/#inverseisogroup).
{{% /proof %}}

El anillo de los enteros cumple la siguiente curiosa propiedad, que en términos categóricos se denomina ser *inicial* en la categoría de los anillos.

{{% proposition %}}
Para todo anillo $R$ existe un único homorfismo $f\colon \mathbb Z\rightarrow R$. 
{{% /proposition %}}


{{% proof %}}

Cualquier homomorfismo $f\colon \mathbb Z\rightarrow R$ satisface $f(0)=0$ y $f(1)=1$. Por tanto, si $n>0$ en $\mathbb Z$,
$$\begin{array}{rcl}
f(n)&=&f(1+\stackrel{n}{\cdots}+1)\cr&=&f(1)+\stackrel{n}{\cdots}+f(1)\cr&=&1+\stackrel{n}{\cdots}+1,\cr
f(-n)&=&-f(n).
\end{array}$$
Es fácil comprobar que estas fórmulas definien un homomorfismo, que ha de ser único.  
{{% /proof %}}



## Ideales

{{% watch %}}
En adelante, todos los anillos que consideremos serán conmutativos.
{{% /watch %}}

Existe otro tipo destacado de subconjunto de un anillo que juega un papel más importante que los subanillos.

{{% definition %}}
Dado un anillo $R$, un **ideal** $I\subset R$ es un subgrupo aditivo tal que $ra\in I$ para todo $r\in R$ y $a\in I$.
{{% /definition %}}

En $\mathbb Z$ los números pares forman un ideal.

{{% example name="Ideales" %}}
Dado un anillo cualquiera $R$, los siguientes son ejemplos de ideales:

* El total $R\subset R$.

* El trivial $\\{0\\}\subset R$.

* Dado $a\in R$, el **ideal principal** generador por $a$ está formado por sus múltiplos $$(a)=\\{ra\mid r\in R\\}\subset R.$$ Observa que, si $R=\mathbb{Z}$, dado $n\in\mathbb{Z}$, $(n)=\langle n\rangle$. 
{{% /example %}}

Más adelante veremos que no hay más subgrupos de $\mathbb{Z}$ que estos y que por tanto coinciden con los ideales.

{{% proposition %}}
El **núcleo** de un homomorfismo $f\colon R\rightarrow S$, $$\ker f=\\{a\in R\;|\;f(a)=0\\},$$ es un ideal $\ker f\subset R$.
{{% /proposition %}}

{{% proof %}}
Sabemos que $\ker f\subset R$ es un subgrupo aditivo. Queda probar la condición de ideal. Si $a\in\ker f$ y $r\in R$ entonces $f(ra)=f( r )f(a)=f( r )0=0$ luego $ra\in \ker f$.
{{% /proof %}}

Por tanto, en $R[x]$, los polinomios $f(x)$ tales que $f(1)=0$ forman un ideal pues constituyen el núcleo del homomorfismo de evaluación en $1\in R$. De hecho podríamos evaluar en cualquier otro elemento de $R$. 

{{% remark %}}
Un homomorfismo de anillos $f\colon R\rightarrow S$ es inyectivo si y solo si $\ker f=\\{0\\}$, ya que esto es cierto a nivel de grupos. Dicho de otro modo, para probar la inyectividad de $f$ basta ver que si $a\in R$ es tal que $f(a)=0$ entonces $a=0$.
{{% /remark %}}

Veamos ahora la relación entre ideales y unidades.

{{% proposition %}}
Un ideal $I\subset R$ contiene una unidad $\Leftrightarrow$ $I=R$.
{{% /proposition %}}

{{% proof %}}
$\Leftarrow$ Obvio porque $1\in R=I$ es una unidad.

$\Rightarrow$ Si $u\in I\subset R$ es una unidad, $u^{-1}\in R$ y por ser $I$ un ideal $1=uu^{-1}\in I.$

Si $1\in I$ y $a\in R$ entonces $1a=a\in I$, por tanto $R\subset I$, así que $I=R$.  
{{% /proof %}}

{{% corollary %}}
Un anillo es un cuerpo $\Leftrightarrow$ tiene solo dos ideales (necesariamente el total y el trivial).
{{% /corollary %}}

{{% proof %}}
$\Rightarrow$ Sea $k$ un cuerpo. Los cuerpos, en tanto que anillos no triviales, tienen al menos dos ideales: el trivial y el total. Si $I\subset k$ es un ideal no trivial entonces existe un elemento $a\in I\subset k$ no nulo. Como $k$ es un cuerpo este elemento ha de ser una unidad, así que $I=k$.

$\Leftarrow$ Sea $R$ un anillo cuyos dos únicos ideales son $\\{0\\}$ y $R$. En particular $R$ no es trivial. Sea $a\in R$ un elemento no trivial. Como $a\in (a)$, este ideal no puede ser el trivial, así que ha de ser el total $(a)=R$. Al ser $1\in R=(a)$ ha de existir un elemento $r\in R$ tal que $ra=1$, así que $a$ es una unidad.  
{{% /proof %}}

{{% corollary %}}
Si $f\colon k\rightarrow R$ es un homomorfismo de anillos donde $k$ es un cuerpo y $R$ no es trivial entonces $f$ es inyectivo.
{{% /corollary %}}

{{% proof %}}
El ser $f\colon k\rightarrow R$ un homomorfismo, $f(1)=1$. Como $R$ no es trivial, $1\neq 0$ luego $1\notin\ker f\subset k$ no puede ser el total. Por ser $k$ es un cuerpo la única opción posible es $\ker f=\\{0\\}$, luego $f$ es inyectivo.  
{{% /proof %}}



## Cocientes

{{% theorem %}}
Dado un anillo $R$ y un ideal $I\subset R$, existe una única estructura de anilo en el grupo cociente $R/I$ tal que la proyección natural $\pi\colon R\twoheadrightarrow R/I$, $\pi(a)=a+I$, es un homomorfismo de anillos. El núcleo de esta proyección es $\ker \pi=I$. 
{{% /theorem %}}


{{% proof %}}
Partimos de que el correspondiente enunciado para [grupos](../groups/#groupquotient) ya se ha probado.

Si $R/I$ fuera un anillo y $\pi\colon R\rightarrow R/I$ un homomorfismo entonces
$$
\begin{array}{rcl}
(a+I)(b+I)&=&\pi(a)\pi(b)\cr
&=&\pi(ab)\cr
&=&(a+b)+I.
\end{array}
$$
Veamos que esta fórmula para la multiplicación, necesariamente única si queremos que $\pi$ sea un homomorfismo, define una operación binaria en $R/I$. Para ver que está bien definida hay que comprobar que $$\left.\begin{array}{r}a+I=a'+I\cr b+I=b'+I\end{array}\right\\}\Rightarrow(ab)+I=(a'b')+I.$$ Esto equivale a $$\left.\begin{array}{r}a-a'\in I\cr b-b'\in I\end{array}\right\\}\Rightarrow ab-a'b'= (a-a')b+a'(b-b')\in I.$$ Las propiedades que el producto y la suma deben satisfacer se cumplen obviamente pues se derivan de las correspondientes propiedades de la suma y el producto en $R$, por tanto $R/I$ es un anillo. El elemento neutro para el producto de $R/I$ es $1+I$.
{{% /proof %}}

{{% example name="$\mathbb{Z}/(n)$" %}}
Dado $n\in\mathbb Z$, vamos a estar particularmente interesados en los anillos $\mathbb{Z}/(n)$. Según hemos visto en el capítulo de grupos, si $n=0$ entonces $\mathbb{Z}\cong\mathbb{Z}/(0)$. Si $n\neq 0$, podemos suponer que $n>0$ ya que $(n)=(-n)$. En este caso, vimos en el capítulo de conjuntos que 
$$\mathbb{Z}/(n)=\\{[0],\dots,[n-1]\\}.$$
Es más, dado $m\in\mathbb{Z}$, $[m]=[r]$, donde $r$ es el resto no negativo de la división de $m$ por $n$, $m=c\cdot n +r$, ya que $0\leq r<n$ y $m-r=c\cdot n\in (n)$. 
{{% /example %}}

{{% theorem name="Primer Teorema de Isomorfía" label="primer" %}}
Dado un homomorfismo $f\colon R\rightarrow S$, existe un único homomorfismo $\bar f\colon R/\ker f\rightarrow \operatorname{im}f$ tal que $f$ factoriza como $f=i\circ\bar f\circ p$, es decir, $f$ encaja en el siguente **diagrama conmutativo**, $$\require{AMScd}\begin{CD}R @>f>> S\cr @V{p}VV @AA{i}A\cr \frac{R}{\ker f} @>>{\overline{f}}> \operatorname{im} f \end{CD}$$ 
 Aquí $p$ es la proyección natural e $i$ es la inclusión. Además $\bar f$ es un isomorfismo.
{{% /theorem %}}


{{% proof %}}
La factorización es la vista para [grupos](../groups/#groupsisomorph). Basta por tanto ver que $\overline{f}$ preserva el $1$ y los productos. Recordemos que esta aplicación está definida como $\overline{f}(a+I)=f(a)$. De este modo,
$$
\begin{array}{rcl}
\overline{f}(1+I)&=&f(1)\cr
&=&1,\cr
\overline{f}((a+I)(b+I))&=&\overline{f}((ab)+I)\cr
&=&f(ab)\cr
&=&f(a)f(b)\cr
&=&\overline{f}(a+I)\overline{f}(b+I).
\end{array}
$$
{{% /proof %}}

{{% corollary %}}
$\mathbb{R}/(x^2+1)\cong\mathbb{C}$.
{{% /corollary %}}

{{% proof %}}
Consideremos el homomorfismo $f\colon \mathbb R[x]\rightarrow\mathbb C$ definido como $f(p(x))=p(i)$. Este homomorfismo está bien definido porque es la composición de la inclusión $\mathbb{R}[x]\subset \mathbb{C}[x]$ y la evaluación $ev_i\colon\mathbb{C}[x]\rightarrow\mathbb{C}$. Es sobreyectivo ya que dado $a+ib\in\mathbb C$, $f(bx+a)=a+ib$ por tanto $\operatorname{im} f =\mathbb C$. Basta ahora ver que $\ker f=(x^2+1)$. La inclusión $\supset$ es sencilla porque todo elemento $p(x)\in (x^2+1)$ es múltiplo del polinomio $x^2+1$, es decir, de la forma $p(x)=(x^2+1)q(x)$ y entonces $f(p(x))=p(i)=(i^2+1)q(i)=0$. Para ver $\subset, tomamos ahora un elemento $q(x)\in \ker f$, es decir, tal que $p(i)=0$. Dividimos $p(x)$ entre $x^2+1$, obteniendo así una expresión en $\mathbb{R}[x]$ de la forma
$$p(q)=c(x)(x^2+1)+r(x).$$
Como $x^2+1$ tiene grado $2$, el resto $r(x)$ tendrá grado $<2$, es decir, $r(x)=ax+b$ para ciertos $a,b\in\mathbb{R}$. Entonces,
$$
\begin{array}{rcl}
0&=&p(i)\cr
&=&c(i)(i^2+1)+r(i)\cr
&=&b+ia.
\end{array}
$$
Un número complejo es cero si y solo si su parte real y su parte imaginaria son cero, $b=a=0$. Por tanto $r(x)=0$ y $p(q)=c(x)(x^2+1)\in (x^2+1)$.
{{% /proof %}}



## Dominios y fracciones 

{{% definition %}}
Dado un anillo $R$, un **divisor de cero** es un elemento $a\in R$ no nulo, $a\neq 0$, tal que existe otro $b\in R$, $b\neq 0$, de modo que $ab=0$. Un anillo no trivial $R$ es un **dominio (de integridad)** si no posee divisores de cero.
{{% /definition %}}


{{% remark %}}
Dicho de otro modo, $R$ es un dominio cuando dados $a,b\in R$ tales que $ab=0$ entonces $a=0$ o $b=0$. Los dominios poseen la **propiedad cancelativa**, es decir, si $ab=ac$ y $a\neq 0$ entonces $b=c$ ya que esto equivale a $a(b-c)=0$. Los cuerpos $k$ y los enteros $\mathbb Z$ son dominios. Los subanillos de un dominio también son dominios. El anillo $\mathbb Z/(6)$ no es un dominio porque aquí $2\cdot 3=6=0$ pero $2\neq 0\neq 3$.
{{% /remark %}}


{{% proposition %}}
Si $R$ es un dominio entonces $R[x]$ también.
{{% /proposition %}}


{{% proof %}}
Dados dos polinomios no nulos $p(x)=a_nx^n+\cdots$ y $q(x)=b_mx^m+\cdots$ de grados respectivos $n$ y $m$ ($a_n\neq 0\neq b_m$), su producto $p(x)q(x)=a_nb_mx^{n+m}+\cdots$ es no nulo de grado $n+m$ ya que $a_nb_m\neq 0$ por ser $R$ un dominio.
{{% /proof %}}


{{% corollary %}}
Si $R$ es un dominio entonces $R[x_1,\dots, x_n]$ también.
{{% /corollary %}}


Cualquier subanillo de un cuerpo es un dominio. Veamos que, recíprocamente, todo dominio se puede incluir en un cuerpo.

{{% definition %}}
Dado un dominio $R$, su **cuerpo de fracciones** $Q( R )$ es el cociente del conjunto $$\left\\{\frac{a}{b}\;\bigg|\; a,b\in R,\,b\neq 0\right\\}$$ por la relación de equivalencia $$\frac{a}{b}\sim\frac{a'}{b'}\Leftrightarrow ab'=a'b$$ dotado de las operaciones $$\begin{array}{rcl}\displaystyle \frac{a}{b}+\frac{c}{d}&\displaystyle =&\displaystyle  \frac{ad+bc}{bd},\cr\displaystyle \frac{a}{b}\cdot\frac{c}{d}&\displaystyle =&\displaystyle \frac{a c}{b d}.\end{array}$$
{{% /definition %}}



El ejemplo principal es $Q(\mathbb Z)=\mathbb Q$.



{{% proposition %}}
El cuerpo de fracciones $Q( R )$ de un dominio $R$ está bien definido. La aplicación $i\colon R\rightarrow Q( R )$, $i(a)=\frac{a}{1}$, es un homomorfismo inyectivo. Todo homomorfismo inyectivo $f\colon R\rightarrow k$ donde $k$ es un cuerpo factoriza de manera única a través de $i$, es decir, existe un único homomorfismo $g\colon Q( R )\rightarrow k$ tal que $f=g\circ i$, $$f\colon R\stackrel{i}\rightarrow Q( R )\stackrel{g}\rightarrow k.$$
{{% /proposition %}}


{{% proof %}}
La relación es simétrica y reflexiva porque el producto en $R$ es conmutativo. Veamos la transitividad. Si $$\displaystyle \frac{a}{b}\sim \frac{a'}{b'}\sim \frac{a'^\prime}{b'^\prime}$$ entonces $$\begin{array}{rcĺ}ab'&=&a'b,\cr a'b'^\prime&=&a'^\prime b'.\end{array}$$ En particular, 
$$\begin{array}{rcl}
(a b'^\prime) b'&=&(ab')b'^\prime\cr
&=&(a'b)b'^\prime\cr
&=&(a'b'^\prime)b\cr
&=&(a'^\prime b')b\cr
&=&(a'^\prime b)b'.
\end{array}$$
Por la propiedad cancelativa de los dominios, $ab'^\prime=a'^\prime b$, es decir $\frac{a}{b}\sim \frac{a'^\prime}{b'^\prime}$. Por tanto el conjunto cociente $Q( R )$ está bien definido. Demostrar que las definiciones de la suma y la multiplicación en $Q(R)$ no dependen de la elección de fracciones representantes es laborioso pero trivial, no es distinto de la construcción clásica de los números racionales. También es fácil probar que los axiomas que definen los anillos se verifican. Obviamente el cero y el uno de $Q( R )$ son $\frac{0}{1}$ y $\frac{1}{1}$, respectivamente. Por tanto una fracción $\frac{a}{b}$ es nula $\Leftrightarrow$ $a=0$. Si $\frac{a}{b}$ es no nula entonces es claramente una unidad y $(\frac{a}{b})^{-1}=\frac{b}{a}$, por lo que $Q( R )$ es un cuerpo.

Es inmediato ver que $i$ es un homomorfismo. Es inyectivo porque $a\in\ker f$ si y solo si $\frac{a}{1}=\frac{0}{1}$, lo cual equivale a $a=0$.

Dado $f\colon R\rightarrow k$ como en el enunciado, si existiera una descomposición $f=g\circ i$ entonces tendríamos que
$$f(a)=(g\circ i)(a)=g(i(a))=g\left(\frac{a}{1}\right).$$
Toda fracción de $Q( R )$ se puede descomponer como
$$\frac{a}{b}=\frac{a}{1}\cdot\frac{1}{b}=\frac{a}{1}\left(\frac{b}{1}\right)^{-1},$$
por tanto tendríamos que
$$g\left(\frac{a}{b}\right)=g\left(\frac{a}{1}\left(\frac{b}{1}\right)^{-1}\right)=g\left(\frac{a}{1}\right)g\left(\frac{b}{1}\right)^{-1}=f(a)f(b)^{-1}.$$
Esto demuestra que, caso de existir, $g$ sería único.

Ahora basta definir $g\colon Q( R )\rightarrow k$ como $g\left(\frac{a}{b}\right)=f(a)f(b)^{-1}$. Esta definición tiene sentido porque, como $b\neq 0$ y $f$ es inyectivo, $f(b)\neq 0$, y al ser $k$ un cuerpo todo elemento no nulo tiene inverso, luego $f(b)^{-1}$ existe. Con esta definición es un ejercicio comprobar que $g$ es un homomorfismo.  
{{% /proof %}}


{{% definition %}}
Dado un cuerpo $k$, el **cuerpo de funciones racionales** en una variable se define como $k(x)=Q(k[x])$.
{{% /definition %}}


{{% exercise %}}
Da dos definiciones del cuerpo de funciones racionales en varias variables $k(x_1,\dots,x_n)$, una inductiva y otra directa, que sean aparentemente distintas pero isomorfas.
{{% /exercise %}}


{{% definition %}}
Los ideales distintos del total se denominan **propios**. Un ideal $I\subsetneq R$ es **primo** si dados $a,b\in R$ tales que $ab\in I$ entonces $a\in I$ o $b\in I$.
{{% /definition %}}


{{% remark %}}
Un ideal $I\subset R$ es propio si y solo si $R/I$ no es trivial. Si $p\in\mathbb Z$ es un primo entonces el ideal $(p)\subset \mathbb Z$ es primo ya que si $ab\in (p)$ es porque $p$ divide a $ab$, luego $p$ ha de dividir a $a$ o a $b$, es decir $a\in(p)$ o $b\in(p)$. En general $(0)\subset R$ es primo si y solo si $R$ es un dominio.
{{% /remark %}}


{{% proposition %}}
Un ideal $I\subset R$ es primo $\Leftrightarrow$ $R/I$ es un dominio.
{{% /proposition %}}


{{% proof %}}

Ser un ideal propio se corresponde con tener un cociente no trivial. Veamos la equivalencia del resto de propiedades.

$\Rightarrow$ Dados $\bar a,\bar b\in R/I$, si $\bar a\bar b =\overline{ab}=\bar 0$ entonces $ab\in I$, luego $a\in I$ o $b\in I$, es decir $\bar a=\bar 0$ o $\bar b=\bar 0$.

$\Leftarrow$ Dados $a,b\in R$, si $ab\in I$ entonces $\bar a\bar b=\overline{ab}=\bar 0$, luego $\bar a=\bar 0$ o $\bar b=\bar 0$, es decir $a\in I$ o $b\in I$.
 
{{% /proof %}}


{{% definition %}}
Un ideal $I\subsetneq R$ es **maximal** si los únicos ideales que lo contienen son el total $R$ y el propio $I$.
{{% /definition %}}


{{% remark %}}
De otro modo, no puede existir ningún ideal $J$ tal que $I\subsetneq J\subsetneq R$. Todo anillo no trivial posee al menos un ideal maximal. ¿Cuál es en el caso de los cuerpos?
{{% /remark %}}


{{% proposition %}}
Un ideal $I\subset R$ es maximal $\Leftrightarrow$ $R/I$ es un cuerpo.
{{% /proposition %}}


{{% proof %}}
Recordemos que un cuerpo es un anillo no trivial con dos ideales. El anillo $R/I$ es no trivial si y solo si $I\subsetneq R$, que es la primera condición de maximalidad. Es más $R/I$ tiene solo dos ideales si y solo si solo hay dos ideales de $R$ que contengan a $I$ (necesariamente el total y el propio $I$). Esta es la segunda condición de maximalidad.  
{{% /proof %}}


{{% corollary %}}
Todo ideal maximal es primo.
{{% /corollary %}}


{{% definition %}}
Un **dominio de ideales principales** (también **DIP** o **PID**) es un dominio donde todos los ideales son principales.
{{% /definition %}}

Son dominios de ideales principales $\mathbb Z$ y $k[x]$ si $k$ es un cuerpo.



{{% proposition %}}
En un dominio de ideales principales $R$ todos los ideales primos no nulos son maximales.
{{% /proposition %}}


{{% proof %}}

Supongamos que $(a)\subset (b)\subset R$, con $(a)$ primo y $a\neq0$. Entonces $a=cb$ para cierto $c\in R$. En particular $cb\in (a)$, que es primo, luego $c\in (a)$ o $b\in (a)$.

Si $b\in (a)$ entonces $(b)\subset (a)$, luego $(a)=(b)$.

Si $c\in (a)$ entonces $c=da$ para cierto $d\in R$, por tanto $a=dab=dba$. Por la propiedad cancelativa $db=1$, así que $b$ es una unidad, luego $(b)=R$. 
{{% /proof %}}


{{% example name="Ideales maximales y geometría" %}}
Dado un cuerpo $k$, todo punto $\mathbf{a}=(a\_1,\dots,a\_n)\in k^n$ del espacio afín $n$-dimensional define un ideal maximal de $k[x\_1,\dots,x\_n]$, $$I_{\mathbf{a}}=(x\_1-a\_1,\dots,x\_n-a\_n).$$ Es en efecto maximal porque es el núcleo del homomorfismo sobreyectivo de evaluación $$\begin{array}{rcl} k[x\_1,\dots,x\_n]&\longrightarrow& k,\cr p(x\_1,\dots,x\_n)&\mapsto&p(a\_1,\dots,a\_n). \end{array}$$ Por tanto $k[x\_1,\dots,x\_n]/I_{\mathbf{a}}\cong k$ es un cuerpo por el primer teorema de isomorfía. El **Teorema de los Ceros de Hilbert** dice que si $k=\mathbb C$ o cualquier otro cuerpo algebraicamente cerrado, entonces estos son los únicos ideales maximales de $k[x\_1,\dots,x\_n]$, con lo que tendríamos una biyección, $$\\{\text{Ideales maximales de }k[x\_1,\dots,x\_n]\\}\longleftrightarrow k^n.$$ Como consecuencia de esto y de la caracterización de ideales de un cociente deducimos que si $X\subset k^n$ es el conjunto de soluciones de unas ecuaciones polinómicas, $p_i(x\_1,\dots,x\_n)\in k[x\_1,\dots,x\_n]$, $1\leq i\leq m$, $$X\colon\left\\{ \begin{array}{c} p_1(x\_1,\dots,x\_n)=0,\cr \vdots\quad\cr p_m(x\_1,\dots,x\_n)=0, \end{array} \right.$$ entonces tenemos una biyección $$\\{\text{Ideales maximales de }k[x\_1,\dots,x\_n]/(p_1,\dots,p_m)\\}\longleftrightarrow X.$$ El álgebra del anillo cociente $k[x\_1,\dots,x\_n]/(p_1,\dots,p_m)$ no solo captura el conjunto de puntos de $X$ sino toda su geometría. Por desgracia, otros resultados más precisos al respecto se escapan del alcance de la asignatura.
{{% /example %}}


{{% example name="Ideales maximales, análisis y topología" %}}
Dado un espacio topológico compacto de Hausdorff $X$, denotamos $\mathcal C(X)$ al anillo de funciones continuas $X\rightarrow \mathbb C$. Cualquier punto $x\in X$ define un homomorfismo sobreyectivo $$\begin{array}{rcl} ev_x\colon\mathcal C(X)&\longrightarrow& \mathbb C,\cr f&\mapsto&f(x), \end{array}$$ cuyo núcleo $\ker ev_x\subset\mathcal C(X)$ es un ideal maximal por el primer teorema de isomorfía. La **Teoría de Representación de Gelfand** dice que todos los ideales maximales de $\mathcal C(X)$ son de esta forma, con lo que tenemos una biyección $$\\{\text{Ideales maximales de }\mathcal C(X)\\}\longleftrightarrow X.$$ Esta correspondencia da lugar a una equivalencia de categorías entre los espacios compactos de Hausdorff y las $C^{\ast}$-álgebras conmutativas unitarias, que es una clase de anillos a la que $\mathcal C(X)$ pertenece. Esto permite estudiar la topología desde el punto de vista del álgebra y del análisis funcional. 
{{% /example %}}

