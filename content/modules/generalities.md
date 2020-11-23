+++
title = "Generalidades"
weight = 10
+++

Hay razones de peso por las cuales el álgebra lineal se desarrolla sobre cuerpos. Una vez que nos apartamos de los aspectos más básicos, la teoría de módulos difiere sustancialmente del álgebra lineal, se complica. Aquí vamos a estudiar sobre todo los aspectos formales en los que son similares, aunque comenzaremos a vislumbrar diferencias importantes.

## Definición

{{% definition %}}

Dado un anillo $R$, un **$R$-módulo** es un conjunto $M$ equipado con dos aplicaciones, llamadas *suma* y *producto por escalares*,

$$
\begin{array}{ccc}
M\times M\rightarrow M, &\qquad& R\times M\rightarrow M,\cr
(a,b)\mapsto a+b;&&(r,a) \mapsto ra;
\end{array}
$$

que satisfacen las siguientes propiedades, donde $a,b,c\in M$ y $r,s\in R$:

* Asociativa:

$$a+(b+c)=(a+b)+c,\qquad r(sa)=(rs)a.$$

* Conmutativa:

$$a+b=b+a.$$

* Distributiva:

$$r(a+b)=ra+rb,\qquad (r+s)a=ra+sa.$$

* Existencia de *elemento neutro* $0\in M$ para la suma y comportamiento del $1\in R$ como elemento neutro para el producto por escalares:

$$0+a=a,\qquad 1a=a.$$

* Existencia de un *elemento opuesto* para la suma $-a\in M$ para todo $a\in M$ de modo que

$$a+(-a)=0.$$

{{% /definition %}}


{{% remark %}}
Cuando quede claro por el contexto o no sea relevante especificarlo, omitiremos $R$ de la notación. La suma en un módulo lo dota de estructura de grupo abeliano. Recordemos que el elemento neutro de un grupo es único, no puede haber dos distintos que satisfagan la misma propiedad. Los opuestos para la suma también. Restar es sumar el elemento opuesto $a-b=a+(-b)$. Además $0a=0=r0$ y $r(-a)=-ra=(-r)a$. Si $R=k$ es un cuerpo la noción de $R$-módulo coincide con la de $k$-espacio vectorial.
{{% /remark %}}



{{% example name="El módulo trivial" %}}

El conjunto unitario $\\{0\\}$, dotado de las únicas operaciones suma y producto por escalares posibles, es un módulo sobre cualquier anillo $R$. 

{{% /example %}}


{{% example name="$R^n$" %}}
Sus elementos son vectores columna con entradas en $R$, aunque a veces, cuando convenga, se denotarán por filas. La suma se define coordenada a coordenada, y el producto por escalares se define multiplicando el escalar por todas las coordenadas:

$$\left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right)+\left(\begin{array}{c}b_1\cr\vdots\cr b_n\end{array}\right)=\left(\begin{array}{c}a_1+b_1\cr\vdots\cr a_n+b_n\end{array}\right),\qquad r\left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right)=\left(\begin{array}{c}ra_1\cr\vdots\cr ra_n\end{array}\right).$$

Para $n=1$ observamos que el propio $R$ puede considerarse como un $R$-módulo. Para $n=0$ obtenemos el módulo trivial.
{{% /example %}}


{{% example name="Producto de módulos" %}}
Dados dos $R$-módulos $M$ y $N$, su **producto** cartesiano $M\times N$ posee una estructura de $R$-módulo con las siguientes operaciones:

$$\begin{array}{rcl}(a\_1,b\_1)+(a\_2,b\_2)&=&(a\_1+a\_2,b\_1+b\_2),\cr r(a,b)&=&(ra,rb).\end{array}$$

¿Cuál es el elemento neutro para la suma? ¿Cuáles son los opuestos?
{{% /example %}}


{{% proposition %}}
Todo grupo abeliano $A$ posee una única estructura de $\mathbb Z$-módulo. 
{{% /proposition %}}


{{% proof %}}

Dado $a\in A$, si $n>0$ en $\mathbb Z$, estaríamos forzados a definir:

$$\begin{array}{rcl}
n a&=&(1+\stackrel{n}{\cdots}+1)a\cr&=&1a+\stackrel{n}{\cdots}+1a\cr&=&a+\stackrel{n}{\cdots}+a,\cr
(-n)a&=&-na,\cr
0a&=&0.
\end{array}$$

Es fácil comprobar que estas fórmulas definen una estructura de $\mathbb Z$-módulo en $A$, necesariamente única.  
{{% /proof %}}



{{% definition %}}
Un subconjunto $N\subset M$ de un $R$-módulo $M$ es un **submódulo** si:

* $0\in N$.

* $a+b\in N$ para todo $a,b\in N$.

* $ra\in N$ para todo $r\in R$ y $a\in N$.

{{% /definition %}}



{{% remark %}}
Un submódulo $N\subset M$ es un módulo por derecho propio con la suma y el producto por escalares heredados de $M$. En particular es un subgrupo. El módulo trivial $\\{0\\}$ es un submódulo de cualquier otro. Los submódulos de $R$ coinciden con los ideales del anillo. 
{{% /remark %}}



## Homomorfismos

Los homomorfismos de módulos son aplicaciones que preservan la estructura, es decir, la suma y el producto por escalares.

{{% definition %}}
Dados dos $R$-módulos $M$ y $N$, un **homomorfismo** $f\colon M\rightarrow N$ es una aplicación tal que, para todo $r\in R$ y $a,b\in M$,

$$\begin{array}{rcl} f(a+b)&=&f(a)+f(b),\cr f(ra)&=&rf(a).\end{array}$$

Como de costumbre, los homomorfismos inyectivos, sobreyectivos y biyectivos se denominan **monomorfismos**, **epimorfismos** e **isomorfismos**, respectivamente, y los isomorfismos de un módulo en sí mismo se llaman **automorfismos**.
{{% /definition %}}


{{% remark %}}
Los homomorfismos satisfacen $f(-a)=-f(a)$ y $f(0)=0$. La identidad $\operatorname{id}_M\colon M\rightarrow M$ es un isomorfismo. Comprueba que si

$$M\stackrel{f}\longrightarrow N\stackrel{g}\longrightarrow P$$

son homomorfismos entonces la composición $g\circ f\colon M\rightarrow P$ también. Lo mismo es cierto para monomorfismos, epimorfismos, isomorfismos y automorfismos. Es más, demuestra que si $f\colon M\rightarrow N$ es un isomorfismo entonces su aplicación inversa $f^{-1}\colon N\rightarrow M$ también. El símbolo $\cong$ se usará para denotar la relación de ser isomorfos $M\cong N$. Prueba que esta relación es de equivalencia. 
{{% /remark %}}



{{% example name="La inclusión" %}}
Si $M$ es un módulo y $P\subset M$ es un submódulo, la **inclusión** $i\colon P\hookrightarrow M$, $i(a)=a$, es un homomorfismo. ¿Qué diferencia a la inclusión de la identidad?
{{% /example %}}


{{% example name="Objeto cero" %}}
Todo módulo $M$ admite homomorfismos únicos desde $\\{0\\}\rightarrow M$ y hasta $M\rightarrow \\{0\\}$ el módulo trivial. 
{{% /example %}}


{{% example name="Homomorfismo trivial" %}}
Dados dos $R$-módulos cualesquiera $M$ y $N$, la aplicación $M\rightarrow N$ definida como $x\mapsto 0$ para todo $x\in M$ es un homomorfismo, el **homomorfismo trivial**. ¿Puede ser un isomorfismo? 
{{% /example %}}


{{% example name="Producto por escalares" %}}
Dado un $R$-módulo $M$ y $r\in R$, la aplicación $M\stackrel{r\cdot}\rightarrow M$ definida como $x\mapsto r\cdot x$ es un homomorfismo. ¿Puede ser un isomorfismo?
{{% /example %}}


{{% example name="Inclusiones y proyecciones de un producto" %}}
Dados dos $R$-módulos $M$ y $N$, definimos dos homomorfismos de **inclusión**

$$i\_1\colon M\longrightarrow M\times N,\qquad i\_2\colon N\longrightarrow M\times N,$$

mediante las fórmulas

$$i\_1(a)=(a,0),\qquad i\_2(b)=(0,b),$$

y otros dos de **proyección**

$$p\_1\colon M\times N\longrightarrow M,\qquad p\_2\colon M\times N\longrightarrow N,$$

como

$$p\_1(a,b)=a,\qquad p\_2(a,b)=b.$$

Comprueba que $p\_1\circ i\_1=\operatorname{id}\_M$ y $p\_2\circ i\_2=\operatorname{id}\_N$. ¿Son estos homomorfismos isomorfismos? 
{{% /example %}}


{{% example name="Conmutatividad del producto" %}}
El producto de $R$-módulos es conmutativo salvo isomorfismo. Dados dos $R$-módulos $M$ y $N$ tenemos un isomorfismo

$$\begin{array}{rcl}M\times N&\stackrel{\cong}\longrightarrow&N\times M,\cr (a,b)&\mapsto&(b,a).\end{array}$$

¿Cuál es su inverso? 
{{% /example %}}


{{% example name="Matrices" %}}
Toda matriz $B$ de tamaño $m\times n$ con entradas en $R$ da lugar a un homomorfismo definido por la multiplicación de matrices:

$$\begin{array}{rcl} R^n&\stackrel{B\cdot}\longrightarrow&R^m,\cr \left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right)&\mapsto& B\left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right). \end{array}$$

La composición de este tipo de homomorfismos es el producto de matrices. En particular $B$ define un isomorfismo si y solo si es una matriz invertible. Cualquier homomorfismo $f\colon R^n\rightarrow R^m$ es de este tipo. En efecto, si para cada $1\leq i\leq n$ consideramos el elemento

$$e\_i=\left(\begin{array}{c}0\cr\vdots\cr1\cr\vdots\cr0\end{array}\right)\in R^n$$

cuya única coordenada no trivial es la $i$-ésima, que vale $1$, puedes comprobar la matriz que define $f\colon R^n\rightarrow R^m$ es aquella cuyas columnas son los $f(e\_i)$,

$$\left(f(e\_1)\mid\cdots\mid f(e\_n)\right).$$

{{% /example %}}


{{% exercise %}}
Demuestra que si $M\cong M'$ y $N\cong N'$ entonces $M\times N\cong M'\times N'$.
{{% /exercise %}}



{{% proposition %}}
Si $M$ es un $R$-módulo y $S=\\{a\_1,\dots,a\_n\\}\subset M$ un subconjunto cualquiera, existe un único homomorfismo $\phi=\phi_{S}\colon R^n\rightarrow M$ tal que $\phi(e_i)=a_i$.
{{% /proposition %}}

{{% proof %}}
Todo $x=(x\_1,\dots,x\_n)\in R^n$ se puede escribir como $x=\sum\_{i=1}^nx\_ie\_i$. Por tanto, si existiera $\phi$ tendría que cumplir que 

$$
\begin{array}{rcl}
\phi(x)&=&\phi(\sum\_{i=1}^nx\_ie\_i)\cr
&=&\sum\_{i=1}^nx\_i\phi(e\_i)\cr
&=&\sum\_{i=1}^nx\_ia\_i.
\end{array}
$$

Esto demostraría la unicidad, caso de que existiera. Es más, es fácil comprobar que la fórmula $\phi(x)=\sum_{i=1}^nx_ia_i$ define un homomorfismo, luego existe.
{{% /proof %}}

{{% proposition %}}
Dado un homomorfismo $f\colon M\rightarrow N$, su **imagen** $\operatorname{im} f\subset N$ es un submódulo. 
{{% /proposition %}}


{{% proof %}}

* $0=f(0)\in \operatorname{im} f$.

* $f(a)+f(b)=f(a+b)\in \operatorname{im} f$ para $a,b\in M$.

* $rf(a)=f(ra)\in \operatorname{im} f$ para todo $r\in R$ y $a\in M$.

{{% /proof %}}

{{% proposition %}}
El **núcleo** de un homomorfismo $f\colon M\rightarrow N$,

$$\ker f=\\{a\in M\mid f(a)=0\\},$$

es un submódulo $\ker f\subset M$.
{{% /proposition %}}


{{% proof %}}

* $0\in\ker f$ pues $f(0)=0$.

* Si $a,b\in\ker f$ entonces $a+b\in \ker f$ puesto que $f(a+b)=f(a)+f(b)=0+0=0$.

* Si $a\in\ker f$ y $r\in R$ entonces $ra\in \ker f$ pues $f(ra)=rf(a)=r0=0$.

{{% /proof %}}


{{% remark %}}
Como ocurre con los grupos y con los anillos, un homomorfismo de módulos $f\colon M\rightarrow N$ es inyectivo si y solo si $\ker f=\\{0\\}$. De otro modo, la inyectividad de $f$ equivale a que si $a\in M$ es tal que $f(a)=0$ entonces $a=0$.
{{% /remark %}}


## Módulos libres

{{% definition %}}
Sea $M$ un $R$-módulo y $S=\\{a\_1,\dots,a\_n\\}\subset M$ un subconjunto. Decimos que $S$ **genera** $M$ si todo elemento de $x\in M$ es **combinación lineal** de $S$, es decir, de la forma

$$x=r\_1a\_1+\cdots+r\_na\_n$$

para ciertos $r\_1,\dots,r\_n\in R$. Decimos que $S$ es **linealmente independiente** si la única combinación lineal de $S$ que da como resultado $0$ es aquella que tiene todos los coeficientes nulos, es decir si $r\_1,\dots,r\_n\in R$ son tales que

$$r\_1a\_1+\cdots+r\_na\_n=0$$

entonces $r\_1=\cdots=r\_n=0$. Decimos además que $S$ es una **base** de $M$ si lo genera y es linealmente independiente. Un $R$-módulo es **finitamente generado** si posee un subconjunto finito que lo genera, y es **libre** si posee una base.
{{% /definition %}}



{{% remark %}}
Si $R=k$ es un cuerpo todo $R$-módulo es libre puesto que todo $k$-espacio vectorial posee una base. Los $k$-espacios vectoriales finitamente generados se denominan también de dimensión finita. Es posible considerar bases de módulos no finitamente generados, pero aquí no lo haremos.
{{% /remark %}}


{{% example name="$R^n$ es libre" %}}
El subconjunto $\\{e\_1,\dots,e\_n\\}\subset R^n$ es una base denominada **canónica**.
{{% /example %}}

Podemos definir un submódulo con un conjunto prefijado de generadores al igual que lo hicimos con los [ideales](/estalg/rings/definitions/#generators).

{{% definition %}}
El **submódulo generado por** un conjunto finito de elementos $a_1,\dots,a_n\in M$ está formado por todas las combinaciones lineales de los generadores con coeficientes en el anillo: 

$$(a_1,\dots,a_n)=\\{r_1a_1+\dots+r_na_n \mid  r_1,\dots,r_n\in R\\}\subset M.$$

Un **módulo cíclico** es uno que está generado por un único elemento $(a)=\\{ra \mid  r\in R\\}$ y que por tanto está formado por sus múltiplos. 
{{% /definition %}}


{{% exercise %}}
Comprueba que $(a_1,\dots,a_n)\subset M$ es en efecto un submódulo. Observa que $a_1,\dots,a_n\in (a_1,\dots, a_n)$. Es más, demuestra que si $N\subset M$ es un submódulo y $a_1,\dots,a_n\in N$ entonces $(a_1,\dots,a_n)\subset N$. Intenta dar una definición razonable de ideal generado por un conjunto infinito de elementos que satisfaga las propiedades análogas al caso finito. 
{{% /exercise %}}


{{% remark %}}
En términos del homomorfismo

$$\phi\_S\colon R^n\longrightarrow M$$

definido antes, podemos afirmar lo siguiente sobre el conjunto $S=\\{a\_1,\dots,a\_n\\}\subset M$: 

* $S$ genera si y solo si $\phi\_S$ es sobreyectivo. 

En particular, $(a\_1,\dots,a\_n)=\operatorname{im} \phi\_S$.

* $S$ es linealmente independiente si y solo si $\phi\_S$ es inyectivo. 

* $S$ es una base si y solo si $\phi\_S$ es un isomorfismo. 

En particular, si $S$ es una base de $M$ entonces para todo $x\in M$ existe un único $(r\_1,\dots,r\_n)\in R^n$ tal que

$$x=\phi\_S(r\_1,\dots,r\_n)=r\_1a\_1+\cdots+r\_na\_n.$$

Decimos entonces que $(r\_1,\dots,r\_n)$ son las **coordenadas** de $x$ respecto de $S$. Es más, la aplicación que envía cada elemento a sus coordenadas respecto de $S$ es

$$\phi\_S^{-1}\colon M\longrightarrow R^n,$$

que es un isomorfismo, por tanto la asignación de coordenadas respecto de una base preserva sumas y productos por escalares. 
{{% /remark %}}



{{% remark %}}
Sea $f\colon M\rightarrow N$ un homomorfismo de $R$-módulos y $S=\\{a\_1,\dots,a\_n\\}\subset M$. Los siguientes enunciados son consecuencia de las observaciones anteriores: 

* Si $S\subset M$ genera y $f$ es sobreyectivo $\Rightarrow$ $f(S)\subset N$ genera.

* Si $S\subset M$ es linealmente independiente y $f$ es inyectivo $\Rightarrow$ $f(S)\subset N$ es linealmente independiente.

* Si $S\subset M$ es una base y $f$ es biyectivo $\Rightarrow$ $f(S)\subset N$ es una base.

* Si $S\subset M$ genera entonces $f(S)\subset\operatorname{im}f$ genera.

Concluimos que un $R$-módulo es libre si y solo si es isomorfo a algún $R^n$. Del último punto también se deduce que la imagen del homomorfismo $A\colon R^n\rightarrow R^m$ definido por una matriz $A$ de tamaño $m\times n$ con entradas en $R$ está generada por las columnas de $A$.
{{% /remark %}}


Seguidamente definimos la noción de determinante para matrices sobre un anillo igual que se hacía para los cuerpos.

{{% definition %}}
El **determinante** $|A|$ de una matriz cuadrada $A=(a\_{ij})$ de tamaño $n\times n$ con entradas en un anillo conmutativo $R$ se define como

$$|A|=\sum\_{\sigma\in S\_n}\operatorname{signo}(\sigma)a\_{1\sigma(1)}\cdots a\_{n\sigma(n)}.$$

Aquí $S_n$ denota el grupo de permutaciones de $n$ elementos.
{{% /definition %}}


{{% remark %}}
Los determinantes de matrices con entradas en un anillo conmutativo satisfacen las siguientes propiedades habituales. Puedes comprobarlas como ejercicio.

* El determinante de la matriz identidad es $|I|=1$. 

* Si $A$ tiene una fila de ceros entonces $|A|=0$. 

* Una matriz $A$ y su traspuesta $A^t$ tienen el mismo determinante, $|A|=|A^t|$. 

* El determinante preserva productos, $|AB|=|A||B|$. 

* Las fórmulas del desarrollo de un determinante por los adjuntos de una fila o columna también son válidas en este contexto. 

* Si $A$ es una matriz cuadrada invertible entonces $|A|\in R^{\times}$ es una unidad y $|A^{-1}|=|A|^{-1}$.

* Recíprocamente, si $A$ es cuadrada y $|A|\in R^{\times}$ es una unidad entonces $A$ es invertible. Su inversa es la matriz traspuesta de la adjunta de $A$ dividida por $|A|$. 

Las matrices invertibles son necesariamente cuadradas si $R$ no es el anillo trivial. Esto se comprueba por reducción al absurdo. En efecto, sean $A$ y $B$ matrices tales que $AB=I$ y $BA=I$. Como las matrices identidad $I$ son cuadradas, si $A$ tiene tamaño $m\times n$ entonces el tamaño de $B$ tiene que ser $n\times m$. Podemos suponer sin pérdida de generalidad que $m>n$. Completamos la columnas de $A$ y las filas de $B$ con ceros hasta formar matrices cuadradas y observamos que

$$\left(\begin{array}{c|c}A&0\end{array}\right)\left(\begin{array}{c}B\cr \hline 0\end{array}\right)=AB+0=AB=I,$$

pero esto es imposible porque los determinantes de las matrices de la izquierda son $0$, pues contienen alguna fila o columna de ceros, pero el determinante de $I$ es $1$.
{{% /remark %}}




{{% proposition %}}
Todas las bases de un mismo $R$-módulo libre $M$ tienen el mismo número de elementos. 
{{% /proposition %}}


{{% proof %}}
Si $S$ y $S'$ son bases con $n$ y $m$ elementos, respectivamente, cada una de ellas define un isomorfismo $\phi\_S\colon R^n\rightarrow M$, $\phi\_{S'}\colon R^m\rightarrow M$. Componiendo el primero con el inverso del segundo obtenemos un isomorfismo $\phi\_{S'}^{-1}\circ\phi\_S\colon R^n\rightarrow R^m$. Este isomorfismo tiene que estar definido por una matriz $A$ de tamaño $m\times n$ invertible. Como las matrices invertibles son cuadradas deducimos que $m=n$.
{{% /proof %}}



{{% definition %}}
El **rango** de un $R$-módulo libre $M$ es el número de elementos de una base. 
{{% /definition %}}


Cuando $R=k$ es un cuerpo, el rango de un $k$-espacio vectorial se denomina dimensión.


{{% remark %}}
Si $S=\\{a\_1,\dots,a\_n\\}$ y $S'=\\{a\_1',\dots,a\_n'\\}$ son bases de un mismo $R$-módulo libre de rango $n$, el isomorfismo $\phi\_{S'}^{-1}\circ\phi\_S\colon R^n\rightarrow R^n$ considerado en la demostración anterior está definido por una matriz $B=(b_{ij})$ invertible $n\times n$ sobre $R$, que es la única que satisface las siguientes ecuaciones para todo $1\leq i\leq n$,

$$a\_i=b\_{1i}a\_1'+\cdots+b\_{ni}a\_n'.$$

Es decir, las columnas de $B$ son las coordenadas de los elementos de $S$ respecto de la base $S'$. Si $x\in M$ tiene coordenadas $(r\_1,\dots, r\_n)$ respecto de $S$ y $(r\_1',\dots, r\_n')$ respecto de $S'$ entonces se satisface que

$$B\left(\begin{array}{c}r\_1\cr\vdots\cr r\_n\end{array}\right)=\left(\begin{array}{c}r\_1'\cr\vdots\cr r\_n'\end{array}\right).$$

Por eso $B$ se denomina **matriz de cambio de base** de $S$ a $S'$. 
{{% /remark %}}



{{% example name="No todos los módulos son libres" %}}
El $\mathbb Z$-módulo $\mathbb Z/(2)$ está generado por el conjunto $S=\\{\bar 1\\}$ pero $S$ no es linealmente independiente porque $2\cdot\bar 1=\bar 2=\bar 0$ y $0\neq 2\in\mathbb Z$. De hecho el $\mathbb Z$-módulo $\mathbb Z/(2)$ no puede tener ninguna base ya que los subconjuntos de $\mathbb Z/(2)$ son $\varnothing$, $\\{\bar 0\\}$, $\\{\bar 1\\}$ y $\\{\bar 0,\bar 1\\}$, los dos primeros no generan y los dos últimos no son linealmente independientes. Este argumento, por elemental, es algo complejo. Es más sencillo observar que los $\mathbb Z$-módulos libres poseen un único elemento, $\mathbb Z^0=\\{0\\}$, o infinitos, $\mathbb Z^n$ con $n>0$, por tanto $\mathbb Z/(2)$, que tiene dos elementos, no puede ser libre.
{{% /example %}}


## Torsión

En este apartado $R$ denotará siempre un dominio.

{{% definition %}}
Dado un $R$-módulo $M$, decimos que $a\in M$ es un elemento de **torsión** si existe algún $r\in R$ no nulo, $r\neq 0$, tal que $ra=0$. 
{{% /definition %}}


{{% remark %}}
El $0\in M$ es siempre un elemento de torsión ya que $1\neq 0$ y $1\cdot 0 = 0$. Dado un entero no nulo $0\neq n\in\mathbb Z$, todo elemento $\bar a$ del $\mathbb Z$-módulo $\mathbb Z/(n)$ es de torsión puesto que $n\bar a=\overline{na}=\bar 0$. Más generalmente, si $I\subset R$ es un ideal no nulo entonces todo elemento de $R/I$ es de torsión, pues existe $0\neq a\in I$ y dado $\bar r\in R/I$, $a\bar r=\overline{ar}=0$.
{{% /remark %}}


Veamos una condición suficiente, aunque no necesaria, para que un módulo no sea libre.

{{% proposition %}}
Si $M$ es un $R$-módulo que tiene elementos no triviales de torsión entonces $M$ no es libre. 
{{% /proposition %}}


{{% proof %}}
Supongamos por reducción al absurdo que $\\{a\_1,\dots,a\_n\\}\subset M$ fuera una base. Tomamos un elemento no trivial de torsión $0\neq x\in M$ y lo escribimos como

$$x=r\_1a\_1+\cdots+r\_na\_n$$

con $r\_1,\dots,r\_n\in R$. Ha de haber algún $r_i\neq 0$ para cierto $1\leq i\leq n$ ya que $x\neq 0$. Como $x\in M$ es de torsión existe $0\neq s\in R$ tal que

$$0=sx=sr\_1a\_1+\cdots+sr\_na\_n.$$

Uno de los coeficientes de esta combinación lineal es $sr\_i\neq 0$ que es no nulo porque $R$ es un dominio. Esto contradice la independencia lineal.
{{% /proof %}}


{{% remark %}}
El $\mathbb Z$-módulo $\mathbb Q$ no tiene torsión, es decir, el único elemento de torsión es el $0$, pero se puede comprobar que no es libre. No posee ninguna base, ni finita ni infinita. 
{{% /remark %}}


Los elementos de torsión forman un submódulo.
{{% proposition %}}
Si $M$ es un $R$-módulo, el subconjunto $T(M)\subset M$ formado por los elementos de torsión es un submódulo.
{{% /proposition %}}

{{% proof %}}
 
Dados $a,b\in T(M)$ existen $s,t\in R$ no nulos, $s\neq 0\neq t$, tales que $sa=0=tb$. 

* $0\in T(M)$ tal como hemos visto antes.

* $a+b\in T(M)$ pues $st\neq 0$ y $st(a+b)=t(sa)+s(tb)=0$.

* Dado $r\in R$, $ra\in T(M)$ pues $s(ra)=r(sa)=0$.

{{% /proof %}}

{{% remark %}}
Según hemos visto antes, si $I\subset R$ es un ideal no nulo entonces $T(R/I)=R/I$. Como $R$ no tiene divisores de cero, $T( {R} )=\\{0\\}$, y más generalmente $T(R^n)=\\{0\\}$, $n\geq 0$.
{{% /remark %}}

Los homomorfismos preservan la torsión.

{{% proposition label="homotorsion" %}}
Si $f\colon M\rightarrow N$ es un homomorfismo de $R$-módulos entonces $f(T(M))\subset T(N)$. Si $f$ es un isomorfismo entonces $f(T(M))= T(N)$. 
{{% /proposition %}}

{{% proof %}}
Dado $a\in T(M)$ existe $0\neq r\in R$ tal que $ra=0$ luego $rf(a)=f(ra)=f(0)=0$ y por tanto $f(a)$ es de torsión. Esto prueba la inclusión. Si $f$ además es un isomorfismo entonces podemos aplicarle la parte ya probada a $f^{-1}\colon N\rightarrow M$, con lo que tenemos $f^{-1}(T(N))\subset T(M)$, lo cual equivale a la otra inclusión $T(N)\subset f(T(M))$.
{{% /proof %}}


{{% corollary label="torsioniso" %}}
Si dos módulos son isomorfos $M\cong N$ entonces sus submódulos de torsión también $T(M)\cong T(N)$.
{{% /corollary %}}

{{% proof %}}
Tomamos un isomorfismo $f\colon M\rightarrow N$. Consideramos la restricción $f_{|_{T(M)}}\colon T(M)\rightarrow N$, que será inyectiva. Tomamos la correspondiente aplicación sobreyectiva $g\colon T(M)\rightarrow \operatorname{im} f_{|_{T(M)}}$ definida como $g(x)=f_{|_{T(M)}}(x)$. Como $f_{|_{T(M)}}$ es inyectiva, $g$ también, así que esta última es un isomorfismo. Por la proposición anterior, $\operatorname{im} f_{|_{T(M)}}=f(T(M))=T(N)$. Esto concluye la prueba.
{{% /proof %}}


La torsión preserva productos.

{{% proposition label="torsionproduct" %}}
Dados dos $R$-módulos $M$ y $N$, tenemos que $T(M\times N)=T(M)\times T(N)$ .
{{% /proposition %}}


{{% proof %}}
Veamos primero $\subset$. Si $(a,b)\in T(M\times N)$ existe $0\neq r\in R$ tal que $r(a,b)=(ra,rb)=(0,0)$, es decir $ra=0$ y $rb=0$, por lo que $a\in T(M)$ y $b\in T(N)$, o dicho de otro modo $(a,b)\in T(M)\times T(N)$. 

Veamos ahora $\supset$. Si $(a,b)\in T(M)\times T(N)$, es decir $a\in T(M)$ y $b\in T(N)$, entonces existen $r,s\in R$ no nulos tales que $ra=0$ y $sb=0$, por tanto $rs\neq 0$ y $rs(a,b)=(s(ra),r(sb))=(0,0)$, luego $(a,b)\in T(M\times N)$.
{{% /proof %}}


 
## Cocientes

{{% definition %}}
Dado un $R$-módulo $M$ y un submódulo $N\subset M$, el **$R$-módulo cociente** $M/N$ es el cociente de los grupos abelianos subyacentes dotado del producto por escalares

$$r(a+N)=(ra)+N.$$

{{% /definition %}}


{{% remark %}}
Recordemos que $M/N=\\{a+N \mid  a\in M\\}$ de modo que $a+N=b+N$ si y solo si $a-b\in N$. En particular $a+N=0+N$ si y solo si $a\in N$. El elemento $a+N$ del cociente se denomina **clase** de $a$ **módulo** $N$. Cuando el submódulo $N$ se sobreentiende se escribe simplemente

$$a+N=\bar a=[a].$$

La suma en el cociente se define como $(a+N)+(b+N)=(a+b)+N$. El cero en el cociente es $0+N$. Comprueba que $M/M$ es el módulo trivial y $M/\\{0\\}\cong M$. Si $R$ es un dominio y $0\neq x\in R$ todo elemento del $R$-módulo cociente $\bar a\in R/(x)$ es de torsión pues $x\bar a=\overline{xa}=0$. 
{{% /remark %}}


{{% theorem %}}
El $R$-módulo cociente $M/N$ está bien definido. Su estructura es la única que hace que la **proyección natural** $p\colon M\twoheadrightarrow M/N$, $p(a)=a+N$, sea un homomorfismo. El núcleo de esta proyección es $\ker p=N$. 
{{% /theorem %}}


{{% proof %}}
Para ver que la producto por escalares está bien definido hay que comprobar que 

$$
a+N=a'+N\Rightarrow(ra)+N=(ra')+N.
$$

Esto equivale a 

$$
a-a'\in N\Rightarrow ra-ra'= r(a-a')\in N.
$$

Las propiedades que la suma y el producto por escalares deben satisfacer se cumplen obviamente pues se derivan de las correspondientes propiedades de $M$.

Probemos la unicidad. Si $p\colon M\rightarrow M/N$ es un homomorfismo entonces

$$\begin{array}{rcl}
p(a+b)&=&p(a)+p(b),\cr p(ra)&=&rp(a),
\end{array}$$

lo cual equivale a

$$\begin{array}{rcl}
(a+b)+N&=&(a+N)+(b+N),\cr (ra)+N&=&r(a+N).
\end{array}$$

El núcleo de la proyección natural es

$$\ker p =\\{a\in M \mid  p(a)=0\\},$$

pero $p(a)=a+N$ y $a+N=0+N$ si y solo si $a\in N$, luego $\ker p=N$.  
{{% /proof %}}

{{% example name="$R[ x ]/(p(x))$ como $R$-módulo" %}}
Sea $R$ un anillo y $p(x)\in R[ x ]$ un polinomio mónico de grado $n$. El $R[ x ]$-módulo cociente $R[ x ]/(p(x))$ es también un $R$-módulo, restringiendo el producto por escalares al subanillo $R\subset R[ x ]$. Hemos [visto](../../rings/definitions/#uniquerep) que todo elemento del cociente está representado por un único polinomio de grado $<n$. Es decir, todo elemento de $R[ x ]/(p(x))$ se puede escribir como combinación lineal de $S=\\{1,\bar{x},\dots,\bar{x}^{n-1}\\}$ de manera única. Por tanto, $R[ x ]/(p(x))$ es libre como $R$-módulo y $S$ es una base. Recuerda que, sin embargo, cuando estudiamos la torsión vimos que, si $R$ es un dominio, $R[ x ]/(p(x))$ no es libre como $R[ x ]$-módulo.
{{% /example %}}

La siguiente proposición también tiene un análogo para anillos [ya demostrado](/estalg/rings/definitions/#factorquotient).

{{% proposition label="factorquotientmodules" %}}
Dado un submódulo $N\subset M$ y un homomorfismo $f\colon M\rightarrow P$ tal que $N\subset \ker f$, $f$ factoriza de manera única a través de la proyección natural, es decir existe un único homomorfismo $g\colon M/N\rightarrow P$ tal que $f=g\circ p$,

$$f\colon M\stackrel{p}\twoheadrightarrow M/N\stackrel{g}\rightarrow P.$$

{{% /proposition %}}


{{% proof %}}
Si $f=g\circ p$ entonces tendríamos

$$f(a)=(g\circ p)(a)=g(p(a))=g(a+N).$$

Definimos la aplicación $g\colon M/N\rightarrow P$ como

$$g(a+N)=f(a).$$

Veamos que en efecto está bien definida. La unicidad se seguirá de la primera fórmula.

Si $a+N=a'+N$ entonces $a-a'\in N\subset\ker f$ luego

$$0=f(a-a')=f(a)-f(a').$$

Por tanto

$$g(a+N)=f(a)=f(a')=g(a'+N).$$

Claramente $g$ es un homomorfismo pues se define como el homomorfismo $f$ en los representantes.  
{{% /proof %}}


{{% remark %}}
En la proposición anterior podemos tomar siempre $N=\ker f$. 
{{% /remark %}}

El siguiente resultado es una versión para módulos del primer teorema de isomorfía, [ya recordado para anillos](/estalg/rings/definitions/#primer).

{{% theorem name="Primer Teorema de Isomorfía" label="isomodules" %}}
Dado un homomorfismo de módulos $f\colon M\rightarrow N$, existe un único homomorfismo de módulos $\bar f\colon M/\ker f\rightarrow \operatorname{im}f$ tal que $f$ factoriza como $f=i\circ\bar f\circ p$, es decir, $f$ encaja en el siguente **diagrama conmutativo**, 

![Primer teorema de isomorfía](../../images/isomorfiamodulos.svg)

Aquí $p$ es la proyección natural e $i$ es la inclusión. Además $\bar f$ es un isomorfismo.
{{% /theorem %}}

{{% proof %}}
El primer teorema de isomorfía para grupos garantiza la existencia de un único homomorfismo de grupos $\bar{f}$ que satisface las propiedades del enunciado. En particular viene dado por $\bar{f}([m])=f(m)$. Por tanto, al ser $f$ un homomorfismo de módulos $\bar{f}$ también lo será. 
{{% /proof %}}

{{% example name="El cociente de un producto por un factor" %}}
Recordemos que dados dos $R$-módulos $M$ y $N$ podemos considerar el $R$-módulo producto $M\times N$ y los homomorfismos de inclusión $i\_1\colon M\rightarrow M\times N$, $i\_1(a)=(a,0)$, y proyección $p\_2\colon M\times N\rightarrow N$, $p\_2(a,b)=b$. El primero es inyectivo y el segundo sobreyectivo. Claramente $\operatorname{im}i\_1=M\times\\{0\\}=\ker p\_2$, por tanto el teorema anterior nos proporciona isomorfismos

$$\begin{array}{rclrcl}
\frac{M\times N}{M\times\\{0\\}}&\stackrel{\cong}\longrightarrow&N,&\qquad M&\stackrel{\cong}\longrightarrow&M\times\\{0\\},\\\ 
[(a,b)]&\mapsto& b,&a&\mapsto&(a,0).\end{array}$$

Además, el homomorfismo inyectivo $i_1$ induce un isomorfismo $M\cong M\times\\{0\\}$. 
Análogamente podemos obtener isomorfismos

$$\begin{array}{rclrcl}
\frac{M\times N}{\\{0\\}\times N}&\stackrel{\cong}\longrightarrow&M,&\qquad N&\stackrel{\cong}\longrightarrow&\\{0\\}\times N,\\\ 
[(a,b)]&\mapsto& a,&b&\mapsto&(0,b).\end{array}$$

{{% /example %}}

Recordemos que un $R$-módulo es *cíclico* si se puede generar por un solo elemento.


{{% proposition %}}
Un $R$-módulo $M$ es cíclico $\Leftrightarrow$ $M\cong R/I$ para algún ideal $I\subset R$. 
{{% /proposition %}}


{{% proof %}}
$\Leftarrow$ El módulo $R/I$ es cíclico pues $\\{\bar 1\\}\subset R/I$ genera, así que cualquier módulo isomorfo a $R/I$ será también cíclico. 

$\Rightarrow$ Sea $\\{a\\}\subset M$ un generador. El homomorfismo $\phi\_{\\{a\\}}\colon R\rightarrow M$ que envía $1\mapsto a$ es por tanto sobreyectivo, así que por el primer [teorema](#isomodules) de isomorfía, $R/\ker \phi\_{\\{a\\}}\cong M$, con lo que podemos tomar $I=\ker \phi\_{\\{a\\}}$.   
{{% /proof %}}

{{% corollary label="torsionquotient" %}}
Si dos módulos son isomorfos $M\cong N$ entonces $M/T(M)\cong N/T(N)$.
{{% /corollary %}}

{{% proof %}}
Tomamos un isomorfismo $f\colon M\rightarrow N$. Consideramos la aplicación sobreyectiva $g=p\circ f\colon M\twoheadrightarrow N/T(N)$ definida como la composición del isomorfismo $f$ con la proyección natural $p\colon N\twoheadrightarrow N/T(N)$. Por una [proposición anterior](#homotorsion), $\ker g=f^{-1}(T(N))=T(M)$, así que aplicando el primer teorema de isomorfía obtenemos el isomorfismo deseado $\bar{g}\colon M/T(M)\rightarrow N/T(N)$.
{{% /proof %}}


{{% proposition %}}
Dado un $R$-módulo $M$ y un submódulo $N\subset M$, si $N$ y $M/N$ son finitamente generados entonces $M$ también lo es. Si, además, $N$ y $M/N$ son libres de rangos $p$ y $q$, entonces $M$ es libre de rango $p+q$.
{{% /proposition %}}


{{% proof %}}
Sean $\\{\bar a\_1,\dots,\bar a\_p\\}\subset M/N$ y $\\{b\_1,\dots,b\_q\\}\subset N$ conjuntos de generadores. Veamos que $S=\\{ a\_1,\dots, a\_p,b\_1,\dots,b\_q\\}\subset M$ genera. Dado $x\in M$, consideramos $\bar x\in M/N$ y lo escribimos como combinación lineal de los generadores de $M/N$ con coeficientes en $R$

$$\begin{array}{rcl}\bar x&=&r\_1\bar a\_1+\cdots+r\_p\bar a\_p\cr
&=&\overline{r\_1a\_1+\cdots+r\_pa\_p}.
\end{array}$$

Tenemos entonces que

$$x-(r\_1a\_1+\cdots+r\_pa\_p)\in N$$

así que lo podemos escribir como combinación lineal de los geberadores  de $N$ con coeficientes en $R$,

$$x-(r\_1a\_1+\cdots+r\_pa\_p)=s\_1b\_1+\cdots+s\_qb\_q.$$

Despejando vemos que $x$ es combinación lineal de $S$, y por tanto $S$ genera $M$.

Supongamos ahora que $\\{\bar a\_1,\dots,\bar a\_p\\}$ y $\\{b\_1,\dots,b\_q\\}$ son linealmente independientes (y, por tanto, bases de $M/N$ y $N$). Veamos que $S$ también lo es. Sean $r_1,\ldots,r_p,s_1,\ldots,s_q\in R$ tales que

$$r\_1a\_1+\cdots+r\_pa\_p+s\_1b\_1+\cdots+s\_qb\_q=0.$$

Tomando clases módulo $N$, obtenemos que $r\_1\bar a\_1+\cdots+r\_p\bar a\_p=0$, y por tanto $r\_1=\cdots=r\_p=0$. La igualdad anterior queda entonces como $s\_1b\_1+\cdots+s\_qb\_q=0$, de donde $s\_1=\cdots=s\_q=0$.
{{% /proof %}}

{{% remark %}}
Si $M$ es finitamente generado, $M/N$ también lo es, porque si $\\{a\_1,\dots, a\_n\\}\subset M$ genera entonces $\\{\bar{a}\_1,\dots, \bar{a}\_n\\}$ genera $M/N$. En cambio, en general, $N$ podría no ser finitamente generado.
{{% /remark %}}


{{% corollary %}}
Dado un dominio de ideales principales $R$, un $R$-módulo libre finitamente generado $M$ de rango $r$ y un submódulo $N\subset M$, el $R$-módulo $N$  es libre finitamente generado de rango $\leq r$.
{{% /corollary %}}


{{% proof %}}
Por inducción en el rango de $M$, que denotamos $n$. Para $n=0$ es obvio ya que en este caso $M=\\{0\\}$ tendría que ser el módulo trivial, que no tiene más submódulos que él mismo. 

Sea ahora $n>0$ y supongamos el resultado cierto para $R$-módulos libres de rango $n-1$. Como $M\cong R^n$, basta probar el resultado para $R^n$. Observamos que $R^n=R^{n-1}\times R$ y consideramos el homomorfismo de proyección sobre la última coordenada $p=p\_2\colon R^n\rightarrow R$, cuyo núcleo es $R^{n-1}\times \\{0\\}\cong R^{n-1}$, que es libre de rango $n-1$. Sea $N\subset R^n$ un submódulo y $p\_{|\_{N}}\colon N\rightarrow R$ la restricción del homomorfismo anterior. Como 

$$\ker p\_{|\_{N}}=N\cap \ker p= N\cap (R^{n-1}\times \\{0\\})\subset R^{n-1}\times \\{0\\},$$

deducimos que $\ker p\_{|\_{N}}$ es finitamente generado de rango $\leq n-1$ por hipótesis de inducción. Es más, por el primer [teorema](#isomodules) de isomorfía aplicado a $p\_{|\_{N}}$, 

$$\frac{N}{\ker p\_{|\_{N}}}\cong \operatorname{im} p\_{|\_{N}}.$$

Más aún, $\operatorname{im} p\_{|\_{N}}\subset R$ es un submódulo, por tanto un ideal, y $R$ es un dominio de ideales principales, así que $\operatorname{im} p\_{|\_{N}}$ es libre y finitamente generado (por un solo elemento), y por tanto de rango $\leq 1$. Ahora podemos deducir, haciendo uso de la proposición anterior, que $N$ es libre y finitamente generado de rango $\leq (n-1)+1=n$.
{{% /proof %}}