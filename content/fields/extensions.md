+++
title = "Extensiones"
weight = 10
+++

## Extensiones de cuerpos

{{% definition %}}
Una **extensión (de cuerpos)** $$F\subset K$$ es un par formado por un cuerpo $K$ y un subanillo $F$ que también es un cuerpo. Decimos en este caso que $K$ es una extensión de $F$. Observa que $K$ es un $F$-espacio vectorial con la suma y el producto por escalares de $F$. La extensión es **finita** si $\dim\_FK<\infty$, en dicho caso definimos el **grado** de la extensión como $$[K:F]=\dim\_FK.$$ 
{{% /definition %}}



{{% example name="Ejemplos de extensiones" %}}

* $\mathbb R\subset\mathbb C$ es finita de grado $[\mathbb{C},\mathbb{R}]=2$, ya que $\\{1,i\\}\subset\mathbb C$ es una base como $\mathbb R$-espacio vectorial. 

* $\mathbb Q\subset\mathbb R$ no es finita porque cualquier $\mathbb Q$-espacio vectorial de dimensión finita es numerable, pero $\mathbb R$ no lo es.

* Todo cuerpo $F$ posee la **extensión trivial** $F\subset F$, que es la única de grado $1$, el resto tienen grado $>1$. En efecto, $\dim\_FF=1$ así que, como $F\subset K$, $[K:F]=\dim\_FK\geq 1$ dándose la igualdad si y solo si $F=K$.

* $F\subset F(x)$ tampoco es finita.

* $F\subset F[x]/(p(x))$, donde $p(x)\in F[x]$ es un polinomio irreducible. En efecto, por ser $F[x]$ un DFU tenemos que $p(x)\in F[x]$ es primo, y por ser $F[x]$ un dominio de ideales  principales tenemos que el ideal primo $(p(x))\subset F[x]$, al ser no trivial, es maximal, por tanto $F[x]/(p(x))$ es un cuerpo. Sabemos además que 
$$[F[x]/(p(x)):F]=\text{grado }p(x).$$
{{% /example %}}


{{% definition %}}
Dadas dos extensiones $F\subset K$ y $F\subset L$ de un mismo cuerpo $F$, un **homomorfismo** de extensiones $f\colon K\rightarrow L$ es un homomorfismo de anillos que deja fijo a $F$, es decir, que satisface $f(\alpha)=\alpha$ para todo $\alpha\in F$. Un **endomorfismo** de una extensión $F\subset K$ un homomorfismo de extensiones $f\colon K\rightarrow K$. Un **isomorfismo** de extensiones es un homomorfismo biyectivo. Un **automorfismo** de una extensión $F\subset K$ es un endomorfismo biyectivo. 
{{% /definition %}}


{{% remark %}}
La identidad es un homomorfismo de extensiones y la composición de homomorfismos de extensiones es también un homomorfismo de extensiones. Lo mismo ocurre con isomorfismos y automorfismos. Además, la aplicación inversa de un isomorfismo de extensiones es otro isomorfismo de extensiones, e igual para los automorfismos. Los homorfismos de cuerpos son inyectivos, así que los homomorfismos de extensiones también. 
{{% /remark %}}

{{% proposition %}}
Un homorfismo $f\colon K\rightarrow L$ de extensiones de $F$ es también un homomorfismo de $F$-espacios vectoriales.
{{% /proposition %}}

{{% proof %}}
Como $f$ es un homomorfismo de anillos, preserva sumas. Dado $\alpha\in F\subset K$ y $x\in K$, por ser $f$ un homomorfismo de anillos, $f(\alpha x)=f(\alpha)f(x)$. Como $f$ es un homomorfismo de extensiones de $F$, $f(\alpha)=\alpha$. Por tanto $f(\alpha x)=\alpha f(x)$, es decir, $f$ preserva el producto por escalares de $F$.
{{% /proof %}}

{{% corollary %}}
Si $f\colon K\rightarrow L$ es un isomorfismo de extensiones de $F$ entonces $[K:L]\cong [L:K]$.
{{% /corollary %}}

Más adelante veremos ejemplos de extensions no isomorfas del mismo grado.

{{% corollary %}}
Todo endomorfismo $f\colon K\rightarrow K$ de una extensión finita $F\subset K$ es un automorfismo.
{{% /corollary %}}

{{% proof %}}
Como $f$ es un homomorfismo inyectivo de $F$-espacios vectoriales y su partida y su llegada poseen la misma dimensión, ha de ser un isomorfismo.
{{% /proof %}}

{{% proposition %}}
Dadas dos extensiones $\mathbb Q\subset K$ y $\mathbb Q\subset L$ de $\mathbb Q$, cualquier homomorfismo de anillos $f\colon K\rightarrow L$ es un homomorfismo de extensiones. 
{{% /proposition %}}

{{% proof %}}
Por ser $f$ un homomorfismo de anillos, $f(0)=0$. Es más, como $f(1)=1$ y $f$ preserva sumas, es fácil ver que $f(n)=n$ para cualquier $n\in\mathbb Z$, $n>0$. Además $f$ preserva opuestos, luego $f(-n)=-f(n)=n$. Esto prueba que $f$ deja fijo a $\mathbb Z$. Todo racional se puede expresar como $\frac{p}{q}=pq^{-1}$ para $p,q\in\mathbb Z$, $q\neq 0$. Los homomorfismos de anillos preservan productos e inversos, así que $$\begin{array}{rcl}f\left(\frac{p}{q}\right)&=&f(pq^{-1})\cr &=&f(p)f(q^{-1})\cr &=&f(p)f(q)^{-1}\cr &=&pq^{-1}\cr &=&\frac{p}{q}.\end{array}$$   
{{% /proof %}}

{{% corollary %}}
Dada una extension finita $\mathbb{Q}\subset K$, todo homomorfismo de anillos $f\colon K\rightarrow K$ es un automorfismo de la extensión $\mathbb{Q}\subset K$.
{{% /corollary %}}


{{% definition %}}
Dada una extensión $F\subset K$, decimos que $\alpha\in K$ es **algebraico** si existe $p(x)\in F[x]$ no nulo tal que $p(\alpha)=0$. En caso contrario decimos que $\alpha$ es **trascendente**. 
{{% /definition %}}

{{% remark %}}
Si tenemos dos extensiones sucesivas $F\subset K\subset L$ y $\alpha\in L$ es algebraico sobre $F$ entonces también es algebraico sobre $K$ ya que $F[x]\subset K[x]$. ¡Ojo! El recíproco no es cierto. 
{{% /remark %}}

{{% example name="Existencia de elementos trascendentes en $\mathbb Q\subset\mathbb C$" %}}
Como $\mathbb Q$ es numerable, $\mathbb Q[x]$ también. Además, todo polinomio tiene una cantidad finita de soluciones en $\mathbb C$. Por tanto hay una cantidad numerable de elementos algebraicos para la extensión $\mathbb Q\subset\mathbb C$. Como $\mathbb C$ no es numerable, han de existir elementos trascendentes, de hecho una cantidad no numerable de ellos. Lo mismo se aplica a la extensión $\mathbb Q\subset\mathbb R$. Dar un ejemplo concreto de número trascendente es sin embargo bastante complicado. Es conocido que $\pi$ es trascendente sobre $\mathbb Q$ pero no es fácil probarlo. 
{{% /example %}}

{{% definition %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$, su **polinomio irreducible** $p(x)\in F[x]$ es el único polinomio mónico irreducible con coeficientes en $F$ que tiene a $\alpha$ como raíz. El **grado** de $\alpha$ sobre $F$ es el de su polinomio irreducible.
{{% /definition %}}

{{% remark %}}
La condición de ser mónico es solo para garantizar su unicidad. Si encontramos un polinomio irreducible con coeficientes en $F$ que tiene a $\alpha$ como raíz, basta dividirlo por su coeficiente líder para convertirlo en mónico.
{{% /remark %}}

{{% theorem %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$, el polinomio irreducible de $\alpha$ es el generador mónico del núcleo del homomorfismo $f\colon F[x]\rightarrow K$, $f(p(x))=p(\alpha)$. Es más, hay un isomorfismo de extensiones de $F$,
$$\frac{F[x]}{(p(x))}\cong F[\alpha].$$
En particular, 
$$[F[\alpha]:F]=\text{grado }\alpha.$$ 
{{% /theorem %}}

{{% proof %}}
Ser algebraico equivale a $\ker f\neq (0)$, pues los elementos de $\ker f$ son los polinomios con coeficientes en $F$ que tienen a $\alpha$ como raíz. En particular, $\ker f\neq F[x]$ ya que los polinomios constantes no nulos no tienen raíces. 

Supongamos que $\alpha$ tiene polinomio irreducible $p(x)$. Entonces $p(x)\in\ker f$, así que $(p(x))\subset\ker f$. Como $F[x]$ es un DIP, $(p(x))$ es maximal por ser $p(x)$ irreducible, así que $(p(x))=\ker f$. 

Recíprocamente, supongamos que $\ker f=(p(x))$. Por el primer teorema de isomorfía, $f$ induce un isomorfismo
$$\overline{f}\colon\frac{F[x]}{(p(x))}\stackrel{\cong}\longrightarrow F[\alpha].$$
Como $F[\alpha]\subset K$ es un dominio, así que el ideal $(p(x))\subset F[x]$ es primo. Como $F[x]$ es un DFU, esto equivale a decir que $p(x)$ es irreducible. Podemos además suponer que es mónico, dividiendo por su coeficiente líder si fuera necesario.

Cabe destacar que todos los generadores de $\ker f$ son asociados, así que, de entre ellos, hay uno único que es mońico. Este es el polinomio irreducible de la definición.

Por ser $F[x]$ un DIP, el ideal primo no nulo $\ker f=(p(x))\subset F[x]$ es maximal, por tanto el cociente $F[x]/(p(x))$ es un cuerpo, así que $F[\alpha]$ también, por ser isomorfos. Además, $\overline{f}$ es un isomorfismo de extensiones ya que está definido como $$\overline{f}([q(x)])=f(q(x))=q(\alpha),$$ así que, dado $\beta\in F$, 
$$
\begin{array}{rcl}
\overline{f}(\beta\cdot[q(x)])&=&\overline{f}([\beta\cdot q(x)])\cr
&=&\beta\cdot q(\alpha)\cr
&=&\beta\cdot\overline{f}([q(x)]).
\end{array}
$$

La segunda ecuación se deduce de que extensiones isomorfas tienen el mismo grado.
{{% /proof %}}

El siguiente corolario se basa en el hecho de que $F[x]$ es un dominio euclídeo. Su importancia estriba en que da un método para calcular el polinomio irreducible de un elemento algebraico sin necesidad de  comprobar la irreducibilidad por otros métodos.

{{% corollary %}}
Dada una extensión $F\subset K$, el polinomio irreducible de un elemento algebraico $\alpha\in K$ es el polinomio no nulo de menor grado en $F[x]$ que tiene a $\alpha$ como raíz.
{{% /corollary %}}

{{% corollary %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$ de grado $n$, $\\{1,\alpha,\dots,\alpha^{n-1}\\}\subset F[\alpha]$ es una base como $F$-espacio vectorial. 
{{% /corollary %}}

{{% proof %}}
El isomorfismo de extensiones del teorema anterior es también un isomorfismo de $F$-espacios vectoriales. Sabemos que $\\{1,\bar{x},\dots,\bar{x}^{n-1}\\}$ es una base de $F[x]/(p(x))$, así que su imagen, $\\{1,\alpha,\dots,\alpha^{n-1}\\}$, es una base de $F[\alpha]$.
{{% /proof %}}

{{% corollary %}}
Dada una extensión $F\subset K$ y elementos algebraicos $\alpha\_1,\dots,\alpha\_n\in K$, la extensión $F\subset F[\alpha\_1,\dots,\alpha\_n]$ es finita. 
{{% /corollary %}}

{{% proposition %}}
Si $F\subset K$ es una extensión, $\alpha\in K$ y $q(x)\in F[x]$ es un polinomio no nulo que tiene a $\alpha$ como raíz, entonces el grado de $\alpha$ sobre $F$ es menor o igual que el grado de $q(x)$. 
{{% /proposition %}}

{{% proof %}}
Consideramos el homomorfismo $f\colon F[x]\rightarrow K$ del teorema anterior. Si $p(x)$ es el polinomio irreducible de $\alpha$, $\ker f=(p(x))$. Como $\alpha$ es una raíz de $q(x)$, $q(x)\in\ker f$, así que $q(x)$ es un multiplo no nulo de $p(x)$, de donde se deduce la desigualdad de grados.
{{% /proof %}}

{{% example name="Grado de algunos elementos" %}}
Sea $F\subset K$ una extensión y $\alpha\in K$ un elemento algebraico.

* No hay elementos de grado $0$ porque los polinomios no nulos de grado $0$ no tienen raíces.

* El grado de $\alpha$ es $1$ si y solo si $\alpha\in F$. En efecto, esto equivale a decir que $\alpha$ es raíz de un polinomio mónico de grado $1$ en $F[x]$ (todos ellos irreducibles) que no puede ser otro que $x-\alpha$.

* El grado de $\alpha$ es $2$ si y solo si $\alpha\notin F$ pero es raíz de un polinomio de grado $2$ en $F[x]$.

* Dado $\alpha\in K$ tal que $\alpha\notin F$ pero $\alpha^2\in F$, el grado de $\alpha$ es $2$ y su polinomio irreducible es $x^2-\alpha^2\in F[x]$.

* Si $F\subset\mathbb R$, el grado de $i\in\mathbb C$ sobre $F$ es $2$ pues $i\notin F$ pero es raíz de $x^2+1\in F[x]$, que es su polinomio mínimo.

* Si $n\in\mathbb Z$ es libre de cuadrados, el grado de $\sqrt{n}\in\mathbb C$ sobre $\mathbb Q$ es $2$ pues $\sqrt{n}\notin\mathbb Q$ pero es raíz de $x^2-n\in\mathbb Q[x]$.

* Si $p\in\mathbb Z$ es primo, el grado de $\sqrt[n]{p}\in\mathbb C$ sobre $\mathbb Q$ es $n$ puesto que es raíz del polinomio irreducible $x^n-p\in\mathbb Q[x]$. Este polinomio es irreducible por el criterio de [Eisenstein](../../rings/factorization/#eisenstein) para el primo $p$. Hay por tanto números complejos, incluso reales, de grado cualquiera sobre $\mathbb Q$.

* Si $\mathbb C\subset K$ es una extensión, los únicos elementos algebraicos son los de $\mathbb C$ ya que los únicos polinomios irreducibles en $\mathbb C[x]$ son los de grado $1$, así que todo elemento algebraico tiene grado $1$. Deducimos por tanto que la única extensión finita de $\mathbb C$ es la trivial.
{{% /example %}}


Veamos que los homomorfismos de extensiones de $F$ preservan raíces de polinomios con coeficientes en $F$.

{{% proposition %}}
Dadas dos extensiones $F\subset K$ y $F\subset L$ del mismo cuerpo $F$ y un homomorfismo de extensiones $f\colon K\rightarrow L$, si $\alpha\in K$ es raíz de un polinomio $p(x)\in F[x]$ entonces $f(\alpha)\in L$ también es raíz de $p(x)$. 
{{% /proposition %}}


{{% proof %}}
Como $f\colon K\rightarrow L$ es un homomorfismo de extensiones, $f$ deja fijo a $F$. Si $p(x)=a\_nx^n+\cdots+a\_1x+a\_0$ con $a\_i\in F$ y $\alpha\in K$ es una raíz entonces $$a\_n\alpha^n+\cdots+a\_1\alpha+a\_0=0,$$ por tanto $$\begin{array}{rcl} 0&=&f(0)\cr &=&f(a\_n\alpha^n+\cdots+a\_1\alpha+a\_0)\cr &=&f(a\_n)f(\alpha)^n+\cdots+f(a\_1)f(\alpha)+f(a\_0)\cr &=&a\_nf(\alpha)^n+\cdots+a\_1f(\alpha)+a\_0, \end{array}$$ así que $f(\alpha)\in L$ también es raíz de $p(x)$.
{{% /proof %}}


{{% example name="Extensiones no isomorfas del mismo grado" %}}
Las extensiones $\mathbb Q[i]$ y $\mathbb Q[\sqrt{2}]$ de $\mathbb Q$ tienen grado $2$ pero no son isomorfas porque el polinomio $x^2+1\in\mathbb Q[x]$ tiene raíces en $\mathbb Q[i]$ pero no en $\mathbb Q[\sqrt{2}]\subset\mathbb R$. 
{{% /example %}}


{{% proposition %}}
Dada una extensión $F\subset K$, $\alpha\in K$ es trascendente si y solo si hay un isomorfismo $F[x]\cong F[\alpha]$ que deja fijo a $F$. 
{{% /proposition %}}

{{% proof %}}
En virtud del teorema anterior, el elemento $\alpha$ es trascendente si y solo si el homomorfismo $f\colon F[x]\rightarrow K$, $f(p(x))=p(\alpha)$, tiene núcleo trivial. Por el primer teorema de isomorfía, esto equivale a que $f$ induzca un isomorfismo 
$$F[x]\cong \frac{F[x]}{(0)}\cong\operatorname{im} f=F[\alpha]$$
definido por la misma fórmula $p(x)\mapsto p(\alpha)$. Este isomorfismo obviamente deja fijo a $F$.
{{% /proof %}}


{{% corollary %}}
 Dada una extensión $F\subset K$ y $\alpha\in K$ tal que $F[\alpha]$ tiene dimensión finita como $F$-espacio vectorial, $\alpha$ es algebraico. 
{{% /corollary %}}


{{% proof %}}
 No puede ser trascendente porque el anillo de polinomios $F[x]$ no tiene dimensión finita sobre $F$.  
{{% /proof %}}


{{% corollary %}}
 Si $F\subset K$ es una extensión finita, todo $\alpha\in K$ es algebraico. 
{{% /corollary %}}


{{% proof %}}
 Es consecuencia de que $F[\alpha]\subset K$ es un sub-$F$-espacio vectorial.  
{{% /proof %}}



{{% proposition %}}
 Dadas dos extensiones consecutivas $F\subset K\subset L$, si $F\subset L$ es finita entonces también lo son $F\subset K$ y $K\subset L$. 
{{% /proposition %}}


{{% proof %}}
 Como $K$ es un sub-$F$-espacio vectorial de $L$, si $F\subset L$ es finita entonces $F\subset K$ también. Es más, como $F\subset K$, cualquier conjunto de generadores de $L$ como $F$-espacio vectorial también lo genera como $K$-espacio vectorial, así que $K\subset L$ también es finita.  
{{% /proof %}}



{{% proposition %}}
 Dadas dos extensiones finitas consecutivas $F\subset K\subset L$, $F\subset L$ es finita de grado $$[L:F]=[L:K][K:F].$$ 
{{% /proposition %}}


{{% proof %}}
 Dada una base $\\{x\_1,\dots, x\_p\\}\subset K$ como $F$-espacio vectorial y una base $\\{y\_1,\dots, y\_q\\}\subset L$ como $K$-espacio vectorial, afirmamos que $$\\{x\_iy\_j\\}_{\substack{1\leq i\leq p\cr 1\leq j\leq q}}\subset L$$ es una base como $F$-espacio vectorial. Hemos de ver que todo elemento de $L$ se puede expresar de manera única como combinación lineal de este conjunto con coeficientes en $F$. La base de $L$ como $K$-espacio vectorial nos garantiza que todo $\alpha\in L$ se puede escribir de manera única como $$\alpha=\beta\_1y\_1+\cdots+\beta\_qy\_q,$$ con $\beta\_j\in K$. La base de $K$ como $F$-espacio vectorial nos asegura que cada uno de estos coeficientes se puede expresar de manera única como $$\beta\_j=\gamma\_{1j}x\_1+\cdots+\gamma\_{pj}x\_p$$ con $\gamma\_{ij}\in F$. Por tanto $$\alpha=\sum\_{i=1}^p\sum\_{j=1}^q\gamma\_{ij}x\_iy\_j$$ y esta expresión es única.  
{{% /proof %}}


{{% remark %}}
En las condiciones del enunciado anterior, decimos que $K$ es una **extensión intermedia** de $F\subset L$.
{{% /remark %}}

{{% example name="$\mathbb Q[\sqrt[3]{2},i]$" %}}
Consideremos la extensión $\mathbb Q\subset\mathbb Q[\sqrt[3]{2},i]$. Tenemos que $$\mathbb Q\subset\mathbb Q[\sqrt[3]{2}]\subset\mathbb Q[\sqrt[3]{2},i].$$ Ya hemos visto que la extensión $\mathbb Q\subset\mathbb Q[\sqrt[3]{2}]$  tiene grado $3$. Además, como $\mathbb Q[\sqrt[3]{2}]\subset\mathbb R$, la extensión $\mathbb Q[\sqrt[3]{2}]\subset\mathbb Q[\sqrt[3]{2},i]$ tiene grado $2$. Por tanto $$\begin{array}{rcl}[\mathbb Q[\sqrt[3]{2},i]:\mathbb Q]&=&[\mathbb Q[\sqrt[3]{2},i]:\mathbb Q[\sqrt[3]{2}]][\mathbb Q[\sqrt[3]{2}]:\mathbb Q]\cr &=&2\cdot 3=6.\end{array}$$
{{% /remark %}}



{{% corollary %}}
 Dadas extensiones $F\subset K\subset L$: 

* $[K:F]=[L:F]\Rightarrow K=L$.

* $[L:F]=[L:K]\Rightarrow F=K$.


{{% /corollary %}}


{{% proof %}}
 Usando la fórmula para el grado de extensiones consecutivas vemos que en el primero caso $[L:K]=1$ y en el segundo $[K:F]=1$, así que basta usar que la única extensión de grado $1$ es la trivial.
{{% /proof %}}



{{% corollary %}}
 Si $F\subset K$ es una extensión de grado $[K:F]=p$ primo entonces no posee extensiones intermedias. 
{{% /corollary %}}


{{% proof %}}
 Dada una posible extensión intermedia $F\subset L\subset K$, tenemos que $p=[K:F]=[K:L][L:F]$. Por ser $p$ primo esto implica que bien $[K:F]=[K:L]$ o bien $[K:F]=[L:F]$, es decir $F=L$ o $K=L$.  
{{% /proof %}}


{{% corollary %}}
 Dada una extensión finita $F\subset K$, el grado de cualquier $\alpha\in K$ divide a $[K:F]$. 
{{% /corollary %}}


{{% proof %}}
 Basta observar que tenemos extensiones sucesivas $F\subset F[\alpha]\subset K$ y por tanto $[K:F]=[K:F[\alpha]][F[\alpha]:F]$.  
{{% /proof %}}


{{% corollary %}}
 Dada una extensión finita $F\subset K$, existe una cantidad finita de elementos $\alpha\_1,\dots,\alpha\_n\in K$ tales que $K=F[\alpha\_1,\dots,\alpha\_n]$, que denominamos **generadores** de $K$ sobre $F$. 
{{% /corollary %}}


{{% proof %}}
 Por inducción en el grado. Si $[K:F]=1$ no hay nada que demostrar pues $K=F$. Sea $n>1$ y supongamos que $[K:F]=n$ y que el resultado es cierto para extensiones de grado ${<}n$. Entonces, como la inclusión $F\subsetneq K$ es estricta ha de existir $\alpha\in K$ tal que $\alpha\_1\notin F$. Por tanto $F\subsetneq F[\alpha\_1]\subset K$. Esto implica que $[F[\alpha\_1]:F]>1$ así que $$\begin{array}{rcl}n&=&[K:F]\cr &=&[K:F[\alpha\_1]][F[\alpha\_1]:F]\cr &>&[K:F[\alpha\_1]].\end{array}$$ Entonces, por hipótesis de inducción, han de existir $\alpha\_2,\dots,\alpha\_n\in K$ tales que $$\begin{array}{rcl}K&=&F[\alpha\_1][\alpha\_2,\dots,\alpha\_n]\cr &=&F[\alpha\_1,\dots,\alpha\_n].\end{array}$$   
{{% /proof %}}





## Construcciones con regla y compás

{{% definition %}}
 Un punto, recta o circunferencia del plano $\mathbb R^2$ se considera **construido** en los siguientes casos:

* Los puntos $(0,0)$ y $(1,0)$.

![constructible-11](../../images/constructible-11.png)

* Las rectas que pasan por dos puntos construidos.

![constructible-12](../../images/constructible-12.png)

* Las circunferencias de centro un punto construido que pasan por otro punto construido, ya esté este punto dentro o fuera de la recta.

![constructible-13](../../images/constructible-13.png)

* El punto de intersección de dos rectas construidas.

![constructible-14](../../images/constructible-14.png)

* Los puntos de intersección de dos circunferencias construidas.

![constructible-16](../../images/constructible-16.png)

* Los puntos de intersección de una recta y una circunferencia construidas.

![constructible-15](../../images/constructible-15.png)

Un número real $a\in\mathbb R$ es **constructible** si su valor absoluto $|a|$ es la distancia entre dos puntos constructibles.

{{% /definition %}}


Deducimos que además podemos construir:

* El punto medio entre dos puntos construidos.

![constructible-17](../../images/constructible-17.png)

* La recta perpendicular a una recta construida que pasa por un punto consruido.

![constructible-0](../../images/constructible-0.png)

![constructible-18](../../images/constructible-18.png)

* La recta paralela a una recta construida que pasa por un punto consruido.

![constructible-1](../../images/constructible-1.png)

* Los puntos que están a una distancia constructible de un punto construido dentro de una recta construida. Intuitivamente esta propiedad nos dice que podemos transportar distancias constructibles.

![constructible-2](../../images/constructible-2.png)


{{% proposition %}}
 Un punto $(a,b)\in\mathbb R^2$ es constructible si y solo si sus coordenadas $a,b\in\mathbb R$ son números constructibles. 
{{% /proposition %}}


{{% proof %}}
 $\Rightarrow$ Trazando paralelas y perpendiculares por puntos constructibles, podemos construir los ejes de coordenadas y las proyecciones de $(a,b)$ sobre los mismos. La distancia de las proyecciones al origen son $|a|$ y $|b|$, así que las coordenadas son constructibles. ![constructible-3](../../images/constructible-3.png) 

$\Leftarrow$ Recíprocamente, asi $a$ y $b$ son constructibles podemos construir los puntos sobre los ejes de coordenadas que están a distancia $|a|$ y $|b|$ del origen y obtener $(a,b)$ como el punto de intersección de las paralelas a los ejes que pasan por estos puntos.
{{% /proof %}}


{{% proposition %}}
 El subconjunto de $\mathbb R$ formado por los números constructibles es un cuerpo. 
{{% /proposition %}}


{{% proof %}}

El $0$ y el $1$ son constructibles ya que el $(0,0)$ y el $(1,0)$ están construidos.

Dados $a\geq b\geq 0$ constructibles, podemos construir $a+b$ y $a-b$ tomando a partir del origen puntos del eje horizonal a distancias $a$ y $b$,
![constructible-4](../../images/constructible-4.png)
![constructible-5](../../images/constructible-5.png)
Por tanto también son constructibles $-a-b$ y $-a+b$. Esto demuestra que la suma de dos números constructibles cualesquiera y el opuesto de uno dado son constructibles.

Para construir el producto de dos números constructibles $a,b> 0$ usamos triángulos semejantes. Construimos primero el triángulo ractángulo con base en el eje horizontal, de longitud 1, vértice en el origen y altura $a$. El triángulo semejante de base $b$ tiene altura $ab$.
![constructible-6](../../images/constructible-6.png)
Esto demuestra que también son constructibles $(-a)b$, $a(-b)$ y $(-a)(-b)$, es decir, el producto de dos números constructibles cualesquiera (multiplicar por $0$ da $0$, que es constructible). Con esto hemos visto que los números constructibles forman un subanillo de $\mathbb R$.

La construcción del inverso de un número constructible $a> 0$ se lleva a cabo del mismo modo
![constructible-7](../../images/constructible-7.png)
Por tanto $(-a)^{-1}=-a^{-1}$ también es constructible. Esto demuestra que el anillo de los números constructibles es un cuerpo.
 {{% /proof %}}



{{% watch %}}
 El cuerpo de los números constructibles contiene a $\mathbb Q$ ya que está contenido en $\mathbb R$ y cualquier racional se puede obtener a partir del $1$ sumando, tomando opuestos y dividiendo por números no nulos. Esto se aplica también a cualquier cuerpo contenido en $\mathbb C$ pero obviamente no es válido para los cuerpos finitos $\mathbb Z/(p)$. 
{{% /watch %}}


{{% proposition %}}
 Si $a\in\mathbb R$ es positivo $a>0$ y constructible entonces $\sqrt{a}$ también es constructible. 
{{% /proposition %}}


{{% proof %}}

Es consecuencia del conocido teorema de la media geométrica. En el eje horizontal tomamos el punto a la izquierda del origen a distancia $a$. Trazamos una circunferencia que pase por él y que tenga centro en el punto medio entre este punto y el $(1,0)$. La distancia del origen al punto de corte con la circunferencia de la perpendicular al eje horizontal es $\sqrt{a}$.
![constructible-8](../../images/constructible-8.png)
 {{% /proof %}}


Hasta ahora hemos demostrado que podemos construir números constructibles a partir del $1$ sumando, restando, dividiendo por números no nulos, y tomando raíces cuadradas de números positivos. Los siguientes resultados demuestras que no hay más números constructibles que los que se pueden obtener de este modo.

{{% proposition %}}
 Dados cuatro puntos en $\mathbb R^2$ cuyas coordenadas están en un subcuerpo $F\subset\mathbb R$, los puntos de intersección de las rectas y circunferencias que se pueden dibujar apoyándose en dichos puntos tienen coordenadas en $F$ o en $F[\sqrt{r}]$ para cierto $r\in F$ positivo $r>0$ que no sea el cuadrado de ningún número de $F$. 
{{% /proposition %}}


{{% proof %}}
 Dados dos puntos $(a\_0,b\_0), (a\_1,b\_1)\in\mathbb R^2$, la recta que pasa por ambos tiene ecuación 
$$(a\_1-a\_0)(y-b\_0)=(b\_1-b\_0)(x-a\_0),$$
y la circunferencia de centro el primero que pasa por el segundo está definida por
$$(x-a\_0)^2+(y-b\_0)^2=(a\_1-a\_0)^2+(b\_1-b\_0)^2.$$ 
Si las coordenadas está en $F$ entonces los coeficientes de ambas ecuaciones también.

La intersección de dos de estas rectas tiene coordenadas en $F$ porque las soluciones de un sistema de ecuaciones lineales con coeficientes en un cuerpo siempre están en dicho cuerpo.

Para hallar la intersección de una recta y una circunferencia, despejamos una incógnita de la ecuación de la recta y la sustituimos en la ecuación de la circunferencia. Esto nos da una ecuación de grado $2$ con coeficientes en $F$. Para que esta ecuación tenga solución su discriminante ha de ser $D\geq 0$. En ese caso la solución está en $F[\sqrt{D}]$. Por tanto las coordenadas del punto de intersección están en este cuerpo. Si $D$ es el cuadrado de un número de $F$ entonces $F[\sqrt{D}]=F$.

Para intersecar dos circunferencias, observamos que la diferencia de ambas ecuaciones es de grado $1$, por tanto este caso se reduce al anterior.

 
{{% /proof %}}


{{% watch %}}
 Recuerda que antes hemos visto que $[F[\sqrt{r}]:F]=2$. 
{{% /watch %}}


{{% theorem %}}
Dados números reales constructibles $a\_1,\dots,a\_m\in\mathbb R$, hay una cadena de extensiones $$\mathbb Q=F\_0\subset F\_1\subset F\_2\subset\cdots\subset F\_n=K$$ tales que

* $K\subset\mathbb R$ es un subcuerpo,

* $a\_1,\dots,a\_m\in K$,

* Cada $F\_{i+1}=F\_i[\sqrt{r\_i}]$, $0\leq i{<}n$, donde $r\_i\in F\_i$ es un número positivo $r\_i>0$ que no es un cuadrado en $F\_i$.

En particular $[K:\mathbb Q]=2^n$.


{{% /theorem %}}


{{% proof %}}
 La construtibilidad de los números $a\_i$ equivale a la de los puntos $(a\_i,0)$. Los puntos constructibles se construyen a partir de los básicos, $(0,0)$ y $(1,0)$, trazando e intersecando rectas y circunferencias mendiante los métodos permitidos. Los puntos básicos tienen coordenadas en $\mathbb Q$. Por la propisición anterior, los puntos que se construyen a partir de ellos tendrán coordenadas en extensiones sucesivas de $\mathbb Q$ obtenidas al añadir nuevas raíces cuadradas de números positivos, por tanto el teorema se sigue de la proposición anterior por inducción. La observación sobre el grado se siguie de la fórmula del grado para extensiones intermedias, que en este caso nos dice que $$[K:\mathbb Q]=\prod\_{i=0}^{n-1}[F\_{i+1}:F\_i]=2^n$$ ya que por el tercer apartado $[F\_{i+1}:F\_i]=2$.
{{% /proof %}}


{{% watch %}}
 La cantidad de raíces cuadradas que hemos de añadir a $\mathbb Q$ para construir $K$ ($n$ según la notación del teorema) no tiene relación con la cantidad de números constructibles $a\_1,\dots,a\_m$ que queremos que $K$ posea. 
{{% /watch %}}


{{% corollary %}}
 Los números constructibles son algebraicos sobre $\mathbb Q$ y el grado de un número constructible es siempre una potencia de $2$. 
{{% /corollary %}}


{{% proof %}}
 Por el teroema anterior, si $a\in \mathbb R$ es constructible entonces $a\in K$ para cierta extensión finita $\mathbb Q\subset\mathbb K$ de grado $2^n$. En particular $a$ es algebraico sobre $\mathbb Q$ y su grado divide a $2^n$, así que ha de ser una potencia de $2$.
{{% /proof %}}


{{% example name="Números constructibles de grado $2^m$ cualquiera" %}}
 Si $p\in\mathbb Z$ es un primo positivo, $\sqrt[n]{p}$ es constructible si y solo si $n$ es una potencia de $2$. Sabemos que este número tiene grado $n$ sobre $\mathbb Q$, así que solo puede ser constructible si $n=2^m$. Además en este caso podemos ver por inducción en $m$ que de hecho es constructible. Para $m=0$ es obvio porque es entero y si $\sqrt[2^{m-1}]{p}$ es constructible entonces $$\sqrt[2^m]{p}=\sqrt{\sqrt[2^{m-1}]{p}}$$ también, por ser la raíz cuadrada de un número constructible. 
{{% /example %}}


{{% definition %}}
 Un ángulo $\theta\in[0,2\pi)$ es **constructible** si el número $\cos \theta\in\mathbb R$ es constructible. 
{{% /definition %}}


Por la construcción geométrica de senos y cosenos, está claro que la definición anterior es equivalente a decir que $\sin \theta$ es constructible, o que la recta que pasa por el origen y hace ángulo $\theta$ con el eje horizontal es constructible, o más generalmente que podemos construir la recta que pasa por un punto constructible y que hace ángulo $\theta$ con otra recta constructible que pasa por él.

![constructible-9](../../images/constructible-9.png)

Veamos que en general es imposible trisecar un ángulo cualquiera con regla y compás.

{{% proposition %}}
 El ángulo de $60º$ es constructible pero su trisección no. 
{{% /proposition %}}


{{% proof %}}
 Este ángulo se puede construir porque $\cos  60º=\frac{1}{2}$ es constructible. Cada ángulo de su trisección tendría $20º$ y el ángulo de $20º$ no es constructible. En efecto, la siguiente fórmula trigonométrica es cierta en general $$\cos 3\theta=4\cos^3\theta-3\cos\theta.$$ Tomando $\theta= 20º$ deducimos que $\alpha=\cos 20º$ es una raíz del polinomio $8x^3-6x-1$. Vamos a ver que este polinomio es irreducible sobre $\mathbb Q$, por tanto $\alpha$ tendrá grado $3$ sobre $\mathbb Q$, así que no podrá ser constructible. El polinomio $8x^3-6x-1$ es primitivo, por tanto es irreducible sobre $\mathbb Q$ si y solo si lo es sobre $\mathbb Z$. Sobre $\mathbb Z$ es irreducible por el criterio de reducción módulo $5$, ya que $3x^3-x-1\in\mathbb Z/(5)[x]$ tiene grado $\leq 3$ pero no tiene raíces.
{{% /proof %}}


{{% proposition %}}
 Un polígono regular de $p$ lados, $p\in\mathbb Z$ primo, puede construirse con regla y compás si y solo si $p=2^n+1$. 
{{% /proposition %}}


{{% proof %}}
 Esto equivale a la constructibilidad del ángulo de $\frac{2\pi}{p}$ radianes. 

$\Leftarrow$  Es un resultado de Gauss que no probaremos.

$\Rightarrow$ El número complejo $z=\cos\frac{2\pi}{p}+i\sin \frac{2\pi}{p}$ es una raíz $p$-ésima de la unidad, es decir, una raíz del polinomio $x^p-1$. Este polinonimio factoriza como $$(x-1)(x^{p-1}+\cdots+x+1)$$ y como $z\neq 1$, $z$ es raíz del segundo, que se denomina $p$-ésimo **polinomio ciclotómico** $$p(x)=x^{p-1}+\cdots+x+1.$$ Veamos que este polinomio es irreducible sobre $\mathbb Q$. Para ello hacemos el cambio de variable $x=y+1$, que se corresponde con el isomorfismo $$f\colon \mathbb Q[x]\longrightarrow \mathbb Q[y]$$ definido $f(p(x))=p(y+1)$, cuyo inverso viene dado por $f^{-1}(q(y))=q(x-1)$. Bastará por tanto comprobar que $p(y+1)$ es irreducible. Como $x^p-1=(x-1)p(x)$ entonces 
$$\begin{array}{rcl}
yp(y+1)&=&(y+1)^p-1\cr
&=& \sum\_{n=1}^{p}\binom{p}{n}y^n.
\end{array}$$
Aplicando la propiedad cancelativa en el dominio $\mathbb Q[y]$ obtenemos que
$$\begin{array}{rcl}
p(y+1)&=&\sum\_{n=1}^{p}\binom{p}{n}y^{n-1}.
\end{array}$$
Este polinomio es irreducible por el criterio de Eisenstein para el primo $p$ ya que el coeficiente líder es $1$, el término independiente es $p$, y $p$ divide a $\binom{p}{n}$ para todo $0{<}n{<}p$. 

Por ser el polinomio ciclotómico irreducible y tener a $z$ como raíz, deducimos que $z$ tiene grado $p-1$ sobre $\mathbb Q$. Si $\theta$ fuera constructible, tendríamos un cuerpo $K\subset\mathbb R$ tal que $\cos\frac{2\pi}{p}, \sin\frac{2\pi}{p}\in K$ y $[K:\mathbb Q]=2^n$. Como $K$ está contenido en los reales, $[K[i]:K]=2$, luego $[K[i]:\mathbb Q]=[K[i]:K][K:\mathbb Q]=2^{n+1}$. Además, $z\in K[i]$ luego el grado de $z$, que es $p-1$, ha de ser una potencia de $2$.
{{% /proof %}}


{{% example name="Primos de Fermat" %}}
  Los enteros primos $p\in\mathbb Z$ tales que el polígono regular de $p$ lados se puede construir con regla y compás, es decir los que son de la forma $p=2^n+1$, se denominan **primos de Fermat**. Solo se conocen los siguientes: 3, 5, 17, 257 y 65537. No se sabe siquiera si hay una cantidad finita o infinita de primos de Fermat. Este problema fue planteado por Eisenstein en 1844 y permanece abierto. 

La siguiente imagen, obtenida de [Wikipedia](https://en.wikipedia.org/wiki/Constructible_polygon), muestra la construcción paso a paso de un polígono regular de 17 lados con regla y compás. En el artículo de Wikipedia enlazado se puede encontrar otra construccón de este polígono regular, así como una construcción completa del de 257 lados y el comienzo de la construcción del de 65537 lados. 

![17-lados](../../images/HeptadecagonConstructionAni.gif)


{{% /example %}}










