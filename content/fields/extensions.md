+++
title = "Extensiones"
weight = 10
+++

## Extensiones de cuerpos

{{% definition %}}
Una **extensión (de cuerpos)**

$$F\subset K$$

es un par formado por un cuerpo $K$ y un subanillo $F$ que también es un cuerpo. Decimos en este caso que $K$ es una extensión de $F$. Observa que $K$ es un $F$-espacio vectorial con la suma y el producto por escalares de $F$. La extensión es **finita** si $\dim\_FK<\infty$, en dicho caso definimos el **grado** de la extensión como

$$[K:F]=\dim\_FK.$$

{{% /definition %}}

{{% remark %}}
El grado de una extensión $F\subset K$ es $[K:F]\geq 1$. No hay extensiones de grado $0$ ya que todo cuerpo $K\neq \{0\}$.
{{% /remark %}}



{{% example name="Ejemplos de extensiones" %}}

* $\mathbb R\subset\mathbb C$ es finita de grado $[\mathbb{C},\mathbb{R}]=2$, ya que $\\{1,i\\}\subset\mathbb C$ es una base como $\mathbb R$-espacio vectorial. 

* $\mathbb Q\subset\mathbb R$ no es finita porque cualquier $\mathbb Q$-espacio vectorial de dimensión finita es numerable, pero $\mathbb R$ no lo es.

* Todo cuerpo $F$ posee la **extensión trivial** $F\subset F$, que es la única de grado $1$, el resto tienen grado $>1$. En efecto, $\dim\_FF=1$ así que, como $F\subset K$, $[K:F]=\dim\_FK\geq 1$ dándose la igualdad si y solo si $F=K$.

* $F\subset F(x)$ tampoco es finita.

* $F\subset F[ x ]/(p(x))$, donde $p(x)\in F[ x ]$ es un polinomio irreducible. En efecto, por ser $F[ x ]$ un DFU tenemos que $p(x)\in F[ x ]$ es primo, y por ser $F[ x ]$ un dominio de ideales  principales tenemos que el ideal primo $(p(x))\subset F[ x ]$, al ser no trivial, es maximal, por tanto $F[ x ]/(p(x))$ es un cuerpo. Sabemos además que 

$$[F[ x ]/(p(x)):F]=\text{grado }p(x).$$

{{% /example %}}


{{% definition %}}
Dadas dos extensiones $F\subset K$ y $F\subset L$ de un mismo cuerpo $F$, un **homomorfismo** de extensiones $f\colon K\rightarrow L$ es un homomorfismo de anillos que deja fijo a $F$, es decir, que satisface $f(\alpha)=\alpha$ para todo $\alpha\in F$. Un **endomorfismo** de una extensión $F\subset K$ un homomorfismo de extensiones $f\colon K\rightarrow K$. Un **isomorfismo** de extensiones es un homomorfismo biyectivo. Un **automorfismo** de una extensión $F\subset K$ es un endomorfismo biyectivo. 
{{% /definition %}}

La conjugación $\mathbb{C}\rightarrow \mathbb{C}$, $z\mapsto\bar{z}$, es un homomorfismo de extensiones de $\mathbb{R}$ ya que $x=\bar{x}$ para todo $x\in\mathbb{R}$.

{{% remark %}}
La identidad es un homomorfismo de extensiones y la composición de homomorfismos de extensiones es también un homomorfismo de extensiones. Lo mismo ocurre con isomorfismos y automorfismos. Además, la aplicación inversa de un isomorfismo de extensiones es otro isomorfismo de extensiones, e igual para los automorfismos. Los homomorfismos de cuerpos son inyectivos, así que los homomorfismos de extensiones también. 
{{% /remark %}}

{{% proposition %}}
Un homomorfismo $f\colon K\rightarrow L$ de extensiones de $F$ es también un homomorfismo de $F$-espacios vectoriales.
{{% /proposition %}}

{{% proof %}}
Como $f$ es un homomorfismo de anillos, preserva sumas. Dado $\alpha\in F\subset K$ y $x\in K$, por ser $f$ un homomorfismo de anillos, $f(\alpha x)=f(\alpha)f(x)$. Como $f$ es un homomorfismo de extensiones de $F$, $f(\alpha)=\alpha$. Por tanto $f(\alpha x)=\alpha f(x)$, es decir, $f$ preserva el producto por escalares de $F$.
{{% /proof %}}

{{% corollary %}}
Si $f\colon K\rightarrow L$ es un isomorfismo de extensiones de $F$ entonces $[K:F] = [L:F]$.
{{% /corollary %}}

Más adelante veremos ejemplos de extensiones no isomorfas del mismo grado.

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
Por ser $f$ un homomorfismo de anillos, $f(0)=0$. Es más, como $f(1)=1$ y $f$ preserva sumas, es fácil ver que $f(n)=n$ para cualquier $n\in\mathbb Z$, $n>0$. Además $f$ preserva opuestos, luego $f(-n)=-f(n)=-n$. Esto prueba que $f$ deja fijo a $\mathbb Z$. Todo racional se puede expresar como $\frac{p}{q}=pq^{-1}$ para $p,q\in\mathbb Z$, $q\neq 0$. Los homomorfismos de anillos preservan productos e inversos, así que

$$\begin{array}{rcl}f\left(\frac{p}{q}\right)&=&f(pq^{-1})\cr &=&f(p)f(q^{-1})\cr &=&f(p)f(q)^{-1}\cr &=&pq^{-1}\cr &=&\frac{p}{q}.\end{array}$$

 
{{% /proof %}}

{{% corollary %}}
Dada una extension finita $\mathbb{Q}\subset K$, todo homomorfismo de anillos $f\colon K\rightarrow K$ es un automorfismo de la extensión $\mathbb{Q}\subset K$.
{{% /corollary %}}


{{% definition %}}
Dada una extensión $F\subset K$, decimos que $\alpha\in K$ es **algebraico** si existe $p(x)\in F[ x ]$ no nulo tal que $p(\alpha)=0$. En caso contrario decimos que $\alpha$ es **trascendente**. 
{{% /definition %}}

{{% remark %}}
Si tenemos dos extensiones sucesivas $F\subset K\subset L$ y $\alpha\in L$ es algebraico sobre $F$ entonces también es algebraico sobre $K$ ya que $F[ x ]\subset K[ x ]$. ¡Ojo! El recíproco no es cierto. Todo $\alpha\in F$ es algebraico sobre $F$ ya que es raíz de $x-\alpha\in F[ x ]$.
{{% /remark %}}

El elemento $\sqrt{2}\in\mathbb{R}$ es algebraico sobre $\mathbb{Q}$, aunque $\sqrt{2}\notin\mathbb{Q}$. Análogamente $i\in\mathbb{C}$ es algebraico sobre $\mathbb{R}$ ya que es raíz de $x^2+1\in\mathbb{R}[ x ]$, y también sobre $\mathbb{Q}$.


{{% example name="Existencia de elementos trascendentes en $\mathbb Q\subset\mathbb C$" %}}
Como $\mathbb Q$ es numerable, $\mathbb Q[ x ]$ también. Además, todo polinomio tiene una cantidad finita de soluciones en $\mathbb C$. Por tanto hay una cantidad numerable de elementos algebraicos para la extensión $\mathbb Q\subset\mathbb C$. Como $\mathbb C$ no es numerable, han de existir elementos trascendentes, de hecho una cantidad no numerable de ellos. Lo mismo se aplica a la extensión $\mathbb Q\subset\mathbb R$. Dar un ejemplo concreto de número trascendente es sin embargo bastante complicado. Es conocido que $\pi$ es trascendente sobre $\mathbb Q$ pero no es fácil probarlo. 
{{% /example %}}

{{% definition %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$, su **polinomio irreducible** $p(x)\in F[ x ]$ es el único polinomio mónico irreducible con coeficientes en $F$ que tiene a $\alpha$ como raíz. El **grado** de $\alpha$ sobre $F$ es el de su polinomio irreducible.
{{% /definition %}}

{{% remark %}}
La existencia del polinomio irreducible de un elemento algebraico no es obvia y la veremos como consecuencia del siguiente teorema. También es posible probarla usando que $F[ x ]$ es un DFU. La condición de ser mónico es solo para garantizar su unicidad. Si encontramos un polinomio irreducible en $F[ x ]$ que tiene a $\alpha$ como raíz, basta dividirlo por su coeficiente líder para convertirlo en mónico.
{{% /remark %}}

{{% theorem %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$, el polinomio irreducible de $\alpha$ es el generador mónico del núcleo del homomorfismo $f\colon F[ x ]\rightarrow K$, $f(p(x))=p(\alpha)$. Es más, $F[\alpha]$ es un cuerpo y $f$ induce un isomorfismo de extensiones de $F$,

$$\frac{F[ x ]}{(p(x))}\cong F[\alpha].$$

En particular, 

$$[F[\alpha]:F]=\text{grado }\alpha.$$

{{% /theorem %}}

{{% proof %}}
El homomorfismo $f$ está bien definido por el principio de sustitución, ya que es el único tal que $f_{|_F}\colon F\hookrightarrow K$ es la inclusión y $f(x)=\alpha$.

Ser $\alpha$ algebraico equivale a $\ker f\neq (0)$, pues los elementos de $\ker f$ son los polinomios en $F[ x ]$ que tienen a $\alpha$ como raíz. En particular, $\ker f\subsetneq F[ x ]$ ya que los polinomios constantes no nulos no tienen raíces. 

Supongamos que $\alpha$ tiene polinomio irreducible $p(x)$. Entonces $p(x)\in\ker f$, así que $(p(x))\subset\ker f$. Como $F[ x ]$ es un DIP, $(p(x))$ es maximal por ser $p(x)$ irreducible, así que $(p(x))=\ker f$. 

Recíprocamente, supongamos que $\ker f=(p(x))$ (este ideal es principal porque $F[ x ]$ es un DIP). Por el primer teorema de isomorfía, $f$ induce un isomorfismo

$$\overline{f}\colon\frac{F[ x ]}{(p(x))}\stackrel{\cong}\longrightarrow F[\alpha].$$

Como $F[\alpha]\subset K$ es un dominio, el ideal $(p(x))\subset F[ x ]$ es primo. Como $F[ x ]$ es un DFU, esto equivale a decir que $p(x)$ es irreducible. Podemos además suponer que es mónico, dividiendo por su coeficiente líder si fuera necesario. En estas condiciones hemos visto arriba que el cociente es un cuerpo, más concretamente una extensión de $F$ del mismo grado que $p(x)$. Esto implica que el anillo $F[\alpha]$ es también un cuerpo, por ser isomorfo al cociente. Es más, según vimos en el tema de factorización, el isomorfismo $\overline{f}$ se comporta sobre $F$ como la identidad, por tanto es un isomorfismo de extensiones, así que el grado de $F[\alpha]$ sobre $F$ es también el de $p(x)$.
{{% /proof %}}

El siguiente corolario se basa en el hecho de que $F[ x ]$ es un dominio euclídeo. Su importancia estriba en que da un método para calcular el polinomio irreducible de un elemento algebraico sin necesidad de  comprobar la irreducibilidad por otros métodos.

{{% corollary %}}
Dada una extensión $F\subset K$, el polinomio irreducible de un elemento algebraico $\alpha\in K$ es el polinomio mónico no nulo de menor grado en $F[ x ]$ que tiene a $\alpha$ como raíz.
{{% /corollary %}}

{{% corollary %}}
Dada una extensión $F\subset K$ y un elemento algebraico $\alpha\in K$ de grado $n$, $\\{1,\alpha,\dots,\alpha^{n-1}\\}\subset F[\alpha]$ es una base como $F$-espacio vectorial. 
{{% /corollary %}}

{{% proof %}}
El isomorfismo de extensiones del teorema anterior es también un isomorfismo de $F$-espacios vectoriales. Sabemos que $\\{1,\bar{x},\dots,\bar{x}^{n-1}\\}$ es una base de $F[ x ]/(p(x))$, donde $p(x)$ es el polinomio irreducible de $\alpha$, así que su imagen, $\\{1,\alpha,\dots,\alpha^{n-1}\\}$, es una base de $F[\alpha]$.
{{% /proof %}}

{{% proposition %}}
Si $F\subset K$ es una extensión, $\alpha\in K$ y $q(x)\in F[ x ]$ es un polinomio no nulo que tiene a $\alpha$ como raíz, entonces el polinomio irreducible de $\alpha$ divide a $q(x)$, en particular el grado de $\alpha$ sobre $F$ es menor o igual que el grado de $q(x)$. 
{{% /proposition %}}

{{% proof %}}
Consideramos el homomorfismo $f\colon F[ x ]\rightarrow K$ del teorema anterior. Si $p(x)$ es el polinomio irreducible de $\alpha$, $\ker f=(p(x))$. Como $\alpha$ es una raíz de $q(x)$, $q(x)\in\ker f$, así que $q(x)$ es un multiplo no nulo de $p(x)$.
{{% /proof %}}

{{% example name="Grado de algunos elementos" %}}
Sea $F\subset K$ una extensión y $\alpha\in K$ un elemento algebraico.

* No hay elementos de grado $0$ porque los polinomios no nulos de grado $0$ no tienen raíces.

* El grado de $\alpha$ es $1$ si y solo si $\alpha\in F$. En efecto, esto equivale a decir que $\alpha$ es raíz de un polinomio mónico de grado $1$ en $F[ x ]$ (todos ellos irreducibles) que no puede ser otro que $x-\alpha$.

* El grado de $\alpha$ es $2$ si y solo si $\alpha\notin F$ pero es raíz de un polinomio de grado $2$ en $F[ x ]$.

* Dado $\alpha\in K$ tal que $\alpha\notin F$ pero $\alpha^2\in F$, el grado de $\alpha$ es $2$ y su polinomio irreducible es $x^2-\alpha^2\in F[ x ]$.

* Si $F\subset\mathbb R$, el grado de $i\in\mathbb C$ sobre $F$ es $2$ pues $i\notin F$ pero es raíz de $x^2+1\in F[ x ]$, que es su polinomio irreducible.

* Si $n\in\mathbb Z$ es libre de cuadrados, el grado de $\sqrt{n}\in\mathbb C$ sobre $\mathbb Q$ es $2$ pues $\sqrt{n}\notin\mathbb Q$ pero es raíz de $x^2-n\in\mathbb Q[ x ]$.

* Si $p\in\mathbb Z$ es primo, el grado de $\sqrt[n]{p}\in\mathbb C$ sobre $\mathbb Q$ es $n$ puesto que es raíz del polinomio irreducible $x^n-p\in\mathbb Q[ x ]$. Este polinomio es irreducible por el criterio de [Eisenstein](../../rings/factorization/#eisenstein) para el primo $p$. Hay por tanto números complejos, incluso reales, de grado cualquiera sobre $\mathbb Q$.

* Si $\mathbb C\subset K$ es una extensión, los únicos elementos algebraicos son los de $\mathbb C$ ya que los únicos polinomios irreducibles en $\mathbb C[ x ]$ son los de grado $1$.

{{% /example %}}


Veamos que los homomorfismos de extensiones de $F$ preservan raíces de polinomios con coeficientes en $F$.

{{% proposition %}}
Dadas dos extensiones $F\subset K$ y $F\subset L$ del mismo cuerpo $F$ y un homomorfismo de extensiones $f\colon K\rightarrow L$, si $\alpha\in K$ es raíz de un polinomio $p(x)\in F[ x ]$ entonces $f(\alpha)\in L$ también es raíz de $p(x)$. 
{{% /proposition %}}


{{% proof %}}
Como $f\colon K\rightarrow L$ es un homomorfismo de extensiones, $f$ deja fijo a $F$. Si $p(x)=a\_nx^n+\cdots+a\_1x+a\_0$ con $a\_i\in F$ y $\alpha\in K$ es una raíz entonces

$$a\_n\alpha^n+\cdots+a\_1\alpha+a\_0=0,$$

por tanto

$$\begin{array}{rcl} 0&=&f(0)\cr &=&f(a\_n\alpha^n+\cdots+a\_1\alpha+a\_0)\cr &=&f(a\_n)f(\alpha)^n+\cdots+f(a\_1)f(\alpha)+f(a\_0)\cr &=&a\_nf(\alpha)^n+\cdots+a\_1f(\alpha)+a\_0, \end{array}$$

así que $f(\alpha)\in L$ también es raíz de $p(x)$.
{{% /proof %}}


{{% example name="Extensiones no isomorfas del mismo grado" %}}
Las extensiones $\mathbb Q[i]$ y $\mathbb Q[\sqrt{2}]$ de $\mathbb Q$ tienen grado $2$ pero no son isomorfas porque el polinomio $x^2+1\in\mathbb Q[ x ]$ tiene raíces en $\mathbb Q[i]$ pero no en $\mathbb Q[\sqrt{2}]\subset\mathbb R$. 
{{% /example %}}


{{% proposition %}}
Dada una extensión $F\subset K$, $\alpha\in K$ es trascendente si y solo si hay un isomorfismo $F[ x ]\cong F[\alpha]$ que deja fijo a $F$. 
{{% /proposition %}}

{{% proof %}}
En virtud del teorema anterior, el elemento $\alpha$ es trascendente si y solo si el homomorfismo $f\colon F[ x ]\rightarrow K$, $f(p(x))=p(\alpha)$, tiene núcleo trivial. Por el primer teorema de isomorfía, esto equivale a que $f$ induzca un isomorfismo 

$$F[ x ]\cong \frac{F[ x ]}{(0)}\cong\operatorname{im} f=F[\alpha]$$

definido por la misma fórmula $p(x)\mapsto p(\alpha)$. Este isomorfismo obviamente deja fijo a $F$.
{{% /proof %}}


{{% corollary %}}
Dada una extensión $F\subset K$ y $\alpha\in K$ tal que $F[\alpha]$ tiene dimensión finita como $F$-espacio vectorial, $\alpha$ es algebraico. 
{{% /corollary %}}


{{% proof %}}
No puede ser trascendente porque el anillo de polinomios $F[ x ]$ no tiene dimensión finita sobre $F$.  
{{% /proof %}}


{{% corollary %}}
Si $F\subset K$ es una extensión finita, todo $\alpha\in K$ es algebraico. 
{{% /corollary %}}

{{% proof %}}
Es consecuencia de que $F[\alpha]\subset K$ es un sub-$F$-espacio vectorial.  
{{% /proof %}}

Deducimos por tanto que la única extensión finita de $\mathbb C$ es la trivial.

{{% proposition %}}
Dadas dos extensiones consecutivas $F\subset K\subset L$, si $F\subset L$ es finita entonces también lo son $F\subset K$ y $K\subset L$. 
{{% /proposition %}}


{{% proof %}}
Como $K$ es un sub-$F$-espacio vectorial de $L$, si $F\subset L$ es finita entonces $F\subset K$ también. Es más, como $F\subset K$, cualquier conjunto de generadores de $L$ como $F$-espacio vectorial también lo genera como $K$-espacio vectorial, así que $K\subset L$ también es finita.  
{{% /proof %}}



{{% proposition %}}
Dadas dos extensiones finitas consecutivas $F\subset K\subset L$, $F\subset L$ es finita de grado

$$[L:F]=[L:K][K:F].$$

{{% /proposition %}}


{{% proof %}}
Dada una base $\\{x\_1,\dots, x\_p\\}\subset K$ como $F$-espacio vectorial y una base $\\{y\_1,\dots, y\_q\\}\subset L$ como $K$-espacio vectorial, afirmamos que

$$\\{x\_iy\_j\\}_{\substack{1\leq i\leq p\cr 1\leq j\leq q}}\subset L$$

es una base como $F$-espacio vectorial. Hemos de ver que todo elemento de $L$ se puede expresar de manera única como combinación lineal de este conjunto con coeficientes en $F$. La base de $L$ como $K$-espacio vectorial nos garantiza que todo $\alpha\in L$ se puede escribir de manera única como

$$\alpha=\beta\_1y\_1+\cdots+\beta\_qy\_q,$$

con $\beta\_j\in K$. La base de $K$ como $F$-espacio vectorial nos asegura que cada uno de estos coeficientes se puede expresar de manera única como

$$\beta\_j=\gamma\_{1j}x\_1+\cdots+\gamma\_{pj}x\_p$$

con $\gamma\_{ij}\in F$. Por tanto

$$\alpha=\sum\_{i=1}^p\sum\_{j=1}^q\gamma\_{ij}x\_iy\_j$$

y esta expresión es única.  
{{% /proof %}}


{{% remark %}}
En las condiciones del enunciado anterior, decimos que $K$ es una **extensión intermedia** de $F\subset L$. Decimos que es **estricta** si ninguna de las dos inclusiones es una igualdad.
{{% /remark %}}

{{% corollary %}}
Dada una extensión $F\subset K$ y elementos algebraicos $\alpha\_1,\dots,\alpha\_n\in K$, la extensión $F\subset F[\alpha\_1,\dots,\alpha\_n]$ es finita. 
{{% /corollary %}}

{{% proof %}}
Por inducción en $n$. Para $n=1$ está probado en el teorema anterior. Supongamos que $F\subset F[\alpha\_1,\dots,\alpha\_{n-1}]=L$ es finita. Como $\alpha\_n$ es algebraico sobre $F$, también lo es sobre $L$, así que $L\subset L[\alpha\_n]=F[\alpha\_1,\dots,\alpha\_n]$ es finita. El corolario se deduce ahora de la proposición anterior.
{{% /proof %}}

{{% example name="$\mathbb Q[\sqrt[3]{2},i]$" %}}
Consideremos la extensión $\mathbb Q\subset\mathbb Q[\sqrt[3]{2},i]$. Tenemos que

$$\mathbb Q\subset\mathbb Q[\sqrt[3]{2}]\subset\mathbb Q[\sqrt[3]{2},i].$$

Ya hemos visto que la extensión $\mathbb Q\subset\mathbb Q[\sqrt[3]{2}]$  tiene grado $3$. Además, como $\mathbb Q[\sqrt[3]{2}]\subset\mathbb R$, la extensión $\mathbb Q[\sqrt[3]{2}]\subset\mathbb Q[\sqrt[3]{2},i]$ tiene grado $2$. Por tanto

$$\begin{array}{rcl}[\mathbb Q[\sqrt[3]{2},i]:\mathbb Q]&=&[\mathbb Q[\sqrt[3]{2},i]:\mathbb Q[\sqrt[3]{2}]][\mathbb Q[\sqrt[3]{2}]:\mathbb Q]\cr &=&2\cdot 3=6.\end{array}$$

{{% /example %}}

{{% corollary %}}
Dada una extensión $F\subset K$, el subconjunto $L\subset K$ formado por los elementos de $K$ que son algebraicos sobre $F$ es un subcuerpo tal que $F\subset L$.
{{% /corollary %}}

{{% proof %}}
Los elementos de $F$ son algebraicos de grado $1$ sobre $F$, así que $F\subset L$. Veamos que $L\subset K$ es un subanillo. Tenemos que $0,1\in F\subset L$. Dados $\alpha,\beta\in L$, por el corolario anterior $F\subset F[\alpha,\beta]$ es una extensión finita, así que todos sus elementos son algebraicos. Como $\alpha+\beta,\alpha\beta,-\alpha\in F[\alpha,\beta]$, deducimos que estos tres elementos son en efecto algebraicos. Esto prueba que $L\subset K$ es un subanillo. Además, si $\alpha\neq 0$ entonces $\alpha^{-1}\in F[\alpha,\beta]$, que por lo mismo será también algebraico, por tanto $L$ es un cuerpo.
{{% /proof %}}



{{% corollary %}}
Dadas extensiones $F\subset K\subset L$: 

* $[K:F]=[L:F]\Rightarrow K=L$.

* $[L:F]=[L:K]\Rightarrow F=K$.

{{% /corollary %}}


{{% proof %}}
Usando la fórmula para el grado de extensiones consecutivas vemos que en el primero caso $[L:K]=1$ y en el segundo $[K:F]=1$, así que basta usar que la única extensión de grado $1$ es la trivial.
{{% /proof %}}



{{% corollary %}}
Si $F\subset K$ es una extensión de grado $[K:F]=p$ primo entonces no posee extensiones intermedias estrictas. 
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
Por inducción en el grado. Si $[K:F]=1$ no hay nada que demostrar pues $K=F$. Supongamos que $[K:F]=m>1$ y que el resultado es cierto para extensiones de grado ${<}m$. Entonces, como la inclusión $F\subsetneq K$ es estricta ha de existir $\alpha\_1\in K$ tal que $\alpha\_1\notin F$. Por tanto $F\subsetneq F[\alpha\_1]\subset K$. Esto implica que $[F[\alpha\_1]:F]>1$ así que

$$\begin{array}{rcl}m&=&[K:F]\cr &=&[K:F[\alpha\_1]][F[\alpha\_1]:F]\cr &>&[K:F[\alpha\_1]].\end{array}$$

Entonces, por hipótesis de inducción, han de existir $\alpha\_2,\dots,\alpha\_n\in K$ tales que

$$\begin{array}{rcl}K&=&F[\alpha\_1][\alpha\_2,\dots,\alpha\_n]\cr &=&F[\alpha\_1,\dots,\alpha\_n].\end{array}$$

 
{{% /proof %}}

En la siguiente sección veremos que, para extensiones contenidas en $\mathbb{C}$ basta uno.


## Elementos primitivos

Recuerda que $\alpha\in\mathbb{C}$ es una **raíz múltiple** de $f(x)\in\mathbb{C}[ x ]$ si $(x-\alpha)^2|f$.

{{% proposition %}}
Un polinomio $f(x)\in\mathbb{C}[ x ]$ tiene una raíz múltiple $\alpha\in\mathbb{C}$ si y solo si $\alpha$ es raíz de $f$ y de su derivada $f'$.
{{% /proposition %}}

{{% proof %}}
Sabemos que $\alpha$ es raíz de $f$ si y solo si $(x-\alpha)|f$, es decir, si y solo si $f(x)=g(x)(x-a)$ para cierto $g(x)\in\mathbb{C}[ x ]$. Por tanto, $\alpha$ es una raíz múltiple de $f(x)$ si y solo si $(x-\alpha)|g$, es decir, si y solo si $\alpha$ es también una raíz de $g$. La derivada de $f$ es

$$f'(x)=g'(x)(x-\alpha)+g(x),$$

luego $f'(\alpha)=g(\alpha)$, así que $\alpha$ es una raíz de $f'$ si y solo si es raíz de $g$.
{{% /proof %}}

{{% proposition %}}
Un polinomio $f(x)\in\mathbb{C}[ x ]$ tiene alguna raíz múltiple si y solo si $f$ y $f'$ no son coprimos.
{{% /proposition %}}

{{% proof %}}
$\Rightarrow$ Si $\alpha$ es una raíz múltiple de $f$, hemos visto antes que también es raíz de $f'$, por tanto $x-\alpha$ divide tanto a $f$ como a $f'$.

$\Leftarrow$ Si $f$ y $f'$ no son coprimos, entonces $\operatorname{mcd}(f,f')=g(x)$ es un polinomio no constante. Como $\mathbb{C}$ es algebraicamente cerrado, $g(x)$ tiene alguna raíz $\alpha\in\mathbb{C}$. Es más, como $g|f$ y $g|f'$, $\alpha$ también es raíz de $f$ y de $f'$, luego es una raíz múltiple de $f$.
{{% /proof %}}

{{% proposition %}}
Dada una extensión $F\subset\mathbb{C}$, si $f(x)\in F[ x ]$ es irreducible entonces $f$ y $f'$ son coprimos, en particular $f$ no tiene raíces múltiples en $\mathbb{C}$.
{{% /proposition %}}

{{% proof %}}
Como $f$ es irreducible, no es constante, así que $f'\neq 0$. Sea $g=\operatorname{mcd}(f,f')$. Si $g$ no es constante, entonces $g$ y $f$ son asociados, ya que $g|f$ y $f$ es irreducible. Podemos pues suponer que $g=f$. Entonces $f|f'$, pero esto es imposible porque $f'\neq 0$, así que el grado de $f'$ es $<$ el grado de $f$.
{{% /proof %}}

{{% definition %}}
Dada una extensión finita $F\subset K$, decimos que $\alpha\in K$ es un **elemento primitivo** si $K=F[\alpha]$.
{{% /definition %}}

Como de costumbre, en el enunciado del siguiente resultado "casi todo" significa "todo menos una cantidad finita".

{{% lemma %}}
Dada una extensión finita $F\subset K$ tal que $K\subset\mathbb{C}$ y $K=F[\alpha,\beta]$, $\gamma=\beta+c\alpha$ es un elemento primitivo para casi todo $c\in F$.
{{% /lemma %}}

{{% proof %}}
Sean $f(x),g(x)\in F[ x ]$ los polinomios irreducibles de $\alpha,\beta\in K$, respectivamente. Supongamos que sus grados respectivos son $m,n\geq 1$. Sean $\alpha\_1,\dots,\alpha\_m$ y $\beta\_1,\dots,\beta\_n$ sus raíces en $\mathbb{C}$, con $\alpha=\alpha\_1$ y $\beta=\beta\_1$. Como $f$ y $g$ no tienen raíces múltiples por ser irreducibles, los $\alpha\_i$ son todos distintos, y también los $\beta\_j$. Dado $c\in F$, denotemos

$$\gamma\_{ij}=\beta\_j+c\alpha\_i.$$

Veamos que, si $(i,j)\neq (k,l)$, la igualdad $\gamma\_{ij}=\gamma\_{kl}$ solo puede ser cierta para un único valor de $c\in F$. En efecto, esto es cierto pues equivale a 

$$c(\alpha\_i-\alpha\_k)=\beta\_l-\beta\_j.$$

Si $i\neq k$ entonces $\alpha\_i\neq \alpha\_k$ y podemos despejar $c$, que sería única. Si $i=k$ entonces $j\neq l$, luego $\beta\_l\neq \beta\_j$ y no hay ningún valor de $c$ que satisfaga la ecuación. Por tanto, para casi todos los $c\in F$, los $\gamma\_{ij}$ son todos distintos. Fijemos tal $c\in F$, necesariamente no nula, y demostremos que $\gamma=\gamma_{11}$ es un elemento primitivo.

Consideramos la extensión intermedia $F\subset F[\gamma]\subset F[\alpha,\beta]$. Bastará demostrar que $\alpha\in F[\gamma]$, ya que entonces también $\beta=\gamma-c\alpha\in F[\gamma]$, y por tanto tendríamos la otra inclusión $F[\gamma]\supset F[\alpha,\beta]$. 

Como $g(x)\in F[ x ]$, $h(x)=g(\gamma-cx)\in F[\gamma][ x ]$. Tenemos que $\alpha\in \mathbb{C}$ es raíz de $h$ ya que $h(\alpha)=g(\gamma-c\alpha)=g(\beta)=0$. También es raíz de $f\in F[ x ]$, que es su polinomio mínimo. Veamos que no poseen más raíces complejas en común. En efecto, si algún otro $\alpha\_i$, $i>1$, fuera raíz de $h$, entonces $0=h(\alpha\_i)=g(\gamma-c\alpha\_i)$. Como las raíces de $g$ son los $\beta\_j$, tendríamos que $\gamma-c\alpha\_i=\beta\_j$, así que $\gamma\_{11}=\beta\_j+c\alpha\_i=\gamma_{ij}$, lo cual es imposible porque $i\neq 1$. De aquí deducimos que $\operatorname{mcd}(f,h)=x-\alpha$ en $\mathbb{C}[ x ]$. El divisor común máximo de dos polinomios está bien definido salvo producto por constantes no nulas. Es más, divisor común máximo de dos polinomios en $F[\gamma][ x ]$ lo es también en $\mathbb{C}[ x ]$, ya que toda división euclídea en el primero lo es también en el segundo, así que que el resultado de aplicar el algoritmo de Euclides en el primero es también válido en el segundo. Esto demuestra que $x-\alpha\in F[\gamma][ x ]$, así que en efecto $ \alpha\in F[\gamma]$.
{{% /proof %}}


{{% theorem name="del elemento primitivo" %}}
Toda extensión finita contenida en $\mathbb{C}$ posee un elemento primitivo.
{{% /theorem %}}

{{% proof %}}
Sea $F\subset K$ una extensión finita. Vimos al final de la sección anterior que estaba generada por una cantidad finita de elementos $\alpha\_1,\dots,\alpha\_n\in K$, $K=F[\alpha\_1,\dots,\alpha\_n]$. Demostraremos este teorema por inducción en el número $n$ de generadores. Para $n=1$ no hay nada que demostrar. Probémoslo para $n$ generadores suponiendo el resultado cierto para $n-1$. Aplicando la hipótesis de inducción, $F[\alpha\_1,\dots,\alpha\_{n-1}]=F[\beta]$, así que $K=F[\beta,\alpha\_n]$, que por el lema anterior posee un elemento primitivo.
{{% /proof %}}

Este teorema es cierto bajo hipótesis mucho más generales, pero la prueba se complica.



## Construcciones con regla y compás

{{% definition %}}
Un punto, recta o circunferencia del plano $\mathbb R^2$ se considera **construido** en los siguientes casos:

* Los puntos $(0,0)$ y $(1,0)$.

![Puntos constructibles](../../images/puntos.svg)

* Las rectas que pasan por dos puntos construidos.

![Recta constructible](../../images/recta.svg)

* Las circunferencias de centro un punto construido que pasan por otro punto construido.

![Circunferencia constructible](../../images/circunferencia.svg)

* El punto de intersección de dos rectas construidas.

![Intersección de rectas constructibles](../../images/intersec_rectas.svg)

* Los puntos de intersección de dos circunferencias construidas.

![Intersección de circunferencias constructibles](../../images/intersec_circs.svg)

* Los puntos de intersección de una recta y una circunferencia construidas.

![Intersección de recta y circunferencia constructible](../../images/intersec_recta_circ.svg)

Un número real $a\in\mathbb R$ es **constructible** si su valor absoluto $|a|$ es la distancia entre dos puntos constructibles.

{{% /definition %}}


Deducimos que además podemos construir:

* El punto medio entre dos puntos construidos.

![Punto medio](../../images/medio.svg)

* La recta perpendicular a una recta construida que pasa por un punto construido.

![Perpendicular sobre un punto de la recta](../../images/perpendicular_interior.svg)

![Perpendicular sobre un punto exterior](../../images/perpendicular_exterior.svg)

* La recta paralela a una recta construida que pasa por un punto construido.

![Paralela](../../images/paralela.svg)

* Los puntos que están a una distancia constructible de un punto construido dentro de una recta construida. Intuitivamente esta propiedad nos dice que podemos transportar distancias constructibles.

![Transporte de longitud](../../images/distancia.svg)


{{% proposition %}}
Un punto $(a,b)\in\mathbb R^2$ es constructible si y solo si sus coordenadas $a,b\in\mathbb R$ son números constructibles. 
{{% /proposition %}}


{{% proof %}}
$\Rightarrow$ Trazando paralelas y perpendiculares por puntos constructibles, podemos construir los ejes de coordenadas y las proyecciones de $(a,b)$ sobre los mismos. La distancia de las proyecciones al origen son $|a|$ y $|b|$, así que las coordenadas son constructibles. 

![Coordenadas](../../images/coordenadas.svg) 

$\Leftarrow$ Recíprocamente, asi $a$ y $b$ son constructibles podemos construir los puntos sobre los ejes de coordenadas que están a distancia $|a|$ y $|b|$ del origen, es decir, $(\pm a,0)$ y $(0,\pm b)$, y obtener $(a,b)$ como punto de intersección de las paralelas a los ejes que pasan por $(a,0)$ y $(0,b)$.
{{% /proof %}}


{{% proposition %}}
El subconjunto de $\mathbb R$ formado por los números constructibles es un cuerpo. 
{{% /proposition %}}


{{% proof %}}

El $0$ y el $1$ son constructibles ya que el $(0,0)$ y el $(1,0)$ están construidos.

Dados $a\geq b\geq 0$ constructibles, podemos construir $a+b$ y $a-b$ tomando a partir del origen puntos del eje horizonal a distancias $a$ y $b$,

![Suma](../../images/suma.svg)

![Resta](../../images/resta.svg)

Por tanto también son constructibles $-a-b$ y $-a+b$. Esto demuestra que la suma de dos números constructibles cualesquiera y el opuesto de uno dado son constructibles.

Para construir el producto de dos números constructibles $a,b> 0$ usamos triángulos semejantes. Construimos primero el triángulo ractángulo con base en el eje horizontal, de longitud 1, vértice en el origen y altura $a$. El triángulo semejante de base $b$ tiene altura $ab$.

![Producto](../../images/producto.svg)

Esto demuestra que también son constructibles $(-a)b$, $a(-b)$ y $(-a)(-b)$, es decir, el producto de dos números constructibles cualesquiera (multiplicar por $0$ da $0$, que es constructible). Con esto hemos visto que los números constructibles forman un subanillo de $\mathbb R$.

La construcción del inverso de un número constructible $a> 0$ se lleva a cabo del mismo modo

![Inverso](../../images/inverso.svg)

Por tanto $(-a)^{-1}=-a^{-1}$ también es constructible. Esto demuestra que el anillo de los números constructibles es un cuerpo.
{{% /proof %}}



{{% remark %}}
El cuerpo de los números constructibles contiene a $\mathbb Q$ ya que está contenido en $\mathbb R$ y cualquier racional se puede obtener a partir del $1$ sumando, tomando opuestos y dividiendo por números no nulos. Esto se aplica también a cualquier cuerpo contenido en $\mathbb C$ pero obviamente no es válido para los cuerpos finitos $\mathbb Z/(p)$. 
{{% /remark %}}


{{% proposition %}}
Si $a\in\mathbb R$ es positivo $a>0$ y constructible entonces $\sqrt{a}$ también es constructible. 
{{% /proposition %}}


{{% proof %}}

Es consecuencia del conocido teorema de la media geométrica. En el eje horizontal tomamos el punto a la izquierda del origen a distancia $a$. Trazamos una circunferencia que pase por él y que tenga centro en el punto medio entre este punto y el $(1,0)$. La distancia del origen al punto de corte con la circunferencia de la perpendicular al eje horizontal es $\sqrt{a}$.

![Raíz cuadrada](../../images/raiz.svg)

{{% /proof %}}


Hasta ahora hemos demostrado que podemos construir números constructibles a partir del $1$ sumando, restando, dividiendo por números no nulos, y tomando raíces cuadradas de números positivos. Los siguientes resultados demuestran que no hay más números constructibles que los que se pueden obtener de este modo.

{{% proposition %}}
Dados cuatro puntos en $\mathbb R^2$ cuyas coordenadas están en un subcuerpo $F\subset\mathbb R$, los puntos de intersección de las rectas y circunferencias que se pueden dibujar apoyándose en dichos puntos tienen coordenadas en $F$ o en $F[\sqrt{r}]$ para cierto $r\in F$ positivo $r>0$ que no sea el cuadrado de ningún número de $F$. 
{{% /proposition %}}


{{% proof %}}
Dados dos puntos $(a\_0,b\_0), (a\_1,b\_1)\in\mathbb R^2$, la recta que pasa por ambos tiene ecuación 

$$(a\_1-a\_0)(y-b\_0)=(b\_1-b\_0)(x-a\_0),$$

y la circunferencia de centro el primero que pasa por el segundo está definida por

$$(x-a\_0)^2+(y-b\_0)^2=(a\_1-a\_0)^2+(b\_1-b\_0)^2.$$

Si las coordenadas están en $F$ entonces los coeficientes de ambas ecuaciones también.

La intersección de dos de estas rectas tiene coordenadas en $F$ porque las soluciones de un sistema de ecuaciones lineales con coeficientes en un cuerpo siempre están en dicho cuerpo.

Para hallar la intersección de una recta y una circunferencia, despejamos una incógnita de la ecuación de la recta y la sustituimos en la ecuación de la circunferencia. Esto nos da una ecuación de grado $2$ con coeficientes en $F$. Para que esta ecuación tenga solución su discriminante ha de ser $D\geq 0$. En ese caso la solución está en $F[\sqrt{D}]$. Por tanto las coordenadas del punto de intersección están en este cuerpo. Si $D$ es el cuadrado de un número de $F$ entonces $F[\sqrt{D}]=F$.

Para intersecar dos circunferencias, observamos que la diferencia de ambas ecuaciones es de grado $1$, por tanto este caso se reduce al anterior.


{{% /proof %}}


Recuerda que antes hemos visto que $[F[\sqrt{r}]:F]=2$ si $r\in F$ y $\sqrt{r}\notin F$. 



{{% theorem %}}
Dados números reales constructibles $a\_1,\dots,a\_m\in\mathbb R$, hay una cadena de extensiones

$$\mathbb Q=F\_0\subset F\_1\subset F\_2\subset\cdots\subset F\_n=K$$

tales que

* $K\subset\mathbb R$ es un subcuerpo,

* $a\_1,\dots,a\_m\in K$,

* Cada $F\_{i+1}=F\_i[\sqrt{r\_i}]$, $0\leq i{<}n$, donde $r\_i\in F\_i$ es un número positivo $r\_i>0$ que no es un cuadrado en $F\_i$.

En particular $[K:\mathbb Q]=2^n$.
{{% /theorem %}}


{{% proof %}}
La construtibilidad de los números $a\_i$ equivale a la de los puntos $(a\_i,0)$. Los puntos constructibles se construyen a partir de los básicos, $(0,0)$ y $(1,0)$, trazando e intersecando rectas y circunferencias mediante los métodos permitidos. Los puntos básicos tienen coordenadas en $\mathbb Q$. Por la proposición anterior, los puntos que se construyen a partir de ellos tendrán coordenadas en extensiones sucesivas de $\mathbb Q$ obtenidas al añadir nuevas raíces cuadradas de números positivos, por tanto el teorema se sigue de la proposición anterior por inducción. La observación sobre el grado se sigue de la fórmula del grado para extensiones intermedias, que en este caso nos dice que

$$[K:\mathbb Q]=\prod\_{i=0}^{n-1}[F\_{i+1}:F\_i]=2^n$$

ya que por el tercer apartado $[F\_{i+1}:F\_i]=2$.
{{% /proof %}}


La cantidad de raíces cuadradas que hemos de añadir a $\mathbb Q$ para construir $K$ ($n$ según la notación del teorema) no tiene relación con la cantidad de números constructibles $a\_1,\dots,a\_m$ que queremos que $K$ posea. 


{{% corollary %}}
Los números constructibles son algebraicos sobre $\mathbb Q$ y el grado de un número constructible es siempre una potencia de $2$. 
{{% /corollary %}}


{{% proof %}}
Por el teorema anterior, si $a\in \mathbb R$ es constructible entonces $a\in K$ para cierta extensión finita $\mathbb{Q}\subset K$ de grado $2^n$. En particular $a$ es algebraico sobre $\mathbb Q$ y su grado divide a $2^n$, así que ha de ser una potencia de $2$.
{{% /proof %}}


{{% example name="Números constructibles de grado $2^m$ cualquiera" %}}
Si $p\in\mathbb Z$ es un primo positivo, $\sqrt[n]{p}$ es constructible si y solo si $n$ es una potencia de $2$. Sabemos que este número tiene grado $n$ sobre $\mathbb Q$, así que solo puede ser constructible si $n=2^m$. Además en este caso podemos ver por inducción en $m$ que de hecho es constructible. Para $m=0$ es obvio porque es entero y si $\sqrt[2^{m-1}]{p}$ es constructible entonces

$$\sqrt[2^m]{p}=\sqrt{\sqrt[2^{m-1}]{p}}$$

también, por ser la raíz cuadrada de un número constructible. 
{{% /example %}}

{{% remark %}}
Más adelante veremos que hay números cuyo grado es una potencia de $2$ pero que no son constructibles, por ejemplo, las raíces reales del polinomio $x^4−6x+3\in\mathbb{Q}[ x ]$, que al ser irreducible tienen grado $4=2^2$.
{{% /remark %}}


{{% definition %}}
Un ángulo $\theta\in[0,2\pi)$ es **constructible** si el número $\cos \theta\in\mathbb R$ es constructible. 
{{% /definition %}}


Por la construcción geométrica de senos y cosenos, está claro que la definición anterior es equivalente a decir que $\sin \theta$ es constructible, o que la recta que pasa por el origen y hace ángulo $\theta$ con el eje horizontal es constructible, o más generalmente que podemos construir la recta que pasa por un punto constructible y que hace ángulo $\theta$ con otra recta constructible que pasa por él.

![Ángulo constructible](../../images/angulo.svg)

Veamos que en general es imposible trisecar un ángulo cualquiera con regla y compás.

{{% proposition %}}
El ángulo de $60º$ es constructible pero su trisección no. 
{{% /proposition %}}


{{% proof %}}
Este ángulo se puede construir porque $\cos  60º=\frac{1}{2}$ es constructible. Cada ángulo de su trisección tendría $20º$ y el ángulo de $20º$ no es constructible. En efecto, la siguiente fórmula trigonométrica es cierta en general

$$\cos 3\theta=4\cos^3\theta-3\cos\theta.$$

Tomando $\theta= 20º$ deducimos que $\alpha=\cos 20º$ es una raíz del polinomio $8x^3-6x-1$. Vamos a ver que este polinomio es irreducible sobre $\mathbb Q$, por tanto $\alpha$ tendrá grado $3$ sobre $\mathbb Q$, así que no podrá ser constructible. El polinomio $8x^3-6x-1$ es primitivo, por tanto es irreducible sobre $\mathbb Q$ si y solo si lo es sobre $\mathbb Z$. Sobre $\mathbb Z$ es irreducible por el criterio de reducción módulo $5$, ya que $3x^3-x-1\in\mathbb Z/(5)[ x ]$ tiene grado $\leq 3$ pero no tiene raíces.
{{% /proof %}}


{{% proposition %}}
Un polígono regular de $p$ lados, $p\in\mathbb Z$ primo, puede construirse con regla y compás si y solo si $p=2^n+1$. 
{{% /proposition %}}


{{% proof %}}
Esto equivale a la constructibilidad del ángulo de $\frac{2\pi}{p}$ radianes. 

$\Leftarrow$  Es un resultado de Gauss que no probaremos.

$\Rightarrow$ El número complejo $\zeta=e^{\frac{2\pi i}{p}}=\cos\frac{2\pi}{p}+i\sin \frac{2\pi}{p}$ es una raíz $p$-ésima de la unidad, es decir, una raíz del polinomio $x^p-1$. Este polinomio factoriza como

$$(x-1)(x^{p-1}+\cdots+x+1)$$

y como $\zeta\neq 1$, $\zeta$ es raíz del segundo, que se denomina $p$-ésimo **polinomio ciclotómico**

$$f(x)=x^{p-1}+\cdots+x+1.$$

Veamos que este polinomio es irreducible sobre $\mathbb Q$. Para ello hacemos el cambio de variable $x=y+1$, que se corresponde con el isomorfismo $g$ que pasamos a definir. 

Consideramos el único homomorfismo de anillos

$$g\colon \mathbb Q[ x ]\longrightarrow \mathbb Q[y]$$

tal que $g\_{|\_{\mathbb{Q}}}$ es la inclusión $\mathbb{Q}\subset\mathbb{Q}[y]$ y $g(x)=y+1$, que está bien definido por el principio de sustitución. El homomorfismo $g$ está definido sobre un polinomio cualquiera $h(x)\in\mathbb{Q}[ x ]$ como $g(h(x))=h(y+1)$.
Análogamente, consideramos el único homomorfismo

$$g'\colon \mathbb Q[y]\longrightarrow \mathbb Q[ x ]$$

tal que $g'\_{|\_{\mathbb{Q}}}$ es la inclusión $\mathbb{Q}\subset\mathbb{Q}[ x ]$ y $g'(y)=x-1$. Sobre un polinomio cualquiera $h'(y)\in\mathbb{Q}[y]$, el homomorfismo $g'$ está definido como $g'(h'(y))=h'(x-1)$. Es fácil comprobar que $g'\circ g=1\_{\mathbb{Q}[ x ]}$ y $g\circ g'=1\_{\mathbb{Q}[y]}$, por tanto $g$ es un isomorfismo con inverso $g^{-1}=g'$. En particular, $f(x)$ es irreducible en $\mathbb{Q}[ x ]$ si y solo si $g(f(x))=f(y+1)$ es irreducible en $\mathbb{Q}[y]$. Vamos a probar esto último.

Como $x^p-1=(x-1)f(x)$ entonces 

$$\begin{array}{rcl}
yf(y+1)&=&(y+1)^p-1\cr
&=& \sum\_{n=1}^{p}\binom{p}{n}y^n.
\end{array}$$

Aplicando la propiedad cancelativa en el dominio $\mathbb Q[y]$ obtenemos que

$$\begin{array}{rcl}
f(y+1)&=&\sum\_{n=1}^{p}\binom{p}{n}y^{n-1}.
\end{array}$$

Este polinomio es irreducible por el criterio de Eisenstein para el primo $p$ ya que el coeficiente líder es $1$, el término independiente es $p$, y $p$ divide a $\binom{p}{n}$ para todo $0{<}n{<}p$. 

Por ser el polinomio ciclotómico $f(x)$ irreducible y tener a $\zeta$ como raíz, deducimos que $\zeta$ tiene grado $p-1$ sobre $\mathbb Q$. Si $\frac{2\pi}{p}$ fuera constructible, tendríamos un cuerpo $K\subset\mathbb R$ tal que $\cos\frac{2\pi}{p}, \sin\frac{2\pi}{p}\in K$ y $[K:\mathbb Q]=2^n$. Como $K$ está contenido en los reales, $[K[i]:K]=2$, luego $[K[i]:\mathbb Q]=[K[i]:K][K:\mathbb Q]=2^{n+1}$. Además, $\zeta\in K[i]$ luego el grado de $\zeta$, que es $p-1$, ha de ser una potencia de $2$.
{{% /proof %}}


{{% example name="Primos de Fermat" %}}
 Los enteros primos $p\in\mathbb Z$ tales que el polígono regular de $p$ lados se puede construir con regla y compás, es decir los que son de la forma $p=2^n+1$, se denominan **primos de Fermat**. Solo se conocen los siguientes: 3, 5, 17, 257 y 65537. No se sabe siquiera si hay una cantidad finita o infinita de primos de Fermat. Este problema fue planteado por Eisenstein en 1844 y permanece abierto. 

La siguiente imagen, obtenida de [Wikipedia](https://en.wikipedia.org/wiki/Constructible_polygon), muestra la construcción paso a paso de un polígono regular de 17 lados con regla y compás. En el artículo de Wikipedia enlazado se puede encontrar otra construccón de este polígono regular, así como una construcción completa del de 257 lados y el comienzo de la construcción del de 65537 lados. 

![Heptadecágono](../../images/HeptadecagonConstructionAni.gif)


{{% /example %}}










