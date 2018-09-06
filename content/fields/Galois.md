+++
title = "Teoría de Galois"
weight = 20
+++

En esta sección supondremos sin necesida de mencionarlo explícitamente que todos los cuerpos que consideremos son subcuerpos de $\mathbb C$.

## El Grupo de Galois

{{%  definition  %}}Dada una extensión $F\subset K$, su **grupo de Galois** $G(K/F)$ es el conjunto de los automorfismos de $F\subset K$. {{% /definition %}}

{{% ojo %}} La estructura de grupo del grupo de Galois es la composición. El elemento unidad es la identidad. El grupo de Galois de la extensión trivial es el grupo trivial $G(F/F)=\\{\operatorname{id}\_{F}\\}$. Recuerda que si la extensión $F\subset K$ es finita cualquier homomorfismo de extensiones $f\colon K\rightarrow K$ es un elemento de $G(K/F)$, y si además $F=\mathbb Q$ entonces nos vale cualquier homomorfismo de anillos $f$, pues todos preservan $\mathbb Q$. Recuerda también que todo elemento de $G(K/F)$ es además un isomorfismo de $F$-espacios vectoriales, pero no todo isomorfismo de $F$-espacios vectoriales $f\colon K\rightarrow K$ está en $G(K/F)$ ya que podría no preservar el producto en $K$, o incluso el $1$. Asimismo, recuerda que todo elemento de $G(K/F)$ preserva raíces de polinomios con coeficientes en $F$. {{% /ojo %}}

{{% example name="$G(\mathbb C/\mathbb R)$"   %}} Un homomorfismo de $\mathbb R$-espacios vectoriales $f\colon \mathbb C\rightarrow\mathbb C$ está determinado por la imagen de los elementos de una base, por ejemplo $\\{1,i\\}\subset\mathbb C$. Para que $f\in G(\mathbb C/\mathbb R)$ ha de ser un homomorfismo de anillos, así que debe satisfacer $f(1)=1$. También ha de preservar raíces en $\mathbb C$ de polinomios en $\mathbb R[x]$. Las raíces complejas de $x^2+1$ son $\pm i$, así que $f$ ha de cumplir $f=\pm i$. Por tanto los dos posibles elementos de $G(\mathbb C/\mathbb R)$ son los homomorfismos de $\mathbb R$-espacios vectoriales definidos por $$\begin{array}{rcl}f(1)&=&1,\cr f(i)&=&i,\end{array}$$ y por $$\begin{array}{rcl}f(1)&=&1,\cr f(i)&=&-i.\end{array}$$ Algunos de estos dos homomorfismos de $\mathbb R$-espacios vectoriales podría no estar en $G(\mathbb C/\mathbb R)$ pues podría no preservar el producto, pero ambos lo preservan porque claramente el primero es la identidad $\operatorname{id}\_{\mathbb C}$ y el segundo es la conjugación, que denotaremos $c$. Así que $G(\mathbb C/\mathbb R)=\\{\operatorname{id}\_{\mathbb C},c\\}$, que es un grupo cíclico de orden $2$ generado por la conjugación $c$, que satisface $c\circ c=\operatorname{id}_{\mathbb C}$. {{% /example %}}

{{% proposition   %}} Si $F\subset K$ es una extensión de grado $[K:F]=2$ entonces $K=F[\sqrt{\delta}]$ para cierto $\delta\in F$ y $G(K/F)=\\{\operatorname{id}_K,c\\}$ es un grupo cíclico de orden $2$ cuyo generador $c$ denominamos **conjugación** y satisface $c(\sqrt{\delta})=-\sqrt{\delta}$. {{% /proposition %}}

{{% proof %}} Como la extensión no es trivial, ha de existir algún $\alpha\in K$ tal que $\alpha\notin F$. El grado de este elemento ha de dividir a $2$. Como no puede ser $1$ porque $\alpha\notin F$, ha de ser $2$. La extensión $F\subset F[\alpha]$ también tiene grado $2$ y $F[\alpha]\subset K$ por tanto $K=F[\alpha]$. Si $x^2+ax+b\in F[x]$ es el polinomio irreducible de $\alpha$, entonces $$\alpha=\frac{-a\pm\sqrt{\delta}}{2}$$ donde $\delta=a^2-4b\in F$ es el **discriminante**. Deducimos por tanto que $\sqrt{\delta}\in K$, $\sqrt{\delta}\notin F$, y $K=F[\sqrt{\delta}]$. Sabemos que $\\{1,\sqrt{\delta}\\}\subset K$ es una base como $F$-espacio vectorial. Como cualquier $f\in G(K/F)$ preserva $1$ y las raíces de $x^2-\delta$, tenemos solo dos posibilidades:
$$\begin{array}{rcl}f(1)&=&1,\cr f(\sqrt{\delta})&=&\sqrt{\delta},\end{array}$$ y $$\begin{array}{rcl}f(1)&=&1,\cr f(\sqrt{\delta})&=&-\sqrt{\delta}.\end{array}$$ El primero es la identidad $\operatorname{id}\_{K}$, que es obviamente un isomorfismo de extensiones. El segundo es el que denominamos conjugación $c$. Dejamos como ejercicio probar que la conjugación es un homomorfismo de extensiones.  {{%  /proof %}}

{{% example name="$G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)$"   %}} Aquí $\sqrt[3]{2}$ denota la raíz cúbica de $2$ real por lo que $\mathbb Q[\sqrt[3]{2}]\subset\mathbb R$. El resto de raíces cúbicas de $2$ son puramente complejas. Cualquier $f\colon \in G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)$ ha de preservar las raíces de $x^3-2\in\mathbb Q[x]$. La única raíz de este polinomio que está en $\mathbb Q[\sqrt[3]{2}]$ es $\sqrt[3]{2}$, por tanto $f(\sqrt[3]{2})=\sqrt[3]{2}$. Una base de $\mathbb Q[\sqrt[3]{2}]$ como $\mathbb Q$-espacio vectorial está formada por las primeras tres potencias de $\sqrt[3]{2}$, es decir, $\\{1,\sqrt[3]{2},(\sqrt[3]{2})^2\\}$. Como $f(\sqrt[3]{2})=\sqrt[3]{2}$ ha de preservar la unidad y los productos, $f$ tiene que mandar cada uno de los elementos de esta base a sí mismo, así que necesariamente $f=\operatorname{id}_{\mathbb Q[\sqrt[3]{2}]}$, por tanto en este caso el grupo de Galois es el tivial, $G(\mathbb Q[\sqrt[3]{2}]/\mathbb Q)=\\{\operatorname{id}\_{\mathbb Q[\sqrt[3]{2}]}\\}$ a pesar de que la extensión $\mathbb Q\subset \mathbb Q[\sqrt[3]{2}]$ no es trivial, es de grado $3$. {{% /example %}}

{{%  definition  %}} Dado un cuerpo $F$ y un polinomio mónico no constante $p(x)\in F[x]$, un **cuerpo de descomposición** de $p(x)$ es una extensión $F\subset K$ tal que: 

* El polinomio $p(x)$ factoriza en $K[x]$ como $p(x)=(x-\alpha\_1)\cdots(x-\alpha\_n)$, $\alpha\_i\in K$.

* $K=F[\alpha\_1,\dots,\alpha\_n]$.

{{% /definition %}}

{{% ojo %}} Dado un cuerpo $F$, que suponemos $F\subset\mathbb C$, como todo polinomio de grado positivo en $\mathbb C[x]$ factoriza como producto de polinomios de grado $1$, todo polinomio mónico de grado positivo $p(x)\in F[x]$ tiene un único cuerpo de descomposición $K\subset \mathbb C$ que es $K=F[\alpha\_1,\dots,\alpha\_n]$, donde los $\alpha\_i$ son las raíces complejas de $p(x)$. {{% /ojo %}}

{{% proposition   %}} Toda extensión $F\subset K$ de grado $2$ es un cuerpo de descomposición. {{% /proposition %}}

{{% proof %}} Ya hemos visto que $K=F[\sqrt{\delta}]$ para cierto $\delta\in F$, entonces $K$ es el cuerpo de descomposición de $x^2-\delta$ ya que $F[\sqrt{\delta},-\sqrt{\delta}]=F[\sqrt{\delta}]$ y $x^2-\delta=(x+\sqrt{\delta})(x-\sqrt{\delta})\in K[x]$.  {{%  /proof %}}


El **grupo simétrico** de $n$ letras, es decir el **grupo de permutaciones** de $\\{1,\dots,n\\}$, se denotará $S\_n$. 

{{% proposition   %}} Dada una extensión $F\subset K$, si $K$ es el cuerpo de descomposición de un polinomio $p(x)\in F[x]$ con $n$ raíces distintas en $K$, entonces hay un único homomorfismo inyectivo $$\varphi\colon G(K/F)\longrightarrow S\_n$$ tal que, si $\alpha\_1,\dots,\alpha\_n\in K$ son la raíces de $p(x)$ en $K$ y $f\in G(K/F)$, la permutación $\varphi(f)=\sigma$ es la única que satisface la siguiente ecuación para todo $i=1,\dots,n$, $$f(\alpha\_i)=\alpha_{\sigma(i)}.$$ {{% /proposition %}}

{{% proof %}} Como $f$ preserva raíces de polinomios con coeficientes en $F$, $f$ ha de mandar el conjunto $\\{\alpha\_1,\dots,\alpha\_n\\}$ dentro de sí mismo. Además ha de hacerlo de manera biyectiva por ser $f$ un automorfismo, por tanto existe una única permutación $\sigma\in S\_n$ que satisface la ecuación del enunciado. Esto me permite definir la aplicación $\varphi$ de manera única. 

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

Comprobemos por último que $\varphi$ es inyectivo. Para ello debemos probar que si $f\in G(K/F)$ es tal que $\varphi(f)$ es le permutación identidad entonces $f=\operatorname{id}\_{K}$. Por definición $\varphi(f)$ es la permutación identidad si y solo si $f(\alpha\_i)=\alpha\_i$ para todo $i=1,\dots,n$. Como $K=F[\alpha\_1,\dots,\alpha\_n]$, todo elemento $\alpha\in K$ se puede escribir como polinomio en $\alpha\_1,\dots,\alpha\_n$ con coeficientes en $F$, es decir $$\alpha=\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}$$ para ciertos $b\_{m\_1,\dots,m\_n}\in F$, casi todos nulos. Entonces
$$\begin{array}{rcl}
f(\alpha)&=&f\left(\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}\right)\cr
&=&\sum\_{m\_i\geq 0} f(b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n})\cr
&=&\sum\_{m\_i\geq 0} f(b\_{m\_1,\dots,m\_n})f(\alpha\_1)^{m\_1}\cdots f(\alpha\_n)^{m\_n}\cr
&=&\sum\_{m\_i\geq 0} b\_{m\_1,\dots,m\_n}\alpha\_1^{m\_1}\cdots\alpha\_n^{m\_n}\cr
&=&\alpha,
\end{array}$$
así que $f=\operatorname{id}\_{K}$. En las ecuaciones anteriores hemos usado que $f$ deja fijo a $F$ y a las raíces $\alpha\_1,\dots,\alpha\_n\in K$ de $p(x)$.

 
{{%  /proof %}}

Uno homomorfismo $\varphi$ como el del enunciado se denomina **representación** del grupo de Galois como grupo de permutaciones.

{{% proposition   %}} Dadas dos extensiones consecutivas $F\subset L\subset K$, tenemos que $G(K/L)\subset G(K/F)$. {{% /proposition %}}

{{% proof %}} En efecto, si $f\colon K\rightarrow K$ es un isomorfismo de anillos que deja fijo a $L$ entonces también deja fijo a $F$ ya que $F\subset L$.  {{%  /proof %}}

Los subgrupos del grupo de Galois nos permiten construir nuevas extensiones intermedias.

{{%  definition  %}} Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$ definimos el **cuerpo fijo** de $H$ del siguiente modo: $$K^{H}=\\{\alpha\in K\;|\; f(\alpha)=\alpha\;\forall f\in H\\}.$$ {{% /definition %}}

{{% proposition   %}} Dada una extensión $F\subset K$ y un subgrupo $H\subset G(K/F)$, el cuerpo fijo $K^H$ es un subcuerpo de $K$ que contiene a $F$, $$F\subset K^H\subset K.$$ {{% /proposition %}}

{{% proof %}} El conjunto $K^H$ está contenido en $K$ por definición. Es más, cualquier $\alpha\in F$ satisface $f(\alpha)=\alpha$ para todo $f\in G(K/F)$, en particular para todo $f\in H$, por tanto $F\subset K^H$.  

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

 
{{%  /proof %}}


{{%  theorem %}} Dada una extensión finita $F\subset K$, su grupo de Galois $G(K/F)$ es finito y su orden divide a $[K:F]$. {{% /theorem %}}

El **orden** de un grupo finito $G$, es decir, su número de elementos, se denotará $|G|$.

{{%  definition  %}} Una **extensión de Galois** es una extensión finita $F\subset K$ tal que $|G(K/F)|=[K:F]$. {{% /definition %}}

{{% corollary %}} Si $K\subset F$ es una extensión de Galois entonces $$K^{G(K/F)}=F.$$ {{% /corollary %}}

{{% proof %}} Sea $L\subset K^{G(K/F)}$. Como todo elemento de $G(K/F)$ deja fijo a $L$ por definición, tenemos que la inclusión $G(K/L)\subset G(K/F)$ es una igualdad. Como $|G(K/L)|$ divide a $[K:L]$ y $|G(K/F)|=[K:F]$ entonces $[K:F]$ divide a $[K:L]$. Pero $[K:L]$ también divide a $[K:F]$ por la fórmula del grado para extensiones consecutivas. Por tanto $[K:F]=[K:L]$ y en consecuencia $F=L$.  {{%  /proof %}}


{{%  theorem %}} Las extensiones de Galois de un cuerpo $F$ coinciden con los cuerpos de descomposición de los polinomios de $F[x]$. {{% /theorem %}}

{{% corollary %}} Toda extensión finita $F\subset K$ está contenida en una extensión de Galois. {{% /corollary %}}

{{% proof %}} Por ser finita $K=F[\alpha\_1,\dots,\alpha\_n]$ para ciertos $\alpha\_1,\dots,\alpha\_n\in K$ necesariamente algebraicos. Si $p\_i(x)\in F[x]$ es un polinomio que tiene a $\alpha\_i$ como raíz, $1\leq i\leq n$, entonces todos los $\alpha\_i$ son raíces de $p(x)=p\_1(x)\cdots p\_n(x)$, así que $K$ está contenido en el cuerpo de descomposición de $p(x)$.  {{%  /proof %}}

{{% corollary %}} Dadas extensiones $F\subset K\subset L$, si $F\subset L$ es de Galois entonces $K\subset L$ también. {{% /corollary %}}

{{% proof %}} Si $L$ es el cuerpo de descomposición de un polinomio $p(x)\in F[x]$ entonces $L$ es el cuerpo de descomposición del mismo polinomio visto ahora en $K[x]$. En efecto, si $\alpha\_1,\dots,\alpha\_n$ son las raíces complejas de $p(x)$ entonces $L=F[\alpha\_1,\dots,\alpha\_n]=K[\alpha\_1,\dots,\alpha\_n]$. Aquí hay que comprobar la segunda igualdad por doble inclusión. La inclusión $\subset$ es obvia porque $F\subset K$ y $\supset$ es consecuencia de que $K\subset L$ y $\alpha\_1,\dots,\alpha\_n\in K\subset L$.  
{{%  /proof %}}

{{% theorem name="(fundamental de la teoría de Galois)"  %}} Dada una extensión de Galois $F\subset K$ tenemos la siguiente biyección: $$\begin{array}{rcl}\left\\{\text{extensiones intermedias }F\subset L\subset K\right\\}&\longleftrightarrow& \left\\{\text{subgrupos }H\subset G(K/F)\right\\},\cr L&\mapsto&G(K/L),\cr K^H&\leftarrow&H.\end{array}$$ {{% /theorem %}}


## Extensiones ciclotómicas

Dado $n\geq 1$, las **raíces $n$-ésimas de la unidad** son las $n$ raíces complejas diferentes del polinomio $$x^n-1$$, $$e^{\frac{2\pi i t}{n}}, \qquad 0\leq t{<}n.$$
El conjunto formado por estos $n$ números complejos es un grupo cíclico de orden $n$ para la multiplicación, generado por la **raíz $n$-ésima primitiva**, $$\zeta=\zeta_n=e^{\frac{2\pi i}{n}}.$$ Si $n=p$ es primo, cualquier raíz distinta de $1$ genera estre grupo.

{{% proposition   %}} Dado un entero primo $p\geq 1$, la extensión $\mathbb Q\subset\mathbb Q[\zeta]$ es de Galois, de grado $p-1$ y su grupo de Galois es cíclico.{{% /proposition %}}

{{% proof %}} El cuerpo de descomposición de $x^p-1$ es $$\mathbb Q[1,\zeta,\dots,\zeta^{p-1}]=\mathbb Q[\zeta].$$ En efecto $\supset$ es obvio y $\subset$ es consecuencia de que como $\zeta\in\mathbb Q[\zeta]$ entonces todas las potencias $\zeta^n\in \mathbb Q[\zeta]$ también. Esto demuestra que $\mathbb Q[\zeta]$ es de Galois.

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

  {{%  /proof %}}

## Extensiones de Kummer

En esta sección y en las siguientes supondremos que todos los cuerpos que manejemos están contenidos en $\mathbb C$. Dado un cuerpo $F$, nuestro objetivo es estudiar el cuerpo de descomposición $K$ del polinomio $$q(x)=x^p-a\in F[x]$$ donde $p$ es primo y $a$ no tiene raíces $p$-ésmas en $F$. La **raíz $p$-ésima primitiva de la unidad** es $$\zeta\_p=e^{\frac{2\pi i}{p}}\in\mathbb C.$$ Las raíces $p$-ésimas de la unidad son las potencias de $\zeta\_p$, que forman un grupo cíclico de orden $p$ restecto de la multiplicación, $$1,\zeta\_p,\dots,\zeta\_p^{p-1}.$$ Por tanto si $\alpha$ es una raíz compleja de $q(x)$ el conjunto de todas sus raíces es $$\alpha,\zeta\_p\alpha,\dots,\zeta\_p^{p-1}\alpha.$$ En particular si $\zeta\_p\in F$ entonces $K=F[\alpha]$.

{{% proposition   %}} Si $F\subset \mathbb C$ es un subcuerpo tal que $\zeta\_p\in F$ y $p(x)=x^p-a\in F[x]$ no tiene raíces en $F$ entonces el cuerpo de descomposición $K$ de $p(x)$ tiene grado $p$ sobre $F$. {{% /proposition %}}

{{% proof %}} Hemos observado que $K=F[\alpha]$ y $\alpha$ es una raíz de $p(x)$, que es de grado $p$, por tanto $[K:F]\leq p$. Al ser $F\subset K$ de Galois, para probar la otra desigualdad bastará ver que $|G(K/F)|\geq p$. 

Como $\alpha\notin F$ y $F= K^{G(K/F)}$, ha de existir algún $f\in G(K/F)$ tal que $f(\alpha)\neq\alpha$. Como $f$ preserva raíces de polinomios en $F[x]$, $f(\alpha)=\zeta\_p^i\alpha$ para cierto $0{<}i{<}p$. Usaremos esto para ver que las potencias $f^j$ de $f$ son diferentes para todo $0\leq j{<}p$, así que $G(K/F)$ tiene al menos $p$ elementos. Para ello basta comprobar que cada una de estas potencias $f^j$ manda $\alpha$ a un elemento diferente. Vamos a probar por inducción que $$f^j(\alpha)=(\zeta\_p^{i})^{j}\alpha.$$ Todos estos elementos son diferentes ya que al ser $p$ primo todas las potencias de $\zeta\_p$ distintas de $1$, por ejempo $\zeta\_p^i$, tienen orden multiplicativo $p$, así que todos los $(\zeta\_p^i)^{j}$ son diferentes para $0\leq j{<}p$. Para $j=1$ la ecuación anterior es cierta. Si es cierta para $j-1$ entonces
$$\begin{array}{rcl}
f^j(\alpha)&=&f(f^{j-1}(\alpha))\cr
&=&f((\zeta\_p^{i})^{j-1}\alpha)\cr
&=&(f(\zeta\_p)^{i})^{j-1}f(\alpha)\cr
&=&(\zeta\_p^{i})^{j-1}\zeta\_p^i\alpha\cr
&=&(\zeta\_p^{i})^{j}\alpha.
\end{array}$$
Aquí hemos usado que $f(\zeta\_p)=\zeta\_p$ ya que $\zeta\_p\in F$.   {{%  /proof %}}

Sorprendentemente el resultado a anterior tiene un recíproco.

{{%  theorem %}} Si $F\subset \mathbb C$ es un subcuerpo tal que $\zeta\_p\in F$ y $F\subset K$ es una extensión de Galois de grado $[K:F]=p$ primo entonces $K=F[\alpha]$ para cierto $\alpha\in K$ que es raíz de un polinomio de la forma $x^n-a\in F[x]$. {{% /theorem %}}

{{% proof %}} Al ser la extensión de Galois $|G(K/F)|=[K:F]=p$, por tanto $G(K/F)$ es cíclico de orden $p$, así que todo $f\in G(K/F)$ distinto de la identidad genera el grupo de Galois, $$G(K/F)=\\{f^0,f^1,\dots, f^{p-1}\\}.$$ 

Ahora vamos a concentrarnos en el hecho de que $f$ es un homomorfismo de $F$-espacios vectoriales. Como $f^p=\operatorname{id}_K$ tenemos que cualquier autovalor $\lambda$ de $f$ satisface $\lambda^p=1$. Además $f$ es diagonalizable, pues niguna potencia de una caja de Jordan de tamaño $2\times 2$ o superior es la matriz identidad. Como $f$ es diagonalizable y distinto de la identidad, tendrá que tener algún autovalor $\lambda\neq 1$. Este autovalor ha de ser forzosamente de la forma $\lambda =\zeta\_p^i$ para cierto $0{<}i{<}p$. 

Sea $\alpha\in K$ un autovector asociado a $\zeta\_p^i$, $$f(\alpha)=\zeta\_p^i\alpha.$$  Tenemos entonces que
$$\begin{array}{rcl}
f(\alpha^p)&=&f(\alpha)^p\cr
&=&(\zeta\_p^i\alpha)^p\cr
&=&(\zeta\_p^i)^p\alpha^p\cr
&=&\alpha^p.
\end{array}$$
Se deduce por inducción que $f^i(\alpha^p)=\alpha^p$ para todo $i\geq 1$, por tanto $\alpha^p\in K^{G(K/F)}=F$. Esto demuestra que $\alpha\in K$ es raíz del polinomio $x^p-\alpha^p\in F[x]$. Además, como $f(\alpha)\notin \alpha$ entonces $\alpha\notin F$ así que $F\subsetneq F[\alpha]\subset K$  y como $[K:F]=p$ es primo concluimos que $K=F[\alpha]$.  {{%  /proof %}}

Las extensiones del tipo que hemos estudiado en esta sección se denominan **extensiones de Kummer**.

## Solubilidad por radicales

{{%  definition  %}}Una extensión $F\subset K$ es una **extensión por radicales** si hay una sucesión finita de extensiones $$F=F\_0\subset F\_1\subset\cdots\subset F\_n=K$$ tales que $F\_{i+1}=F\_i[\alpha\_i]$ donde $\alpha\_i$ es es raíz de un polinomio de la forma $x^{p\_i}-a\_i\in F\_i[x]$ con $p\_i$ es primo, $i=0,\dots,p-1$. {{% /definition %}}

{{% ojo %}} Observa que toda extensión por radicales es finita pues cada $F\_i\subset F\_{i+1}$ es finita de grado $\leq p\_i$ ya que $r\_i$ es raíz de un polinomio de grado $p\_i$ con coeficientes en $F\_i$. {{% /ojo %}}

{{%  definition  %}} Dado un polinomio no nulo $p(x)\in F[x]$ decimos que la ecuación $p(x)=0$ se puede **resolver por radicales** si existe una extensión por radicales de $F$ en la que $p(x)$ factoriza como producto de polinomios de grado $1$. {{% /definition %}}

{{% ojo %}} Esto equivale a decir que hay una extensión por radicales de $F$ que contiene al cuerpo de descomposición de $p(x)$. {{% /ojo %}}

{{%  definition  %}} Un grupo finito $G$ es **soluble** si existe una sucesión de subgrupos $$\\{1\\}=G\_0\subset G\_i\subset \cdots\subset G\_n=G$$ tal que $G\_i\subset G\_{i+1}$ es normal y $G\_{i+1}/G\_i$ es cíclico de orden $p\_i$ primo, $0\leq i{<}n$. {{% /definition %}}

{{% proposition   %}} Toda extensión por radicales $F\subset K$ tiene grupo de Galois $G(K/F)$ soluble. {{% /proposition %}}

{{% proof %}}   {{%  /proof %}}

{{%  theorem %}} Sea $F$ un cuerpo y $p(x)\in F[x]$ un polinomio con cuerpo de descomposición $K$. La ecuación $p(x)=0$ se puede resolver por radicales si y solo si $G(K/F)$ es soluble. {{% /theorem %}}

{{% proof %}} 

$$\Rightarrow$$ 

  {{%  /proof %}}
