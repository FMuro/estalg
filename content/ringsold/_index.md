+++
title = "Enteros"
weight = 35
hidden = true
+++


## Anillos y cuerpos

Un anillo es un conjunto con dos operaciones binarias internas, llamadas {\em suma} y {\em producto}, que satisfacen ciertas propiedades:

{{% definition %}}
{Anillo}
{ Un {\bf anillo} es una terna $(R,+,\cdot )$ donde $R$ es un conjunto y $+$ y $\cdot$ son operaciones internas binarias sobre $R$, llamadas {\em suma} y {\em producto} respectivamente, tales que se satisfacen las siguientes propiedades:
\begin{enumerate}
\item El par $(R,+)$ es un grupo abeliano, cuyo elemento neutro llamaremos "cero" y lo notaremos por $0$.
\item La operación $\cdot$ es {\em asociativa}: $\forall a,b,c\in R$ es
$a\cdot (b\cdot c)=(a\cdot b)\cdot c.$
\item La operación $\cdot$ es {\em distributiva} a derecha y a izquierda respecto de $+$, es decir: $\forall a,b,c\in R$
$$a\cdot (b+c)=a\cdot b+a\cdot c\ \mbox{ y }\ (a+b)\cdot c=a\cdot c+b\cdot c.$$
\item La operación $\cdot$ tiene un elemento neutro, que llamaremos "uno" y lo notaremos por $1$: 
$1 \cdot a = a = a \cdot 1$ para todo $a\in R$.
\end{enumerate}
}
{{% /definition %}}

{{% watch %}}
Es un hecho curioso y poco conocido que la conmutatividad del grupo aditivo $(R,+)$ es de hecho una consecuencia de la existencia de un elemento neutro para el producto, el elemento $1$.

En efecto, dados $a,b\in R$, podemos desarrollar la expresión $(1+1)\cdot (a+b)$ de dos formas aplicando las propiedades distributivas a derecha y a izquierda:
$$(1+1)\cdot (a+b)=1\cdot (a+b)+1\cdot (a+b)=a+b+a+b,$$
$$(1+1)\cdot (a+b)=(1+1)\cdot a+(1+1)\cdot b=a+a+b+b.$$
De donde $a+b+a+b=a+a+b+b$. Sumando el opuesto de $a$ a la izquierda y el opuesto de $b$ a la derecha se tiene $b+a=a+b$.

Por tanto, la existencia de "uno" implica que la operación $+$ es conmutativa.
{{% /watch %}}

{{% definition %}}
{Anillo conmutativo}
{Sea $(R,+,\cdot)$ un anillo. Si además la operación producto es {\em conmutativa} ($\forall a,b\in R\ a\cdot b=b\cdot a$) se dice que el anillo es {\bf conmutativo}.
}
{{% /definition %}}

%?? todos los anillos considerados serán unitarios
%{{% definition %}}
{Anillo con elemento unidad}
%{Sea $(R,+,\cdot)$ un anillo. Si $R$ contiene un {\em elemento neutro} para el producto distinto de %$0$, es decir, si existe un elemento $1\ne 0$ en $R$ tal que $a\cdot 1=1\cdot a$ para todo $a\in %R$, se dice que $R$ es un anillo {\bf unitario} o {\bf con elemento unidad}.
%}
%{{% /definition %}}

{{% watch %}}
Como viene siendo habitual, en adelante notaremos la operación producto $\cdot$ mediante la yuxtaposición de los correspondientes elementos.

En adelante diremos "sea $R$ un anillo" en lugar de "sea $(R,+,\cdot)$ un anillo", dando por conocidas la operación suma y producto siempre que no haya confusión.
{{% /watch %}}

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item Los conjuntos de números $\Z$, $\Q$, $\RR$ y $\C$ son anillos conmutativos. La estructura de anillo de $\Z$ viene determinada por su estructura de grupo, puesto que el producto de dos enteros $xy$ es la suma del número $y$ tantas veces como indique $x$, si $x\geq 0$ ($xy=y+\stackrel{x}{\cdots}+y$), o bien la suma del número $-y$ tantas veces como indique $-x$, si $x\leq 0$ ($xy=(-y)+\stackrel{-x}{\cdots}+(-y)$). Esto no ocurre para $\Q$, $\RR$ y $\C$, obviamente.
\item El conjunto ${\cal M}(n)$ de las matrices $n\times n$ sobre $\Z$, $\Q$, $\RR$ o $\C$ es un anillo con respecto a la suma y al producto de matrices. Este anillo {\bf no es conmutativo}.
\item Si $A$ es un anillo conmutativo, el conjunto $A[x_1,\ldots ,x_n]$ de los polinomios en $n$ indeterminadas con coeficientes en $A$ es también un anillo conmutativo.
\end{enumerate}
{{% /example %}}

{{% proposition %}}
 En un anillo $A$ se verifican las siguientes propiedades:
\begin{enumerate}
\item[1)] $0 \cdot a=0 = a \cdot 0$ para todo $a\in A$.
\item[2)] $(-1)\cdot a = -a = a \cdot (-1)$ para todo $a\in A$.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}
 1) Como $0 \cdot a = (0 + 0)\cdot a = 0 \cdot a + 0 \cdot a$, deducimos que $0 \cdot a=0$. La otra igualdad es análoga.


\noindent 2) Como $0 = 0 \cdot a = (1 + (-1))\cdot a = 1\cdot a + (-1)\cdot a =  a + (-1)\cdot a$, deducimos que $(-1)\cdot a = -a$.  La otra igualdad es análoga.
{{% /proof %}}

{{% watch %}}
 Un anillo $R$ se dice que es {\em nulo} si tiene un único elemento, en cuyo caso  $1=0$. Recíprocamente, si en un anillo $R$ se tiene $1=0$, entonces $R$ será un anillo nulo, pues para todo elemento $a\in R$ de verificará $a = 1\cdot a = 0\cdot a = 0$. 
{{% /watch %}}

{{% definition %}}
{Unidades}
{Sea $R$ un anillo. Se dice que un elemento $x\in R$ es una {\bf unidad} en $R$ si tiene un inverso multiplicativo, es decir, si existe un elemento $y\in R$ tal que $xy=yx=1$. En tal caso, el elemento $y$ es único y se llamará el {\em inverso} de $x$ y de denotará por $x^{-1}$.

Notaremos por $R^*$ al subconjunto de las unidades de $R$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item Las unidades de $\Z$ son $1$ y $-1$, es decir, $\Z^*=\\{ 1,-1\\}$. Sin embargo $\Q^*=\Q\setminus\\{ 0\\}$, $\R^*=\R\setminus\\{ 0\\}$ y $\C^*=\C\setminus\\{ 0\\}$.
\item Las unidades de ${\cal M}(n)$ son las matrices invertibles.
\item Sea $\Q [x]$ el anillo de polinomios en la indeterminada $x$ con coeficientes racionales, entonces
$$\Q [x]^*=\Q^*=\Q\setminus\\{ 0\\}.$$
\end{enumerate}
{{% /example %}}

{{% proposition %}}

Si $R$ es un anillo, el conjunto $R^*$ de las unidades de $R$ es un grupo para el producto del anillo.
{{% /proposition %}}

{{% proof %}}
 El {\em elemento neutro} del producto es $1$, que pertenece a $R^*$ pues su inverso es él mismo. Si $x\in R^*$ su simétrico $x^{-1}$ también pertenece a $R^*$, pues el {\em simétrico} de $x^{-1}$ es el propio $x$. Si $x,y\in R^*$ entonces poseen inversos multiplicativos, pongamos $x^{-1}$ e $y^{-1}$ respectivamente, y se tiene que $y^{-1}x^{-1}$ es el inverso multiplicativo de $xy$, luego la operación producto es {\em interna} en $R^*$. Sabemos que el producto verifica la {\em propiedad asociativa} en todo $R$, en particular también será asociativo en $R^*$.

Por tanto $(R^*,\cdot )$ es grupo.
{{% /proof %}}

{{% definition %}}
{Cuerpo} {Un {\bf cuerpo} es un anillo conmutativo $R$ tal que $1\neq 0$ y todo elemento distinto de cero es una unidad, i.e. $R^* = R\setminus\\{0\\}$.}
{{% /definition %}}

{{% example name="Ejemplo" %}}

$\Q$, $\R$ y $\C$ son cuerpos.
{{% /example %}}

## Subanillos

{{% definition %}}
{Subanillo}{
Sea $(R,+,\cdot )$ un anillo y sea $S\subset R$ un subconjunto. Decimos que $S$ es un {\bf subanillo} de $R$ si se verifican las siguientes propiedades:
\begin{enumerate}
\item[(i)] $S$ es un subgrupo (aditivo) de $(R,+)$, es decir: 
\begin{itemize}
\item[-)] $0\in S$.
\item[-)] Si $x,y\in S$, entonces $x-y\in S$.
\end{itemize}
\item[(ii)] $1\in S$.
\item[(iii)] Si $x,y\in S$, entonces $x\cdot y\in S$.
\end{enumerate}
}
{{% /definition %}}

{{% watch %}}
Si $S$ es un asubanillo de $(R,+,\cdot )$, entonces $S$ es un anillo con las operaciones $+$ y $\cdot$.
{{% /watch %}}

Veamos algunos ejemplos.

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item $\Z\subset\Q\subset\R\subset\C$ es una cadena de subanillos. De hecho $\Q$ y $\R$ son {\bf subcuerpos} de $\C$ (cuerpos dentro de un cuerpo).
%\item $\Z 2=\\{ 2n\mid n\in\Z\\}$ es un subanillo de $\Z$ {\em sin elemento unidad}.
%\item Todo anillo $R$ tiene los subanillos {\em impropios} $\\{ 0\\}$ y $R$.
\item El subconjunto 
$$S=\frac{1}{2}\cdot\Z=\left\\{\frac{m}{2}\mid m\in\Z\right\\}\subset \Q$$
es un subgrupo aditivo de $\Q$, pero no es un subanillo al no ser cerrado para el producto, pues
$$\frac{1}{2}\cdot\frac{1}{2}=\frac{1}{4}\notin S.$$
\item El conjunto $\Z 2=\\{ 2n\mid n\in\Z\\}\subset \Z$ es un subgrupo aditivo de $\Z$ y es cerrado para el producto, pero no es subanillo porque $1\notin\Z 2$
\end{enumerate}
{{% /example %}}

\inhibe
Dejamos como ejercicio la demostración de la siguiente propiedad.

{{% proposition %}}

Sea $S$ un subconjunto de una anillo $R$. Entonces $S$ es subanillo si y solo si es un subgrupo de $R$ para la suma y el producto es interno en $S$, es decir, si y solo si satisface las siguientes propiedades:
\begin{enumerate}
\item $S\ne\varnothing$.
\item $\forall x,y\in S, x-y\in S$.
\item $\forall x,y\in S, xy\in S$.
\end{enumerate}
{{% /proposition %}}
\endinhibe

## Homomorfismos de anillos

De manera análoga a lo que se hizo con los grupos, podemos introducir el concepto de homomorfismo de anillo, que será una aplicación compatible con la suma (homomorfismo de grupos) y con el producto.

{{% definition %}}
{Homomorfismo de anillos}{
Sean $R$ y $S$ dos anillos. Una aplicación $f\colon R\to S$ se dice que es un {\bf homomorfismo de anillos} si para todo par de elementos $x,y\in R$ se verifica que
$$f(x+y)=f(x)+f(y),\ f(xy)=f(x)f(y)\mbox{ y }f(1_R)=1_S.$$

Si $f$ es un homomorfismo sobreyectivo se dice {\bf epimorfismo}, si es un homomorfismo inyectivo se dice {\bf monomorfismo} y si es un homomorfismo biyectivo se dice {\bf isomorfismo}. Si existe un isomorfismo entre dos anillos $R$ y $S$, se dice que ambos anillos son {\bf isomorfos} y se escribe $R\cong S$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item La aplicación identidad de un anillo $R$, $Id_R$, es un isomomorfismo de anillos.
\item Si $S$ es un subanillo del anillo $R$, entonces la inclusión $i:S \longrightarrow R$ es un homomorfismo de anillos. Como $i$ es in yectiva, de hecho es un monomorfismo de anillos.
%??\item Sea $m>0$ un entero. La aplicación $p_m\colon\Z\to\Z /\Z m$ dada por $p_m (x)=x+\Z m$ es un %homomorfismo de anillos.
%??\item De hecho, si $R$ es un anillo copnmutativo y unitario e $I\subset R$ es un ideal, la %aplicación $p\colon R\to R/I$ dada por $p (x)=x+I$ es un homomorfismo de anillos.
\item Sea $R$ el conjunto de las matrices de la forma
$$\left(\begin{array}{rr} a & b\\ -b & a\end{array}\right),\mbox{ con }a,b\in\R .$$
Es fácil comprobar que $R$ es un subanillo del anillo de la matrices ${\cal M}_2(\R)$ cuadradas de orden 2 con coeficientes en $\R$. Definamos la aplicación
$$\phi\colon R\to\C$$
por la regla
$$\phi\left(\begin{array}{rr} a & b\\ -b & a\end{array}\right) =a+ib\in\C .$$

Se comprueba que $\phi$ es un homomorfismo, pues es compatible con el producto:
$$\phi\left(\left(\begin{array}{rr} a_1 & b_1\\ -b_1 & a_1\end{array}\right)
\left(\begin{array}{rr} a_2 & b_2\\ -b_2& a_2\end{array}\right)\right) =
\phi\left(\begin{array}{rr} a_1a_2-b_1b_2 & a_1b_2+a_2b_1\\ -a_1b_2-a_2b_1 & a_1a_2-b_1b_2\end{array}\right)=$$
$$=a_1a_2-b_1b_2+i(a_1b_2+a_2b_1)=(a_1+ib_1)(a_2+ib_2)=$$
$$=\phi\left(\begin{array}{rr} a_1 & b_1\\ -b_1 & a_1\end{array}\right)
\phi\left(\begin{array}{rr} a_2 & b_2\\ -b_2& a_2\end{array}\right) ,
$$
con la suma:
$$
\phi\left(\left(\begin{array}{rr} a_1 & b_1\\ -b_1 & a_1\end{array}\right) +
\left(\begin{array}{rr} a_2 & b_2\\ -b_2& a_2\end{array}\right)\right) =
\phi\left(\begin{array}{rr} a_1+a_2 & b_1+b_2\\ -b_1-b_2 & a_1+a_2\end{array}\right)
=$$
$$=a_1+a_2+i(b_1+b_2)=(a_1+ib_1)+(a_2+ib_2)=$$
$$=\phi\left(\begin{array}{rr} a_1 & b_1\\ -b_1 & a_1\end{array}\right) +
\phi\left(\begin{array}{rr} a_2 & b_2\\ -b_2& a_2\end{array}\right) ,
$$
y transforma la unidad de $R$ en la unidad de $\C$:
$$\phi (I)=\phi\left(\begin{array}{rr} 1 & 0\\ 0 & 1\end{array}\right)=1.$$

Es inmediato comprobar que $\phi$ es sobreyectiva. Para ver que es inyectiva, como $\phi$ es un homomorfismo de grupos, podemos calcular el $\ker (\phi )$. En efecto,
$$\phi\left(\begin{array}{rr} a & b\\ -b & a\end{array}\right) =a+ib=0\Leftarrow a=0=b.$$
Luego
$$\ker (\phi )=\left\\{\left(\begin{array}{rr} 0 & 0\\ -0 & 0\end{array}\right)\right\\}$$
y $\phi$ es inyectiva. Por tanto $\phi$ es un isomomorfismo de anillos y $R\cong\C$.
\end{enumerate}
{{% /example %}}

{{% theorem %}}
{Núcleo e imagen de un homomorfismo}{
Sean $R$ y $S$ anillos conmutativos. Sea $\phi\colon R\to S$ un homomorfirmos de anillos. Entonces $\im (\phi )$ es un subanillo de $S$ y $\ker (\phi )$ sabemos que es un subgrupo aditivo de $(R,+)$ que además verifica la siguiente propiedad:
$$ \forall x\in R,\ \forall y \in \ker (\phi ) \ \text{\ se tiene\ }\ x\cdot y \in \ker (\phi ).
$$
}
{{% /theorem %}}

{{% proof %}}
 Sabemos que $\im (\phi )$ es un subgrupo (aditivo) de $(S,+)$. Sean $y_1,y_2\in\im (\phi )$: existen $x_1,x_2\in R$ tales que $\phi (x_1)=y_1$ y $\phi (x_2)=y_2$. Por ser $\phi$ homomorfismo $y_1y_2=\phi (x_1)\phi (x_2)=\phi (x_1x_2)$, luego $y_1y_2\in\im (\phi )$. Además, $1_S= \phi(1_R) \in \im (\phi )$. Por tanto, $\im (\phi )$ es un subanillo de $S$.

Ya sabemos que $\ker (\phi )\subset R$ es un subgrupo aditivo.

Sean $x\in R$ e $y\in\ker (\phi)$. Entonces $\phi (xy)=\phi (x)\phi (y)=\phi (x) 0=0$, luego $xy\in\ker (\phi )$.
{{% /proof %}}

{{% theorem %}}
{Isomorfismo inverso}{
Si $\phi\colon R\to S$ es un isomorfismo de anillos, entonces también lo es $\phi^{-1}\colon S\to R$.
}
{{% /theorem %}}

{{% proof %}}

Sabemos que $\phi^{-1}$ es isomorfismo de grupos aditivos. Veamos entonces que es compatible con el producto. Sean $y_1,y_2\in S$, se verifica
$$\phi\left(\phi^{-1}(y_1y_2)\right) =y_1y_2,$$
$$\phi\left(\phi^{-1}(y_1)\phi^{-1}(y_2)\right) =\phi\left(\phi^{-1}(y_1)\right)\phi\left(\phi^{-1}(y_2)\right)=y_1y_2.$$
Luego $\phi\left(\phi^{-1}(y_1y_2)\right) =\phi\left(\phi^{-1}(y_1)\phi^{-1}(y_2)\right)$, como $\phi$ es inyectiva se sigue que $\phi^{-1}(y_1y_2) =\phi^{-1}(y_1)\phi^{-1}(y_2)$. 

Además, $\phi^{-1}(1_S) = \phi^{-1}(\phi(1_R)) = 1_R$.

Por tanto $\phi^{-1}$ es isomorfismo de anillos.
{{% /proof %}}

## Ideales

{\bf A partir de este momento, todos los anillos que consideremos serán conmutativos.}

{{% definition %}}
{Ideal de un anillo (conmutativo)}{
Sea $(R,+,\cdot )$ un anillo (conmutativo) y sea $I\subset R$ un subconjunto. Decimos  que $I$ es un ideal de $R$ si $I$ es un subgrupo de $(R,+)$ y para todo $x\in R, y\in I$ se verifica que $xy\in I$.
}
{{% /definition %}}


{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item Si $R$ es un anillo conmutativo, los subgrupos triviales $\\{ 0\\}$ y $R$ son ideales de $R$. Llamaremos {\bf ideales propios} de $R$ a los no triviales.
\item Un ideal $I$ de un anillo $R$ es el total, si y solo si $1\in I$.
\item Si $\phi: R\to S$ es un homomorfismo de anillos, entonces $\ker(\phi)$ es un ideal de $R$.
\item Sea $R$ un anillo conmutativo y $x\in R$ un elemento. Sea el subconjunto
$$Rx=\\{ rx\mid r\in R\\}$$
de los "múltiplos" de $x$ en $R$. Entonces $Rx$ es un ideal de $R$, que llamaremos {\em el ideal de $R$ generado por $x$}. Diremos que un ideal de este tipo es un {\bf ideal principal}
\item Se demostrará más adelante (ver página \pageref{subgruposZ}) que los subgrupos de $(\Z ,+)$ son de la forma $\Z n$ con $n\geq 0$ (nótese que $\Z n = \Z (-n)$). Por tanto cada $\Z n$ coincide con el ideal generado por $n$ y por tanto también es un ideal de $\Z$. Así pues, todos los subgrupos de $(\Z ,+)$ son ideales del anillo $\Z$. 

Esto es debido a que en el anillo $\Z$, el producto viene determinado por la suma.
\item Por otro lado, $\Z$ es un subanillo de $\Q$ pero no un ideal pues el elemento $\frac{1}{2}\cdot 1\notin\Z$. 
\end{enumerate}
{{% /example %}}

## Anillos cociente

Sean $R$ un anillo (conmutativo) e $I$ un ideal de $R$. Como el grupo $(R,+)$ es abeliano, el subgrupo $I$ de $(R,+)$ es normal. Sabemos entonces (tema 2, grupos cocientes) que la operación
$$(x+I)+(y+I)=(x+y)+I\ \forall x,y\in R$$
está bien definida y dota de estructura de grupo (también abeliano) al cociente $R/I$.

Recordemos que el cociente de grupos viene definido por la relación de equivalencia en $R$
$$x_1\sim_I x_2\Longleftrightarrow x_1-x_2\in I.$$
Las clases de equivalencia de esta relación son los conjuntos $x+I$, luego
$$x_1+I=x_2+I\Longleftrightarrow x_1-x_2\in I.$$

De manera análoga el producto en $R$ define una operación interna y binaria en el cociente:
$$(x+I)(y+I)=(xy)+I\ \forall x,y\in R.$$
Veamos que esta operación está bien definida. Sean $x_1,x_2,y_1,y_2\in R$ tales que $x_1+I=x_2+I$ y $y_1+I=y_2+I$, tenemos que probar que la operación no depende de los representantes elegidos en cada clase, es decir, que $x_1y_1+I=x_2y_2+I$. Lo cual ourre si y solo si $x_1y_1-x_2y_2\in I$.
$$x_1y_1-x_2y_2=x_1y_1-x_2y_1+x_2y_1-x_2y_2=(x_1-x_2)y_1+x_2(y_1-y_2).$$
Como $x_1+I=x_2+I$, se tiene que $x_1-x_2\in I$. Al ser $I$ ideal, también tenemos que $(x_1-x_2)y_1\in I$. Análogamente $x_2(y_1-y_2)\in I$. Luego
$$x_1y_1-x_2y_2\in I.$$

Una vez definidas las operaciones suma y producto, dejamos como ejercicio comprobar que $(R/I,+,\cdot )$ es un anillo conmutativo. Nótese el elemento cero de $R/I$ es la clase $0+I=I$ y que el elemento uno de $R/I$ es la clase $1+I$.

{{% theorem %}}
{Anillo cociente}{
Sean $(R,+,\cdot )$ un anillo conmutativo e $I\subset R$ un ideal. Entonces el conjunto cociente $R/I$ con las operaciones $+$ y $\cdot$ previamente definidas es de nuevo un anillo conmutativo, que llamaremos {\em anillo cociente} de $R$ por $I$.
}
{{% /theorem %}}

{{% watch %}}
 Si $I$ es un ideal del anillo $R$, la proyección natural $p: R \longrightarrow R/I$ es un epimorfismo de anillos cuyo núcleo es el ideal $I$.

Nótese que el anillo cociente $R/I$ es nulo si y solo si $I=R$.
{{% /watch %}}

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item En el anillo $\Z$ los ideales $\Z n$ con $n\geq 1$ producen anillos cocientes finitos de $n$ elementos:
$$\frac{\Z}{\Z n}=\left\\{ 0+\Z n,1+\Z n,\ldots ,(n-1)+\Z n\right\\} = \left\\{ \overline{0},\overline{1},\ldots ,\overline{n-1}\right\\} .$$
\item Para $n=2$, estas son las tablas de las operaciones en $\frac{\Z}{\Z 2}$:

\begin{tabular}{c||c|c}
+ & $\overline{0}$ & $\overline{1}$ \\
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{1}$ \\
\hline
$\overline{1}$ & $\overline{1}$ & $\overline{0}$
\end{tabular}
\quad\quad
\begin{tabular}{c||c|c}
$\cdot$ & $\overline{0}$ & $\overline{1}$ \\
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{0}$ \\
\hline
$\overline{1}$ & $\overline{0}$ & $\overline{1}$
\end{tabular}.

Por tanto comprobamos que $\frac{\Z}{\Z 2}$ es un cuerpo.
\item Para $n=3$, estas son las tablas de las operaciones en $\frac{\Z}{\Z 3}$:

\begin{tabular}{c||c|c|c}
+ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$\\
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ \\
\hline
$\overline{1}$ & $\overline{1}$ & $\overline{2}$ & $\overline{0}$\\
\hline
$\overline{2}$ & $\overline{2}$ & $\overline{0}$ & $\overline{1}$
\end{tabular}
\quad\quad
\begin{tabular}{c||c|c|c}
$\cdot$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$\\ 
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{0}$ & $\overline{0}$  \\
\hline
$\overline{1}$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$   \\
\hline
$\overline{2}$ & $\overline{0}$ & $\overline{2}$ & $\overline{1}$  
\end{tabular}.

Por tanto comprobamos que $\frac{\Z}{\Z 3}$ es un cuerpo (todos sus elementos no nulos son unidades).
\item En el anillo $R=\Q [x]$ de los polinomios en la indeterminada $x$ con coeficientes racionales, consideramos el ideal $I=\Q[x]\cdot (x^2-2)$.

Dado que $x^2+I=2+I$, es fácil comprobar que en cada clase del conjunto cociente $R/I$ podemos encontrar un representante de grado menor o igual que 1, de donde
$$\frac{\Q [x]}{\Q[x]\cdot (x^2-2)}=\left\\{ (ax+b)+I\mid a,b\in\Q\right\\} .$$

Además, cada elemento no nulo $(ax+b)+I$ posee un inverso multiplicativo, luego el anillo cociente $R/I$ es un cuerpo. Dejamos como ejercicio la demostración de este hecho.
\end{enumerate}
{{% /example %}}

## Factorización canónica

Hay un teorema de factorización canónica para homomorfismos de anillos.

{{% theorem %}}
{Factorización canónica}
{	Todo homomorfismo de anillos conmutativos, $f\colon R\to S$, factoriza de manera única como la composición $f=i\circ\bar f\circ p$:
	\[\xymatrix{R\ar[r]^-{f}\ar[d]_-p& S\\
		R/\ker(f)\ar[r]^-\cong_-{\bar f}& \im(f)\ar[u]_-i}\]
donde  $p$ es la proyección natural (que es un epimorfismo de anillos), $i$ es la inclusión (que es un monomorfismo de anillos), y $\bar f$ es un isomorfismo de anillos.}
{{% /theorem %}}

{{% proof %}}

	La factorización es la misma que la de una aplicación cualquiera. Ya sabemos que $p$ e $i$ son homomorfismos de anillos. Sabemos también que $p$ es sobreyectiva, $i$ es inyectiva y que $\bar f$, definida por ${\bar f}(x +\ker(f))=f(x)$, es biyectiva. Por último, también sabemos que $\bar f$ es un homomorfismo de grupos aditivos. Es evidente que $\bar f (1_{R/\ker (f)})=\bar f (1_R+\ker (f))=f(1_R)=1_S$. Falta ver que $\bar f$ es compatible con el producto. Por comodidad, llamaremos $I=\ker(f)$. Al ser $f$ un homomorfismo de anillos se tiene:
	\begin{align*}
		\bar f((x_1  +I )(x_2  +I ))&= \bar f((x_1 x_2)+I )\\
		&=f(x_1 x_2) \\
		&=f(x_1) f(x_2) \\
		&=\bar f(x_1  + I )\bar f(x_2 +I).
	\end{align*}
	Luego $\bar f$ es también un homomorfismo de anillos.
{{% /proof %}}

{{% corollary %}}
{\label{epimorfismo}}
	Si $f\colon R\to S$ es un epimorfismo de anillos entonces la aplicación $\bar f\colon R/\ker(f)\to S$ es un isomorfismo.
{{% /corollary %}}

{{% corollary %}}

	Si $f\colon R\to S$ es un monomorfismo de anillos entonces $\bar f\colon R\to \im(f)$ es un isomorfismo.
{{% /corollary %}}

### Divisores de cero. Dominios de integridad

{{% example name="Ejemplo" %}}
 Estudiemos el anillo cociente $\frac{\Z}{\Z 4}$. Las tablas de sus operaciones son:

\begin{center}
\begin{tabular}{c||c|c|c|c}
+ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ & $\overline{3}$\\
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ & $\overline{3}$ \\
\hline
$\overline{1}$ & $\overline{1}$ & $\overline{2}$ & $\overline{3}$ & $\overline{0}$\\
\hline
$\overline{2}$ & $\overline{2}$ & $\overline{3}$ & $\overline{0}$ & $\overline{1}$\\
\hline
$\overline{3}$ & $\overline{3}$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ \\ \hline
\end{tabular}
\quad\quad
\begin{tabular}{c||c|c|c|c}
$\cdot$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ & $\overline{3}$\\ 
\hline\hline
$\overline{0}$ & $\overline{0}$ & $\overline{0}$ & $\overline{0}$  & $\overline{0}$  \\
\hline
$\overline{1}$ & $\overline{0}$ & $\overline{1}$ & $\overline{2}$ & $\overline{3}$   \\
\hline
$\overline{2}$ & $\overline{0}$ & $\overline{2}$ & $\overline{0}$   & $\overline{2}$ \\ 
\hline
$\overline{3}$ & $\overline{0}$ & $\overline{3}$ & $\overline{2}$   & $\overline{1}$ \\ \hline
\end{tabular}.
\end{center}

Observamos pues que las unidades de $\frac{\Z}{\Z 4}$ son $\overline{1}$ y $\overline{3}$. Observamos también que, aún siendo $\overline{2} \neq \overline{0}$, se tiene que $\overline{2} \cdot \overline{2} = \overline{0}$.
{{% /example %}}

{{% definition %}}
{Divisor de cero}{
Sea $R$ un anillo (conmutativo). Se dice que un elemento $x\in R$ es un {\bf divisor de cero} si existe un elemento no nulo $y\in R$ tal que $xy=0$.
}
{{% /definition %}}

En un anillo no nulo, el $0$ siempre es un divisor de cero, pues $1\cdot 0 = 0$.

{{% example name="Ejemplo" %}}

En el anillo $\Z/\Z 4$, el elemento $2+\Z 4$ es un divisor de cero, pues $(2+\Z 4)(2+\Z 4) = 0+\Z 4$.

Asimismo, en el anillo $\Z /\Z 6$ el elemento $2+\Z 6$ es un divisor de cero, pues
$$(2+\Z 6)(3+\Z 6)=6+\Z 6=0+\Z 6.$$
{{% /example %}}

{{% definition %}}
{Dominio de Integridad}{
Un {\bf dominio de integridad} (DDI) es un anillo conmutativo no nulo ($1\neq 0$) cuyo único divisor de cero es el $0$.
}
{{% /definition %}}

{{% proposition %}}
 Sea $R$ un anillo no nulo. Las siguientes propiedades son equivalentes:
\begin{enumerate}
\item[(a)] $R$ es un DDI.
\item[(b)] Si $r,s\in R$, $rs=0$ $\Longrightarrow$ $r=0$ ó $s=0$.
\end{enumerate}
{{% /proposition %}}

{{% example name="Ejemplo" %}}
\quad
\begin{enumerate}
\item Los anillos $\Z$, $\Q$, $\R$ y $\C$ son dominios de integridad.
\item Los anillos cociente $\Z /\Z n$ con $n>0$ son dominio de integridad si y solo si $n$ es un número primo\footnote{Esto se demostrará más adelante.}.
\end{enumerate}
{{% /example %}}

{{% theorem %}}
{Dominio de integridad y propiedad cancelativa}{
Sea $R$ un anillo conmutativo. Entonces $R$ es un dominio de integridad si y solo si se satisface en $R$ la {\em propiedad cancelativa}, es decir, 
$$xy=xz \wedge x\ne 0\Rightarrow y=z.$$
}
{{% /theorem %}}

{{% proof %}}

Si $R$ es un dominio de integridad, supongamos que $xy=xz$ con $x\ne 0$. Entonces
$$xy=xz\Rightarrow xy-xz=0\Rightarrow x(y-z)=0\stackrel{x\ne 0}{\Longrightarrow} y-z=0\Rightarrow y=z.$$

Recíprocamente, si se verifica la propiedad cancelativa, sea $x\in R$, $x\ne 0$ tal que existe $y\in R$ con $xy=0$. Entonces
$$0=xy=x0\Rightarrow y=0.$$
Luego $R$ no tiene divisores de cero.
{{% /proof %}}

{{% proposition %}}

Todo dominio de integridad finito es un cuerpo.
{{% /proposition %}}

{{% proof %}}

Sea $R$ un dominio de integridad finito, sea $x\in R$ un elemento no nulo. Vamos a probar que $x$ es una unidad.

Consideremos la aplicación $f\colon R\to R$ dada por $f(y)=xy$.

Veamos que $f$ es inyectiva. Si $f(y)=f(z)$ entonces $xy=xz$. por la propiedad cancelativa $y=z$. Luego $f$ es inyectiva.

Como $R$ es finito cualquier aplicación inyectiva $f\colon R\to R$ es también sobreyectiva (y por tanto biyectiva). Así que existe $y\in R$ tal que $f(y)=1$. Es decir,
$$xy=f(y)=1.$$
Luego todo elemento no nulo $x\in R$ tiene inverso multiplicativo. Por tanto $R$ es un cuerpo.
{{% /proof %}}

{{% example name="Ejemplo" %}}

Si $p\in Z$ es primo, el anillo $\Z /\Z p$ es un dominio de integridad, pues dados 
$\overline{m},\overline{n} \in \Z /\Z p$, si $\overline{m}\cdots \overline{n} = \overline{0}$, entonces $\overline{mn}=\overline{0}$ y por tanto $mn\in \Z p$. Ahora bien, si el número primo $p$ divide a $mn$, tiene que dividir a $m$ o a $n$ y por tanto $\overline{m}=\overline{0}$ ó
$\overline{n} = \overline{0}$. Como $\Z /\Z p$ es finito, deducimos que es un cuerpo.
{{% /example %}}

{{% watch %}}
En adelante notaremos por $\F_p$ al cuerpo $\Z /\Z p$, con $p$ número primo.
{{% /watch %}}

{{% proposition %}}

Sea $R$ un anillo conmutativo. Entonces el conjunto de las {\em no unidades} de $R$ ($R\setminus R^*$) es igual a la unión de todos los {\em ideales propios} de $R$.
{{% /proposition %}}

{{% proof %}}

Si $x$ no es una unidad en $R$ entonces $Rx=\\{ yx\mid y\in R\\}$ es un ideal propio de $R$ que contiene a $x$, pues $1\notin Rx$.

Recíprocamente, si una unidad $y\in R$ perteneciera a un ideal $I\subset R$ entonces para cualquier $x\in R$ tendríamos que $x=(xy^{-1})y\in I$, de donde $I=R$. Luego ninguna unidad puede pertenecer a un ideal propio de $R$.
{{% /proof %}}

Acabamos de demostrar lo siguiente:

{{% corollary %}}

Si un ideal $I\subset R$ contiene una unidad en $R$ entonces $I=R$.
{{% /corollary %}}

{{% corollary %}}

Un anillo conmutativo no nulo es un cuerpo si y solo si no tiene ideales propios no nulos.
{{% /corollary %}}

## Ideales primos y maximales

{{% definition %}}
{Ideal maximal}{
Sea $R$ un anillo (conmutativo). Decimos que un ideal propio $I\subset R$, $I\neq R$, es {\bf maximal} si los únicos ideales que lo contienen son el propio $I$ y $R$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}

El ideal $\Z p\subset \Z$ con $p$ primo es un ideal maximal. En efecto, si $I\subset\Z$ es un ideal tal que $\Z p\subset I$, como sabemos que $I$ ha de ser de la forma $\Z n$ para algún natural $n$, se tendrá que $\Z p\subset \Z n$, lo que implica que $p\in \Z n$, es decir, que $n$ divide a $p$. Como $p$ es primo, o bien $n=1$, en cuyo caso $I=\Z n = \Z$, o bien $n=p$, en cuyo caso $I= \Z_n = Z p$.

Otra manera de probar lo anterior es la siguiente:
si $I\subset\Z$ es un ideal con $I\neq \Z$ tal que $\Z p\subset I$, entonces la aplicación
$$\begin{array}{rccl}
f\colon & \F_p = \Z / \Z p  & \to & \Z / I\\
 & n+I & \mapsto & f(n+\Z p)=n+I
\end{array}$$
está bien definida y 
es un homomorfismo sobreyectivo de grupos (es un epimorfismo). Entonces $|\Z / \Z p|=|\Z / I| |\ker (f)|$, y como $\ker (f) \neq \F_p$ (porque $f(1+\Z p)=1+I \neq 0+I$), se debe tener $|,\ker (f)| = 1$, o lo que es lo mismo, $\ker (f) = \\{0\\}$, de donde $f$ también es inyectiva (y por tanto biyectiva), lo que implica que $I=\Z p$.
{{% /example %}}

{{% definition %}}
{Ideal primo}{
Sea $R$ un anillo (conmutativo). Decimos que un ideal propio $I$ de $R$ es un {\bf ideal primo} si satisface la siguiente propiedad:
$$x,y\in R,\ xy\in I\Rightarrow x\in I\mbox{ ó }y\in I.$$
}
{{% /definition %}}

{{% proposition %}}
 Sea $R$ un anillo. Las propiedades siguientes son equivalentes:
\begin{enumerate}
\item[(a)] $R$ es un DDI.
\item[(b)] El ideal $\\{0\\}$ de $R$ es un ideal primo.
\end{enumerate}
Asimismo, las propiedades siguientes también son equivalentes:
\begin{enumerate}
\item[(a')] $R$ es un cuerpo.
\item[(b')] El ideal $\\{0\\}$ de $R$ es un ideal maximal.
\end{enumerate}
{{% /proposition %}}

{{% proposition %}}

Sean $R$ un anillo conmutativo e $I\subset R$ un ideal propio de $R$. Entonces:
\begin{enumerate}
\item $I$ es un ideal primo de $R$ si y solo si el anillo $R/I$ es un dominio de integridad.
\item $I$ es un ideal maximal de $R$ si y solo si el anillo $R/I$ es un cuerpo.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}

\begin{enumerate}
\item Supongamos que $I$ es un ideal primo. Sean $x,y\in R$ tales que $(x+I)(y+I)=0+I$, entonces
$$0+I=(x+I)(y+I)=xy+I\Leftrightarrow xy\in I\Rightarrow x\in I\ \vee\ y\in I\Rightarrow$$
$$\Rightarrow x+I=0+I\ \vee\ y+I=0+I.$$
Luego $R/I$ no tiene divisores de cero.

Recíprocamente, si $R/I$ es un dominio de integridad, sean $x,y\in R$ tales que $xy\in I$. Entonces:
$$xy\in I\Rightarrow 0+I=xy+I=(x+I)(y+I)\Rightarrow x+I=0+I\ \vee\ y+I=0+I\Rightarrow$$
$$\Rightarrow x\in I\ \vee\ y\in I.$$
Luego $I$ es un ideal primo.
\item Supongamos que $I\subset R$ es un ideal maximal. Sea la proyección $p\colon R\to R/I$ dada por $p(x)=x+I$, que sabemos que es un homomorfismo de anillos. Si $J\subset R/I$ es un ideal, dejamos como ejercicio comprobar que $p^{-1}(J)$ es un ideal de $R$ que contiene a $I$, luego debe ser $p^{-1}(J)=I$ o $p^{-1}(J)=R$. En el primer caso $J=\\{ 0+I\\}$ y en el segundo $J=R/I$. Luego los únicos ideales de $R/I$ son los triviales y, por tanto, $R/I$  es un cuerpo.

Recíprocamente, si $R/I$ es un cuerpo sea $J\subset R$ un ideal tal que $I\subsetneqq J$. Sea $x\in J\setminus I$, como $x\notin I$ entonces $x+I\ne 0+I$ y $x+I$ tiene un inverso en $R/I$. Sea $y\in R$ tal que $(x+I)(y+I)=1+I$. Como $(x+I)(y+I)=xy+I$, se tiene que $1\in xy + I\subset J$. Luego $J=R$ concluyendo que $I$ es maximal.
\end{enumerate}
{{% /proof %}}

Como todo cuerpo es dominio de integridad (porque toda unidad no es divisor de cero), tenemos el siguiente corolario.

{{% corollary %}}

Todo ideal maximal de un anillo conmutativo (no nulo) es un ideal primo.
{{% /corollary %}}

El recíproco no es cierto.

{{% example name="Ejemplo" %}}

Sea $R=\Q [x,y]$ el anillo de polinomios en dos variables con coeficientes racionales. Sea el ideal $I=Rx$ de los polinomios que son múltiplos de $x$. El ideal $I$ no es máximal, pues está contenido en el ideal
$$J=\\{ g(x,y)\in R\mid\mbox{el término independiente de }g(x,y)\mbox{ es nulo}\\}.$$

Veamos que $I$ es un ideal primo que no es maximal.

Consideremos la aplicación $\phi\colon R\to\Q [y]$ dada por $\phi (f(x,y))=f(0,y)$. Se comprueba fácilmente que $\phi (f+g)=\phi (f)+\phi (g)$, $\phi (fg)=\phi (f)\phi (g)$ y que $\phi (1)=1$. Además $\phi$ es sobreyectiva. Luego $\phi$ es un homomorfismo sobreyectivo de anillos.

Como $f(0,y)=0$ si y solo si $f(x,y)$ es un múltiplo de $x$, se tiene que $\ker (\phi )=I$. Por el corolario \ref{epimorfismo} es $R/I\cong\Q [y]$. Como $\Q[y]$ es un dominio de integridad que no es un cuerpo, $I$ es ideal primo que no es maximal.
{{% /example %}}

## La característica de un dominio de integridad

{{% proposition %}}

Sea $R$ un dominio de integridad y sea $S=\langle 1\rangle$ el subgrupo aditivo de $R$ generado por $1$. Si $S$ es un grupo finito de orden $p$ entonces $p$ es primo y $px=x+\stackrel{p}{\cdots}+x=0$ para todo $x\in R$
{{% /proposition %}}

{{% proof %}}

Supongamos que $p=p_1p_2$. Como el orden de $1$ es $p$, se tiene que
$$0=p1=(p_1p_2)1=(p_11)(p_21).$$
Al ser $R$ un dominio de integridad, debe ser $p_11=0$ o $p_21=0$, en cuyo caso $p$, el orden de $1$, divide a $p_1$ o a $p_2$. Luego de los dos factores de $p$ uno es él mismo y el otro $1$. Es decir, $p$ es primo.

Por otro lado, si $x\in R$, se tiene
$$px=(p1)x=(1+\stackrel{p}{\cdots}+1)x=0x=0.$$
{{% /proof %}}

{{% definition %}}
{Característica de un dominio de integridad}{
Sea $R$ un dominio de integridad. Si el orden de $S=\langle 1\rangle$ es un número primo $p>0$, diremos que $R$ tiene {\bf característica $p$}. Si por el contrario el orden de $1$ es infinito diremos $R$ tiene {\bf característica $0$}.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}

$\F_p$ y $\F_p[x]$ tienen característica $p$. Sin embargo $\Z$, $\Q$, $\R$ y $\R [x]$ tienen característica 0.
{{% /example %}}

{{% watch %}}
Si $R$ es un dominio de integridad finito entonces existe un primo $p>0$ tal que $R$ tiene característica $p$. El recíproco no es cierto, existen dominios de integridad infinitos con característica positiva, por ejemplo $\F_p[x]$.
{{% /watch %}}


<!--


## Algoritmo de Euclides. Identidad de Bézout


Veamos un procedimiento, el algoritmo de Euclides, para el cálculo
del divisor común máximo.

%
{{% proposition %}}
 Sean $a,b\in\Z$ no nulos, pongamos $|a|\geq |b|$, y
efectuemos la división euclídea $a=qb+r$. Entonces
$$
\mbox{mcd}(a,b)= \mbox{mcd}(b,r).
$$
{{% /proposition %}}

{{% proof %}}
 Si $r=0$ es $a=qb$, luego
$\mbox{mcd}(a,b)=b=\mbox{mcd}(b,0)$. Si $r\neq 0$, sean
$$
d=\mbox{mcd}(a,b), \quad d'=\mbox{mcd}(b,r)\; ;
$$
entonces $d|r=a-qb$, luego $d|d'$. Por otra parte, $d'|a=qb+r$,
luego $d'|d$ y así $d'=\pm d$.
{{% /proof %}}

%
\begin{metodocolor}{Algoritmo de Euclides}
{El resultado anterior nos permite describir el {\bf Algoritmo de Euclides:} Sean $a,b$ enteros no nulos, pongamos $|a|\geq |b|$,
y efectuemos la división euclídea $a=qb+r.$ Como $r< |b|$, podemos dividir $b$ entre $r$, y así sucesivamente, obteniendo:

$$\begin{array}{lcll}
    a & = & qb+r & 0 \leq r < |b| \\
    b & = & q_0r+r_1 & 0 \leq r_1 < r \\
    r & = & q_1r_1+r_2 & 0 \leq r_2 < r_1 \\
    r_1 & = & q_2r_2+r_3 & 0 \leq r_3 < r_2 \\
     & \vdots &  &  \\
    r_{n-1} & = & q_nr_n+r_{n+1} & 0 \leq r_{n+1} < r_n \\
    r_n & = & q_{n+1}r_{n+1}+0 & r_{n+2}=0
  \end{array}
$$
Pues al ser los restos enteros mayores o iguales que cero cada vez más pequeños, debemos obtener alguno, $r_{n+2}$, que sea nulo.}
\end{metodocolor}

%
{{% proposition %}}
 En la situación anterior se tiene que $\mbox{mcd}(a,b)=r_{n+1}$.
Es decir, el divisor común máximo de $a$ y $b$ es el último resto no
nulo al aplicar sucesivamente el algoritmo de división.
{{% /proposition %}}


{{% proof %}}
 Por la proposición anterior se tiene
que:
$$
\mbox{mcd}(a,b) = \mbox{mcd}(b,r)=\mbox{mcd}(r,r_1)=
\dots=\mbox{mcd}(r_{n-1},r_n)=$$
$$=\mbox{mcd}(r_n,r_{n+1})=r_{n+1},
$$
lo cual demuestra el resultado.
{{% /proof %}}

Con este algoritmo hemos demostrado la existencia del divisor común máximo.

{{% theorem %}}
{Existencia del divisor común máximo} {Dados
dos enteros no nulos $a$ y $b$, existe el divisor común máximo de $a$ y $b$, $\operatorname{mcd}(a,b)$, que es único salvo el signo.}
{{% /theorem %}}

{{% watch %}}
 Sean $a,b$ enteros y sea $d=\mbox{mcd}(a,b)$. Obsérvese que para cualesquiera enteros $\gamma, \delta$ se verifica que $\gamma a + \delta b$ es un múltiplo de $d$.
{{% /watch %}}

Asociada al divisor común máximo está la identidad de Bézout, cuya
existencia teórica viene afirmada por el siguiente teorema:


{{% theorem %}}
{Identidad de Bézout} {Sean $a,b$
enteros no nulos y sea $d=\mbox{mcd}(a,b)$. Existen enteros $\alpha,\beta$
tales que
$$
\alpha a+\beta b=d.
$$
}
{{% /theorem %}}


{{% proof %}}
 Demostramos la existencia de manera no
constructiva. Sea el subgrupo de $\Z$ generado por $a$ y $b$:
$$
S=\langle a,b\rangle =\\{n\in\Z\mid n=xa+yb, \; x,y\in\Z\\}\, .
$$
Sabemos (Subgrupos de $\Z$, página \pageref{subgruposZ}) que existe $n_0>0$ tal que $S=\Z n_0$. Vamos a demostrar que $n_0=d$, lo haremos probando que $d|n_0$ y $n_0|d$.

Como $n_0\in S$, existen $\alpha,\beta\in\Z$ tales que 
$$n_0=\alpha a+\beta b.$$
Por definición $d|a$ y $d|b$ luego
$d|n_0$.

Para ver que $n_0|d$, demostraremos
que $n_0|a$ y $n_0|b$. Vamos a probar que $n_0|a$, la otra relación
se prueba de forma análoga. Por la división euclídea podemos
escribir $a=qn_0+r$ con $0\leq r < n_0$. Entonces,
$$
r=a-qn_0=a-q(\alpha a +\beta b)=(1-q\alpha)a + (-q\beta) b.
$$
Por la minimalidad de $n_0$ en $S=\Z n_0$ tiene que ser $r=0$, luego $n_0|a$.
{{% /proof %}}

%
{{% watch %}}
 Los enteros $\alpha$ y $\beta$ que
aparecen en la identidad de Bézout no son únicos. En efecto: para
cualesquiera $\alpha, \beta$ tales que $\alpha a +\beta b=d$, es
$$
(\alpha -k b)a + (\beta+k a)b=d, \quad \forall k\in\Z \, .
$$
{{% /watch %}}

%{{% corollary %}}
 Sean $a,b >0$ enteros y sea $d=\mbox{mcd}(a,b)$. Para cualesquiera enteros $\gamma, \delta$ se verifica que $\gamma a + \delta b$ es un múltiplo de $d.$
%{{% /corollary %}}

La identidad de Bézout nos permite probar el siguiente teorema:


{{% theorem %}}
{Teorema de Euclides} {Sean $a,b,c$ enteros tales que $c|ab$
y $\mbox{mcd}(c,a)=1$; entonces $c|b$. En particular, si $p$ es
primo, $p|ab$ y $p$ no divide a $a$, entonces $p|b$.}
{{% /theorem %}}

%
{{% proof %}}
 Evidentemente, la segunda afirmación es
consecuencia de la pri\-me\-ra; demostremos ésta. Por la identidad de
Bézout, $1 = \alpha a + \beta c.$ Multiplicando por $b$ esta
expresión, se tiene que $b = \alpha ab + \beta cb.$ Como $c|ab$ y
$c|cb$, se tiene que $c|b.$
{{% /proof %}}

%
{{% proposition %}}
 Sean $a,b \in \Z$ no nulos,
$$
d=\mbox{mcd}(a,b), \quad  a'=\frac{a}{d}, \quad b'=\frac{b}{d}\, .
$$
Entonces $a',b'$ son primos entre sí.
{{% /proposition %}}


{{% proof %}}

Si $a'$ y $b'$ no son primos entre sí, entonces existe $d' \in \Z,$ $\pm 1\neq d'$, tal que $d'|a'$ y
$d'|b'$. Luego $dd'|a'd=a$, $dd'|b'd=b$ y $dd'$ no divide a $d$, lo que no es posible.
{{% /proof %}}

%
Ahora podemos redefinir el mínimo común múltiplo usando el máximo
común divisor.


{{% proposition %}}
 Sean $a,b \in\Z$ no nulos, $d = \mbox{mcd}(a,b).$ Se verifica que $\mbox{mcm}(a,b) =
ab/d.$
{{% /proposition %}}

{{% proof %}}
 Sean
$$
m= ab/d, \quad a'=a/d, \quad b'=b/d.
$$

Se tiene que $m = a' b = a b'$, luego es múltiplo de $a$ y $b$. Sea
$m' \in \Z$ múltiplo de $a$ y $b$, $m'=a a"=bb"$. Dividiendo esta
última igualdad por $d$ obtenemos $a'a"=b'b"$ y, por el teorema de
Euclides, $a'|b"$, es decir, $b"=a'c$. Sustituyendo $m'=ba'c=mc$,
luego $m$ es el mínimo común múltiplo de $a$ y $b.$
{{% /proof %}}

%

Esto prueba la existencia del mínimo común múltiplo.

{{% theorem %}}
{Existencia del mínimo común múltiplo} {Dados
dos enteros $a,b$, existe el mínimo común múltiplo de $a$ y $b$, ${\rm mcm}(a,b)$, que es único salvo el signo.}
{{% /theorem %}}

% A continuación escribimos unas cuantas propiedades del máximo común
% divisor y del mínimo común múltiplo.
%
% $$
% \begin{array}{rcl}
% \mbox{mcd}(a,b)c & = & \mbox{mcd}(ac,bc) \\
% \mbox{mcm}(a,b)c & = & \mbox{mcm}(ac,bc) \\
% \mbox{mcd}(\mbox{mcm}(a,b),\mbox{mcm}(a,c))
% & = & \mbox{mcm}(a,\mbox{mcd}(b,c)) \\
% \mbox{mcm}(\mbox{mcd}(a,b),\mbox{mcd}(a,c)) & = &
% \mbox{mcd}(a,\mbox{mcm}(b,c))
% \end{array}
% $$

%

{{% watch %}}
[Número primo] En todas estas notas llamamos números primos a aquellos enteros $p \not= 0, \pm 1$ que son divisibles únicamente por $\pm p$ y $\pm 1$.
{{% /watch %}}

El siguiente resultado nos permitirá trabajar con los enteros a través de sus factores primos.

{{% theorem %}}
 {Teorema fundamental de la divisibilidad} {Todo entero distinto de $0$ y $\pm 1$ se descompone en producto finito de números primos. Esta descomposición es única salvo orden y producto por $\pm 1$.}
{{% /theorem %}}

%
{{% proof %}}
 Vamos primero a demostrar la
existencia de la descomposición. Sea $n\neq 0, \pm 1$ un
entero fijo, y vamos a demostrar que $n$ se descompone en producto
de primos. Podemos suponer que $n>0$ porque, si lo demostramos en
este caso y $n=p_1\cdots p_r$, entonces $-n=(- 1) \cdot p_1\cdots p_r$, lo
que demuestra el resultado para los enteros negativos.

%
La existencia de la descomposición se prueba por inducción a partir
de $n=2$. El número $n=2$ es primo. Supongamos que $n>2$ y que todos
los números menores que $n$ se descomponen en producto finito de
primos. Si $n$ es primo hemos terminado: es producto de un primo (él
mismo). Si no lo es, se descompone en producto $n=n_1n_2$ de dos
enteros positivos estrictamente menores que $n$. Al aplicar a $n_1$
y $n_2$ la hipótesis de inducción, vemos que $n$ se descompone en
producto finito de primos.

%
Para demostrar la unicidad (salvo orden y producto por unidades),
basta considerar enteros positivos $n$ por la misma razón que antes.
Además, basta ver que no puede haber dos descomposiciones distintas
de un mismo número positivo en producto de primos po\-si\-ti\-vos. Vamos a
operar por reducción al absurdo. Supongamos que hay números que
admiten dos descomposiciones distintas en producto de primos
positivos:
$$
n=p_1\cdots p_r=q_1\cdots q_s.
$$

Supongamos que $r \leq s$. Tenemos $p_1 |n=q_1 \cdots q_s$, luego $p_1 |
q_i$, para algún $i$, con $1 \leq i \leq s$, de donde $p_1 = q_i$, al ser $q_i$ primo.
Podemos suponer $i=1$. Dividiendo por $p_1$ se tiene que $p_2\cdots p_r=q_2\cdots q_s.$
Repitiendo el razonamiento para $p_2,  \dots, p_r$, llegamos a $1 =
q_{r+1} \cdots q_s.$ Luego $r=s$ y $p_i = q_i, \quad i=1, \dots, r$.
{{% /proof %}}



{{% theorem %}}
 {Teorema (Euclides)} {El conjunto de los primos es infinito.}
{{% /theorem %}}

%
{{% proof %}}
 Supongamos que no, es decir, que el
conjunto de los primos fuese finito, y sean $p_1,\ldots, p_r$ todos
los primos. Sea $n=p_1\cdots p_r+1$. Por la factorización única, $n$
debe ser divisible por algún $p_i$, lo que implicaría que $p_i|1$ y
eso es imposible.
{{% /proof %}}

%
{{% watch %}}
 Veremos otra forma de ver el máximo común
divisor y el mínimo común múltiplo en función de los factores primos. La factorización única de un entero positivo $n$ la escribiremos
usualmente en la forma
$$
n=\prod_{p>0 \; \mathrm{primo}} p^{\nu_{n}(p)}
$$
donde todos los $\nu_n(p)$ son cero salvo un número finito. La
factorización se puede extender a enteros $n<0$ poniendo
$$
n=(-1)\, \prod_{p>0\; \mathrm{primo}} p^{\nu_{-n}(p)}\, .
$$
Considerando solo números primos positivos, como hemos hecho antes.
{{% /watch %}}

No es difícil comprobar la veracidad de la siguiente proposición, que nos da las definiciones de {\em divisor común máximo} y {\em mínimo común múltiplo} tal y como se trabajan en {\em secundaria}.

{{% proposition %}}

Sean
$$
a=\pm\prod_{p>0\; \mathrm{primo}} p^{\nu_{a}(p)}, \quad b=\pm\prod_{p>0\;
\mathrm{primo}} p^{\nu_{b}(p)}
$$
las descomposiciones de dos enteros $a$ y $b$ en producto de primos. Consideremos
$$
d=\prod_{p>0\; \mathrm{primo}} p^{\min({\nu_{a}(p),\nu_{b}(p))}}\,\mbox{ y }\,
m=\prod_{p>0\; \mathrm{primo}}
p^{\max({\nu_{a}(p),\nu_{b}(p))}}.
$$
Entonces $d=\operatorname{mcd}(a,b)$ y $m={\rm mcm}(a,b)$.
{{% /proposition %}}


## Congruencias


\newcommand{\co}[3]{$#1\equiv #2\;\mathrm{(mod}\, #3\mathrm{)}$}
\newcommand{\cop}[3]{#1\equiv #2\;\mathrm{(mod}\,
#3\mathrm{)}}




%
La divisibilidad nos conduce naturalmente a la noción de congruencia de módulo $m\in\Z\setminus\\{ 0\\}$.

%

{{% definition %}}
{Congruencia} {Dados enteros dos $a,b$ y un entero no nulo $m$, se dirá que $a$ {\bf es congruente con} $b$ {\bf módulo} si $a-b$ es divisible por $m$. En este caso se escribirá \co{a}{b}{m}.}
{{% /definition %}}

%
{{% watch %}}
 De la división euclídea se deduce que siempre se puede suponer
positivo el módulo $m$ de la congruencia. En efecto, si $m<0$ y \co{a}{b}{m}
es $a-b=km,$ luego $a-b=(-k)(-m)$ y por tanto \co{a}{b}{-m}. Esto es lo que haremos de ahora en adelante.
{{% /watch %}}

Una propiedad fundamental de las congruencias es la siguiente:


{{% proposition %}}
 Sean $a,b\in\Z$. Entonces \co{a}{b}{m} si y solo si $a$ y $b$ dan
el mismo resto en la división euclídea por $m$.
{{% /proposition %}}

%
{{% proof %}}
 En efecto, si \co{a}{b}{m}, entonces $m|(b-a)$. Sean
$a=qm+r$ $b=q'm+r'$,$0 \leq r,r'<m,$ entonces $a-b=(q-q')m+(r-r')$, igualdad que solo es posible cuando $r'-r=0$ ya que $|r'-r|<m$.
 Recíprocamente, si $a=qm+r$, $b=q'm+r$ es $a-b=(q-q')m,$ luego \co{a}{b}{m}.

{{% /proof %}}

%

{{% watch %}}
La relación {\em "ser congruente con"} es precisamente la relación $\sim_{\Z m}$ definida en el tema anterior (Página \pageref{relizq}). Luego es una relación de equivalencia y el conjunto cociente es el anillo $\Z /\Z m$.

En consecuencia las congruencias son compatibles con la suma y el producto.
{{% /watch %}}


{{% proposition %}}
 Sea $m>0$ un entero. Sean $a,b,c,d\in\Z$ tales que \co{a}{b}{m} y \co{c}{d}{m}. Se verifican las siguientes propiedades:
\begin{enumerate}
\item \co{a + c}{b + d}{m}.
\item \co{ac}{bd}{m}.
\end{enumerate}
{{% /proposition %}}

{{% watch %}}
[Propiedad cancelativa] De cara a resolver ecuaciones en congruencias será necesario saber en qué condiciones se puede aplicar la propiedad cancelativa. Es decir, se trata de ver cuándo se verifica que
$$
\cop{ax}{bx}{m} \Longrightarrow \cop{a}{b}{m}.
$$

Si $m$ es un número primo entonces $\Z /\Z m$ es un dominio de integridad (de hecho es un cuerpo) y se satisface la propiedad cancelativa.

Si $m$ no es primo, en general no se satisface la propiedad cancelativa. Por ejemplo,
$$
\cop{2\cdot 2}{0\cdot 2}{4} \quad \hbox{y}\quad 2 \not\equiv 0 \quad
\mathrm{(mod}\ 4).
$$
{{% /watch %}}

{{% theorem %}}
{Congruencias y propiedad cancelativa}{
Sean $x,m\in\Z$, $m>0$, se verifica la propiedad
$$
\forall a,b\in\Z ,\ \cop{ax}{bx}{m} \Longrightarrow \cop{a}{b}{m}
$$
si y solo si $x$ y $m$ son primos entre si.
}
{{% /theorem %}}

{{% proof %}}

Si $1<d=\mbox{mcd}(x,m)$, $x=x'd$, $m=m'd$, entonces
\co{m'x}{0\cdot x}{m} pero $m'\not\equiv 0 \mathrm{(mod} \ m)$ porque
$0<m'<m$.

Recíprocamente, si $\mbox{mcd}(x,m)=1$, sea \co{ax}{bx}{m}.
Por la identidad de Bézout existen $\alpha, \beta \in\Z$ tales que
$\alpha x +\beta m=1$. Así, $a=\alpha ax+\beta am$, $b=\alpha
bx+\beta bm$, luego
$$
a-b=\alpha (ax-bx)+\beta (a-b)m,
$$
que es múltiplo de $m$. Por tanto, \co{a}{b}{m}.
{{% /proof %}}

Veamos ahora que ocurre con la ecuación $ax=b, \; a,b\in \Z.$ Sabemos que la ecuación anterior tiene
solución entera si y solo si $a|b$ y su solución es $x= \frac{b}{a} \in \Z.$ En el caso de las congruencias tenemos

{{% proposition %}}
 La ecuación en congruencias

\begin{center} \co{ax}{b}{m}  \end{center}

\noindent tiene solución si y solo si $d=\mbox{mcd}(a,m)$ divide a
$b.$
{{% /proposition %}}


{{% proof %}}
 Supongamos que $d|b$, $b=dc.$ La
identidad de Bézout nos dice que $d = \alpha a + \beta m$, luego
$b=dc=\alpha a c + \beta m c.$ Como \co{mc}{0}{m}, se tiene que
\co{\alpha ac}{b}{m}, es decir, $\alpha c$ es solución de la
ecuación.

%
Para la implicación contraria supongamos que $x_0$ es una solución
de la ecuación en congruencias. Es decir $ax_0 - b = km$, luego $d
|ax_0-km =b.$
%veremos que la ecuación
%\co{10x}{14}{15} no tiene solución. Si tuviera, existiría un entero
%$c$ tal que $ 15 |10c-14$, luego $5|10c-14$, que es una
%contradicción pues 5 no divide a 14.
{{% /proof %}}


{{% theorem %}}
{Teorema chino del resto} {Sean $m_1, m_2, \dots, m_n$
enteros, mayores que 1, primos entre sí dos a dos, $a_1, a_2, \dots,
a_n \in \Z.$ El sistema de congruencias:
\begin{center}
  \co{x}{a_1}{m_1} \\
   \co{x}{a_2}{m_2} \\
  $\vdots$ \\
   \co{x}{a_n}{m_n}
\end{center}
tiene solución. Además, si $x$ y $x'$ son dos soluciones, entonces
\co{x}{x'}{M}, donde $M=m_1m_2 \cdots m_n.$ Recíprocamente, si $x$
es una solución y \co{x'}{x}{M}, entonces $x'$ es solución.}
{{% /theorem %}}

%
{{% proof %}}
 Denotemos $M_i = M/m_i$, $\forall i=1,
\dots, n.$ Es claro que
$$
\mbox{mcd}(m_i, M_i) =1, \quad \forall i=1, \dots, n,
$$
luego, por la identidad de Bézout, existen $\alpha_i,
\beta_i \in \Z$ verificando $$1 = \alpha_i m_i + \beta_i M_i, \quad i=1, \dots, n.$$

Tomemos $x = a_1\beta_1M_1 + a_2\beta_2M_2 + \cdots + a_n\beta_nM_n$
y comprobemos que $x$ es solución. Para ello tendremos que comprobar
que \co{x}{a_i}{m_i}, para todo $i$, o, equivalentemente, que
\co{x-a_i}{0}{m_i}, para todo $i.$ Usando la identidad de Bézout
correspondiente, tenemos $a_i = a_i\alpha_im_i+ a_i\beta_iM_i.$
Entonces,

$$
x-a_i=a_1\beta_1M_1+ \cdots + a_n\beta_nM_n - a_i\alpha_im_i-
a_i\beta_iM_i=
$$
$$
=a_1\beta_1M_1+ \cdots +a_{i-1}\beta_{i-1}M_{i-1}+a_{i+1}\beta_{i+1}M_{i+1}+\cdots+ a_n\beta_nM_n -
a_i\alpha_im_i,
$$
\noindent y, al ser todos los sumandos múltiplos de $m_i$, es
\co{x-a_i}{0}{m_i}.

Dejamos como ejercicio la demostración de la última parte del enunciado.
{{% /proof %}}

{{% example name="Ejemplo" %}}

Resolvamos el siguiente sistema de congruencias:
\begin{center}
  \co{x}{1}{2} \\
   \co{x}{2}{3} \\
   \co{x}{3}{5}
\end{center}

Siguiendo la notación de la demostración anterior, en nuestro caso tenemos $m_1=2, m_2=3, m_3=5,$ $M=30, M_1=15, M_2=10$ y $M_3=6.$ Por la identidad de Bezout tenemos
\begin{center}
mcd$(m_1,M_1) = 1, 1= (-7)\cdot 2 + 1 \cdot 15,$ luego $\beta_1 = 1.$ \\
mcd$(m_2,M_2) = 1, 1= (-3)\cdot 3 + 1 \cdot 10,$ luego $\beta_2 = 1.$ \\
mcd$(m_3,M_3) = 1, 1= (-1)\cdot 5 + 1 \cdot 6,$ luego $\beta_3 = 1.$
\end{center}
Por tanto una solución del sistema es
$$x=a_1\beta_1M_1 + a_2\beta_2M_2 + a_3\beta_3M_3=53.$$
Las soluciones son los enteros congruentes con 53 módulo 30.
{{% /example %}}


\begin{figure}[htbp]
 \centering
 {
 \includegraphics[scale=0.5]{Pierre_de_Fermat.eps}
 }
 \caption{Pierre de Fermat}
 \label{fig:Fermat}
\end{figure}

Terminamos este tema probando dos teoremas muy importantes, debidos a Fermat (1640) y a Euler (1736). Aunque el teorema de Euler es una generalización del pequeño teorema de Fermat, enunciamos este último como un teorema y no como un corolario por razones históricas: el de Fermat es casi un siglo anterior al de Euler.

{{% theorem %}}
{Unidades de $\Z /\Z m$}
{El grupo de las unidades del anillo $\Z /\Z m$ es
$$U_m=\\{ a+\Z m\mid \mbox{mcd}(a,m)=1, 0\leq a<m\\}.$$
}
{{% /theorem %}}

{{% proof %}}
 Supongamos que $a+  \Z m$ es
unidad. Entonces existe $b+  \Z m$ tal que $(a+ \Z m)(b+  \Z m)=1+
\Z m$, luego $ab-1=qm$, y $ab-qm=1$, por tanto $a$ y $m$ son primos
entre sí.

Recíprocamente, supongamos que $\mbox{mcd}(a,m)=1.$ Por la identidad
de Bezout existen enteros $r,s$ con $ra+sm=1.$ Luego $1+  \Z
m=(ra+sm)+  \Z m=(ra+  \Z m)+(sm+  \Z m)=(a+ \Z m)(r+  \Z m).$ Es decir, $a+  \Z m$ es una unidad.
{{% /proof %}}

{{% watch %}}
 El anillo $\Z / \Z p$ es un cuerpo si y solo si $p$ es primo. De hecho
$$U_p=\\{ 1+\Z p,\ldots (p-1)+\Z p\\}$$
y $|U_p|=p-1$.
{{% /watch %}}

{{% theorem %}}
{(Pequeño) Teorema de Fermat (1640)}
{Si $p$ es primo y no divide a $a\in \Z$, entonces \co{a^{p-1}}{1}{p}.}
{{% /theorem %}}

{{% proof %}}

Si $p$ no divide a $a$ entonces $a+\Z p\in U_p$. Como el orden del grupo $U_p$ es $p-1$, por el teorema de Lagrange, se tiene
$$(a+\Z p)^{p-1}=1+\Z p.$$
Es decir, \co{a^{p-1}}{1}{p}.
{{% /proof %}}

El teorema de Euler generalizará este resultado a enteros no primos. Antes hemos de dar la definición de la función indicatriz de Euler, que asocia a cada entero $m$ la cantidad de unidades de $\Z /\Z m$.

{{% definition %}}
{Función $\phi$ o indicatriz de Euler}
{A la cantidad de números enteros $a, 1 \leq a \leq m$,
que son primos con $m$ se le denota por $\phi(m)$, la {\bf función $\phi$
o indicatriz de Euler}. Es decir,
$$\phi (m) =|U_m|.$$}
{{% /definition %}}

{{% watch %}}
Sea $p\in\N$, $p$ es primo si y solo si $\phi (p)=p-1$.
{{% /watch %}}

{{% proposition %}}

Sea $p\in\N$ primo, entonces $\phi (p^r)=(p-1)p^{r-1}.$
{{% /proposition %}}

{{% proof %}}

Se trata de contar los números entre 1 y $p^r$ que son primos con $p^r$. Como $p$ es primo, son los números que no son múltiplos de $p$. Vamos a contar los que sí son múltiplos de $p$ y restárselos a $p^r$. Los múltiplos de $p$ son
$$\\{ p,2p,\ldots ,p^r=p^{r-1}p\\} ,$$
es decir, hay $p^{r-1}$ múltiplos de $p$. Luego
$$\phi (p^r)=p^r-p^{r-1}=(p-1)p^{r-1}.$$
{{% /proof %}}

\begin{teorema}
Sean $m$ y $n$ dos enteros primos entre si, entonces $\phi (mn)=\phi (m)\phi (n)$.
\end{teorema}

{{% proof %}}

Se trata demostrar que hay tantos elementos en $U_{mn}$ como en $U_m\times U_n$. Vamos a establecer una aplicación biyectiva entre ambos conjuntos. Sea 
$$\begin{array}{rcl}
   f\colon U_{mn} & \to & U_m\times U_n\\
   x+\Z mn & \mapsto & (x+\Z m,x+\Z n).
  \end{array}$$
Como $m$ y $n$ son primos entre sí, si $x+\Z mn\in U_{mn}$ entonces $\mcd (x,mn)=1$, luego $\mcd (x,m)=\mcd (x,n)=1$. Es decir, $(x+\Z m,x+\Z n)\in U_m\times U_n$
  
Además hay que comprobar que $f$ es una aplicación (está bien definida), es decir, que no depende de la elección del representante de la clase $x+\Z mn$. Si $x+\Z mn=y+\Z mn$ ¿es $(x+\Z m,x+\Z n)=(y+\Z m,y+\Z n)$?
$$x+\Z mn=y+\Z mn\Leftrightarrow mn|(x-y)\stackrel{{\mathrm mcd}(m,n)=1}{\Longleftrightarrow}$$
$$\Leftrightarrow\left\\{\begin{array}{l} m|(x-y)\Leftrightarrow x+\Z m=y+\Z m\\ n|(x-y)\Leftrightarrow x+\Z n=y+\Z n\end{array}\right\\}\Leftrightarrow(x+\Z m,x+\Z n)=(y+\Z m,y+\Z n).$$

De la expresión anterior se deduce que $f$ es inyectiva, pues si $x+\Z mn$ e $y+\Z mn$ son tales que $f(x+\Z mn)=f(y+\Z mn)$, es decir,
$$(x+\Z m,x+\Z n)=(y+\Z m,y+\Z n),$$
se obtiene que $x+\Z mn=y+\Z mn$.

Por último, veamos que $f$ es sobreyectiva. Sea $(a+\Z m,b+\Z n)\in U_m\times U_n$ ¿existe $x+\Z mn\in U_{mn}$ tal que $f(x+\Z mn)= (a+\Z m,b+\Z n)$? Como ${\mathrm mcd}(m,n)=1$, aplicando el {\em teorema chino del resto} existe algún entero $x$ tal que $\cop{x}{a}{m}$ y $\cop{x}{b}{n}$. Sabemos que $x+\Z m=a+\Z m$ es unidad en $\Z /\Z m$ y que $x+\Z n=b+\Z n$ es unidad en $\Z /\Z n$ de donde se deduce, por ser $m$ y $n$ primos entre sí, que $x+\Z mn$ es una unidad en $\Z /\Z mn$. Luego $f$ es sobreyectiva, pues
$$f(x+\Z mn)=(x+\Z m,x+\Z n)=(a+\Z m,b+\Z n).$$

Por tanto, hay tantos elementos en $U_{mn}$ como en $U_m\times U_n$. Luego $\phi (mn)=\phi (m)\phi (n)$.
{{% /proof %}}

{{% corollary %}}

Sea $n$ un entero y $n=p_1^{n_1} p_2^{n_2} \cdots p_r^{n_r}$ su descomposición en factores primos, entonces
$$\phi (n)=(p_1-1)\cdots (p_r-1)p_1^{n_1-1}\cdots p_r^{n_r-1}.$$
{{% /corollary %}}

{{% proof %}}

$$\phi (n)=\phi (p_1^{n_1} \cdots p_r^{n_r})=\phi (p_1^{n_1})\cdots \phi (p_r^{n_r})=(p_1-1)p_1^{n_r-1}\cdots (p_r-1)p_r^{n_r-1}=$$
$$=(p_1-1)\cdots (p_r-1)p_1^{n_1-1}\cdots p_r^{n_r-1}.$$
{{% /proof %}}

{{% watch %}}
Si $n$ es un entero y $n=p_1^{n_1} p_2^{n_2} \cdots p_r^{n_r}$ es su descomposición en factores primos, entonces
$$\phi (n)=(p_1-1)\cdots (p_r-1)p_1^{n_1-1}\cdots p_r^{n_r-1}=n\left( 1-\frac{1}{p_1}\right)\cdots\left( 1-\frac{1}{p_r}\right).$$
{{% /watch %}}

{{% example name="Ejemplo" %}}

Vamos a calcular $\phi (360)$. Como $360=2^33^25$, entonces
$$\phi (360)=\phi (2^3)\phi (3^2)\phi (5)=(2-1)2^2(3-1)3(5-1)=96.$$
{{% /example %}}

\begin{figure}[htbp]
 \centering
 {
 \includegraphics[scale=1]{Leonhard_Euler.eps}
 }
 \caption{Leonhard Euler}
 \label{fig:Euler}
\end{figure}

{{% theorem %}}
 {Teorema de Euler (1736)} {Sea $a+ \Z m$ una unidad en $\Z /
\Z m.$ Entonces \begin{center} \co{a^{\phi(m)}}{1}{m}.
\end{center}}
{{% /theorem %}}

{{% proof %}}

La demostración es análoga a la del teorema de Fermat. Si $a+\Z m\in U_m$, como $|U_m|=\phi (m)$, por el teorema de Lagrange
$$(a+\Z m)^{\phi (m)}=1+\Z m.$$
Luego \co{a^{\phi(m)}}{1}{m}.
{{% /proof %}}

{{% example name="Ejemplo" %}}

Calcular el resto de dividir $62347^{5827}$ entre $20$. Como $62347=3117\cdot 20+7$, entonces
\co{62347^{5827}}{7^{5827}}{20}. Además $7$ es primo con $20$, luego podemos aplicar el teorema de Euler.
Por un lado $\phi (20)=8$, por otro, si dividimos $5827$ entre $8$ se obtiene $5827=728\cdot 8+3$. Por el teorema de Euler \co{7^8}{1}{20}, luego
$$7^{5827}=(7^8)^{728}7^3\equiv 7^3\ \mbox{(mod }m\mbox{)}.$$
$7\cdot 7=49$ y \co{49}{9}{20}. Luego \co{7^3}{9\cdot 7}{20} y \co{63}{3}{20}. De donde el resto de dividir $62347^{5827}$ entre $20$ es $3$.
{{% /example %}}

-->
