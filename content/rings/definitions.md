+++
title = "Fundamentos"
weight = 10
+++

Recuerda que un **anillo** $R$ es un conjunto donde están definidas las siguientes operaciones para $a,b\in R$:

* **suma**: $a+b$,

* **multiplicación** o **producto**: $ab$,

y además existen elementos:

* **cero**: $0$,

* **uno**: $1$,

que satisfacen las propiedades habituales de asociatividad y distributividad. La suma debe ser conmutativa y en esta asignatura solo consideraremos anillos donde el producto también lo es. Todos los elementos $a$ han de poseer **opuestos** para la suma $-a$, con lo cual podemos restar. Los que poseen inversos para el producto se denominan **unidades** y podemos dividir por ellos. Un **cuerpo** es un anillo donde $0\neq 1$ y todo elemento no nulo es una unidad. Se puede comprobar que $0=1$ en un anillo $R$ si y solo si $R=\\{0\\}$ es el anillo trivial.

Ejemplos de anillos son: 

* Los números enteros $\mathbb Z$, racionales $\mathbb Q$, reales $\mathbb R$ y complejos $\mathbb C$, pero no los naturales $\mathbb N$.

* El anillo de polinomios $R[ x ]$ en una variable $x$ con coeficientes en un anillo $R$. 

* El anillo de polinomios en varias variables $R[x\_1,\dots, x\_n]$, que se puede definir inductivamente como $R[x\_1,\dots, x\_{n-1}][x\_n]$. 

* El álgebra de Boole de las partes de un conjunto. 

* El anillo de funciones continuas $\mathcal{C}(X,\mathbb{R})$ definidas en un espacio topológico $X$ con valores reales. También lo es su versión con valores complejos $\mathcal{C}(X,\mathbb{C})$ y, cuando la naturaleza de $X$ le dé sentido, lo anillos de funciones derivables, analíticas, etc.

La suma dota a un anillo de estructura de grupo abeliano.

El **producto** cartesiano $R\times S$ de dos anillos $R$ y $S$ es un anillo con las operaciones definidas por coordenadas. El cero y el uno del producto son $(0,0)$ y $(1,1)$.

Recuerda también que un **subanillo** $R'\subset R$ de un anillo $R$ es un subconjunto cerrado para la suma y el producto que contiene al $1$ y a los opuestos de todos sus elementos. Los subanillos son subgrupos para la suma. Podemos ver $R\subset R[ x ]$ como el subanillo de los polinomios constantes, sin embargo $R\times\\{0\\}\subset R\times S$ en general no es un subanillo. El total $R\subset R$ siempre es un subanillo pero $\\{0\\}\subset R$ generalmente no.



## El principio de sustitución

Recuerda que un **homomorfismo** de anillos $f\colon R\rightarrow S$ es una aplicación que preserva esta estructura, es decir la suma, el producto, el $0$ y el $1$. Los homomorfismos inyectivos se denominan **monomorfismos**, los sobreyectivos **epimorfismos** y los biyectivos **isomorfismos**. Estos últimos se denotan con el símbolo $\cong$. Los isomorfismos de un anillo en sí mismo reciben el nombre de **automorfismos**. 

Todas estas clases de morfismos son cerradas para la composición y contienen a la identidad. Es más, el inverso de un isomorfismo es también un isomorfismo, e igual para automorfismos. La conjugación compleja es un automorfismo no trivial de $\mathbb{C}$. El inverso de un isomorfismo también es un isomorfismo. La inclusión de un subanillo $R'\hookrightarrow R$ es un monomorfismo y la proyección sobre la primera coordenada $R\times S\twoheadrightarrow R$ es un epimorfismo, sin embargo estos, en general, no son isomorfismos. Se da el hecho curioso de que, para todo anillo $R$, existe un único homomorfismo $\mathbb{Z}\rightarrow R$, es decir, $\mathbb{Z}$ es el objeto incial en la categoría de los anillos.

Los homomorfismos preservan las unidades y sus inversos. La **imagen** de un homomorfismo $f\colon R\rightarrow S$ es un subanillo $\operatorname{im} f\subset S$. 

Dado un anillo $R$ y $a\in R$ está definido el homomorfismo de **evaluación** $ev_a\colon R[ x ]\rightarrow R$ como $ev_a(p(x))=p(a)$. Los anillos de polinomios satisfacen una propiedad universal relacionada con estos homomorfismos.

{{% theorem name="Principio de sustitución" label="sustitucion" %}}
Dado un homomorfismo de anillos $f\colon R\rightarrow S$ y un elemento $c\in S$ existe un único homomorfismo $g\colon R[ x ]\rightarrow S$ tal que la restricción de $g$ a $R$ es $f$ y $g(x)=c$.
{{% /theorem %}}


{{% proof %}}

Dado $p(x)=a_nx^n+\cdots+ a_1x+ a_0\in R[ x ]$, si tal $g\colon R[ x ]\rightarrow S$ existiera satisfaría

$$
\begin{array}{rl}
g(p(x))&=g(a_nx^n+\cdots+a_1x+ a_0)\cr
&=g(a_n)g(x)^n+\cdots+ g(a_1)g(x)+g(a_0)\cr 
&=f(a_n)c^n+\cdots+ f(a_1)c+f(a_0).
\end{array}
$$

Definimos pues

$$
g(p(x))=f(a_n)c^n+\cdots+ f(a_0).
$$

Es tedioso pero trivial comprobar $g$ así definido es un homomorfismo. El cálculo anterior demuestra la unicidad.
{{% /proof %}}


{{% corollary %}}
Dado un homomorfismo de anillos $f\colon R\rightarrow S$ y elementos $c_1,\dots, c_n\in S$ existe un único homomorfismo $g\colon R[x_1,\dots,x_n]\rightarrow S$ tal que la restricción de $g$ a $R$ es $f$ y $g(x_i)=c_i$, $1\leq i\leq n$.
{{% /corollary %}}


{{% proof %}}

Se puede demostrar directamente como el teorema anterior, pero también se puede probar a partir de él por inducción en $n$.

Para $n=1$, la existencia y unicidad de $g\colon R[x_1]\rightarrow S$ es el teorema anterior.

Veamos que $n-1\Rightarrow n$. Suponiendo que hay un único homomorfismo $h\colon R[x\_1,\dots,x\_{n-1}]\rightarrow S$ que se restringe a $f\colon R\rightarrow S$ sobre las constantes y satisface $g(x_i)=c_i$, $1\leq i\leq n-1$, aplicamos el teorema anterior a

$$R[x\_1,\dots,x\_n]=(R[x\_1,\dots,x\_{n-1}])[x\_n]$$

y obtenemos el homomorfismo buscado.  
{{% /proof %}}


## Añadir elementos a un anillo

La siguiente definición nos da una receta para añadir nuevos elementos a un anillo contenido en otro mayor.

{{% definition %}}
Dado un anillo $S$, un subanillo $R\subset S$ y $s\in S$, el **menor subanillo** $R[s]\subset S$ que contiene a $R$ y a $s$ es la imagen $R[s]=\operatorname{im} g$ del homomorfismo $g\colon R[ x ]\rightarrow S$, definido por el [principio de sustitución](#sustitucion), cuya restricción $g_{|_R}\colon R\hookrightarrow S$ es la inclusión y $g(x)=s$.
{{% /definition %}}


{{% remark %}}
La propiedad de ser el menor viene dada porque todo elemento de $R[s]$ se puede expresar (aunque no de manera única) como $a_ns^n+\cdots+a_1s+a_0$ para ciertos $a_i\in R$. Por tanto, si $U\subset S$ es un subanillo tal que $R\subset U$ y $s\in U$ entonces $R[s]\subset U$. En particular $\mathbb R[i]=\mathbb C$ y $\mathbb Z[i]\subset\mathbb C$ son los enteros de Gauss. 
{{% /remark %}}

{{% exercise %}}
Da una definición directa del menor subanillo $R[s_1,\dots,s_n]\subset S$ que contiene a varios elementos $s_i\in S$. 
{{% /exercise %}}

También podemos añadir nuevos elementos a un anillo $R$ de manera abstracta, es decir, sin tener previamente otro anillo mayor. El propio anillo de polinomios $R[ x ]$ consiste en añadirle un nuevo elemento $x$ a $R$ de manera libre. Para añadir a $R$ elementos que satisfagan ciertas ecuaciones polinómicas necesitaremos trabajar con cocientes. 

A diferencia de otras estructuras algebraicas, no es posible definir el cociente de un anillo por un subanillo. El tipo de subconjunto adecuado para definir cocientes son los ideales. 

Recordemos que un **ideal** $I\subset R$ de un anillo $R$ es un subconjunto cerrado para la suma y para el producto por escalares de $R$ que contiene al $0$. En particular, si $a_1,\dots,a_n\in I$ y $r_1,\dots, r_n\in R$ entonces la **combinación lineal** $r_1a_1+\cdots+r_na_n\in I$. Tanto el total $R\subset R$ como el trivial $\\{0\\}\subset R$ son ideales. Los cuerpo se caracterizan como los anillos que poseen exactamente dos ideales (necesariamente el total y el trivial). En general, el único ideal que contiene al $1$ (o a cualquier otra unidad) es el total. Los ideales son subgrupos de los anillos para la suma.

El **núcleo** de un homomorfismo $f\colon R\rightarrow S$ es un ideal 

$$\ker f=\\{a\in R \mid f(a)=0\\}.$$

Este ideal posee la particularidad de que $f$ es inyectivo si y solo si $\ker f = \\{0\\}$.

El **ideal generado por** un conjunto finto de elementos $a_1,\dots,a_n\in R$ está formado por todas las combinaciones lineales de los generadores con coeficientes en el anillo: 

$$(a_1,\dots,a_n)=\\{r_1a_1+\dots+r_na_n  \mid  r_1,\dots,r_n\in R\\}\subset R.$$

Este es el menor ideal que contiene a los elementos $a_1,\dots,a_n\in R$. Es decir, si $I\subset R$ es un ideal y $a_1,\dots,a_n\in I$ entonces $(a_1,\dots,a_n)\subset I$.

Un **ideal principal** es uno que está generado por un único elemento $(a)=\\{ra \mid  r\in R\\}$ y que por tanto está formado por sus múltiplos. En $\mathbb Z$, el ideal de los números pares es $(2)$.

Dado un anillo y un ideal $I\subset R$, la **clase** de $a\in R$ **módulo** $I$ es el subconjunto

$$a+I=\\{a+b \mid b\in I\\}\subset R.$$

Estas clases de equivalencia conforman una partición de $R$ denominada anillo **cociente** $R/I$,

$$R/I=\\{a+I \mid  a\in R\\}.$$

Sabemos que $a+I=b+I$ si y solo si $a-b\in I$. En particular $a+I=0+I$ si y solo si $a\in I$. El anillo conciente es un anillo con la suma

$$(a+I)+(b+I)=(a+b)+I$$

y el producto

$$(a+I)(b+I)=(ab)+I.$$

Su cero es $0+I$ y su uno es $1+I$. Esto hace que la **proyección natural** $p\colon R\twoheadrightarrow R/I$, $p(a)=a+I$, sea un homomorfismo.

Cuando el ideal $I$ se sobreentiende, sus clases de equivalencia se denotan simplemente

$$a+I=\bar a=[a].$$



Dado un polinomio $p(x)=a\_nx^n+\cdots + a_1x+ a\_0\in R[ x ]$, consideramos el anillo $S=R[ x ]/(p(x))$. Por abuso de notación, la clase de una constante $a\in R$ en $S$ se denotará igual, $a\in S$, no $\bar a$. En este nuevo anillo $\bar x\in S$ es una raíz de $p(x)$ puesto que

$$p(\bar{x})=a_n\bar x^n+\cdots + a_1 \bar x+ a_0=\overline{p(x)}=\bar 0\in S.$$

Este anillo posee en ciertos casos una descripción similar a la de los números complejos. Para demostrarlo usaremos el siguiente resultado que asegura que en $R[ x ]$ siempre podemos dividir por un polinomio mónico del modo habitual.

{{% lemma %}}
Dado un polinomio **mónico** $p(x)=x^n+\cdots + a_1x+ a\_0\in R[ x ]$ 
y otro polinomio cualquiera $f(x)\in R[ x ]$, existen dos únicos polinomios  
$c(x), r(x)\in R[ x ]$ tales que $r(x)$ tiene grado $<n$ y $f=c\cdot p+r$. 
{{% /lemma %}}


{{% proof %}}
Sea $f\_0=f$. Si grado $f_0<n$ entonces podemos tomar $c=0$ y $r=f_0$. Veamos ahora cómo proceder si grado $f_0\geq n$. En este caso existen polinomios $c\_1,f\_1\in R[ x ]$ tales que grado $f\_1<$ grado $f\_0$ y $f\_0=c\_1\cdot p + f\_1$. En efecto, si $f\_0=b\_mx^m+\cdots$ tiene grado  $m\geq n$ podemos tomar $c_1(x)=b\_mx^{m-n}$, que tiene sentido pues estamos suponiendo que $m\geq n$. Si el grado de $f\_1$ sigue siendo $\geq n$,  podemos aplicar el mismo razonamiento a $f\_1$ obteniendo así polinomios $c\_2,f\_2\in R[ x ]$ tales que grado $f\_2<$ grado $f\_1$ y $f\_1=c\_2\cdot p + f\_2$. Podemos continuar

$$
\begin{array}{rcl}
f\_0&=&c\_1\cdot p + f\_1,\cr
&\vdots&\cr
f\_{i-1}&=&c\_i\cdot p + f\_i,
\end{array}
$$

hasta que grado $f_i<n$. De este modo

$$f=(c\_1+\cdots+c\_i)\cdot p+f\_i$$

y podemos tomar $c=c\_1+\cdots+c\_i$ y $r=f\_i$. Hemos probado la existencia.

Veamos la unicidad de $r$. Si $f=c\cdot p+r=c'\cdot p+r'$ en las condiciones del enunciado, tenemos entonces que $r-r'=(c'-c)\cdot p$. Por un lado $r-r'$ tiene grado $<n$. Supongamos por reducción al absurdo que $c'\neq c$. Entonces $c'-c=e\_kx^k+\cdots$ para cierto $k\geq 0$ y $e\_k\in R$ no nulo. Esto implica que $(c'-c)\cdot p=e\_kx^{k+n}+\cdots$ y por tanto tendría grado $\geq n$. Hemos llegado a una contradicción, así que $c=c'$, luego también $r=r'$.
{{% /proof %}}

{{% corollary label="uniquerep" %}}
Dado un polinomio mónico $p(x)=x^n+\cdots + a\_1x+ a\_0\in R[ x ]$ de grado $n$, todo elemento de $R[ x ]/(p)$ posee un único representante de grado $<n$. 
{{% /corollary %}}


{{% proof %}}
En efecto, dado $[\bar{f}]\in R[ x ]/(p)$, $r\in R[ x ]$ es un representante de $[\bar{f}]$ si y solo si $\bar{f}-r\in (p)$, lo que equivale a la existencia de $c\in R[ x ]$ tal que $\bar{f}-r=c\cdot p$, es decir, $\bar{f}=c\cdot p+r$. Este resultado se deduce por tanto del lema anterior.
{{% /proof %}}

{{% remark %}}
El corolario anterior nos dice que, bajo sus condiciones, todo elemento de $R[ x ]/(p)$ se puede escribir de manera única como

$$b\_{n-1}\bar{x}^{n-1}+\cdots+ b\_1\bar{x}+b\_0,$$

donde $b\_0,\dots, b\_{n-1}\in R$. La suma de estos representantes se hace coeficiente a coeficiente, como en $\mathbb{C}$. El producto es más complejo y depende de $p(x)$.

En particular, si $n\geq 1$, el homomorfismo $R\hookrightarrow R[ x ]/(p)\colon r\mapsto\bar{r}$ que envía cada constante a la clase del correspondiente polinomio constante es inyectivo. Por ello, en en estos casos eliminaremos la barra de las clases de los polinomios constantes y las denotaremos simplemente $r$. De este modo podemos ver $R$ como un subanillo $R\subset R[ x ]/(p)$. Esto refuerza la idea de que este cociente *añade* el elemento $\bar{x}$ a $R$.
{{% /remark %}}

En adelante, cuando hablemos de añadirle a un anillo $R$ una raíz $\alpha$ de un polinomio $p(x)\in R[ x ]$ de manera abstracta nos estaremos refiriendo al cociente $R[ x ]/(p)$ y a $\alpha=\bar{x}$, que como hemos visto es una raíz de $p(x)$ en este anillo. Si $p$ es mónico de grado $n$, todo elemento de $R[ x ]/(p)$ se escribe de manera única como $b\_{n-1}\alpha^{n-1}+\cdots+ b\_1\alpha+b\_0$, con $b\_0,\dots, b\_{n-1}\in R$.

{{% example name="$\mathbb Z[ x ]/(x^3+3x+1)$" %}}
Todo elemento de este anillo se puede expresar de manera única como $a_2 \bar x^2+ a_1 \bar x+ a_0$ para ciertos coeficientes $a_0,a_1,a_2\in\mathbb Z$. La suma se calcula sumando coeficientes. El producto es más complejo porque suele ser necesario reducir el grado del representante obtenido. Esto se hace usando que $\bar x$ es una raíz del denominador. Concretamente en este caso $\bar x^3+3\bar x+1=0$, luego

$$\begin{array}{rcl}\bar x^3&=& -3\bar x-1,\cr \bar x^4&=& -3\bar x^2-\bar x,\cr\bar x^5&=& -3\bar x^3-\bar x^2\cr&=& -3(-3\bar x-1)-\bar x^2\cr&=&-\bar x^2+9\bar x+3,\cr\bar x^6&=&\dots\end{array}$$Usamos esto en el siguiente ejemplo de cálculo,$$\begin{array}{rcl}(- \bar x^2+ \bar x+ 2)(\bar x+ 1)&=& -\bar x^3+3\bar x+2\cr&=& -(-3\bar x-1)+3\bar x+2\cr&=&6\bar x+3.\end{array}$$

{{% /example %}}

Es posible añadir a un anillo de manera abstracta no solo uno sino varios elementos que satisfagan determinadas ecuaciones. Se puede hacer tanto de manera directa como inductiva. Prueba a hacerlo como ejericio.

Frecuentemente necesitaremos construir homomorfismos que partan de anillos cociente. Para facilitar esta tarea disponemos de los dos resultados siguientes.

{{% proposition label="factorquotient" %}}
Dado un ideal $I\subset R$ y un homomorfismo $f\colon R\rightarrow S$ tal que $I\subset \ker f$, $f$ factoriza de manera única a través de la proyección natural, es decir existe un único homomorfismo $g\colon R/I\rightarrow S$ tal que $f=g\circ p$,

$$f\colon R\stackrel{p}\twoheadrightarrow R/I\stackrel{g}\rightarrow S.$$

{{% /proposition %}}


{{% proof %}}

Si $f=g\circ p$ entonces tendríamos

$$f(a)=(g\circ p)(a)=g(p(a))=g(a+I).$$

Definimos la aplicación $g\colon R/I\rightarrow S$ como

$$g(a+I)=f(a).$$

Veamos que en efecto está bien definida. La unicidad se seguirá de la primera fórmula.

Si $a+I=a'+I$ entonces $a-a'\in I\subset\ker f$ luego

$$0=f(a-a')=f(a)-f(a').$$

Por tanto

$$g(a+I)=f(a)=f(a')=g(a'+I).$$

Claramente $g$ es un homomorfismo pues se definie como el homomorfismo $f$ en los representantes.  
{{% /proof %}}


{{% theorem name="Primer Teorema de Isomorfía" label="primer" %}}
Dado un homomorfismo $f\colon R\rightarrow S$, existe un único homomorfismo $\bar f\colon R/\ker f\rightarrow \operatorname{im}f$ tal que $f$ factoriza como $f=i\circ\bar f\circ p$, es decir, $f$ encaja en el siguente **diagrama conmutativo**, 

![Primer teorema de isomorfía](../../images/isomorfianillos.svg)

Aquí $p$ es la proyección natural e $i$ es la inclusión. Además $\bar f$ es un isomorfismo.
{{% /theorem %}}

La demostración de este resultado es conocida. Basta recordar que $\bar{f}$ se define como $\bar{f}(\bar{a})=f(a)$, $a\in R$.

Veamos finalmente que el cuerpo de los números complejos es isomorfo al anillo obtenido al añadirle a $\mathbb{R}$ de manera abstracta una raíz de $x^2+1$ por el procedimiento anterior.

{{% corollary %}}
$\mathbb R[ x ]/(x^2+1)\cong\mathbb C$.
{{% /corollary %}}

{{% proof %}}
Consideremos el homomorfismo $f\colon \mathbb R[ x ]\rightarrow\mathbb C$ definido por la inclusión $\mathbb R\subset\mathbb C$ y tal que $f(x)=i$. Este homomorfismo es sobreyectivo ya que dado $a+ib\in\mathbb C$, $f(bx+a)=a+ib$ por tanto $\operatorname{im} f =\mathbb C$. Basta ahora ver que $\ker f=(x^2+1)$. Como $\mathbb R$ es un cuerpo, todo ideal no trivial de $\mathbb{R}[ x ]$ está generado por cualquiera de sus elementos no nulos de grado mínimo. Por tanto es suficiente comprobar que $x^2+1\in\ker f$ y que $\ker f$ no posee ningún polinomio no trivial de grado $<2$. Claramente $f(x^2+1)=i^2+1=0$. Si $bx+a\in\mathbb{R}[ x ]$ es un polinomio no trivial entonces $f(bx+a)=a+ib$ es un número complejo no trivial, con lo que queda demostrado.
{{% /proof %}}


## Cuerpos de fracciones 

Recordemos que, dado un anillo $R$, un **divisor de cero** es un elemento $a\in R$ no nulo, $a\neq 0$, tal que existe otro $b\in R$, $b\neq 0$, de modo que $ab=0$. Un anillo no trivial $R$ es un **dominio (de integridad)** si no posee divisores de cero.

Dicho de otro modo, $R$ es un dominio cuando dados $a,b\in R$ tales que $ab=0$ entonces $a=0$ o $b=0$. Los dominios poseen la **propiedad cancelativa**, es decir, si $ab=ac$ y $a\neq 0$ entonces $b=c$ ya que esto equivale a $a(b-c)=0$. Los cuerpos $k$ y los enteros $\mathbb Z$ son dominios. Los subanillos de un dominio también son dominios. El anillo $\mathbb Z/(6)$ no es un dominio porque aquí $\bar 2\cdot \bar 3=\bar 6=\bar 0$ pero $\bar 2\neq\bar 0\neq\bar 3$.

Sabemos que si $R$ es un dominio entonces $R[ x ]$ también y que en dicho caso el grado de un producto es el producto de los grados y las unidades de $R[ x ]$ son las de $R$. Por inducción $R[x\_1,\dots,x\_n]$ tambén será un dominio.

Cualquier subanillo de un cuerpo es un dominio. Veamos que, recíprocamente, todo dominio se puede incluir en un cuerpo.

{{% definition %}}
Dado un dominio $R$, su **cuerpo de fracciones** $Q( R )$ es el cociente del conjunto

$$\left\\{\frac{a}{b}\\;\bigg|\\; a,b\in R,\\,b\neq 0\right\\}$$

por la relación de equivalencia

$$\frac{a}{b}\sim\frac{a'}{b'}\Leftrightarrow ab'=a'b$$

dotado de las operaciones

$$\begin{array}{rcl}\displaystyle \frac{a}{b}+\frac{c}{d}&\displaystyle =&\displaystyle  \frac{ad+bc}{bd},\cr[1em]\displaystyle \frac{a}{b}\cdot\frac{c}{d}&\displaystyle =&\displaystyle \frac{a c}{b d}.\end{array}$$

{{% /definition %}}

El ejemplo principal es $Q(\mathbb Z)=\mathbb Q$.

{{% proposition %}}
El cuerpo de fracciones $Q( R )$ de un dominio $R$ está bien definido. La aplicación $i\colon R\rightarrow Q( R )$, $i(a)=\frac{a}{1}$, es un homomorfismo inyectivo. Todo homomorfismo inyectivo $f\colon R\rightarrow k$ donde $k$ es un cuerpo factoriza de manera única a través de $i$, es decir, existe un único homomorfismo $g\colon Q( R )\rightarrow k$ tal que $f=g\circ i$,

$$f\colon R\stackrel{i}\rightarrow Q( R )\stackrel{g}\rightarrow k.$$

{{% /proposition %}}


{{% proof %}}
La relación es simétrica y reflexiva porque el producto en $R$ es conmutativo. Veamos la transitividad. Si

$$\displaystyle \frac{a}{b}\sim \frac{a'}{b'}\sim \frac{a^{\prime\prime}}{b^{\prime\prime}}$$

entonces 

$$\begin{array}{rcl}
ab'&=&a'b,\cr 
a'b^{\prime\prime}&=&a^{\prime\prime} b'.
\end{array}$$

En particular, 

$$\begin{array}{rcl}
(a b^{\prime\prime}) b'&=&(ab')b^{\prime\prime}\cr
&=&(a'b)b^{\prime\prime}\cr
&=&(a'b^{\prime\prime})b\cr
&=&(a^{\prime\prime} b')b\cr
&=&(a^{\prime\prime} b)b'.
\end{array}$$

Por la propiedad cancelativa de los dominios, $ab^{\prime\prime}=a^{\prime\prime} b$, es decir $\frac{a}{b}\sim \frac{a^{\prime\prime}}{b^{\prime\prime}}$. Por tanto el conjunto cociente $Q( R )$ está bien definido. Demostrar que las definiciones de la suma y la multiplicación en $Q( R )$ no dependen de la elección de fracciones representantes es laborioso pero trivial, no es distinto de la construcción clásica de los números racionales. También es fácil probar que los axiomas que definen los anillos se verifican. Obviamente el cero y el uno de $Q( R )$ son $\frac{0}{1}$ y $\frac{1}{1}$, respectivamente. Por tanto una fracción $\frac{a}{b}$ es nula $\Leftrightarrow$ $a=0$. Si $\frac{a}{b}$ es no nula entonces es claramente una unidad y $(\frac{a}{b})^{-1}=\frac{b}{a}$, por lo que $Q( R )$ es un cuerpo.

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

{{% corollary %}}
Dado un homomorfismo inyectivo entre dominios $f\colon R\rightarrow S$, existe un único homomorfismo entre sus cuerpos de fracciones $g\colon Q( R )\rightarrow Q(S)$ que extiende $f$, en el sentido de que el siguiente cuadrado es conmutativo

![Cuerpos de fracciones](../../images/fractionfield.svg)

es decir, $g\circ i_R=i_S\circ f$, donde $i_R$ e $i_S$ son las inclusiones de $R$ y $S$ en sus cuerpos de fracciones.
{{% /corollary %}}

{{% proof %}}
Basta aplicar la proposición anterior a $i_S\circ f\colon R\rightarrow Q(S)$, que es inyectivo por ser composición de inyectivos. El homomorfismo $g$ estará por tanto definido como $g\left(\frac{a}{b}\right)=\frac{g(a)}{g(b)}$.
{{% /proof %}}


{{% definition %}}
Dado un cuerpo $k$, el **cuerpo de funciones racionales** en una variable se define como $k(x)=Q(k[ x ])$.
{{% /definition %}}


{{% exercise %}}
Da dos definiciones del cuerpo de funciones racionales en varias variables $k(x_1,\dots,x_n)$, una inductiva y otra directa, que sean aparentemente distintas pero isomorfas.
{{% /exercise %}}


## Ideales maximales

{{% definition %}}
Los ideales distintos del total se denominan **propios**. Un ideal $I\subset R$ es **maximal** si es propio y los únicos ideales que lo contienen son $I$ y el total $R$.
{{% /definition %}}


{{% remark %}}
De otro modo, no puede existir ningún ideal $J$ tal que $I\subsetneq J\subsetneq R$. Todo anillo no trivial posee al menos un ideal maximal por el axioma de elección. ¿Cuál es en el caso de los cuerpos?
{{% /remark %}}

Recordemos que un ideal $I\subset R$ es **primo** si es propio y dados $a,b\in R$ tales que $ab\in I$ entonces $a\in I$ o $b\in I$.

Si $p\in\mathbb Z$ es un primo entonces el ideal $(p)\subset \mathbb Z$ es primo ya que si $ab\in (p)$ es porque $p$ divide a $ab$, luego $p$ ha de dividir a $a$ o a $b$, es decir $a\in(p)$ o $b\in(p)$.

Sabemos que un ideal $I\subset R$ es primo si y solo si $R/I$ es un dominio. En particular $R$ es un dominio si y solo si el ideal trivial $(0)\subset R$ es primo. Los cuerpos son los anillos cuyo único ideal maximal es $(0)$.

Para dar una caracterización similar de los ideales maximales necesitamos saber cuáles son los ideales de un anillo cociente.

{{% proposition %}}
Sea $f\colon R\rightarrow S$ un homomorfismo. 

* Si $J\subset S$ es un ideal entonces $f^{-1}(J)\subset R$ también y además $\ker f\subset f^{-1}(J)$. 

* Si $I\subset R$ es un ideal y $f$ es sobreyectivo entonces $f(I)\subset S$ también es un ideal.

{{% /proposition %}}


{{% proof %}}
Comenzamos por el primer apartado:

* $0\in f^{-1}(J)$ porque $f(0)=0\in J$.

* Si $a,b\in f^{-1}(J)$ es porque $f(a),f(b)\in J$, luego $f(a+b)=f(a)+f(b)\in J$ y por tanto $a+b\in f^{-1}(J)$.

* Dado $a\in f^{-1}(J)$ y $r\in R$,  $f(ra)=f( r )f(a)\in J$ luego $ra\in f^{-1}(J)$.

Además, como $\\{0\\}\subset J$ tenemos que $\ker f=f^{-1}(\\{0\\})\subset f^{-1}(J)$.

En el segundo caso:

* $0=f(0)\in f(I)$ pues $0\in I$.

* Si $a,b\in I$ entonces $a+b\in I$ luego $f(a)+f(b)=f(a+b)\in f(I)$.

* Es más, dado $a\in I$ y $s\in S$, por ser $f$ sobreyectiva $s=f( r )$ para cierto $r\in R$, y como $ra\in I$ entonces $sf(a)=f( r )f(a)=f(ra)\in f(I)$.  

{{% /proof %}}


{{% theorem name="de correspondencia" %}}
Dado un anillo $R$ y un ideal $I$, si $p\colon R\twoheadrightarrow R/I$ denota la proyección natural tenemos la siguiente biyección

$$\begin{array}{rcl}\left\\{\text{ideales de }R\text{ que contienen a }I\right\\}&\longleftrightarrow& \left\\{\text{ideales de }R/I\right\\},\cr I'&\mapsto&p(I'),\cr p^{-1}(J)&\leftarrow&J.\end{array}$$

{{% /theorem %}}


{{% proof %}}

La proyección natural es un homomorfismo sobreyectivo con núcleo $I$, por tanto las aplicaciones del enunciado están bien definidas por la proposición anterior. Veamos que una es inversa de la otra. La igualdad $p(p^{-1}(J))=J$ es cierta por ser $p$ sobreyectiva. En general $I'\subset p^{-1}(p(I'))$. Veamos que la otra inclusión es también cierta si $I\subset I'$. Dado $a\in p^{-1}(p(I'))$, $p(a)\in p(I')$ por tanto existe $b\in I'$ tal que $p(b)=p(a)$. Esto implica que $p(a-b)=p(a)-p(b)=0$, es decir, $a-b\in I\subset I'$, por tanto $a=b+(a-b)\in I'$. 
{{% /proof %}}


{{% corollary %}}
Un ideal $I\subset R$ es maximal $\Leftrightarrow$ $R/I$ es un cuerpo.
{{% /corollary %}}

{{% proof %}}
El cociente $R/I$ es un cuerpo si y solo si posee exactamente dos ideales. Esto ocurre si y solo si hay precisamente dos ideales de $R$ que contienen a $I$. Para que haya más de uno es necesario que $I\subsetneq R$ sea un ideal propio, y que no haya más equivale a que este $I$ sea maximal.
{{% /proof %}}


{{% corollary %}}
Todo ideal maximal es primo.
{{% /corollary %}}


Es importante observar que la correspondencia del teorema anterior respeta cocientes en el sentido siguiente.

{{% proposition %}}
Dado un anillo $R$, un ideal $I\subset R$ y un ideal del cociente $J\subset R/I$, si $p\colon R\twoheadrightarrow R/I$ es la proyección natural tenemos un isomorfismo

$$
\begin{array}{rcl}
\frac{R}{p^{-1}(J)} & \stackrel{\cong}{\longrightarrow} & \frac{\frac{R}{I}}{J},\cr
x+p^{-1}(J) & \mapsto & (x+I)+J.
\end{array}
$$

{{% /proposition %}}

{{% proof %}}
Consideramos la composición de proyecciones naturales

$$R \stackrel{p}{\longrightarrow} \frac{R}{I} \stackrel{p'}{\longrightarrow} \frac{\frac{R}{I}}{J}.$$

Por ser ambas sobreyectivas la composición $p'\circ p$ también lo es. El primer teorema de isomorfía nos proporciona un isomorfismo

$$
\begin{array}{rcl}
\frac{R}{\ker p'\circ p} & \stackrel{\cong}{\longrightarrow} & \frac{\frac{R}{I}}{J}
\end{array}
$$

que se define como en el enunciado, reemplazando $p^{-1}(J)$ por $\ker p'\circ p$. Basta por tanto ver que $\ker p'\circ p=p^{-1}(J)$. En efecto, $x\in \ker p'\circ p$ $\Leftrightarrow$ $(x+I)+J=0$ $\Leftrightarrow$ $p(x)=x+I\in J$ $\Leftrightarrow$ $x\in p^{-1}(J)$.
{{% /proof %}}


{{% corollary %}}
La correspondencia del teorema anterior preserva ideales primos y maximales.
{{% /corollary %}}



{{% definition %}}
Un **dominio de ideales principales** (también **DIP** o **PID**) es un dominio donde todos los ideales son principales.
{{% /definition %}}

Son dominios de ideales principales $\mathbb Z$ y $k[ x ]$ si $k$ es un cuerpo.

{{% proposition %}}
En un dominio de ideales principales $R$ todos los ideales primos no nulos son maximales.
{{% /proposition %}}


{{% proof %}}
Supongamos que $(a)\subset (b)\subset R$, con $(a)$ primo y $a\neq0$. Entonces $a=cb$ para cierto $c\in R$. En particular $cb\in (a)$, que es primo, luego $c\in (a)$ o $b\in (a)$.

Si $b\in (a)$ entonces $(b)\subset (a)$, luego $(a)=(b)$.

Si $c\in (a)$ entonces $c=da$ para cierto $d\in R$, por tanto $a=dab=dba$. Por la propiedad cancelativa $db=1$, así que $b$ es una unidad, luego $(b)=R$. 
{{% /proof %}}

{{% corollary %}}
En un DIP que no es un cuerpo los ideales maximales son los primos no nulos.
{{% /corollary %}}


{{% example name="Ideales maximales y geometría" %}}
Dado un cuerpo $k$, todo punto $\mathbf{a}=(a\_1,\dots,a\_n)\in k^n$ del espacio afín $n$-dimensional define un ideal maximal de $k[x\_1,\dots,x\_n]$,

$$I_{\mathbf{a}}=(x\_1-a\_1,\dots,x\_n-a\_n).$$

Es en efecto maximal porque es el núcleo del homomorfismo sobreyectivo de evaluación

$$\begin{array}{rcl} k[x\_1,\dots,x\_n]&\longrightarrow& k,\cr p(x\_1,\dots,x\_n)&\mapsto&p(a\_1,\dots,a\_n). \end{array}$$

Por tanto $k[x\_1,\dots,x\_n]/I_{\mathbf{a}}\cong k$ es un cuerpo por el primer teorema de isomorfía. El **Teorema de los Ceros de Hilbert** dice que si $k=\mathbb C$ o cualquier otro cuerpo algebraicamente cerrado, entonces estos son los únicos ideales maximales de $k[x\_1,\dots,x\_n]$, con lo que tendríamos una biyección,

$$\\{\text{Ideales maximales de }k[x\_1,\dots,x\_n]\\}\longleftrightarrow k^n.$$

Como consecuencia de esto y de la caracterización de ideales de un cociente deducimos que si $X\subset k^n$ es el conjunto de soluciones de unas ecuaciones polinómicas, $p_i(x\_1,\dots,x\_n)\in k[x\_1,\dots,x\_n]$, $1\leq i\leq m$,

$$X\colon\left\\{ \begin{array}{c} p_1(x\_1,\dots,x\_n)=0,\cr \vdots\quad\cr p_m(x\_1,\dots,x\_n)=0, \end{array} \right.$$

entonces tenemos una biyección

$$\\{\text{Ideales maximales de }k[x\_1,\dots,x\_n]/(p_1,\dots,p_m)\\}\longleftrightarrow X.$$

El álgebra del anillo cociente $k[x\_1,\dots,x\_n]/(p_1,\dots,p_m)$ no solo captura el conjunto de puntos de $X$ sino toda su geometría. Por desgracia, otros resultados más precisos al respecto se escapan del alcance de la asignatura.
{{% /example %}}


{{% example name="Ideales maximales, análisis y topología" %}}
Dado un espacio topológico compacto de Hausdorff $X$, denotamos $\mathcal C(X,\mathbb{C})$ al anillo de funciones continuas $X\rightarrow \mathbb C$. Cualquier punto $x\in X$ define un homomorfismo sobreyectivo de evaluación,

$$\begin{array}{rcl} ev_x\colon\mathcal C(X,\mathbb{C})&\longrightarrow& \mathbb C,\cr f&\mapsto&f(x), \end{array}$$

cuyo núcleo $\ker ev_x\subset\mathcal C(X,\mathbb{C})$ es un ideal maximal por el primer teorema de isomorfía. La **Teoría de Representación de Gelfand** dice que todos los ideales maximales de $\mathcal C(X,\mathbb{C})$ son de esta forma, con lo que tenemos una biyección

$$\\{\text{Ideales maximales de }\mathcal C(X,\mathbb{C})\\}\longleftrightarrow X.$$

Esta correspondencia da lugar a una equivalencia de categorías entre los espacios compactos de Hausdorff y las $C^{\ast}$-álgebras conmutativas unitarias, que es una clase de anillos a la que $\mathcal C(X,\mathbb{C})$ pertenece. Esto permite estudiar la topología desde el punto de vista del álgebra y del análisis funcional. 
{{% /example %}}





