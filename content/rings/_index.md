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

Un anillo es **conmutativo** si además el producto satisface la siguiente propiedad adicional:

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

{{% exercise %}}
Dado un entero primo $p\in\mathbb{Z}$, comprueba que $$S=\left\\{\frac{a}{b}\in\mathbb{Q}\mid p\nmid b\right\\}\subset \mathbb{Q}$$ es un subanillo.
{{% /exercise %}}

{{% exercise label="complexesasmatrices" %}}
Comprueba que 
$$S=\left\\{\left(\begin{array}{rr}a&b\cr -b&a\end{array}\right)\mid a,b\in\mathbb{R}\right\\}\subset M(2,\mathbb{R})$$
es un subanillo.
{{% /exercise %}}


{{% definition %}}
Una **unidad** $u\in R$ es un elemento de un anillo tal que existe $u^{-1}\in R$, denominado **inverso** de $u$, de modo que $$uu^{-1}=1=u^{-1}u.$$ Un **cuerpo** es un anillo conmutativo no trivial donde todos los elementos no nulos son unidades.
{{% /definition %}}

Las unidades de $\mathbb{Z}$ son $\\{1,-1\\}$, mientras que $\mathbb{Q}$, $\mathbb{R}$ y $\mathbb{C}$ son cuerpos. Dado un cuerpo $k$, las unidades de $M(n,k)$ son el grupo $GL(n,k)$ de matrices $n\times n$ de determinante no nulo.

{{% remark %}}
El elemento inverso $u^{-1}$ de una unidad $u$ es único. Esto se demuestra igual que la unicidad de los inversos en un [grupo](../groups/#inverseunique). Si $u$ es una unidad entonces $u^{-1}$ también y $(u^{-1})^{-1}=u$. Dividir por una unidad es multiplicar por el inverso $\frac{a}{u}=au^{-1}$. Los elementos $1$ y $-1$ son siempre unidades (no necesariamente distintas) cuyos inversos son ellos mismos. El subconjunto $R^{\times}\subset R$ formado por las unidades de un anillo $R$ es un grupo con la multiplicación. El grupo multiplicativo $R^\times$ es abeliano si el anillo $R$ es conmutativo. La propiedad de ser un cuerpo se preserva por isomorfismos.
{{% /remark %}}




## Homomorfismos

Los homomorfismos de anillos son aplicaciones entre anillos que preservan la estructura.

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
Si $S\subset M(2,\mathbb{R})$ es el subanillo del ejercicio [anterior](#complexesasmatrices), podemos definir un isomorfismo $f\colon\mathbb{C}\cong S$ como 
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
Todo homomorfismo de anillos $f\colon R\rightarrow S$ se restringe a un homomorfismo entre sus grupos de unidades $f\_{|\_{R^\times}}\colon R^\times\rightarrow S^\times$.
{{% /corollary %}}

{{% proposition %}}
Dados dos homomorfismos de anillos $$R\stackrel{f}\longrightarrow S\stackrel{g}\longrightarrow T$$ 
la composición $g\circ f\colon R\rightarrow T$ también es un homomorfismo. Lo mismo es cierto para isomorfismos. 
{{% /proposition %}}

{{% proof %}}
Comenzamos probando la primera parte. 
La composición $g\circ f$ es un homomorfismo de grupos aditivos. Tenemos que 
$$
\begin{array}{rcl}
(g\circ f)(1)&=&g(f(1))\cr
&=&g(1)\cr
&=&1.
\end{array}
$$
Es más, dados $a,b\in R$, $(g\circ f)(ab)=(g\circ f)(a)(g\circ f)(b)$. Esto se comprueba igual que se hizo para los [grupos](../groups/#homocomp).

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

* Dado $a\in R$, el **ideal principal** generado por $a$ está formado por sus múltiplos $$(a)=\\{ra\mid r\in R\\}\subset R.$$ Observa que, si $R=\mathbb{Z}$, dado $n\in\mathbb{Z}$, $(n)=\langle n\rangle$. 
{{% /example %}}

Más adelante veremos que no hay más subgrupos de $\mathbb{Z}$ que estos y que por tanto coinciden con los ideales.

{{% proposition %}}
El **núcleo** de un homomorfismo $f\colon R\rightarrow S$, $$\ker f=\\{a\in R\;|\;f(a)=0\\},$$ es un ideal $\ker f\subset R$.
{{% /proposition %}}

{{% proof %}}
Sabemos que $\ker f\subset R$ es un subgrupo aditivo. Queda probar la condición de ideal. Si $a\in\ker f$ y $r\in R$ entonces $f(ra)=f( r )f(a)=f( r )0=0$ luego $ra\in \ker f$.
{{% /proof %}}

Por tanto, en $R[x]$, los polinomios $f(x)$ tales que $f(1)=0$ forman un ideal pues constituyen el núcleo del homomorfismo $ev_1\colon R[x]\rightarrow R$ de evaluación en $1\in R$. De hecho podríamos evaluar en cualquier otro elemento de $R$. 

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
Dado un homomorfismo $f\colon R\rightarrow S$, existe un único homomorfismo $\bar f\colon R/\ker f\rightarrow \operatorname{im}f$ tal que $f$ factoriza como $f=i\circ\bar f\circ p$, es decir, $f$ encaja en el siguente **diagrama conmutativo**, $$\require{AMScd}\begin{CD}R @>f>> S\cr @V{\pi}VV @AA{i}A\cr \frac{R}{\ker f} @>>{\overline{f}}> \operatorname{im} f \end{CD}$$ 
 Aquí $\pi$ es la proyección natural e $i$ es la inclusión. Además $\bar f$ es un isomorfismo.
{{% /theorem %}}


{{% proof %}}
La factorización es la vista para [grupos](../groups/#groupsisomorph). Basta por tanto ver que $\overline{f}$ preserva el $1$ y los productos. Recordemos que esta aplicación está definida como $\overline{f}(a+I)=f(a)$. De este modo,
$$
\begin{array}{rcl}
\overline{f}(1+I)&=&f(1)\cr
&=&1,\cr
\overline{f}((a+I)(b+I))&=&\overline{f}((ab)+I)\cr
&=&f(ab)\cr
&=&f(a)f(b)\crhttp://localhost:1313/algbas/
&=&\overline{f}(a+I)\overline{f}(b+I).
\end{array}
$$
{{% /proof %}}

{{% corollary %}}
Dado un anillo cualquiera $R$, la proyección natural $\pi\colon R\cong R/(0)$ es un isomorfismo.
{{% /corollary %}}

{{% proof %}}
Basta aplicarle el primer teorema de isomorfía a la identidad $\id{R}\colon R\rightarrow R$.
{{% /proof %}}

{{% corollary %}}
$\mathbb{R}/(x^2+1)\cong\mathbb{C}$.
{{% /corollary %}}

{{% proof %}}
Consideremos el homomorfismo $f\colon \mathbb R[x]\rightarrow\mathbb C$ definido como $f(p(x))=p(i)$. Este homomorfismo está bien definido porque es la composición de la inclusión $\mathbb{R}[x]\subset \mathbb{C}[x]$ y la evaluación $ev_i\colon\mathbb{C}[x]\rightarrow\mathbb{C}$. Es sobreyectivo ya que dado $a+ib\in\mathbb C$, $f(bx+a)=a+ib$ por tanto $\operatorname{im} f =\mathbb C$. Usando el primer teorema de isomorfía, basta ahora ver que $\ker f=(x^2+1)\subset\mathbb{R}[x]$. La inclusión $\supset$ es sencilla porque todo elemento $p(x)\in (x^2+1)$ es múltiplo del polinomio $x^2+1$, es decir, de la forma $p(x)=(x^2+1)q(x)$ y entonces $f(p(x))=p(i)=(i^2+1)q(i)=0$. Para ver $\subset$, tomamos ahora un elemento arbitrario $p(x)\in \ker f$, es decir, tal que $p(i)=0$. Dividimos $p(x)$ entre $x^2+1$, obteniendo así una expresión en $\mathbb{R}[x]$ de la forma
$$p(x)=c(x)(x^2+1)+r(x).$$
Como $x^2+1$ tiene grado $2$, el resto $r(x)$, si no es trivial, tendrá grado $<2$, es decir, en cualquier caso  $r(x)=ax+b$ para ciertos $a,b\in\mathbb{R}$. Entonces,
$$
\begin{array}{rcl}
0&=&p(i)\cr
&=&c(i)(i^2+1)+r(i)\cr
&=&b+ia.
\end{array}
$$
Un número complejo es cero si y solo si su parte real y su parte imaginaria son cero, $b=a=0$. Por tanto $r(x)=0$ y $p(x)=c(x)(x^2+1)\in (x^2+1)$.
{{% /proof %}}



## Dominios

{{% definition %}}
Dado un anillo $R$, un **divisor de cero** es un elemento $a\in R$ no nulo, $a\neq 0$, tal que existe otro $b\in R$, $b\neq 0$, de modo que $ab=0$. Un anillo no trivial $R$ es un **dominio (de integridad)** si no posee divisores de cero.
{{% /definition %}}

El anillo $\mathbb{Z}$ y los cuerpos son dominios.

{{% remark %}}
Dicho de otro modo, $R$ es un dominio cuando dados $a,b\in R$ tales que $ab=0$ entonces $a=0$ o $b=0$. Los subanillos de un dominio también son dominios. El $1$ y el $-1$ nunca son divisores de cero. La propiedad de ser un dominio se preserva por isomorfismos.
{{% /remark %}}

{{% example name="Un anillo que no es un dominio" %}}
Como conjunto, el anillo $\mathbb{Z}/(4)$ es
$$\mathbb{Z}/(4)=\\{\bar{0},\bar{1},\bar{2},\bar{3}\\}.$$
El elemento neutro para la suma es $\bar{0}$, por tanto $\bar{2}\neq\bar{0}$. Sin embargo $\bar{2}\cdot\bar{2}=\bar{4}=\bar{0}$ ya que $4\in (4)$. Esto prueba que $\bar{2}$ es un divisor de cero en este anillo. ¿Hay algún otro?
{{% /example %}}

{{% exercise %}}
Da mas ejemplos de anillos $\mathbb{Z}/(n)$ que **no** sean dominios.
{{% /exercise %}}

La siguiente propiedad de los dominios se conoce como **propiedad cancelativa**.

{{% proposition %}}
En un dominio, si $ab=ac$ y $a\neq 0$ entonces $b=c$.
{{% /proposition %}}

{{% proof %}}
En un anillo $R$, la ecuación $ab=ac$ equivale a $a(b-c)=0$. Si $a\neq 0$ y $R$ es un dominio entonces no queda otra opción que $b-c=0$, lo cual equivale a $b=c$.
{{% /proof %}}

{{% proposition %}}
Si $R$ es un dominio entonces $R[x]$ también.
{{% /proposition %}}


{{% proof %}}
Dados dos polinomios no nulos $p(x)=a_nx^n+\cdots$ y $q(x)=b_mx^m+\cdots$ de grados respectivos $n$ y $m$ ($a_n\neq 0\neq b_m$), su producto $p(x)q(x)=a_nb_mx^{n+m}+\cdots$ es no nulo de grado $n+m$ ya que $a_nb_m\neq 0$ por ser $R$ un dominio.
{{% /proof %}}

{{% corollary %}}
Si $R$ es un dominio entonces $R[x_1,\dots, x_n]$ también.
{{% /corollary %}}

{{% proposition %}}
Todo dominio finito $R$ es un cuerpo.
{{% /proposition %}}

{{% proof %}}
Sea $a\in R$ un elemento no nulo. Por ser $R$ un dominio, la propiedad cancelativa demuestra que la aplicación
$$
\begin{array}{rcl}
R&\longrightarrow&R,\cr
x&\mapsto&a\cdot x,
\end{array}
$$
es inyectiva. Toda aplicación inyectiva entre conjuntos finitos con el mismo número de elementos es biyectiva. Por tanto, existe $b\in R$ tal que $a\cdot b=1$. Como $R$ es conmutativo, esto implica que $a$ es una unidad con inversa $a^{-1}=b$.
{{% /proof %}}

{{% example name="Cuerpos finitos" %}}
Si $p\in\mathbb{Z}$ es un primo entonces $\mathbb{Z}/(p)$ es un cuerpo con $p$ elementos. En efecto, sabemos que este anillo tiene $p$ elementos, así que en virtud de la proposición anterior basta comprobar que es un dominio. Dados $\bar{m},\bar{n}\in\mathbb{Z}/(p)$, si $\bar{m}\cdot \bar{n}=\overline{mn}=\bar{0}$ entonces $mn\in (p)$, es decir, $p$ divide a $mn$. Pero como $p$ es primo, para que esto ocurra $p$ ha de dividir a $m$ o bien a $n$. En el primero de los casos $\bar{m}=\bar{0}$ y en el segundo $\bar{n}=\bar{0}$, así que no puede haber divisores de $0$ en $\mathbb{Z}/(p)$. Este cuerpo también se denota $\mathbb{F}_p$.
{{% /example %}}

{{% exercise %}}
¿Hay cuerpos finitos cuyo número de elementos no sea primo?
{{% /exercise %}}


## Ideales primos 

{{% definition %}}
Los ideales distintos del total se denominan **propios**. Un ideal $I\subsetneq R$ es **primo** si dados $a,b\in R$ tales que $ab\in I$ entonces $a\in I$ o $b\in I$.
{{% /definition %}}

{{% remark %}}
Un ideal $I\subset R$ es propio si y solo si $R/I$ no es trivial. La propiedad de ser un dominio se preserva por isomorfismos.
{{% /remark %}}

{{% proposition %}}
Un ideal $I\subset R$ es primo $\Leftrightarrow$ $R/I$ es un dominio.
{{% /proposition %}}

{{% proof %}}
Ser un ideal propio se corresponde con tener un cociente no trivial. Veamos la equivalencia del resto de propiedades.

$\Rightarrow$ Veamos que no hay divisores de cero en $R/I$. Dados $\bar a,\bar b\in R/I$, si $\bar a\bar b =\overline{ab}=\bar 0$ entonces $ab\in I$. Como $I$ es primo, esto implica que $a\in I$ o $b\in I$, es decir $\bar a=\bar 0$ o $\bar b=\bar 0$. Por tanto no hay divisores de cero en $R/I$

$\Leftarrow$ Veamos que $I$ es primo. Dados $a,b\in R$, si $ab\in I$ entonces $\bar a\bar b=\overline{ab}=\bar 0$, así que por ser $R/I$ un dominio, entonces $\bar a=\bar 0$ o $\bar b=\bar 0$, es decir $a\in I$ o $b\in I$. Esto prueba que $I$ es primo.
{{% /proof %}}

{{% corollary %}}
El ideal trivial $(0)\subset R$ es primo $\Leftrightarrow$ $R$ es un dominio.
{{% /corollary %}}

{{% proof %}}
Esto es consecuencia de que hay un isomorfismo de anillos $R\cong R/(0)$.
{{% /proof %}}

{{% proposition %}}
Un ideal principal $(n)\subset\mathbb{Z}$ es primo $\Leftrightarrow$ $n=0$ o $n$ es un entero primo.
{{% /proposition %}}

{{% proof %}}
$\Leftarrow$ El ideal $(0)$ es primo porque $\mathbb{Z}$ es un dominio, y si $n$ es un entero primo ya hemos visto antes que entonces $\mathbb{Z}/(n)$ es un dominio, así que $(n)$ también sería primo en este caso.

$\Rightarrow$ Por reducción al absurdo, si $n\neq 0$ no fuera un entero primo, entonces factorizaría $n=ab$ como producto de dos enteros $a,b\in\mathbb{Z}$, $a,b\neq\pm1$. Por tanto, $1<|a|,|b|<|n|$, así que $n$ no divide a $a$ ni a $b$, luego $\bar{a}\neq\bar{0}\neq\bar{b}$ en $\mathbb{Z}/(n)$. Sin embargo $\bar{a}\bar{b}=\overline{ab}=\bar{n}=\bar{0}$ pues $n\in (n)$.
{{% /proof %}}

{{% definition %}}
La **característica** de un dominio de integridad $R$ es el orden de $1\in R$ en el grupo aditivo, es decir, el menor entero $n\geq 1$ tal que
$$1+\stackrel{n}{\cdots}+1=0.$$
Si no existe tal $n$ decimos que $R$ es de característica $0$.
{{% /definition %}}

Los dominios $\mathbb{Z}$, $\mathbb{Q}$, $\mathbb{R}$ y $\mathbb{C}$ tienen característica $0$ mientras que $\mathbb{Z}/(p)$ tiene característica $p$ para $p\in\mathbb{Z}$ primo. Más adelante veremos que la característica de un dominio cualquiera es $0$ o un número entero primo.



## Divisibilidad en $\Z$

En esta sección formalizaremos propiedades de los números enterios relacionadas con la divisibilidad. La mayor parte son bien conocidas. Usaremos sin demostrarlo el siguiente resultado básico de la teoría de conjuntos.

{{% theorem name="Principio de buena ordenación" %}}
Todo subconjunto no vacío de $\Z$ acotado inferiormente posee un mínimo, necesariamente único. 
{{% /theorem %}}



{{% definition %}}
Dados $a,b\in\mathbb{Z}$, decimos que $a$ **divide** a $b$, y escribimos $a |  b$, si existe $c\in\Z$ tal que
$ac=b$. También se dice que $b$ es
**divisible** por $a$.
{{% /definition %}}

{{% remark %}}
Todos los enteros dividen al $0$, pero el $0$ solo se divide a sí mismo. El $1$ solo es divisible por $\pm1$. Obsverva que si $a |  b$ y $b\neq 0$ entonces $|a|\leq |b|$.
{{% /remark %}}

{{% proposition %}}
Las unidades de $\mathbb{Z}$, $1$ y $-1$, son los dos únicos enteros que dividen a todos los demás. 
{{% /proposition %}}

{{% proof %}}
Es obvio que $1$ y $-1$ dividen a cualquier otro $a\in\mathbb{Z}$ ya que $1a=a$ y $(-1)(-a)=a$. Si $b\in\mathbb{Z}$ divide a cualquier otro entero, en particular divide a $1\in\mathbb{Z}$. El $1$ solo es divisible por sí mismo y por $-1$, luego $b=\pm1$.
{{% /proof %}}



{{% proposition %}}
Dados $a,b,c\in\mathbb{Z}$, se satisfacen las siguientes propiedades.

1. $a |  a$  (**reflexiva**) y $-a |  a$.

2. si $a |  b$ y $b |  c$ entonces $a |  c$ (**transitiva**).

3. $a |  b$ y $b |  a$ si y solo si $a=\pm b$.

4. Si $a |  b$ y $a |  c$ entonces $a |  (b + c)$.

5. Si $a |  b$ entonces $a |  bc$, para todo $c\in\Z$.

{{% /proposition %}}

{{% proof %}}
El primer apartado se satisface porque $a1=a$ y $(-a)(-1)=a$.

En el supuesto de 2, $ar=b$ y $bs=c$ para ciertos $r,s\in\mathbb{Z}$, luego $a(rs)=(ar)s=bs=c$, así que $a |  c$.

Con respecto a 3, $\Leftarrow$ se ha probado en 1. Veamos $\Rightarrow$. Bajo estas hipótesis, $ar=b$ y $bs=a$ para ciertos $r,s\in\mathbb{Z}$, luego $a(rs)=(ar)s=bs=a$. Por la propiedad cancelativa del dominio $\mathbb{Z}$, $rs=1$, así que $r$ y $s$ son unidades mutuamente inversas, por lo tanto $r=s=\pm1$ y en consecuencia $a=\pm b$.

En las condiciones de 4, $ar=b$ y $as=c$ para ciertos $r,s\in\mathbb{Z}$, luego $a(r+s)=ar+as=b+c$, y por tanto $a |  (b+c)$.

Por último, en 5, $ar=b$ para cierto $r\in\mathbb{Z}$, así que $a(rc)=(ar)c=bc$, luego $a |  c$.
{{% /proof %}}

A estas alturas de la vida, vamos a aprender a dividir.

{{% theorem name="División euclídea" %}}
Dados $D,d \in \Z$, $d\ne 0$, existen $c,r\in \Z$ únicos tales que:

* $D=dc+r$.

* $0\leq r < |d|$.
{{% /theorem %}}


{{% proof %}}
El subconjunto $$S=\\{ D-dx \mid (x \in \Z) \wedge (D-dx \geq 0) \\}\subset\mathbb{Z}$$
no es vacío. En efecto, si $D\geq 0$ tomamos $x=-dD$ y entonces $D-dx=D+d^2D=D(1+d^2)\geq 0$, y si $D<0$ tomamos $x=dD$ y $D-dx=D-d^2D=D(1-d^2)\geq 0$ ya que, como $d\neq 0$, $d^2\geq 1$.

Como $S$ está acotado inferiormente por $0$, ha de tener un mínimo $r\in S$ por el principio de buena ordenación. Este mínimo se alcanzará para cierto valor de $x=c\in\mathbb{Z}$, y por tanto $r=D-dc\geq 0$, es decir, $D=dc+r$. Veamos que $r<|d|$. Por reducción al absurdo, si $r\geq |d|$ entonces $r'=r-|d|\geq 0$. Es más, como $d\neq 0$, $r'>r$, pero $r'\in S$ ya que $r'=r\pm d=D-dc\pm d=D-d(c\mp 1)$. Esto contradice la minimalidad de $r\in S$.

Veamos ahora la unicidad del cociente y del resto. Supongamos que también $D=dc'+r'$ para ciertos $c',r'\in\mathbb{Z}$ con $0\leq r'<|d|$. Entonces $dc+r=dc'+r'$. Si $r=r'$ entonces $dc=dc'$. Como $d\neq 0$ podemos aplicar la propiedad cancelativa y deducimos que $c=c'$. Veamos que es imposible que $r\neq r'$. De lo contrario, podemos suponer sin pérdida de generalidad que $r>r'$. Como $0\leq r,r'<|d|$ entonces $0<r-r'<|d|$, pero $r-r'=d(c'-c)$, que es divisible por $d$, así que $|d|\leq |r-r'|$, lo cual entra en contradicción.
{{% /proof %}}

{{% remark %}}
En las circunstancias anteriores, decimos que $D$ es el **dividendo**, $d$ es el **divisor**, $c$ es el **cociente** y $r$ es el **resto** de la **división euclídea** de $D$ entre $d$.  Es frecuente relajar la segunda condición del teorema y pedir solo que $0\leq |r|<|d|$. En este caso, el cociente y el resto no tienen por qué ser únicos. Más concretamente, si la división no es exacta siempre hay dos restos posibles, uno positivo y otro negativo, por ejemplo $14=3\cdot 4+2=3\cdot 5+(-1)$.
{{% /remark %}}

{{% proposition %}}
Dados $D,d\in\mathbb{Z}$, $d\neq 0$, $d|D$ si y solo si el resto de la división de $D$ entre $d$ es $r=0$.
{{% /proposition %}}

{{% proof %}}
$\Rightarrow$ Si $d|D$ entonces existe $c\in\mathbb{Z}$ tal que $dc=D$, luego $D=dc+0$ es una división euclídea con resto $r=0$. 

$\Leftarrow$ Recíprocamente, si en la división euclídea $D=dc+r$ tenemos que $r=0$, entonces $d|D$.
{{% /proof %}}

{{% remark %}}
Cuando las condiciones equivalentes de la proposición anterior se dan, decimos que la división euclídea de $D$ entre $d$ es **exacta**. Es frecuente relajar la segunda condición del teorema y pedir solo que $0\leq |r|<|d|$. En este caso, el cociente y el resto no tienen por qué ser únicos. Más concretamente, si la división no es exacta siempre hay dos restos posibles, uno positivo y otro negativo, por ejemplo $14=3\cdot 4+2=3\cdot 5+(-1)$.
{{% /remark %}}



Ahora podemos demostrar que todos los subgrupos de $\mathbb{Z}$ son cíclicos.

{{% theorem label="subgruposZ" %}}
Todos los subgrupos de $\mathbb{Z}$ son cíclicos.
{{% /theorem %}}

{{% proof %}}
Sea $H\subset\mathbb{Z}$ un subrgupo cualquiera. El subgrupo trivial $H=\\{0\\}$ es cíclico pues está generado por el elemento neutro $H=\langle 0\rangle$. Supongamos que $H\neq\\{0\\}$ entonces existe algún elemento $m\in H$ no nulo $m\neq 0$. De hecho existe algún elemento positivo, ya que si $m<0$ entonces $-m\in H$, por ser $H$ un subgrupo, y $-m>0$. 

Sea $$S=\\{m\in H\mid m>0\\}\subset\mathbb{Z}.$$
Por el principio de buena ordenación, hay un mínimo $n\in S$. Veamos que $\langle n\rangle = H$. Por definición, $\langle n\rangle$ está formado por los múltiplos de $n$. La inclusión $\subset$ es cierta ya que $n\in H$, $H$ es un subgrupo y cualquier múltiplo de $n$ se obtiene sumando $n$ o $-n$ consigo mismo un número determinado de veces. Para ver $\supset$, tenemos que comprobar que todos los elementos de $H$ son múltiplos de $n$. Sea $a\in H$. Realizamos la división euclídea de $a$ por $n$: $a=nc+r$, $0\leq r<n$. Si $r=0$ entonces $a=nc\in \langle n\rangle$. Veamos por reducción al absurdo que es imposible que $r\neq 0$. De lo contrario, $0<r<n$. Es más, $r=a-nc\in H$ pues $a\in H$, $nc\in\langle n\rangle \subset H$ y $H$ es un subgrupo. Por tanto $r\in S$, pero $r<n$, y esto contradeciría la minimalidad de $n$.
{{% /proof %}}

{{% remark %}}
En la demostración hemos visto que todo subgrupo $H\subset \mathbb{Z}$ está generado por el menor $n\in H$, $n>0$.
{{% /remark %}}

{{% corollary %}}
Todo subgrupo de $\mathbb{Z}$ es un ideal principal y todo ideal de $\mathbb{Z}$ es principal.
{{% /corollary %}}

{{% proof %}}
Hemos visto que todo subgrupo $H\subset \mathbb{Z}$ es cíclico, es decir $H=\langle n\rangle$ para cierto $n\in\mathbb{Z}$. Anteriormente habíamos observado que $\langle n\rangle=(n)$ coincide con el ideal principal formado por los múltiplos de $n$.

Si $I\subset\mathbb{Z}$ es un ideal, en particular es un subgrupo, así que existe $n\in\mathbb{Z}$ tal que $I=\langle n\rangle = (n)$.
{{% /proof %}}

<!--

{{% definition %}}
{Máximo común divisor} {Dados dos enteros
$a$ y $b$, diremos que $d$ es {\bf un máximo común divisor} de $a$ y $b$ y
denotaremos $d=\mbox{\bf mcd}(a,b)$, si se verifica:
\begin{enumerate}

\item $d|a$ y $d|b$.

\item Si $d'$ es tal que $d'|a$ y $d'|b$ entonces $d'|d$.
\end{enumerate}
Si $1$ es un máximo común divisor de $a$ y $b$, se dice que $a$ y $b$ son {\bf primos entre sí}.}
{{% /definition %}}

{{% watch %}}
Demostraremos más adelante la existencia de máximo común divisor para cualquier par de enteros $a$ y $b$. Si $d$ y $d'$ son dos máximos comunes divisores de $a$ y $b$, entonces debe verificarse que $d|d'$ y $d'|d$, luego $d'=\pm d$. Es decir, el máximo común divisor, si existe, {\bf es único salvo el signo}.
{{% /watch %}}

{{% proposition %}}

Se verifican las siguientes propiedades:
\begin{enumerate}
\item ${\rm mcd}(a,b)=b\Leftrightarrow b|a$.
\item $\mcd (a,b)=\mcd (-a,b)=\mcd (a,-b)=\mcd (-a,-b)$.
\item $\mcd (a,b)=\mcd (b,a)$.
\end{enumerate}
{{% /proposition %}}

{{% definition %}}
{Mínimo común múltiplo} {Sean $a$ y $b$ enteros. Diremos que $m$ es un {\bf mínimo común múltiplo} de $a$
y $b$ y denotaremos $m=\mbox{\bf mcm}(a,b)$, si se verifica:
\begin{enumerate}

\item $a|m$ y $b|m$.

\item Si $m'$ es tal que $a|m'$ y $b|m'$ entonces $m|m'$.
\end{enumerate}}
{{% /definition %}}


{{% watch %}}
 También demostraremos más adelante la existencia de mínimo común múltiplo para cualquier par de enteros $a$ y $b$. Si $m$ y $m'$ son dos mínimos comunes múltiplos de $a$ y $b$, entonces debe verificarse que $m|m'$ y $m'|m$, luego $m'=\pm m$. Es decir, el mínimo común múltiplo, si existe, {\bf es único salvo el signo}.
{{% /watch %}}

{{% proposition %}}

Se verifican las siguientes propiedades:
\begin{enumerate}
\item ${\rm mcm}(a,b)=b\Leftrightarrow a|b$.
\item $\mcm (a,b)=\mcm (-a,b)=\mcm (a,-b)=\mcm (-a,-b)$.
\item $\mcm (a,b)=\mcm (b,a)$.
\end{enumerate}
{{% /proposition %}}

-->
