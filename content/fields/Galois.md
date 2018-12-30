+++
title = "Teoría de Galois"
weight = 20
+++

En esta sección supondremos sin necesida de mencionarlo explícitamente que todos los cuerpos que consideremos son subcuerpos de $\mathbb C$.

## El grupo de Galois

{{% definition %}}
Dada una extensión $F\subset K$, su **grupo de Galois** $G(K/F)$ es el conjunto de los automorfismos de $F\subset K$. 
{{% /definition %}}


{{% remark %}}
La estructura de grupo del grupo de Galois es la composición. El elemento unidad es la identidad. El grupo de Galois de la extensión trivial es el grupo trivial $G(F/F)=\\{\operatorname{id}\_{F}\\}$. Recuerda que si la extensión $F\subset K$ es finita cualquier homomorfismo de extensiones $f\colon K\rightarrow K$ es un elemento de $G(K/F)$, y si además $F=\mathbb Q$ entonces cualquier homomorfismo de anillos $f\colon K\rightarrow K$ es un elemento de $G(K/F)$. Recuerda también que todo elemento de $G(K/F)$ es además un isomorfismo de $F$-espacios vectoriales, pero no todo isomorfismo de $F$-espacios vectoriales $f\colon K\rightarrow K$ está en $G(K/F)$ ya que podría no preservar el producto en $K$, o incluso el $1$. Asimismo, recuerda que todo elemento de $G(K/F)$ preserva raíces de polinomios con coeficientes en $F$. 
{{% /remark %}}


{{% example name="$G(\mathbb C/\mathbb R)$" %}}
Un homomorfismo de $\mathbb R$-espacios vectoriales $f\colon \mathbb C\rightarrow\mathbb C$ está determinado por la imagen de los elementos de una base, por ejemplo $\\{1,i\\}\subset\mathbb C$. Para que $f\in G(\mathbb C/\mathbb R)$ ha de ser un homomorfismo de anillos, así que debe satisfacer $f(1)=1$. También ha de preservar raíces en $\mathbb C$ de polinomios en $\mathbb R[x]$. Las raíces complejas de $x^2+1$ son $\pm i$, así que $f$ ha de cumplir $f(i)=\pm i$. Por tanto los dos posibles elementos de $G(\mathbb C/\mathbb R)$ son los homomorfismos de $\mathbb R$-espacios vectoriales definidos por $$\begin{array}{rcl}f(1)&=&1,\cr f(i)&=&i,\end{array}$$ y por $$\begin{array}{rcl}f(1)&=&1,\cr f(i)&=&-i.\end{array}$$ Algunos de estos dos homomorfismos de $\mathbb R$-espacios vectoriales podría no estar en $G(\mathbb C/\mathbb R)$ pues podría no preservar el producto, pero ambos lo preservan porque claramente el primero es la identidad $\operatorname{id}\_{\mathbb C}$ y el segundo es la conjugación, que denotaremos $c$. Así que $G(\mathbb C/\mathbb R)=\\{\operatorname{id}\_{\mathbb C},c\\}$, que es un grupo cíclico de orden $2$ generado por la conjugación $c$, que satisface $c\circ c=\operatorname{id}_{\mathbb C}$. 
{{% /example %}}


{{% proposition %}}
 Si $F\subset K$ es una extensión de grado $[K:F]=2$ entonces $K=F[\sqrt{\delta}]$ para cierto $\delta\in F$ y $G(K/F)=\\{\operatorname{id}_K,c\\}$ es un grupo cíclico de orden $2$ cuyo generador $c$ denominamos **conjugación** y está caracterizado por satisfacer $c(\sqrt{\delta})=-\sqrt{\delta}$. 
{{% /proposition %}}


{{% proof %}}
 Como la extensión no es trivial, ha de existir algún $\alpha\in K$ tal que $\alpha\notin F$. El grado de este elemento ha de dividir a $2$. Como no puede ser $1$ porque $\alpha\notin F$, ha de ser $2$. La extensión $F\subset F[\alpha]$ también tiene grado $2$ y $F[\alpha]\subset K$ por tanto $K=F[\alpha]$. Si $x^2+ax+b\in F[x]$ es el polinomio irreducible de $\alpha$, entonces $$\alpha=\frac{-a\pm\sqrt{\delta}}{2}$$ donde $\delta=a^2-4b\in F$ es el **discriminante**. Deducimos por tanto que $\sqrt{\delta}\in K$, $\sqrt{\delta}\notin F$, y $K=F[\sqrt{\delta}]$. Sabemos que $\\{1,\sqrt{\delta}\\}\subset K$ es una base como $F$-espacio vectorial. Como cualquier $f\in G(K/F)$ preserva el $1$ y las raíces de $x^2-\delta$, tenemos solo dos posibilidades:
$$\begin{array}{rcl}f(1)&=&1,\cr f(\sqrt{\delta})&=&\sqrt{\delta},\end{array}$$ y $$\begin{array}{rcl}f(1)&=&1,\cr f(\sqrt{\delta})&=&-\sqrt{\delta}.\end{array}$$ El primero es la identidad $\operatorname{id}\_{K}$, que es obviamente un isomorfismo de extensiones. El segundo es el que denominamos conjugación $c$. Dejamos como ejercicio probar que la conjugación, que a priori es solo un homomorfismo de $F$-espacios vectoriales, es de hecho un homomorfismo de extensiones. Solo queda por demostrar que preserva el producto.
{{% /proof %}}


{{% example name="$G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)$" %}}
 Aquí $\sqrt[3]{2}$ denota la raíz cúbica de $2$ real por lo que $\mathbb Q[\sqrt[3]{2}]\subset\mathbb R$. El resto de raíces cúbicas de $2$ son puramente complejas. Cualquier $f \in G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)$ ha de preservar las raíces de $x^3-2\in\mathbb Q[x]$. La única raíz de este polinomio que está en $\mathbb Q[\sqrt[3]{2}]$ es $\sqrt[3]{2}$, ya que las otras dos están en $\mathbb{C}\setminus\mathbb{R}$, por tanto $f(\sqrt[3]{2})=\sqrt[3]{2}$. Una base de $\mathbb Q[\sqrt[3]{2}]$ como $\mathbb Q$-espacio vectorial está formada por las primeras tres potencias de $\sqrt[3]{2}$, es decir, $\\{1,\sqrt[3]{2},(\sqrt[3]{2})^2\\}$. Como $f$ ha de preservar la unidad y los productos, $f$ tiene que mandar cada uno de los elementos de esta base a sí mismo, así que necesariamente $f=\operatorname{id}_{\mathbb Q[\sqrt[3]{2}]}$, por tanto en este caso el grupo de Galois es el tivial, $G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)=\\{\operatorname{id}\_{\mathbb Q[\sqrt[3]{2}]}\\}$ a pesar de que la extensión $\mathbb Q\subset \mathbb Q[\sqrt[3]{2}]$ no es trivial, es de grado $3$. 
{{% /example %}}


{{% definition %}}
Dado un cuerpo $F$ y un polinomio mónico no constante $p(x)\in F[x]$, el **cuerpo de descomposición** de $p(x)$ es $F[\alpha\_1,\dots,\alpha\_n]$, donde $\alpha\_1,\dots,\alpha\_n$ son las raíces complejas de $p(x)$.
{{% /definition %}}


{{% proposition %}}
 Toda extensión $F\subset K$ de grado $2$ es un cuerpo de descomposición. 
{{% /proposition %}}


{{% proof %}}
Ya hemos visto que $K=F[\sqrt{\delta}]$ para cierto $\delta\in F$, entonces $K$ es el cuerpo de descomposición de $x^2-\delta$ ya que las raíces complejas de este polinomio son $\pm\sqrt{\delta}$ y $F[\sqrt{\delta},-\sqrt{\delta}]=F[\sqrt{\delta}]$.
{{% /proof %}}



El **grupo simétrico** de $n$ letras, es decir el **grupo de permutaciones** de $\\{1,\dots,n\\}$, se denotará $S\_n$. 

{{% proposition %}}
 Dada una extensión $F\subset K$, si $K$ es el cuerpo de descomposición de un polinomio $p(x)\in F[x]$ con $n$ raíces distintas en $K$, entonces hay un único homomorfismo inyectivo $$\varphi\colon G(K/F)\longrightarrow S\_n$$ tal que, si $\alpha\_1,\dots,\alpha\_n\in K$ son la raíces de $p(x)$ en $K$ y $f\in G(K/F)$, la permutación $\varphi(f)=\sigma$ es la única que satisface la siguiente ecuación para todo $i=1,\dots,n$, $$f(\alpha\_i)=\alpha_{\sigma(i)}.$$ 
{{% /proposition %}}


{{% proof %}}
 Como $f$ preserva raíces de polinomios con coeficientes en $F$, $f$ ha de mandar el conjunto $\\{\alpha\_1,\dots,\alpha\_n\\}$ dentro de sí mismo. Además ha de hacerlo de manera biyectiva por ser $f$ un automorfismo, por tanto existe una única permutación $\sigma\in S\_n$ que satisface la ecuación del enunciado. Esto me permite definir la aplicación $\varphi$ de manera única. 

Veamos que $\varphi$ es un homomorfismo de grupos. Por un lado $\varphi(\operatorname{id}\_{K})$ es la permutación identidad ya que $\operatorname{id}\_{K}(\alpha\_i)=\alpha\_i$. Por otro lado, dados $f,g\in G(K/F)$, si denotamos $\varphi(f)=\sigma$ y $\varphi(g)=\tau$ entonces 
$$\begin{array}{rcl}
(f\circ g)(\alpha\_i)&=&f(g(\alpha\_i))\cr
&=&f(\alpha\_{\tau(i)})\cr
&=&\alpha\_{\sigma(\tau(i))}\cr
&=&\alpha\_{(\sigma\circ\tau)(i)}.
\end{array}$$
Por tanto
$$\begin{array}{rcl}
\varphi(f\circ g)&=&\sigma\circ\tau\cr
&=&\varphi(f)\circ \varphi(g).
\end{array}$$

Comprobemos por último que $\varphi$ es inyectivo. Para ello debemos probar que si $f\in G(K/F)$ es tal que $\varphi(f)$ es le permutación identidad entonces $f=\operatorname{id}\_{K}$. Por definición $\varphi(f)$ es la permutación identidad si y solo si $f(\alpha\_i)=\alpha\_i$ para todo $i=1,\dots,n$. Como $K=F[\alpha\_1,\dots,\alpha\_n]$, todo elemento $\alpha\in K$ se puede escribir como polinomio en $\alpha\_1,\dots,\alpha\_n$ con coeficientes en $F$, es decir $$\alpha=\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}$$ para ciertos $b\_{m\_1,\dots,m\_n}\in F$, casi todos nulos (y no necesariamente únicos, pero esto es irrelevante). Entonces
$$\begin{array}{rcl}
f(\alpha)&=&f\left(\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}\right)\cr
&=&\sum\_{m\_i\geq 0} f(b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n})\cr
&=&\sum\_{m\_i\geq 0} f(b\_{m\_1,\dots,m\_n})f(\alpha\_1)^{m\_1}\cdots f(\alpha\_n)^{m\_n}\cr
&=&\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}\cr
&=&\alpha,
\end{array}$$
así que $f=\operatorname{id}\_{K}$. En las ecuaciones anteriores hemos usado que $f$ es un homomorfismo de anillos que deja fijo a $F$ y a las raíces $\alpha\_1,\dots,\alpha\_n\in K$ de $p(x)$.
{{% /proof %}}


Uno homomorfismo $\varphi$ como el del enunciado se denomina **representación** del grupo de Galois como grupo de permutaciones.

{{% proposition %}}
 Dadas dos extensiones consecutivas $F\subset L\subset K$, tenemos que $G(K/L)\subset G(K/F)$. 
{{% /proposition %}}


{{% proof %}}
 En efecto, si $f\colon K\rightarrow K$ es un isomorfismo de anillos que deja fijo a $L$ entonces también deja fijo a $F$ ya que $F\subset L$.
{{% /proof %}}


Los subgrupos del grupo de Galois nos permiten construir extensiones intermedias.

{{% definition %}}
 Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$ definimos el **cuerpo fijo** de $H$ del siguiente modo: $$K^{H}=\\{\alpha\in K\;|\; f(\alpha)=\alpha\;\forall f\in H\\}.$$ 
{{% /definition %}}


{{% proposition %}}
 Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$, el cuerpo fijo $K^H$ es un subcuerpo de $K$ que contiene a $F$, $$F\subset K^H\subset K.$$ 
{{% /proposition %}}


{{% proof %}}
 El conjunto $K^H$ está contenido en $K$ por definición. Es más, cualquier $\alpha\in F$ satisface $f(\alpha)=\alpha$ para todo $f\in G(K/F)$, en particular para todo $f\in H$, por tanto $F\subset K^H$.  

Veamos que $K^H\subset K$ es un subanillo. Obviamente $0,1\in F\subset K^H$. Si $\alpha,\beta\in K^H$ entonces, dado $f\in H$, como $f\colon K\rightarrow K$ es un homomorfismo de anillos,
$$\begin{array}{rcl}
f(\alpha+\beta)&=&f(\alpha)+f(\beta)\cr
&=&\alpha+\beta,\cr
f(-\alpha)&=&-f(\alpha)\cr
&=&-\alpha,\cr
f(\alpha\beta)&=&f(\alpha)f(\beta)\cr
&=&\alpha\beta.
\end{array}$$
Por tanto $\alpha+\beta,-\alpha,\alpha\beta\in K^H$. Además $K^H$ es un cuerpo porque si $\alpha\neq 0$ entonces
$$\begin{array}{rcl}
f(\alpha^{-1})&=&f(\alpha)^{-1}\cr
&=&\alpha^{-1}.
\end{array}$$
{{% /proof %}}

{{% proposition %}}
Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$ tenemos que $H\subset G(K/K^H)$.
{{% /proposition %}}

{{% proof %}}
Es obvio porque, por definición de $K^H$, todos los automorfismos de la extensión que están en $H$ dejan fijo a $K^H$.
{{% /proof %}}

## Funciones simétricas


{{% definition %}}
Dado un anillo $R$, un polinomio $f=f(u\_1,\dots,u\_n)\in R[u\_1,\dots,u\_n]$ y un elemento $\sigma\in S_n$. El polinomio $\sigma(f)\in R[u\_1,\dots,u\_n]$ es
$$
\sigma(f)=f(u\_{\sigma(1)},\dots, u\_{\sigma(n)}).
$$
La **órbita** de $f$ es el conjunto de polinomios
$$\\{\sigma(f)\mid \sigma\in S_n\\}.$$
Decimos que $f$ es **simétrico** si $f=\sigma(f)$ para todo $\sigma\in S_n$.
{{% /definition %}}

{{% example name="Una permutación aplicada a un polinomio" %}}
Si tomamos el polinomio $f=2u\_1^2u\_3^2-3u\_2\in\mathbb{Z}[u\_1,u\_2,u\_3]$ y le aplicamos la permutacición
$$\sigma=\left(
\begin{array}{ccc}
1&2&3\cr
2&3&1
\end{array}
\right)=(1\;2\;3)\in S_3$$
obtenemos el polinomio 
$$\sigma(f)=2u\_2^2u\_1^2-3u\_3.$$
Consideranto las $3!=6$ permutaciones de $S_3$, puedes comprobar que la órbita de $f$ es el conjunto
$$
\\{2u\_1^2u\_3^2-3u\_2, 2u\_2^2u\_3^2-3u\_1, 2u\_1^2u\_2^2-3u\_3\\}.
$$
{{% /example %}}

{{% remark %}}
La órbita de un polinomio en $n$ variables tiene como máximo $|S\_n|=n!$ elementos. Es más, el número de elementos de la órbita divide a $n!$. La órbita de un polinomio es un conjunto unitario si y solo si es simétrico. Los polinomios simétricos forman un subanillo de $R[u\_1,\dots,u\_n]$. La aplicación $$\sigma\colon R[u\_1,\dots,u\_n]\rightarrow R[u\_1,\dots,u\_n]$$ definida arriba es, por el principio de sustitución, el único homomorfismo de anillos tal que $\sigma\_{|\_R}$ es la inlcusión $R\subset R[u\_1,\dots,u\_n]$ y $\sigma(u\_i)=u\_{\sigma(i)}$. Dadas $\sigma,\tau\in S_n$ y $f\in R[u\_1,\dots,u\_n]$, $$\sigma(\tau(f))=(\sigma\tau)(f),$$
por tanto el producto de permutaciones se corresponde con la composición de los homomorfismos inducidos. En particular, estos últimos son automorfismos ya que el inverso de $\sigma$ será el definido por la permutación inversa $\sigma^{-1}$. Aquí usamos que la permutación identidad induce la identidad. 
{{% /remark %}}


{{% definition %}}
Los **polinomios simétricos** o **funciones simétricas elementales** en $n$ variables $s\_i\in R[u\_1,\dots,u\_n]$ son:
$$
\begin{array}{rcl}
s\_1&=&\displaystyle \sum\_{1\leq i\leq n}u\_i=u\_1+u\_2+\cdots+u\_n,\cr
s\_2&=&\displaystyle \sum\_{1\leq i < j\leq n}u\_iu\_j=u\_1u\_2+u\_1u\_3+\cdots+u\_{n-1}u\_n,\cr
s\_3&=&\displaystyle \sum\_{1\leq i < j < k\leq n}u\_iu\_ju\_k=u\_1u\_2u\_3+\cdots+u\_{n-2}u\_{n-1}u\_n,\cr
&\vdots&\cr
s\_n&=&u\_1\cdots u\_n.
\end{array}
$$
Es decir, para cada $1\leq j\leq n$,
$$
s\_j=\sum_{1\leq i\_1<\cdots<i\_j\leq n}u\_{i\_1}\cdots u\_{i\_j}.
$$
{{% /definition %}}

{{% remark %}}
Las funciones simétricas elementales en $n$ variables son, salvo signo, los coeficientes del polinomio
$$
\begin{array}{rcl}
P(x)&=&(x-u\_1)\cdots (x-u\_n)\cr
&=&x^n-s\_1x^{n-1}+s\_2x^{n-2}-\cdots+(-1)^ns\_n\cr
&=&\displaystyle \sum\_{i=0}^n(-1)^is\_ix^{n-i}.
\end{array}
$$
En la última línea denotamos $s_0=1$.

En particular, dado un polinomio mónico $f\in F[x]$ degrado $n$ 
$$
\begin{array}{rcl}
P(x)&=&x^n-a\_1x^{n-1}+a\_2x^{n-2}-\cdots+(-1)^na\_n\cr
&=&\displaystyle \sum\_{i=0}^n(-1)^ia\_ix^{n-i}\cr
&=&(x-\alpha\_1)\cdots (x-\alpha\_n)
\end{array}
$$
con $a\_0=1$, cuyas $n$ raíces complejas denotamos $\alpha\_i$, sus coeficientes se obtienen al aplicarle las funciones simétricas elementales a estas raíces,
$$a\_i=s\_i(\alpha\_1,\dots,\alpha\_n).$$
{{% /remark %}}



{{% theorem name="de las funciones simétricas" %}}
Dado un polinomio simétrico $g\in R[u\_1,\dots,u\_n]$, existe un único polinomio $G\in R[z\_1,\dots,z\_n]$ tal que $g=G(s\_1,\dots,s\_n)$.
{{% /theorem %}}

{{% proof %}}
Por doble inducción, primero en el número de variables y luego en el grado. 

Para una sola variable, el resultado es obviamente cierto par cualquier grado ya que $s\_1=u\_1$ y basta tomar $G=g(z\_1)$. También es obvio para polinomios de grado $0$. Supongamos que es cierto para polinomios de hasta $n-1$ variables. 

Consideramos el polinomio $g_0=g(u\_1,\dots,u\_{n-1},0)$. Por hipótesis de inducción existe $G_0\in R[z\_1,\dots,z\_{n-1}]$ tal que $g\_0=G\_0(s'\_1,\dots,s'\_{n-1})$, donde las $s\_i'\in R[u\_1,\dots,u\_{n-1}]$ son las funciones simétricas elementales en $n-1$ variables. El polinomio 
$$p(u\_1,\dots,u\_n)=g(u\_1,\dots,u\_n)-G_0(s\_1,\dots,s\_{n-1})$$
es simétrico pues los polinomios simétricos forman un subanillo de $R[u\_1,\dots,u\_n]$. Por construcción, 
$$p(u\_1,\dots,u\_{n-1},0)=g\_0-G\_0(s'\_1,\dots,s'\_{n-1})=0$$
así que $u\_n|p$. Como $p$ es simétrico, esto implica que $u\_i|p$ para todo $1\leq i\leq n$, así que $s\_n=u\_1\cdots u\_n|p$. Ha de existir por tanto un polinomio $h\in R[u\_1,\dots,u\_n]$ tal que $p=s\_nh$. Al ser $p$ y $s\_n$ simétricos, $h$ es también simétrico. Como $h$ es de menor grado que $g$, por hipótesis de inducción existe $H\in R[z\_1,\dots,z\_n]$ tal que $h=H(s\_1,\dots,s\_n)$. Al ser 
$$
\begin{array}{rcl}
g&=&p+G  _0(s\_1,\dots,s\_{n-1})\cr
&=&s\_nH(s\_1,\dots,s\_n)+G_0(s\_1,\dots,s\_{n-1})
\end{array}$$
podemos tomar $G=z\_nH+G\_0$.
{{% /proof %}}

{{% definition %}}
El **discriminante** en $n$ variables es el polinomio 
$$D=\prod_{1\leq i<j\leq n}(u\_i-u\_j)^2=(u\_1-u\_2)^2\cdots(u\_{n-1}-u\_n)^2.$$
{{% /definition %}}

{{% remark %}}
El discriminante es simétrico y, dados $\alpha\_1, \dots,\alpha_n$, tenemos que $D(\alpha\_1, \dots,\alpha_n)$ si y solo si $\alpha\_i=\alpha\_j$ para ciertos $i\neq j$. Denotaremos $\Delta\in R[z\_1,\dots,z\_n]$ al único polinomio tal que $D=\Delta(s\_1,\dots,s\_n)$.
{{% /remark %}}

{{% example name="Discriminantes en pocas variables" %}}
Para $n=1$ el discriminante es $D=1$. Si $n=2$, entonces
$$
\begin{array}{rcl}
D&=&(u\_1-u\_2)^2\cr
&=&(u\_1+u\_2)^2-4u\_1u\_2\cr
&=&s\_1-4s\_2.
\end{array}
$$
Recuerda que el discriminante de un polinomio de grado $2$ $$x^2-a\_1x+a\_2=(x-\alpha\_1)(x-\alpha\_2)$$ es $$a\_1^2-4a\_2=\Delta(a\_1,a\_2)=D(\alpha\_1,\alpha\_2).$$
{{% /example  %}}

{{% lemma %}}
Dado $p\_1\in R[u\_1,\dots,u\_n]$, si $\\{p\_1,\dots,p\_l\\}$ es su órbita y $h\in R[w\_1,\dots,w\_l]$ es simétrico entonces $h(p\_1,\dots,p\_l)\in R[u\_1,\dots,u\_n]$ también es simétrico.
{{% /lemma %}}

{{% proof %}}
Tomemos $\tau\in S_n$. Como la órbita es $$S=\\{\sigma(p\_1) \mid \sigma\in S_n\\}$$ y $\tau(\sigma(p\_i))=(\tau\sigma)(p\_1)\in S$, deducimos que $\tau(S)\subset S$. Es más, como $\tau\colon R[u\_1,\dots,u\_n]\rightarrow R[u\_1,\dots,u\_n]$ es un automorfismo, $\tau\_{|\_S}$ es una permutación de $S$. Por tanto, ha de existir $\tau'\in S_l$ tal que $$\tau(p\_i)=p\_{\tau'(i)}$$ para todo $i$. Entonces tenemos que 
$$
\begin{array}{rcl}
\tau(h(p\_1,\dots,p\_l))&=&h(\tau(p\_1),\dots,\tau(p\_l))\cr
&=&h(p\_{\tau'(1)},\dots,p\_{\tau'(l)})\cr
&=&\tau'(h)(p\_1,\dots,p\_l)\cr
&=&h(p\_1,\dots,p\_l)
\end{array}
$$
por ser $h$ simétrica.
{{% /proof %}}

{{% theorem name="de descomposición" %}}
Si $K$ es el cuerpo de descomposición de $f\in F[x]$ y $g\in F[x]$ es mónico e irreducible y posee una raíz en $K$ entonces todas las raíces complejas de $g$ están en $K$.
{{% /theorem %}}

{{% proof %}}
Sean $\alpha\_1,\dots,\alpha\_n$ las raíces complejas de $f$ y $\beta\_1$ la raíz de $g$ que está en $K$. Como $\beta\_1\in K=F[\alpha\_1,\dots,\alpha\_n]$, existe $p\_1\in F[u\_1,\dots,u\_n]$ tal que $\beta\_1=p\_1(\alpha\_1,\dots,\alpha\_n)$. Sea $\\{p\_1,\dots,p\_l\\}$ la órbita de $p\_1$ y $\beta\_i=p\_i(\alpha\_1,\dots,\alpha\_n)\in K$, $1\leq i\leq l$. 

Nuestro objetivo ahora es probar que las raíces complejas de $g$ están entre los $\beta\_1,\dots,\beta\_l\in K$. Para ello consideramos el polinomio 
$$h(x)=(x-\beta\_1)\cdots (x-\beta\_l).$$
Supongamos que hemos probado que $h$ tiene coeficientes en $F$. Como $g$ es el polinomio irreducible de $\beta\_1$ sobre $F$ y $\beta\_1$ también es raíz de $h$, deduciremos que $g|h$ en $F[x]$, así que las raíces de $g$ están entre las de $h$, que es lo que nos habíamos propuesto demostrar.

Para ver que $h$ tiene coeficientes en $F$, tomamos las funciones simétricas elementales $s'\_1,\dots, s'\_l$ en $l$ nuevas variables $w\_1,\dots,w\_l$. Los coeficientes de $h$ son los 
$$s'\_i(\beta\_1,\dots,\beta\_l)=s'\_i(p\_1(\alpha\_1,\dots,\alpha\_n),\dots,p\_l(\alpha\_1,\dots,\alpha\_n)).$$ 
Los polinomios $s'\_i(p\_1,\dots,p\_l)\in F[u\_1,\dots,u\_n]$ son simétricos en las $n$ variables $u\_1,\dots,u\_n$ por el lema anterior. Por el teorema de las funciones simétricas, existen $G\_1,\dots, G\_l\in F[z\_1,\dots,z\_n]$ tales que $G\_i(s\_1,\dots,s\_n)=s'\_i(p\_1,\dots,p\_l)$. Aquí $s\_i\in F[u\_1,\dots,u\_n]$ son las funciones simétricas en las $n$ variables $u\_1,\dots,u\_n$. Así que los coeficientes de $h$ son
$$
G\_i(s\_1(\alpha\_1,\dots,\alpha\_n),\dots,s\_n(\alpha\_1,\dots,\alpha\_n)).
$$
Sabemos que $s\_i(\alpha\_1,\dots,\alpha\_n)\in F$ pues son los coeficientes de $f$. Como los $G\_i$ también tiene coeficientes en $F$, deducimos de la fórmula anterior que los coeficientes de $h$ están en $F$.
{{% /proof %}}

{{% definition %}}
Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$, la **órbita** de $\alpha\in K$ por $H$ es 
$$\\{f(\alpha)\mid f\in H\\}.$$
{{% /definition %}}

{{% theorem %}}
Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$, si $\\{\beta\_1,\dots,\beta\_l\\}$ es la órbita de $\beta\_1$ por $H$ entonces el polinomio irreducible de $\beta\_1$ sobre $K^H$ es $$g(x)=(x-\beta\_1)\cdots (x-\beta\_l).$$
En particular $\beta\_1$ es algebraico y su grado es el número de elementos de su órbita.
{{% /theorem %}}

{{% proof %}}
Cada $f\in H$ induce una permutación de $\\{\beta\_1,\dots,\beta\_l\\}$. Los coeficientes de $g$ son funciones simétricas elementales evaluadas en los $\beta\_i$, por tanto no varían al aplicar $f\in H$. Esto demuestra que estos coeficientes están en $K^H$. 

Sea $h\in K^H[x]$ un polinomio que tenga $\beta\_1$ como raíz. Todo elemento de $f\in H\subset G(K/K^H)$ envía raíces de un polinomio con coeficientes en $K^H$ en otras raíces, por tanto toda la órbita $\\{\beta\_1,\dots,\beta\_l\\}$ está formada por raíces de $h$. Esto prueba que $g|h$ en $K[x]$ y por tanto también en $K^H[x]$. Es lo último que faltaba para demostrar el teorema.
{{% /proof %}}

{{% definition %}}
Una extensión $F\subset K$ es **algebraica** si todo elemento de $K$ es algebraico sobre $F$.
{{% /definition %}}

Hemos visto que las extensiones finitas son algebraicas. El recíproco no es cierto en general, pero sí bajo ciertas hipótesis.

{{% lemma %}}
Si $F\subset K$ es una extensión algebraica y el grado de los elementos de $K$ sobre $F$ está uniformemente acotado entonces la extensión es finita.
{{% /lemma %}}

{{% proof %}}
Vamos a probar que si no fuera finita entonces existirían elementos de grado arbitrariamente grande. Para ello construimos una sucesión estrictamente creciente de extensiones intermedias
$$F=F\_0\subsetneq F\_1\subsetneq F\_2\subsetneq\cdots\subsetneq K$$
tales que $F\_{i-1}\subsetneq F\_i$ es finita del siguiente modo. Supuesto construido hasta $F\_{n-1}$, tomamos un elemento $\alpha\_n\in K\setminus F\_{n-1}$ y definimos $F\_n=F\_{n-1}[\alpha\_n]$. Como $\alpha\_n$ es algebraico sobre $F$, también lo es sobre $F\_{n-1}$, así que $F\_{n-1}\subsetneq F\_n$ es finita, y en consecuencia $F\subsetneq F\_n$ también, así que $F\_n\subsetneq K$. Por la fórmula del grado para extensiones intermedias $[F\_n:F]\geq 2^n$, así que cualquier elemento primitivo de $F\subsetneq F\_n$ tiene grado $\geq 2^n$.
{{% /proof %}}

{{% theorem name="del cuerpo fijo" %}}
Dada una extensión $F\subset K$ y un subgrupo finito $H\subset G(K/F)$, $K^H\subset K$ es una extensión finita de grado $[K:K^H]=|H|$.
{{% /theorem %}}

{{% proof %}}
Hemos visto en el teorema anterior que la extensión $K^H\subset K$ es algebraica. Es más, el grado de cualquier elemento es el número de elementos de una órbita, por tanto $\leq |H|$. El lema anterior implica pues que $K^H\subset K$ es finita. Sea $\gamma\in K$ un elemento primitivo, $K=K^H[\gamma]$. Cualquier $f\in H$ dejan fijo a $K^H$, así $f,g\in H$ son iguales si y solo si $f(\gamma)=g(\gamma)$. Esto demuestra que la órbita de $\gamma$ tiene $|H|$ elementos. Este es por tanto el grado de $\gamma$ sobre $K^H$, que es igual a $[K,K^H]$ por ser un elemento primitivo.
{{% /proof %}}

{{% corollary %}}
Si $F\subset K$ es una extensión finita entonces $G(K/F)$ es un grupo finito y $|G(K/F)|$ divide a $[K:F]$.
{{% /corollary %}}

{{% proof %}}
Como $F\subset K^{G(K/F)} \subset K$ es una extensión intermedia, 
$|G(K/F)|=[K,K^{G(K/F)}]$ divide a $[K:F]$.
{{% /proof %}}


## Extensiones de Galois

{{% definition %}}
Una extensión finita $F\subset K$ es de **Galois** si $|G(K/F)|=[K:F]$.
{{% /definition %}}

{{% lemma %}}
Dada una extensión finita $F\subset K$ y un subrgupo $H\subset G(K/F)$, la extensión $K^H\subset K$ es de Galois y $H=G(K/K^H)$.
{{% /lemma %}}

{{% proof %}}
Sabemos que, en general, $H\subset G(K/K^H)$ es un subgrupo, así que $|H|\leq |G(K/K^H)|$. También sabemos que $|G(K/K^H)|$ divide a $[K:K^H]=|H|$, así que tenemos también la otra desigualdad $|G(K/K^H)|\leq|H|$. Esto prueba que $H=G(K/K^H)$, por tanto esta extensión es de Galois.
{{% /proof %}}

{{% lemma %}}
Sea $F\subset K=F[\gamma\_1]$ una extensión finita, $g\in F[x]$ es el polinomio irreducible de $\gamma\_1$ y $\gamma\_1,\dots,\gamma\_r\in K$ las distintas raíces de $g$ en este cuerpo. Para cada $1\leq i\leq n$ existe un único $f\_i\in G(K/F)$ tal que $f\_i(\gamma\_1)=\gamma\_i$. Es más, $G(K/F)=\\{f\_1,\dots,f\_r\\}$.
{{% /lemma %}}

{{% proof %}}
Todos los $\gamma\_i$ poseen el mismo grado sobre $F$ ya que tienen el mismo polinomio irreducible $g$, por tanto $K=F[\gamma\_i]$ para todo $i$. Sabemos que, para cada $i$, hay un único isomorfismo $$h\_i\colon \frac{F[x]}{(g)}\cong K$$ que deja fijo a $K$ tal que $h(\bar{x})=\gamma\_i$. Por tanto, $f\_i=h\_ih\_1^{-1}\in G(K/F)$ es el único que satisface la propiedad del enunciado. Todo elemento $f\in G(K/F)$  está determinado por $f(\gamma\_1)$ y además preserva raíces de $g\in F[x]$, así que $G(K/F)$ consta necesariamente de los $f\_i$ anteriores.
{{% /proof %}}

{{% theorem %}}
Dada una extensión finita $F\subset K$, los siguientes enunciados son equivalentes:

1. $F\subset K$ es de Galois.
2. $F=K^{G(K/F)}$.
3. $K$ es el cuerpo de descomposición de un polinomio de $F[x]$.
{{% /theorem %}}

{{% proof %}}
Veamos $1.\Leftrightarrow 2.$ Por el teorema del cuerpo fijo, $|G(K/F)|=[K:K^{G(K/F)}]$. Como $F\subset K^{G(K/F)}\subset K$, $|G(K/F)|=[K:F]$ si y solo si $F=K^{G(K/F)}$.

Probemos ahora que $1.\Leftrightarrow 3.$ Sea $\gamma\_1\in K$ un elemento primitivo de $F\subset K$, $g\in F[x]$ su polinomio irreducible y $L$ el cuerpo de descomposición de $g$. Sean $\gamma\_1,\dots,\gamma\_n\in \mathbb{C}$ las distintas raíces complejas de $g$, de las cuales $\gamma\_1,\dots,\gamma\_r\in K$ y el resto no están en $K$. Denotemos $n=[G:K]$. El grado de $g$ es $n$. Como $K=F[\gamma\_1]$ y $L=F[\gamma\_1,\dots,\gamma\_n]$, $F\subset K\subset L$. Usando el lema anterior vemos que
$F\subset K$ es de Galois $\Leftrightarrow$ $r=n$ $\Leftrightarrow$ todas las raíces complejas de $g$ están en $K$ $\Leftrightarrow$ $K\supset L$ $\Leftrightarrow$ $K=L$ $\Leftrightarrow$ $K$ es un cuerpo de descomposición. En el último paso hemos usado que $g$ tiene una raíz en $K$.
{{% /proof %}}

{{% corollary %}}
Toda extensión finita $F\subset K$ es una extensión intermedia $F\subset K\subset L$ de una extensión de Galois $F\subset L$.
{{% /corollary %}}

{{% proof %}}
Basta tomar $L$ como el cuerpo de descomposición de un elemento primitivo de $F\subset K$.
{{% /proof %}}

{{% corollary %}}
Si $F\subset K$ es una extensión de Galois y $F\subset L\subset K$ es una extensión intermedia entonces $L\subset K$ también es de Galois.
{{% /corollary %}}

{{% proof %}}
Basta observar que si $K$ es el cuerpo de descomposición de $g\in F[x]$ entonces también es el cuerpo de descomposición de del mismo polinomio visto como polinomio con coeficientes en $L$, $g\in L[x]$.
{{% /proof %}}

{{% theorem name="fundamental de la teoría de Galois" %}}
Dada una extensión de Galois $F\subset K$, las siguientes aplicaciones son biyectivas y mutuamente inversas: $$\begin{array}{rcl}\left\\{\text{ext. intermedias }F\subset L\subset K\right\\}&\longleftrightarrow& \left\\{\text{subgrupos }H\subset G(K/F)\right\\},\cr L&\mapsto&G(K/L),\cr K^H&\leftarrow&H.\end{array}$$ 
{{% /theorem %}}

{{% proof %}}
Dado un subgrupo $H\subset G(K/F)$, ya hemos probado en un lema anterior que $H=G(K/K^H)$, así que la composición que empieza y acaba en la derecha es la identidad. Dada ahora una extensión intermedia $F\subset L\subset K$, acabamos de probar que $L\subset K$ es de Galois, así que por el teorema anterior $K^{G(K/L)}=L$.
{{% /proof %}}

{{% remark %}}
Observa que la correspondencia dada en el Teorema Fundamental da la vuelta a las inclusiones. Es decir, dados dos subgrupos $H'\subset H\subset G(K/F)$ tenemos que $K^{H'}\supset K^H$ y dadas extensiones intermedias $F\subset L\subset L'\subset K$ tenemos que $G(K/L)\supset G(K/L')$. El subgrupo trivial se corresponde con $K$ y el total con $F$.
{{% /remark %}}

{{% corollary %}}
Toda extensión finita $F\subset K$ posee una cantidad finita de extensiones intermedias.
{{% /corollary %}}

{{% proof %}}
Cuando la extensión es de Galois el resultado es cierto porque el grupo $G(K/F)$, que es finito, tiene una cantidad finita de subgrupos, que se corresponden con las extensiones intermedias. Si $F\subset K$ no fuera de Galois, basta tomar $F\subset K\subset L$ con $F\subset L$ de Galois y observar que toda extensión intermedia de $F\subset K$ lo es también de $F\subset L$.
{{% /proof %}}

{{% theorem %}}
Dada una extensión de Galois $F\subset K$ y una extensión intermedia $F\subset L\subset K$, $F\subset L$ es de Galois si y solo si el subgrupo $G(K/L)\subset G(K/F)$ es normal. En dicho caso $$\frac{G(K/F)}{G(K/L)}\cong G(L/F).$$
{{% /theorem %}}

{{% proof %}}
Comenzaremos probando la equivalencia de la primera parte del enunciado.

Sea $\gamma\_1\in L$ un elemento primitivo, $L=F[\gamma\_1]$, con polinomio irreducible $g\in F[x]$. Sean $\gamma\_1,\dots,\gamma\_r\in K$ sus raíces complejas, que están en $K$ porque es un cuerpo de descomposición y $\gamma\_1\in K$.

$\Rightarrow$  Por ser $F\subset L$ de Galois, $L$ es el cuerpo de descomposición de $g$, así que $L=F[\gamma\_1,\dots,\gamma\_r]$. Todo $f\in G(K/L)$ preserva raíces de $g$, por tanto se restringe $f\_{|\_{L}}\colon L\rightarrow L$ y esta restricción está determinada por $f(\gamma\_1)$ que será algún $\gamma\_i$. En particular $f\_{|\_{L}}$ es la identidad si y solo si $f(\gamma\_1)=\gamma\_1$. 

Sea $h\in G(K/L)$ un elemento cualquiera. Para ver que este grupo es normal tenemos que probar que $f^{-1}hf\in G(K/F)$ deja fijo a $L$ y por tanto $f^{-1}hf\in G(K/L)$, es decir, que hay que probar que $(f^{-1}hf)(\gamma\_1)=1$. Esto es cierto porque $h$ deja fijo a $L$, así que 
$$
\begin{array}{rcl}
(f^{-1}hf)(\gamma\_1)&=&f^{-1}(h(f(\gamma\_1)))\cr
&=&f^{-1}(h(\gamma\_i))\cr
&=&f^{-1}(\gamma\_i)\cr
&=&\gamma\_1.
\end{array}
$$

$\Leftarrow$ Si $F\subset L$ no fuera de Galois no podría ser el cuerpo de descomposición de $g$, así que alguna raíz de $g$ no estaría en $L$. Supongamos que $\gamma\_i$ es tal raíz. Como $L=K^{G(K/L)}$ y $\gamma\_i\notin L$, existe $h\in G(K/L)$ tal qye $h(\gamma\_i)\neq\gamma\_i$. Es más, como $F=K^{G(K/F)}$, las raíces de $g$ son la órbita de $\gamma\_1$ por $G(K/F)$, así que existe $f\in G(K/F)$ tal que $f(\gamma\_1)=\gamma\_i$. El elemento $f^{-1}hf\in G(K/F)$ no puede dejar fijo a $\gamma\_1$ ya que de lo contrario $\gamma\_i=f(\gamma\_1)=hf(\gamma\_1)=h(\gamma\_i)\neq\gamma\_i$. Esto implica que $f^{-1}hf$ no deja fijo a $L$, luego $f^{-1}hf\in G(K/L)$.

Una vez establecida la equivalencia de la primera parte del enunciado, demostraremos el isomorfismo de la segunda. Supongamos pues que $F\subset L$ es de Galois. Hemos visto que entonces todo $f\in G(K/F)$ se restringe a $L$, es decir $f\_{|\_{L}}\in G(L/F)$. Esta restricción induce un homomorfismo de grupos
$$
\begin{array}{rcl}
G(K/F)&\longrightarrow&G(L/F),\cr
f&\mapsto&f\_{|\_{L}}.
\end{array}
$$
Obviamente $G(K/L)$ está contenido en el núcleo de este homomorfismo ya que los elementos de $G(K/L)$ se restringen a la identidad sobre $L$. Este homomorfismo es sobreyectivo porque $G(L/F)$ tiene $r$ elementos, uno por cada raíz $\gamma\_i$ de $g$ determinado por $\gamma\_1\mapsto\gamma\_i$, y además hemos visto que en $G(K/F)$ siempre hay elementos que satisfacen $\gamma\_1\mapsto\gamma\_i$. Por el primer teorema de isomorfía y el teorema de Lagrange, el número de elementos del núcleo núcleo es
$$
\frac{|G(K/F)|}{|G(L/F)|}=\frac{[K:F]}{[L:F]}=[K:L]=|G(K/L)|.
$$
Por tanto $G(K/L)$ es todo el núcleo y el isomorfismo del enunciado es el definido por el homomorfismo de restricción y el primer teorema de isomorfía,
$$
\begin{array}{rcl}
\frac{G(K/F)}{G(K/L)}&\stackrel{\cong}\longrightarrow&G(L/F),\cr
[f]&\mapsto&f\_{|\_{L}}.
\end{array}
$$
{{% /proof %}}


## Extensiones ciclotómicas

Dado $n\geq 1$, las **raíces $n$-ésimas de la unidad** son las $n$ raíces complejas diferentes del polinomio $$x^n-1$$, $$e^{\frac{2\pi i t}{n}}, \qquad 0\leq t{<}n.$$
El conjunto formado por estos $n$ números complejos es un grupo cíclico de orden $n$ para la multiplicación, generado por la **raíz $n$-ésima primitiva**, $$\zeta=\zeta_n=e^{\frac{2\pi i}{n}}.$$ Si $n=p$ es primo, cualquier raíz distinta de $1$ genera estre grupo.

{{% proposition %}}
 Dado un entero primo $p\geq 1$, la extensión $\mathbb Q\subset\mathbb Q[\zeta]$ es de Galois, de grado $p-1$ y su grupo de Galois es cíclico.
{{% /proposition %}}


{{% proof %}}
 El cuerpo de descomposición de $x^p-1$ es $$\mathbb Q[1,\zeta,\dots,\zeta^{p-1}]=\mathbb Q[\zeta].$$ En efecto $\supset$ es obvio y $\subset$ es consecuencia de que como $\zeta\in\mathbb Q[\zeta]$ entonces todas las potencias $\zeta^n\in \mathbb Q[\zeta]$ también. Esto demuestra que $\mathbb Q[\zeta]$ es de Galois.

Sabemos que $$x^p-1=(x-1)q(x)$$ donde $$q(x)=x^{p-1}+\cdots+x+1$$ es el $p$-ésimo polinomio ciclotómico, que es irreducible. Como $\zeta\neq 1$, $\zeta$ ha de ser raíz de $q(x)$, así que el grado de la extensión es $p-1$. 

Para ver que el grupo de Galois es cíclico, definimos un homomorfismo
$$\psi\colon G(\mathbb Q[\zeta]/\mathbb Q)\longrightarrow (\mathbb Z/(p))^\times$$ que llega al grupo $(\mathbb Z/(p))^\times$ de unidades del cuerpo $\mathbb Z/(p)$. Este último grupo es conocido que es cíclico de orden $p-1$. Todo $f\in G(\mathbb Q[\zeta]/\mathbb Q)$ preserva raíces de $q(x)$, así que $$f(\zeta)=\zeta^i$$ para cierto $0{<}i{<}p$ único y dependiente de $f$. Definimos $$\psi(f)=\bar i.$$ Acabamos de probar que esta aplicación está bien definida. Veamos ahora que es un homomorfismo. Dado $g\in G(\mathbb Q[\zeta]/\mathbb Q)$, hay un único $0{<}j{<}p$ tal que $$g(\zeta)=\zeta^j$$ y que define $\psi(g)=\bar j$. Entonces
$$\begin{array}{rcl}
(f\circ g)(\zeta)&=&f(g(\zeta))\cr
&=&f(\zeta^j)\cr
&=&f(\zeta)^j\cr
&=&(\zeta^i)^j\cr
&=&\zeta^{ij}.
\end{array}$$
Por tanto
$$\begin{array}{rcl}
\psi(f\circ g)&=&\overline{ij}\cr
&=&\bar{i}\bar{j}\cr
&=&\psi(f)\psi(g).
\end{array}$$
Además, $$\operatorname{id}\_{\mathbb Q[\zeta]}(\zeta)=\zeta$$ por lo que $$\psi(\operatorname{id}\_{\mathbb Q[\zeta]})=1.$$ Esto termina de dedmostrar que $\psi$ es un homomorfismo.

Veamos que $\psi$ es inyectivo. Si $f\in G(\mathbb Q[\zeta]/\mathbb Q)$ es tal que $$\psi(f)=\bar 1$$ es porque $$f(\zeta)=\zeta.	$$

  {{% /proof %}}


## Extensiones de Kummer

En esta sección y en las siguientes supondremos que todos los cuerpos que manejemos están contenidos en $\mathbb C$. Dado un cuerpo $F$, nuestro objetivo es estudiar el cuerpo de descomposición $K$ del polinomio $$q(x)=x^p-a\in F[x]$$ donde $p$ es primo y $a$ no tiene raíces $p$-ésmas en $F$. La **raíz $p$-ésima primitiva de la unidad** es $$\zeta\_p=e^{\frac{2\pi i}{p}}\in\mathbb C.$$ Las raíces $p$-ésimas de la unidad son las potencias de $\zeta\_p$, que forman un grupo cíclico de orden $p$ restecto de la multiplicación, $$1,\zeta\_p,\dots,\zeta\_p^{p-1}.$$ Por tanto si $\alpha$ es una raíz compleja de $q(x)$ el conjunto de todas sus raíces es $$\alpha,\zeta\_p\alpha,\dots,\zeta\_p^{p-1}\alpha.$$ En particular si $\zeta\_p\in F$ entonces $K=F[\alpha]$.

{{% proposition %}}
 Si $F\subset \mathbb C$ es un subcuerpo tal que $\zeta\_p\in F$ y $p(x)=x^p-a\in F[x]$ no tiene raíces en $F$ entonces el cuerpo de descomposición $K$ de $p(x)$ tiene grado $p$ sobre $F$. 
{{% /proposition %}}


{{% proof %}}
 Hemos observado que $K=F[\alpha]$ y $\alpha$ es una raíz de $p(x)$, que es de grado $p$, por tanto $[K:F]\leq p$. Al ser $F\subset K$ de Galois, para probar la otra desigualdad bastará ver que $|G(K/F)|\geq p$. 

Como $\alpha\notin F$ y $F= K^{G(K/F)}$, ha de existir algún $f\in G(K/F)$ tal que $f(\alpha)\neq\alpha$. Como $f$ preserva raíces de polinomios en $F[x]$, $f(\alpha)=\zeta\_p^i\alpha$ para cierto $0{<}i{<}p$. Usaremos esto para ver que las potencias $f^j$ de $f$ son diferentes para todo $0\leq j{<}p$, así que $G(K/F)$ tiene al menos $p$ elementos. Para ello basta comprobar que cada una de estas potencias $f^j$ manda $\alpha$ a un elemento diferente. Vamos a probar por inducción que $$f^j(\alpha)=(\zeta\_p^{i})^{j}\alpha.$$ Todos estos elementos son diferentes ya que al ser $p$ primo todas las potencias de $\zeta\_p$ distintas de $1$, por ejempo $\zeta\_p^i$, tienen orden multiplicativo $p$, así que todos los $(\zeta\_p^i)^{j}$ son diferentes para $0\leq j{<}p$. Para $j=1$ la ecuación anterior es cierta. Si es cierta para $j-1$ entonces
$$\begin{array}{rcl}
f^j(\alpha)&=&f(f^{j-1}(\alpha))\cr
&=&f((\zeta\_p^{i})^{j-1}\alpha)\cr
&=&(f(\zeta\_p)^{i})^{j-1}f(\alpha)\cr
&=&(\zeta\_p^{i})^{j-1}\zeta\_p^i\alpha\cr
&=&(\zeta\_p^{i})^{j}\alpha.
\end{array}$$
Aquí hemos usado que $f(\zeta\_p)=\zeta\_p$ ya que $\zeta\_p\in F$.
{{% /proof %}}


Sorprendentemente el resultado a anterior tiene un recíproco.

{{% theorem %}}
 Si $F\subset \mathbb C$ es un subcuerpo tal que $\zeta\_p\in F$ y $F\subset K$ es una extensión de Galois de grado $[K:F]=p$ primo entonces $K=F[\alpha]$ para cierto $\alpha\in K$ que es raíz de un polinomio de la forma $x^n-a\in F[x]$. 
{{% /theorem %}}


{{% proof %}}
 Al ser la extensión de Galois $|G(K/F)|=[K:F]=p$, por tanto $G(K/F)$ es cíclico de orden $p$, así que todo $f\in G(K/F)$ distinto de la identidad genera el grupo de Galois, $$G(K/F)=\\{f^0,f^1,\dots, f^{p-1}\\}.$$ 

Ahora vamos a concentrarnos en el hecho de que $f$ es un homomorfismo de $F$-espacios vectoriales. Como $f^p=\operatorname{id}_K$ tenemos que cualquier autovalor $\lambda$ de $f$ satisface $\lambda^p=1$. Además $f$ es diagonalizable, pues niguna potencia de una caja de Jordan de tamaño $2\times 2$ o superior es la matriz identidad. Como $f$ es diagonalizable y distinto de la identidad, tendrá que tener algún autovalor $\lambda\neq 1$. Este autovalor ha de ser forzosamente de la forma $\lambda =\zeta\_p^i$ para cierto $0{<}i{<}p$. 

Sea $\alpha\in K$ un autovector asociado a $\zeta\_p^i$, $$f(\alpha)=\zeta\_p^i\alpha.$$  Tenemos entonces que
$$\begin{array}{rcl}
f(\alpha^p)&=&f(\alpha)^p\cr
&=&(\zeta\_p^i\alpha)^p\cr
&=&(\zeta\_p^i)^p\alpha^p\cr
&=&\alpha^p.
\end{array}$$
Se deduce por inducción que $f^i(\alpha^p)=\alpha^p$ para todo $i\geq 1$, por tanto $\alpha^p\in K^{G(K/F)}=F$. Esto demuestra que $\alpha\in K$ es raíz del polinomio $x^p-\alpha^p\in F[x]$. Además, como $f(\alpha)\notin \alpha$ entonces $\alpha\notin F$ así que $F\subsetneq F[\alpha]\subset K$  y como $[K:F]=p$ es primo concluimos que $K=F[\alpha]$.
{{% /proof %}}


Las extensiones del tipo que hemos estudiado en esta sección se denominan **extensiones de Kummer**.

## Solubilidad por radicales

{{% definition %}}
Una extensión $F\subset K$ es una **extensión por radicales** si hay una sucesión finita de extensiones $$F=F\_0\subset F\_1\subset\cdots\subset F\_n=K$$ tales que $F\_{i+1}=F\_i[\alpha\_i]$ donde $\alpha\_i$ es es raíz de un polinomio de la forma $x^{p\_i}-a\_i\in F\_i[x]$ con $p\_i$ es primo, $i=0,\dots,p-1$. 
{{% /definition %}}


{{% watch %}}
 Observa que toda extensión por radicales es finita pues cada $F\_i\subset F\_{i+1}$ es finita de grado $\leq p\_i$ ya que $r\_i$ es raíz de un polinomio de grado $p\_i$ con coeficientes en $F\_i$. 
{{% /watch %}}


{{% definition %}}
 Dado un polinomio no nulo $p(x)\in F[x]$ decimos que la ecuación $p(x)=0$ se puede **resolver por radicales** si existe una extensión por radicales de $F$ en la que $p(x)$ factoriza como producto de polinomios de grado $1$. 
{{% /definition %}}


{{% watch %}}
 Esto equivale a decir que hay una extensión por radicales de $F$ que contiene al cuerpo de descomposición de $p(x)$. 
{{% /watch %}}


{{% definition %}}
 Un grupo finito $G$ es **soluble** si existe una sucesión de subgrupos $$\\{1\\}=G\_0\subset G\_i\subset \cdots\subset G\_n=G$$ tal que $G\_i\subset G\_{i+1}$ es normal y $G\_{i+1}/G\_i$ es cíclico de orden $p\_i$ primo, $0\leq i{<}n$. 
{{% /definition %}}


{{% proposition %}}
 Toda extensión por radicales $F\subset K$ tiene grupo de Galois $G(K/F)$ soluble. 
{{% /proposition %}}


{{% proof %}}
   {{% /proof %}}


{{% theorem %}}
 Sea $F$ un cuerpo y $p(x)\in F[x]$ un polinomio con cuerpo de descomposición $K$. La ecuación $p(x)=0$ se puede resolver por radicales si y solo si $G(K/F)$ es soluble. 
{{% /theorem %}}


{{% proof %}}
 

$$\Rightarrow$$ 

  {{% /proof %}}

