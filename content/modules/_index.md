+++
title = "Módulos"
weight = 20
+++

¿Cómo es el álgebra lineal que resulta al reemplazar el papel de los cuerpos por anillos más generales? El objeto de estudio de esta álgebra lineal generalizada son los módulos. Un módulo $M$ es a un anillo $R$ lo que un espacio vectorial es a un cuerpo. Es decir, el módulo $M$ está dotado de las siguientes operaciones:

* Suma.

* Resta.

* Producto por escalares de $R$. 

Estas operaciones deben satisfacer las propiedades habituales. Además el módulo ha de contener el siguiente elemento:

* Cero $0$.

Tanto este $0\in M$ como el $1\in R$ han de satisfacer las propiedades habituales con respecto a la suma y la multiplicación.

Los módulos sobre el anillo $\mathbb Z$ son simplemente los grupos abelianos. Los espacios vectoriales sobre un cuerpo cualquiera están clasificados por su dimensión. Es decir, dos espacios vectoriales son isomorfos si y solo si tienen la misma dimensión. En este tema estudiaremos fundamentalmente la clasificación de los módulos finitamente generados sobre un dominio de ideales principales. En particular la clasificación de los grupos abelianos finitamente generados. Aplicaremos estos resultados a la resolución de sistemas de ecuaciones lineales diofánticas y al estudio de un tema de álgebra lineal clásica: los endomorfismos de espacios vectoriales de dimensión finita.

## Definición

{{% definition %}}

Dado un anillo $R$, un **$R$-módulo** es un conjunto $M$ equipado con dos aplicaciones, llamadas *suma* y *producto por escalares*,
\\[
\begin{array}{ccc}
M\times M\rightarrow M, &\qquad& R\times M\rightarrow M,\cr
(a,b)\mapsto a+b;&&(r,a) \mapsto ra;
\end{array}
\\]
que satisfacen las siguientes propiedades, donde $a,b,c\in M$ y $r,s\in R$:

* Asociativa: $$a+(b+c)=(a+b)+c,\qquad r(sa)=(rs)a.$$

* Conmutativa: $$a+b=b+a.$$

* Distributiva:
$$r(a+b)=ra+rb,\qquad (r+s)a=ra+sa.$$

* Existencia de *elemento neutro* $0\in M$ para la suma y comportamiento del $1\in R$ como elemento neutro para el producto por escalares:
$$0+a=a,\qquad 1a=a.$$

* Existencia de un *elemento opuesto* para la suma $-a\in M$ para todo $a\in M$ de modo que $$a+(-a)=0.$$

{{% /definition %}}


{{% remark %}}
 Cuando quede claro por el contexto o no sea relevante especificarlo, omitiremos $R$ de la notación. La suma en un módulo lo dota de estructura de grupo abeliano. Recordemos que el elemento neutro de un grupo es único, no puede haber dos distintos que satisfagan la misma propiedad. Los opuestos para la suma también. Restar es sumar el elemento opuesto \\(a-b=a+(-b)\\). Además $0a=0=r0$ y $r(-a)=-ra=(-r)a$. Si $R=k$ es un cuerpo la noción de $R$-módulo coincide con la de $k$-espacio vectorial.
{{% /remark %}}



{{% example name="El módulo trivial" %}}

El conjunto unitario $\\{0\\}$, dotado de las únicas operaciones suma y producto por escalares posibles, es un módulo sobre cualquier anillo $R$. 

{{% /example %}}


{{% example name="$R^n$" %}}
 Sus elementos son vectores conlumna con entradas en $R$, aunque a veces, cuando convenga, se denotarán por filas. La suma se define coordenada a coordenada, y el producto por escalares se define multiplicando el escalar por todas las coordenadas: $$\left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right)+\left(\begin{array}{c}b_1\cr\vdots\cr b_n\end{array}\right)=\left(\begin{array}{c}a_1+b_1\cr\vdots\cr a_n+b_n\end{array}\right),\qquad r\left(\begin{array}{c}a_1\cr\vdots\cr a_n\end{array}\right)=\left(\begin{array}{c}ra_1\cr\vdots\cr ra_n\end{array}\right).$$ Para $n=1$ observamos que el propio $R$ puede considerarse como un $R$-módulo. Para $n=0$ obtenemos el módulo trivial.
{{% /example %}}


{{% example name="Producto de módulos" %}}
Dados dos $R$-módulos $M$ y $N$, su **producto** cartesiano $M\times N$ posee una estructura de $R$-módulo con las siguientes operaciones: $$\begin{array}{rcl}(a\_1,b\_1)+(a\_2,b\_2)&=&(a\_1+a\_2,b\_1+b\_2),\cr r(a,b)&=&(ra,rb).\end{array}$$ ¿Cuál es el elemento neutro para la suma? ¿Cuáles son los opuestos?
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
Es fácil comprobar que estas fórmulas definen una estructra de $\mathbb Z$-módulo en $A$, necesariamente única.  
{{% /proof %}}



{{% definition %}}
Un subconjunto $N\subset M$ de un $R$-módulo $M$ es un **submódulo** si:

* $0\in N$.

* $a+b\in N$ para todo $a,b\in N$.

* $-a\in N$ para todo $a\in N$.

* $ra\in N$ para todo $r\in R$ y $a\in N$.
{{% /definition %}}



{{% remark %}}
Un submódulo $N\subset M$ es un módulo por derecho propio con la suma y el producto por escalares heredados de $M$. El módulo trivial $\\{0\\}$ es un submódulo de cualquier otro. Los submódulos de $R$ coinciden con los ideales del anillo. 
{{% /remark %}}



## Homomorfismos

Los homomorfismos de módulos son aplicaciones que preservan la estructura, es decir, la suma y el producto por escalares.

{{% definition %}}
Dados dos $R$-módulos $M$ y $N$, un **homomorfismo** $f\colon M\rightarrow N$ es una aplicación tal que, para todo $r\in R$ y $a,b\in M$, $$\begin{array}{rcl} f(a+b)&=&f(a)+f(b),\cr f(ra)&=&rf(a).\end{array}$$ Un **isomorfismo** es un homomorfismo biyectivo. Un **automorfismo** es un isomorfismo de un $R$-módulo en sí mismo.
{{% /definition %}}


{{% remark %}}
Los homomorfismos satisfacen $f(-a)=-f(a)$ y $f(0)=0$. La identidad $\operatorname{id}_M\colon M\rightarrow M$ es un isomorfismo. Comprueba que si $$M\stackrel{f}\longrightarrow N\stackrel{g}\longrightarrow P$$ son homomorfismos entonces la composición $g\circ f\colon M\rightarrow P$ también. Lo mismo es cierto para isomorfismos. Es más, demuestra que si $f\colon M\rightarrow N$ es un isomorfismo entonces su aplicación inversa $f^{-1}\colon N\rightarrow M$ también. El símbolo $\cong$ se usará para denotar la relación de ser isomorfos $M\cong N$. Prueba que esta relación es de equivalencia. 
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
Dado un $R$-módulo $M$ y $r\in R$, la aplicación $M\stackrel{r\cdot}\rightarrow M$ definida como $x\mapsto r\cdot x$ es un homomorfismo. ¿Cuándo es un isomorfismo?
{{% /example %}}


{{% example name="Inclusiones y proyecciones de un producto" %}}
Dados dos $R$-módulos $M$ y $N$, definimos dos homomorfismos de **inclusión** $$i\_1\colon M\longrightarrow M\times N,\qquad i\_2\colon N\longrightarrow M\times N,$$ mediante las fórmulas $$i\_1(a)=(a,0),\qquad i\_2(b)=(0,b),$$ y otros dos de **proyección** $$p\_1\colon M\times N\longrightarrow M,\qquad p\_2\colon M\times N\longrightarrow N,$$ como $$p\_1(a,b)=a,\qquad p\_2(a,b)=b.$$ Comprueba que $p\_1\circ i\_1=\operatorname{id}\_M$ y $p\_2\circ i\_2=\operatorname{id}\_N$. ¿Son estos homomorfismos isomorfismos? 
{{% /example %}}


{{% example name="Conmutatividad del producto" %}}
El producto de $R$-módulos es conmutativo salvo isomorfismo. Dados dos $R$-módulos $M$ y $N$ tenemos un isomorfismo $$\begin{array}{rcl}M\times N&\longrightarrow&N\times M,\cr (a,b)&\mapsto&(b,a).\end{array}$$ ¿Cuál es su inverso? 
{{% /example %}}


{{% example name="Matrices" %}}
Toda matriz $B$ de tamaño $m\times n$ con entradas en $R$ da lugar a un homomorfismo definido por la multiplicación de matrices: $$\begin{array}{rcl} R^n&\longrightarrow&R^m,\cr \left(\begin{smallmatrix}a_1\cr\vdots\cr a_n\end{smallmatrix}\right)&\mapsto& B\left(\begin{smallmatrix}a_1\cr\vdots\cr a_n\end{smallmatrix}\right). \end{array}$$ La composición de este tipo de homomorfismos es el producto de matrices. En particular $B$ define un isomorfismo si y solo si es una matriz invertible. Cualquier homomorfismo $f\colon R^n\rightarrow R^m$ es de este tipo. En efecto, si para cada $1\leq i\leq n$ consideramos el elemento $$e\_i=\left(\begin{smallmatrix}0\cr\vdots\cr1\cr\vdots\cr0\end{smallmatrix}\right)\in R^n$$ cuya única coordenada no trivial es la $i$-ésima, que vale $1$, puedes comprobar la matriz que define $f\colon R^n\rightarrow R^m$ es aquella cuyas columnas son los $f(e\_i)$, $$\left(f(e\_1)\mid\cdots\mid f(e\_n)\right).$$
{{% /example %}}


{{% exercise %}}
 Demuestra que si $M\cong M'$ y $N\cong N'$ entonces $M\times N\cong M'\times N'$.
{{% /exercise %}}



{{% proposition %}}
Si $M$ es un $R$-módulo y $S=\\{a\_1,\dots,a\_n\\}\subset M$ un subconjunto cualquiera, existe un único homomorfismo $\phi=\phi_{S}\colon R^n\rightarrow M$ tal quie $\phi(e_i)=a_i$.
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
Dado un homomorfismo $f\colon M\rightarrow N$, su imagen $\operatorname{im} f\subset N$ es un submódulo. 
{{% /proposition %}}


{{% proof %}}

* $0=f(0)\in \operatorname{im} f$.

* $f(a)+f(b)=f(a+b)\in \operatorname{im} f$ para $a,b\in M$.

* $-f(a)=f(-a)\in \operatorname{im} f$ para todo $a\in M$.

* $rf(a)=f(ra)\in \operatorname{im} f$ para todo $r\in R$ y $a\in M$.

 
{{% /proof %}}


{{% proposition %}}
El **núcleo** de un homomorfismo $f\colon M\rightarrow N$, $$\ker f=\\{a\in M\mid f(a)=0\\},$$ es un submódulo $\ker f\subset M$.
{{% /proposition %}}


{{% proof %}}

* $0\in\ker f$ pues $f(0)=0$.

* Si $a,b\in\ker f$ entonces $a+b\in \ker f$ puesto que $f(a+b)=f(a)+f(b)=0+0=0$.

* Si $a\in\ker f$ entonces $-a\in \ker f$ puesto que $f(-a)=-f(a)=0$.

* Si $a\in\ker f$ y $r\in R$ entonces $ra\in \ker f$ pues $f(ra)=rf(a)=r0=0$.
 
{{% /proof %}}


{{% remark %}}
 Como ocurre con los grupos y con los anillos, un homomorfismo de módulos $f\colon M\rightarrow N$ es inyectivo si y solo si $\ker f=\\{0\\}$. De otro modo, la inyectividad de $f$ equivale a que si $a\in M$ es tal que $f(a)=0$ entonces $a=0$.
{{% /remark %}}


## Módulos libres

{{% definition %}}
Sea $M$ un $R$-módulo y $S=\\{a\_1,\dots,a\_n\\}\subset M$ un subconjunto. Decimos que $S$ **genera** $M$ si todo elemento de $x\in M$ es **combinación lineal** de $S$, es decir, de la forma $$x=r\_1a\_1+\cdots+r\_na\_n$$ para ciertos $r\_1,\dots,r\_n\in R$. Decimos que $S$ es **linealmente independiente** si la única combinación lineal de $S$ que da como resultado $0$ es aquella que tiene todos los cieficientes nulos, es decir si $r\_1,\dots,r\_n\in R$ son tales que $$r\_1a\_1+\cdots+r\_na\_n=0$$ entonces $r\_1=\cdots=r\_n=0$. Decimos además que $S$ es una **base** de $M$ si lo genera y es linealmente independiente. Un $R$-módulo es **finitamente generado** si posee un subconjunto finito que genera, y es **libre** si posee una base.
{{% /definition %}}



{{% remark %}}
 Si $R=k$ es un cuerpo todo $R$-módulo es libre puesto que todo $k$-espacio vectorial posee una base. Los $k$-espacios vectoriales finitamente generados se denominan también de dimensión finita.
{{% /remark %}}


{{% example name="$R^n$ es libre" %}}
 El sub conjunto $\\{e\_1,\dots,e\_n\\}\subset R^n$ es una base denominada **canónica**.
{{% /example %}}



{{% watch %}}
 En términos del homomorfismo $$\phi\_S\colon R^n\longrightarrow M$$ definido antes, $S=\\{a\_1,\dots,a\_n\\}\subset M$ genera si y solo si $\phi\_S$ es sobreyectivo y $S$ es linealmente independiente si y solo si $\phi\_S$ es inyectivo. Por tanto $S$ es una base si y solo si $\phi\_S$ es un isomorfismo. En particular, en este caso para todo $x\in M$ existe un único $(r\_1,\dots,r\_n)\in R^n$ tal que $x=\phi\_S(r\_1,\dots,r\_n)=r\_1a\_1+\cdots+r\_na\_n$. Decimos entonces que $(r\_1,\dots,r\_n)$ son las **coordenadas** de $x$ respecto de $S$. Es más, la aplicación que envía cada elemento a sus coordenadas respecto de $S$ es $$\phi\_S^{-1}\colon M\longrightarrow R^n,$$ que es un isomorfismo, por tanto la asignación de coordenadas respecto de una base preserva sumas y productos por escalares. Cualquier $R$-módulo isomorfo a algún $R^n$ es libre porque los isomorfismos preservan bases. Concluimos que un $R$-módulo es libre si y solo si es isomorfo a algún $R^n$.
{{% /watch %}}



{{% watch %}}
 Sea $f\colon M\rightarrow N$ es un homomorfismo de $R$-módulos y $S=\\{a\_1,\dots,a\_n\\}\subset M$. Los siguientes enunciados son consecuencia de las observaciones anteriores. Comprúebalo: 

* Si $S\subset M$ genera y $f$ es sobreyectivo $\Rightarrow$ $f(S)\subset N$ genera.

* Si $S\subset M$ es linealmente independiente y $f$ es inyectivo $\Rightarrow$ $f(S)\subset N$ es linealmente independiente.

* Si $S\subset M$ es una base y $f$ es biyectivo $\Rightarrow$ $f(S)\subset N$ es una base.

* $f(S)\subset\operatorname{im}f$ genera.
{{% /watch %}}


Seguidamente definimos la noción de determinante para matrices sobre un anillo igual que se hacía para los cuerpos.

{{% definition %}}
El **determinante** $|A|$ de una matriz cuadrada $A=(a\_{ij})$ de tamaño $n\times n$ con entradas en un anillo conmutativo $R$ se define como $$|A|=\sum\_{\sigma\in S\_n}\operatorname{signo}(\sigma)a\_{1\sigma(1)}\cdots a\_{n\sigma(n)}.$$ Aquí $S_n$ denota el grupo de permutaciones de $n$ elementos.
{{% /definition %}}


{{% watch %}}
 El determinante de la matriz identidad es $|I|=1$. Si $A$ tiene una fila de ceros entonces $|A|=0$. Una matriz $A$ y su traspuesta $A^t$ tienen el mismo determinante $|A|=|A^t|$. El determinante preserva productos $|AB|=|A||B|$. Las fórmulas del desarrollo de un determinante por los adjuntos de una fila o columna también son válidas en este contexto. Si $A$ es una matriz cuadrada invertible entonces $|A|\in R^{\times}$ es una unidad puesto que $AA^{-1}=I$, luego $|A||A^{-1}|=|AA^{-1}|=|I|=1$. Además vemos que en dicho caso $|A^{-1}|=|A|^{-1}$.  El recíproco también es cierto pues se puede comprobar que si $A$ es cuadrada y $|A|\in R^{\times}$ es una unidad entonces la matriz traspuesta de la adjunta de $A$ dividida por $|A|$ es inversa de $A$. Las matrices invertibles son necesariamente cuadradas si $R$ no es el anillo trivial. Esto se comprueba por reducción al absurdo. En efecto, sean $A$ y $B$ matrices tales que $AB=I$ y $BA=I$. Como las matrices identidad $I$ son cuadradas, si $A$ tiene tamaño $m\times n$ entonces el tamaño de $B$ tiene que ser $n\times m$. Podemos suponer sin pérdida de generalidad que $m>n$. Completamos la columnas de $A$ y las filas de $B$ con ceros hasta formar matrices cuadradas y observamos que $$\left(\begin{array}{c|c}A&0\end{array}\right)\left(\begin{array}{c}B\cr \hline 0\end{array}\right)=AB+0=AB=I,$$ pero esto es imposible porque los determinantes de las matrices de la izquierda son $0$, pues contienen alguna fila o columna de ceros, pero el determinante de $I$ es $1$.
{{% /watch %}}




{{% proposition %}}
 
Todas las bases de un mismo $R$-módulo libre $M$ tiene el mismo número de elementos. 

{{% /proposition %}}


{{% proof %}}
 Si $S$ y $S'$ son bases con $n$ y $m$ elementos, respectivamente, cada una de ellas define un isomorfismo $\phi\_S\colon R^n\rightarrow M$, $\phi\_{S'}\colon R^m\rightarrow M$. Componiendo el primero con el inverso del segundo obtenemos un isomorfismo $\phi\_{S'}^{-1}\circ\phi\_S\colon R^n\rightarrow R^m$. Este isomorfismo tiene que estar definido por una matriz $A$ de tamaño $m\times n$ invertible. Como las matrices invertibles son cuadradas deducimos que $m=n$.

{{% /proof %}}



{{% definition %}}
El **rango** de un $R$-módulo libre $M$ es el número de elementos de una base. 
{{% /definition %}}



{{% watch %}}
 Cuando $R=k$ es un cuerpo, el rango de un $k$-espacio vectorial se denomina dimensión.
{{% /watch %}}


{{% watch %}}
 Si $S=\\{a\_1,\dots,a\_n\\}$ y $S'=\\{a\_1',\dots,a\_n'\\}$ son bases de un mismo $R$-módulo libre de rango $n$, el isomorfismo $\phi\_{S'}^{-1}\circ\phi\_S\colon R^n\rightarrow R^n$ considerado en la demostración anterior está definido por una matriz $B=(b_{ij})$ invertible $n\times n$ sobre $R$, que es la única que satisface las siguientes ecuaciones para todo $1\leq i\leq n$, $$a\_i=b\_{1i}a\_1'+\cdots+b\_{ni}a\_n'.$$ Es decir, las columnas de $B$ son las coordenadas de los elementos de $S$ respecto de la base $S'$. Si $x\in M$ tiene coordenadas $(r\_1,\dots, r\_n)$ respecto de $S$ y $(r\_1',\dots, r\_n')$ respecto de $S'$ entonces se satisface que $$B\left(\begin{smallmatrix}r\_1\cr\vdots\cr r\_n\end{smallmatrix}\right)=\left(\begin{smallmatrix}r\_1'\cr\vdots\cr r\_n'\end{smallmatrix}\right).$$ Por eso $B$ se denomina **matriz de cambio de base** de $S$ a $S'$. 
{{% /watch %}}



{{% example name="No todos los módulos son libres" %}}
 El $\mathbb Z$-módulo $\mathbb Z/(2)$ está generado por el conjunto $S=\\{\bar 1\\}$ pero $S$ no es linealmente independiente porque $2\cdot\bar 1=\bar 2=\bar 0$ y $0\neq 2\in\mathbb Z$. De hecho el $\mathbb Z$-módulo $\mathbb Z/(2)$ no puede tener ninguna base ya que los subconjuntos de $\mathbb Z/(2)$ son $\varnothing$, $\\{\bar 0\\}$, $\\{\bar 1\\}$ y $\\{\bar 0,\bar 1\\}$, los dos primeros no generan y los dos últimos no son linealmente independientes. Este argumento, por elemental, es algo complejo. Es más sencillo observar que los $\mathbb Z$-módulos libres poseen un único elemento, $\mathbb Z^0=\\{0\\}$, o infinitos, $\mathbb Z^n$ con $n>0$, por tanto $\mathbb Z/2$, que tiene dos elementos, no puede ser libre.
{{% /example %}}


## Torsión

En este apartado $R$ denotará siempre un dominio.

{{% definition %}}
Dado un $R$-módulo $M$, decimos que $a\in M$ es un elemento de **torsion** si existe algún $r\in R$ no nulo, $r\neq 0$, tal que $ra=0$. 
{{% /definition %}}


{{% watch %}}
 El $0\in M$ es siempre un elemento de torsión ya que $1\neq 0$ y $1\cdot 0 = 0$. Dado un entero no nulo $0\neq n\in\mathbb Z$, todo elemento $\bar a$ del $\mathbb Z$-módulo $\mathbb Z/(n)$ es de torsión puesto que $n\bar a=\overline{na}=\bar 0$.
{{% /watch %}}


Veamos una condición suficiente, aunque no necesaria, para que un módulo no sea libre.

{{% proposition %}}
 Si $M$ es un $R$-módulo que tiene elementos no triviales de torsión entonces $M$ no es libre. 
{{% /proposition %}}


{{% proof %}}
 Supongamos por reducción al absurdo que $\\{a\_1,\dots,a\_n\\}\subset M$ fuera una base. Tomamos un elemento no trivial de torsión $0\neq x\in M$ y lo escribimos como $$x=r\_1a\_1+\cdots+r\_na\_n$$ con $r\_1,\dots,r\_n\in R$. Ha de haber algún $r_i\neq 0$ para cierto $1\leq i\leq n$ ya que $x\neq 0$. Como $x\in M$ es de torsión existe $0\neq s\in R$ tal que $$0=sx=sr\_1a\_1+\cdots+sr\_na\_n.$$ Uno de los coeficientes de esta combinación lineal es $sr\_i\neq 0$ que es no nulo porque $R$ es un dominio. Esto contradice la independencia lineal.
{{% /proof %}}


{{% watch %}}
 El $\mathbb Z$-módulo $\mathbb Q$ no tiene torsión, pero se puede comprobar que no es libre, es decir, no posee niguna base, ni finita ni infinita. 
{{% /watch %}}


Los elementos de torsión forman un submódulo.
{{% proposition %}}
 Si $M$ es un $R$-módulo, el subconjunto $T(M)\subset M$ formado por los elementos de torsión es un submódulo.
{{% /proposition %}}


{{% proof %}}
  
Dados $a,b\in T(M)$ existen $s,t\in R$ no nulos, $s\neq 0\neq t$, tales que $sa=0=tb$. 

* $0\in T(M)$ tal como hemos visto antes.

* $a+b\in T(M)$ pues $st\neq 0$ y $st(a+b)=t(sa)+s(tb)=0$.

* $-a\in T(M)$ pues $s(-a)=-sa=0$.

* Dado $r\in R$, $ra\in T(M)$ pues $s(ra)=r(sa)=0$.

  {{% /proof %}}


Los homomorfismos preservan la torsión.

{{% proposition %}}
 Si $f\colon M\rightarrow N$ es un homomorfismo de $R$-módulos entonces $f(T(M))\subset T(N)$. Si $f$ es un isomorfismo entonces $f(T(M))= T(N)$. 
{{% /proposition %}}


{{% proof %}}
Dado $a\in T(M)$ existe $0\neq r\in R$ tal que $ra=0$ luego $rf(a)=f(ra)=f(0)=0$ y por tanto $f(a)$ es de torsión. Esto prueba la inclusión. Si $f$ además es un isomorfismo entonces podemos aplicarle la parte ya probada a $f^{-1}\colon N\rightarrow M$, con lo que tenemos $f^{-1}(T(N))\subset T(M)$, lo cual equivale a la otra inclusión $T(N)\subset f(T(M))$.
{{% /proof %}}


{{% corollary %}}
 Si dos módulos son isomorfos $M\cong N$ entonces sus submódulos de torsión también $T(M)\cong T(N)$. 
{{% /corollary %}}


La torsión preserva productos.

{{% proposition %}}
 Dados dos $R$-módulos $M$ y $N$, tenemos que $T(M\times N)=T(M)\times T(N)$ .
{{% /proposition %}}


{{% proof %}}
 Veamos primero $\subset$. Si $(a,b)\in T(M\times N)$ existe $0\neq r\in R$ tal que $r(a,b)=(ra,rb)=(0,0)$, es decir $ra=0$ y $rb=0$, por lo que $a\in T(M)$ y $b\in T(N)$, i.e. $(a,b)\in T(M)\times T(N)$. 

Veamos ahora $\supset$. Si $(a,b)\in T(M)\times T(N)$, es decir $a\in T(M)$ y $b\in T(N)$, entonces existen $r,s\in R$ no nulos tales que $ra=0$ y $sb=0$, por tanto $rs\neq 0$ y $rs(a,b)=(s(ra),r(sb))=(0,0)$, luego $(a,b)\in T(M\times N)\subset M\times N$.
  {{% /proof %}}


## Cocientes

{{% definition %}}
Dado un $R$-módulo $M$ y un submódulo $N\subset M$, el **$R$-módulo cociente** $M/N$ es el cociente de los grupos abelianos subyacentes dotado del producto por escalares $$r(a+N)=(ra)+N.$$
{{% /definition %}}


{{% watch %}}
 Recordemos que $M/N=\\{a+N\,|\, a\in M\\}$ de modo que $a+N=b+N$ si y solo si $a-b\in N$. En particular $a+N=0+N$ si y solo si $a\in N$. El elemento $a+N$ del cociente se denomina **clase** de $a$ **módulo** $N$. Cuando el submódulo $N$ se sobreentiende se escribe simplemente $$a+N=\bar a.$$ La suma en el cociente se define como $(a+N)+(b+N)=(a+b)+N$. El cero en el cociente es $0+N$. Comprueba que $M/M$ es el módulo trivial y $M/(0)\cong M$. Si $R$ es un dominio y $0\neq x\in R$ todo elemento del $R$-módulo cociente $\bar a\in R/(x)$ es de torsión pues $x\bar a=\overline{xa}=0$. 
{{% /watch %}}


{{% theorem %}}
El $R$-módulo cociente $M/N$ está bien definido. Su estructura es la única que hace que la **proyección natural** $p\colon M\twoheadrightarrow M/N$, $p(a)=a+N$, sea un homomorfismo. El núcleo de esta proyección es $\ker p=N$. 
{{% /theorem %}}


{{% proof %}}

Para ver que la producto por escalares está bien definido hay que comprobar que $$a+N=a'+N\Rightarrow(ra)+N=(ra')+N.$$ Esto equivale a $$a-a'\in N\Rightarrow ra-ra'= r(a-a')\in N.$$ Las propiedades que la suma y el producto por escalares deben satisfacer se cumplen obviamente pues se derivan de las correspondientes propiedades de $M$.

Probemos la unicidad. Si $p\colon M\rightarrow M/N$ es un homomorfismo entonces
$$\begin{array}{rcl}
p(a+b)&=&p(a)+p(b),\cr p(ra)&=&rp(a),
\end{array}$$
lo cual equivale a
$$\begin{array}{rcl}
(a+b)+N&=&(a+N)+(b+N),\cr (ra)+N&=&r(a+N).
\end{array}$$

El núcleo de la proyección natural es $$\ker p =\\{a\in M\;|\; p(a)=0\\},$$ pero $p(a)=a+N$ y $a+N=0+N$ si y solo si $a\in N$, luego $\ker p=N$.  
{{% /proof %}}


{{% proposition %}}
Dado un submódulo $N\subset M$ y un homomorfismo $f\colon M\rightarrow P$ tal que $N\subset \ker f$, $f$ factoriza de manera única a través de la proyección natural, es decir existe un único homomorfismo $g\colon M/N\rightarrow P$ tal que $f=g\circ p$, $$f\colon M\stackrel{p}\twoheadrightarrow M/N\stackrel{g}\rightarrow P.$$
{{% /proposition %}}


{{% proof %}}

Si $f=g\circ p$ entonces tendríamos $$f(a)=(g\circ p)(a)=g(p(a))=g(a+N).$$ Definimos la aplicación $g\colon M/N\rightarrow P$ como $$g(a+N)=f(a).$$ Veamos que en efecto está bien definida. La unicidad se seguirá de la primera fórmula.

Si $a+N=a'+N$ entonces $a-a'\in N\subset\ker f$ luego $$0=f(a-a')=f(a)-f(a').$$ Por tanto $$g(a+N)=f(a)=f(a')=g(a'+N).$$ Claramente $g$ es un homomorfismo pues se definie como el homomorfismo $f$ en los representantes.  
{{% /proof %}}


{{% watch %}}
 En la proposición anterior podemos tomar siempre $N=\ker f$. Comprueba que $g$ es inyectivo si y solo si $N=\ker f$. Es más, comprueba que $g$ es un isomorfismo si y solo si $f$ es sobreyectivo y $N=\ker f$. 
{{% /watch %}}


{{% example name="El cociente de un producto por un factor" %}}
Recordemos que dados dos $R$-módulos $M$ y $N$ podemos considerar el $R$-módulos producto $M\times N$ y los homomorfismos de inclusión $i\_1\colon M\rightarrow M\times N$, $i\_1(a)=(a,0)$, y proyección $p\_2\colon M\times N\rightarrow N$, $p\_2(a,b)=b$. El primero es inyectivo y el segundo sobreyectivo. Claramente $\operatorname{im}i\_1=M\times\\{0\\}=\ker p\_2$, por tanto la proposición anterior nos proporciona un isomorfismo $$\frac{M\times N}{M\times\\{0\\}}\cong N.$$ Análogamente podemos obtener un isomorfismo $$\frac{M\times N}{\\{0\\}\times N}\cong M.$$ 
{{% /example %}}


{{% proposition %}}
Dado un $R$-módulo $M$ y un submódulo $N\subset M$, si $N$ y $M/N$ son finitamente generados entonces $M$ también lo es. 
{{% /proposition %}}


{{% proof %}}
Sean $\\{\bar a\_1,\dots,\bar a\_p\\}\subset M/N$ y $\\{b\_1,\dots,b\_q\\}\subset N$ conjuntos de generadores. Veamos que $S=\\{ a\_1,\dots, a\_p,b\_1,\dots,b\_q\\}\subset M$ genera. Dado $x\in M$, consideramos $\bar x\in M/N$ y lo escribimos como combinación lineal de los generadores de $M/N$ con coeficientes en $R$
$$\begin{array}{rcl}\bar x&=&r\_1\bar a\_1+\cdots+r\_p\bar a\_p\cr
&=&\overline{r\_1a\_1+\cdots+r\_pa\_p}.
\end{array}$$
Tenemos entonces que $$x-(r\_1a\_1+\cdots+r\_pa\_p)\in N$$
así que lo podemos escribir como combinación lineal de los geberadores  de $N$ con coeficientes en $R$,
$$x-(r\_1a\_1+\cdots+r\_pa\_p)=s\_1b\_1+\cdots+s\_qb\_q.$$
Despejando vemos que $x$ es combinación lineal de $S$, y por tanto $S$ genera $M$.
  
{{% /proof %}}


{{% corollary %}}
Dado un dominio de ideales principales $R$, todo submódulo de $R^n$ es finitamente generado. 
{{% /corollary %}}


{{% proof %}}

Por inducción en $n$. Para $n=0$ es obvio ya que $R^0=\\{0\\}$. Supongamos que todo submódulo de $R^{n-1}$ es finitamente generado para cierto $n\geq 1$. Sea $M\subset R^n$ un submódulo. Vemos $R^n=R^{n-1}\times R$ y consideramos el homomorfismo de proyección sobre la última coordenada $p=p_2\colon R^n\rightarrow R$. La imagen de la restricción $p\_{|\_{M}}\colon M\rightarrow R$ es un submódulo de $R$, es decir un ideal $(a)\subset R$. Por tanto esta restricción induce un homomorfismo sobreyectivo $p\_{|\_{M}}\colon M\twoheadrightarrow I$ y este induce un isomorfismo
$$\frac{M}{\ker p\_{|\_{M}}}\cong (a).$$ 
El cociente es finitamente generado por serlo $(a)$. El núcleo de $p=p_2\colon R^n\rightarrow R$ es $R^{n-1}\times\\{0\\}\cong R^{n-1}$ así que el $\ker p\_{|\_{M}}\subset R^{n-1}\times\\{0\\}$, que por tanto es finitamente generado por hipótesis de inducción. Usando la proposición anterior vemos que $M$ es también finitamente generado.   
{{% /proof %}}


{{% definition %}}
Un $R$-módulo $M$  es **cíclico** si se puede generar por un solo elemento.
{{% /definition %}}


{{% proposition %}}
Un $R$-módulo $M$ es cíclico $\Leftrightarrow$ $M\cong R/I$ para algún ideal $I\subset R$. 
{{% /proposition %}}


{{% proof %}}
 
$\Leftarrow$ El módulo $R/I$ es cíclico pues $\\{\\bar 1\\}\subset R/I$ genera, así que cualquier módulo isomorfo a $R/I$ será también cíclico. 

$\Rightarrow$ Sea $\\{a\\}\subset M$ un generador. El homomorfismo $\phi\_{\\{a\\}}\colon R\rightarrow M$ que envía $1\mapsto a$ es por tanto sobreyectivo, así que $R/\ker \phi\_{\\{a\\}}\cong M$, con lo que podemos tomar $I=\ker \phi\_{\\{a\\}}$.   
{{% /proof %}}


## Generadores y relaciones

Supongamos que deseamos construir un $\mathbb Z$-módulo $M$ generado por tres elementos $\\{a\_1,a\_2,a\_3\\}\subset M$ que satisfagan las siguientes ecuaciones (relaciones):
$$\begin{array}{rcrcrcl}
3a\_1&+&2a\_2&+&a\_3&=&0,\cr
8a\_1&+&4a\_2&+&2a\_3&=&0,\cr
7a\_1&+&6a\_2&+&2a\_3&=&0,\cr
9a\_1&+&6a\_2&+&a\_3&=&0.
\end{array}$$
¿Cómo hacerlo? Las relaciones anteriores pueden ser codificadas en una matriz
$$A=\left(\begin{array}{cccc}
3&8&7&9\cr
2&4&6&6\cr
1&2&2&1
\end{array}\right).$$
Esta matriz define un homomorfismo
$$\mathbb{Z}^4\stackrel{A}\longrightarrow \mathbb{Z}^3$$
Veamos que el cociente $$M=\frac{\mathbb{Z}^3}{\operatorname{im}A}$$
satisface las condiciones deseadas. En efecto, está generado por las clases de los generadores de $\mathbb{Z}^3$,
$$\begin{array}{rcl}
a\_1&=&\bar{e}\_1,\cr
a\_2&=&\bar{e}\_2,\cr
a\_3&=&\bar{e}\_3.
\end{array}$$
Además $\operatorname{im}A$ está generado por las imágenes de los generadores de $\mathbb{Z}^4$,
$$\begin{array}{rcrcrcr}
Ae\_1&=&3e\_1&+&2e\_2&+&e\_3,\cr
Ae\_2&=&8e\_1&+&4e\_2&+&2e\_3,\cr
Ae\_3&=&7e\_1&+&6e\_2&+&2e\_3,\cr
Ae\_4&=&9e\_1&+&6e\_2&+&e\_3,
\end{array}$$
cuyas clases en el cociente se anulan, lo cual equivale a las ecuaciones del principio. Más aún, esta construcción es universal ya que, por la proposición de factorización de homomofismos a través de cocientes, dado un $\mathbb Z$-módulo $N$ y tres elementos $\\{b\_1,b\_2,b\_3\\}\subset N$ que satisfacen las ecuaciones 
$$\begin{array}{rcrcrcl}
3b\_1&+&2b\_2&+&b\_3&=&0,\cr
8b\_1&+&4b\_2&+&2b\_3&=&0,\cr
7b\_1&+&6b\_2&+&2b\_3&=&0,\cr
9b\_1&+&6b\_2&+&b\_3&=&0,
\end{array}$$
existe un único homomorfismo
$$g\colon M\longrightarrow N$$
que satisface 
$$\begin{array}{rcl}
g(a\_1)&=&b\_1,\cr
g(a\_2)&=&b\_2,\cr
g(a\_3)&=&b\_3.
\end{array}$$
Este homomorfismo es la factorización de $\phi_{\\{b\_1,b\_2,b\_3\\}}\colon\mathbb{Z}^3\rightarrow N$ a través de la proyección natural al cociente $M=\mathbb{Z}^3/\operatorname{im}A$.

Esta construcción se puede generalizar de manera obvia del siguiente modo. Dado un anillo cualquiera $R$, queremos construir un $R$-módulo $M$ con *generadores* $\\{a\_1,\dots,a\_m\\}\subset M$ donde se satisfagan las ecuaciones (*relaciones*)
$$r\_{1j}a\_1+\cdots+r\_{mj}a\_m=0,\quad 1\leq j\leq n,$$
donde $r\_{ij}\in R$, $1\leq i\leq m$, $1\leq j\leq n$. Estas relaciones están determinadas por la matriz $A=(r\_{ij})$, que define un homomorfismo
$$R^n\stackrel{A}\longrightarrow R^m.$$
Podemos tomar $$M=\frac{R^m}{\operatorname{im}A}$$
ya que las clases de los generadores de $R^m$ generan $M$,
$$a\_i=\bar{e}\_i,\quad 1\leq i\leq m,$$
y las imágenes de los generadores de $R^n$ generan $\operatorname{im}A$,
$$Ae\_j=r\_{1j}e\_1+\cdots+r\_{mj}e\_m,\quad 1\leq j\leq n.$$
Estos últimos elementos se anulan en el cociente, lo cual equivale a las ecuaciones del principio. Esta construcción es universal en virtud de la proposición de factorización de homomorfismos a través de cocientes, ya que dado un $R$-módulo $N$ y elementos $\\{b\_1,\dots,b\_m\\}\subset N$ que satisfacen 
$$r\_{1j}b\_1+\cdots+r\_{mj}b\_m=0,\quad 1\leq j\leq n,$$
existe un único homomorfismo
$$g\colon M\longrightarrow N$$
que satisface 
$$g(a\_i)=b\_i,\quad 1\leq i\leq m,$$
que es la factorización de $\phi_{\\{b\_1,\dots,b\_m\\}}\colon R^m\rightarrow N$ a través de la proyección natural al cociente $M=R^m/\operatorname{im}A$.

{{% definition %}}
Una **presentación** de un $R$-módulo $M$ consiste en dos homomorfismos $$R^n\stackrel{A}\longrightarrow R^m\stackrel{f}\twoheadrightarrow M$$ tales que $f$ es sobreyectivo e $\operatorname{im} A=\ker f$. Esto, en virtud de la proposición de factorización de homomorfismos a través de cocientes, equivale a dar un isomorfismo $$g\colon \frac{R^n}{\operatorname{im} A}\stackrel{\cong}\longrightarrow M.$$ Decimos que un módulo es **finitamente presentado** si admite una presentación como esta. 
{{% /definition %}}


{{% watch %}}
 El $R$-módulo $M$ está generado por $\\{f(e\_1),\dots,f(e\_m)\\}\subset M$, que satisfacen las relaciones determinadas por la matriz $A$. 
{{% /watch %}}



{{% proposition %}}
Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ admite una presentación. 
{{% /proposition %}}


{{% proof %}}
 Sea $S=\\{a\_1,\dots,a\_m\\}\subset M$ un conjunto de generadores. Por serlo, el homomorfismo $\phi\_S\colon R^m\rightarrow M$ es sobreyectivo, así que $$\frac{R^m}{\ker\phi\_{S}}\cong M.$$ Según hemos visto anteriormente, el submódulo $\ker \phi\_S\subset R^n$ es finitamente generado. Escogemos un conjunto de generadores $S'=\\{b\_1,\dots,b\_n\\}\subset \ker \phi\_{S}$, que por tanto inducen otro homomorfismo sobreyectivo $\phi\_{S'}\colon R^n\rightarrow \ker \phi\_{S}$. Consideramos su composición con la inclusión, $$A\colon R^n\stackrel{\phi\_{S'}}\twoheadrightarrow \ker \phi\_S\hookrightarrow R^m,$$ que estará definida por una matriz $A$. Al ser $\phi\_{S'}$ sobreyectiva, $\operatorname{im}A=\ker \phi\_{S}$, con lo que $A$ es una presentación de $M$.
{{% /proof %}}


Una presentación de un módulo se puede modificar y simplificar de los siguientes modos.

{{% proposition %}}
Si el $R$-módulo $M$ está presentado por la matriz $A$ de tamaño $m\times n$ entonces también está presentado por la matriz $A'$ en los siguientes casos: 

* Si $A'=QAP^{-1}$ siendo $P$ y $Q$ matrices invertibles.

* Si $A$ se obtienen a partir de $A$ eliminando una columna de ceros.

* Si la $j$-ésima columna de $A$ es $e_i$ y $A'$ se obtiene borrando la $i$-ésima fila y la $j$-ésima columna de $A$.


{{% /proposition %}}


{{% proof %}}
 
* Las matrices invertibles $P$ y $Q$ se corresponden con meros cambios de base en $R^m$ y $R^n$, respectivamente, con lo cual tenemos un isomorfismo $$\begin{array}{rcl}
R^m/\operatorname{im}A&\stackrel{\cong}\longrightarrow& R^m/\operatorname{im}A'\cr x&\mapsto& Qx.\end{array}$$

* Una columna de ceros se corresponde con la relación $0=0$, que no aporta nada, con lo cual puede eliminarse.

* En este caso la $j$-ésima columna se corresponde con la relación $a\_i=0$, así que podemos simplemente eliminar $a\_i$ de la lista de generadores y $a\_i=0$ de la de relaciones. Esto se corresponde con la eliminación de la $i$-ésima fila y la $j$-ésima columna de $A$.
{{% /proof %}}


Cuando una matriz es especialmente sencilla resulta fácil identificar el módulo que presenta.

{{% proposition %}}
El $R$-módulo presentado por la matriz $$A=\left( \begin{array}{ccc} d\_1&&\cr &\ddots&\cr &&d\_n\cr \hline &0& \end{array} \right)$$ de tamaño $m\times n$ con una caja superior diagonal de tamaño $n\times n$ y una caja inferior trivial de tamaño $(m-n)\times n$, es isomorfo a $$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{m-n}.$$ 
{{% /proposition %}}


{{% proof %}}
 Es obvio, ya que este módulo está generado por $\\{a\_1,\dots,a\_n\\}$, donde $a\_i=\bar e\_i$, y las relaciones correspondientes a la matriz $A$ son $$d\_ia\_i=0,\quad 1\leq i\leq n.$$ Por tanto la $i$-ésima coordenada se está considerando módulo $d\_i$, $1\leq i\leq n$, y en el resto no hay relaciones.
{{% /proof %}}



## Forma normal de Smith

En esta sección veremos cómo la matriz de una presentación de un módulo se puede simplificar mediante operaciones elementales.

{{% definition %}}
Las **operaciones elementales por filas** para matrices con entradas en un anillo $R$ son las siguientes:

1. Añadirle a una fila un múltiplo de otra, $F\_i+rF\_j$, $i\neq j$, $r\in R$.

2. Intercambiar dos filas $F\_i\leftrightarrow F\_j$, $i\neq j$.

3. Multiplicar una fila por una unidad $u\in R^\times$, $uF\_i$ .

Las **operaciones elementales por columnas** se definen análogamente.

{{% /definition %}}


Las operaciones elementales anteriores se corresponden con el producto por los siguientes tipos de matrices.

{{% definition %}}
Las **matrices elementales** son las que se obtienen a partir de la identidad realizando una de las operaciones elementales por filas anteriores. Concretamente:

1. $E_{ij}( r )=\left(\begin{array}{ccccccc}1&&&&&&\cr &\ddots&&&&&\cr &&1&\cdots&r&&\cr &&&\ddots&\vdots&&\cr &&&&1&&\cr &&&&&\ddots&\cr &&&&&&1\end{array}\right)$.

2. $E_{ij}=\left(\begin{array}{ccccccc}1&&&&&&\cr &\ddots&&&&&\cr &&0&\cdots&1&&\cr &&\vdots&\ddots&\vdots&&\cr &&1&\cdots&0&&\cr &&&&&\ddots&\cr &&&&&&1\end{array}\right)$.

3. $E_{ii}(u)=\left(\begin{array}{ccccccc}1&&&&&&\cr &\ddots&&&&&\cr &&1&&&&\cr &&&u&&&\cr &&&&1&&\cr &&&&&\ddots&\cr &&&&&&1\end{array}\right)$.

{{% /definition %}}


{{% watch %}}
 Las matrices elementales son invertibles, concretamente:

1. $E\_{ij}( r )^{-1}=E\_{ij}(-r)$.

2. $E\_{ij}^{-1}=E\_{ij}$.

3. $E\_{ii}(u)^{-1}=E\_{ii}(u^{-1})$.

Sus determinantes son
$$\begin{array}{rcl}
|E\_{ij}( r )|&=&1,\cr
|E\_{ij}|&=&-1,\cr
|E\_{ii}(u)|&=&u.
\end{array}$$

Las operaciones elementales por filas y columnas se corresponden con los productos por matrices elementales a izquierda y derecha, respectivamente: 
$$\begin{array}{rclrcl}
A&\stackrel{F\_i+rF\_j}\longrightarrow& E\_{ij}( r )A,& A&\stackrel{C\_i+rC\_j}\longrightarrow& AE\_{ji}( r ),\cr
A&\stackrel{F\_i\leftrightarrow F\_j}\longrightarrow &E\_{ij}A=A,&  A&\stackrel{C\_i\leftrightarrow C\_j}\longrightarrow& AE\_{ij},\cr
A&\stackrel{uF\_i}\longrightarrow& E\_{ii}(u)A,& A&\stackrel{uC\_i}\longrightarrow& AE\_{ii}(u).
\end{array}$$

Por tanto, si $A'$ se obtiene a partir de $A$ a través de operaciones elementales por filas y columnas, entonces existen matrices invertibles $P$ y $Q$ tales que $$A'=QAP^{-1}.$$
En particular $A$ y $A'$ presentan el mismo módulo.

También deducimos que el determinante de una matriz no varía cuando se realiza una operación elemental de tipo 1, cambia de signo al hacer una operación elemental de tipo 2, y pasa a ser un asociado al realizar una operación elemental de tipo 3.

{{% /watch %}}



{{% theorem name="Forma normal de Smith" %}}
Dada una matriz $A$ sobre un dominio euclídeo $R$, existen matrices invertibles $P$ y $Q$, que son productos de matrices elementales, tales que $$QAP^{-1}=D=\left( \begin{array}{ccc|c} d\_1&&&\cr &\ddots&&0\cr &&d\_k&\cr \hline &0&&0 \end{array} \right)$$ es una matriz con una descomposición de tamaño $2\times 2$ por cajas cuya única caja no trivial es la superior izquierda, que es diagonal con entradas diagonales no nulas y satisface $d\_i|d\_{i+1}$ para todo $1\leq i {<} k$. Esta matriz $D$ se denomina **forma normal de Smith** de $A$. <!--- el número $k$ de entradas no nulas es único y los $d_i$ son únicos salvo asociados. --> 
{{% /theorem %}}


{{% proof %}}
  La estrategia para probar la existencia consiste en aplicarle a $A$ una serie de operaciones elementales para llegar a una matriz de la forma 
$$\left(\begin{array}{c|c}
d_1&0\cr \hline 0&B
\end{array}\right)$$
donde $d_1$ divide a todas las entradas de $B$. Una vez hecho esto, pasamos a trabajar del mismo modo con la matriz $B$. De este modo obtenemos el resultado por inducción ya que si un elemento de $R$ divide a todas las entradas de una matriz $B$ entonces también divide a una matriz obtenida a partir de $B$ mediante una operación elemental.

Para llegar a una matriz como la anterior a partir de $A$ aplicamos el siguiente procedimiento:

1. Permutando filas y columnas, mueve la entrada no nula de menor tamaño a la esquina superior izquierda.

2. Dada una entrada no nula de la primera columna $a\_{i1}$, $i>1$, realiza la división euclídea $a\_{i1}=c\cdot a\_{11}+r$ y la operación $F\_{i}-c\cdot F\_1$. La entrada $(i,1)$ de la nueva matriz es el resto $r$. Si este resto es no nulo entonces tiene tamaño menor que $a\_{11}$, así que volvermos al paso 1. Si no, continuamos con otra entrada no nula de la primera columna. Si el resto de entradas de la primera columna son $0$, pasamos a hacer lo análogo con la primera fila, es decir, buscamos una entrada $a\_{1j}$ no nula, $j>1$, realizamos la división euclídea $a\_{1j}=c\cdot a\_{11}+r$ y la operación $C\_{j}-c\cdot C\_1$. La entrada $(1,j)$ de la nueva matriz es el resto $r$. Si este resto no es nulo entonces tiene tamaño menor que el de $a\_{11}$ y pasamos al paso 1. Si no, realizamos el mismo procedimiento con otra entrada no nula de la primera fila.

3. Si hemos llegado hasta aquí es porque el único elemento no nulo de la primera fila y de la primera columna es el $a\_{11}$. Si hay algún elemento no nulo $a\_{ij}$ que no es divisible por $a\_{11}$ realizamos la operación $F\_{1}+F\_{i}$. La matriz resultante tiene el mismo $a\_{11}$, pero en la entrada $(1,j)$ nos encontramos con $a\_{ij}$, que no es múltiplo de $a\_{11}$, así que volvemos al paso 2. (También podríamos hacer la operación $C\_{1}+C\_{j}$ y pasar al paso 2.)

4. Llegados a este punto, nuestra matriz es de la forma $$\left(\begin{array}{c|c}
d_1&0\cr \hline 0&B
\end{array}\right)$$
y $d_1$ divide a todas las entradas de $B$.

Este procedimiento termina porque cada vez que realizamos una división euclídea, el mínimo de los tamaños de los elementos no nulos disminuye. Como este número es un entero no negativo, no puede disminuir indefinidamente, así que no podemos entrar en ningún blucle infinito.

Este método para llegar a la forma normal de Smith se conoce como  **algoritmo de diagonalización** de matrices con entradas en $R$.

<!--- La unicidad de la forma normal de Smith se observa del siguiente modo. Si $d$ divide a todas las entradas de una matriz $A$ entonces también dividirá a todas las entradas de cualquier otra matriz obtenida a partir de $A$ mediante una operación elemental. Las operaciones elementales son reversibles, por tanto el divisor máximo común de las entradas de una matriz no varía al realizar operaciones elementales. La forma normal de Smith se obtiene a partir de $A$ mediante operaciones elementales y el divisor máximo común de sus entradas es $d\_1$, por tanto $d\_1$ también es el divisor máximo común de las entradas de $A$, que es único salvo asociados.

Un **menor** de orden $r$ de una matriz $m\times n$ es el determinante de una submatriz de tamaño $r\times r$, 
$$\left|\begin{array}{ccc}
a\_{i\_1j\_1}&\cdots & a\_{i\_1j\_r}\cr
\vdots&\ddots&\vdots\cr
a\_{i\_rj\_1}&\cdots & a\_{i\_rj\_r}
\end{array}\right|,\qquad 1\leq i\_1{<}\cdots{<}i\_r\leq m,\quad 1\leq j\_1{<}\cdots{<}j	\_r\leq n.$$
Los menores de orden $1$ son simplemente las entradas de la matriz. El razonamiento anterior es igualmente cierto si reemplazamos entradas por menores, es decir, el divisor máximo común de los menores de orden $r$ no varía al hacer operaciones elementales. Para la forma normal de Smith, dicho divisor máximo común es $d\_1\cdots d\_r$ si $1\leq r\leq k$ y $0$ si $r>k$. De aquí se deduce la unicidad de $k$ y de los $d\_i$ salvo asociados. -->

  
{{% /proof %}}


{{% watch %}}
 El teorema anterior es cierto más generalmente para dominios de ideales principales. La demostración es análoga pero hace uso de la identidad de Bézout en lugar de la división euclídea y de un tipo más general de operación elemental. La forma normal de Smith es única salvo asociados, aunque no lo hemos probado. <!--- Si $R=\mathbb Z$ hay una única forma normal de Smith que donde todos los $d\_i$ son positivos, ya que todo entero no nulo es asociado de un único entero positivo. A esta forma normal de Smith se que llega usando también operaciones elementales de tipo $3$. Análogamente, si $R=k[x]$, con $k$ un cuerpo, hay una única forma normal de Smith que donde todos los polinomios $d\_i$ son mónicos. -->
{{% /watch %}}



{{% corollary %}}
 Toda matriz invertible con entradas en un dominio euclídeo es producto de matrices elementales. 
{{% /corollary %}}


{{% proof %}}
 El determinante de una matriz $A$ de tamaño $n\times n$ es asociado del determinante de cualquier otra matriz que se obtenga a partir de $A$ tras realizar una operación elemental. En particular, $|A|$ es asociado del determinante de su forma normal de Smith $D$. El determinante $|D|$ es $0$ si $k{<}n$ y $d\_1\cdots d\_n$ si $k=n$. Si $A$ es invertible entonces $|A|$ es una unidad, luego necesariamente $k=n$ y $d\_1\cdots d\_n$ también es una unidad. En particular todos los $d_i$ son unidades, es decir, la forma normal de Smith es un producto de matrices elementales tipo 3, $D=E\_{11}(d\_1)\cdots E\_{nn}(d\_n)$. Despejando $A=Q^{-1}DP$ vemos que $A$ es producto de matrices elementales.
{{% /proof %}}


{{% corollary %}}
 Dado un dominio de ideales principales $R$, todo submódulo de $R^m$ es libre y de rango $\leq m$. 
{{% /corollary %}}


{{% proof %}}
 Sea $M\subset R^m$ un submódulo. Al demostrar que todo $R$-módulo finitamente generado es finitamente presentado vimos que se puede suponer sin pérdida de generalidad que $M=\operatorname{im}A$ para cierto homomorfismo $A\colon R^n\rightarrow R^m$ (matriz). El $R$-módulo $M$ está pues generado por las columnas de $A$. Haciendo un cambio de base si fuera necesario podemos suponer que $A$ está en forma normal de Smith, como $D$ en el teorema anterior. Claramente las primeras $k$ columnas de $A=D$ son suficientes para generar $M$ y además son linealmente independientes, por tanto forman una base y $M$ es libre. Además $k\leq m$.
{{% /proof %}}


## Teoremas de estructura

Veamos que sobre un dominio de ideales principales todo módulo finitamente generado se descompone salvo isomorfismo como producto de módulos cíclicos.

{{% theorem name="Estructura de módulos finitamente generados sobre un DIP" %}}

Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ es isomorfo a uno de la forma $$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}$$ donde $d\_1,\dots,d\_n\in R$ no son cero ni unidades y satisfacen $d\_i|d\_{i+1}$, $1\leq i{<}n$. <!--- Además los enteros $k,r\geq 0$ son únicos y los $d_i$ son únicos salvo asociados. -->

{{% /theorem %}}


{{% proof %}}
 
Sea $A$ es una presentación de $M$. Su forma normal de Smith $D$ también presenta $M$. Podemos eliminar las columnas de ceros. Algún $d\_i$ podría ser una unidad (los anteriores también tendrían que serlo, pues lo dividen). Podemos suponer sin pérdida de generalidad que este elemento es $d\_i=1$, multiplicando por una matriz elemental tipo 3 si fuera necesario, así que podemos eliminar la $i$-ésima fila y la $i$-ésima columna. De este modo acabamos con una matriz $$\left( \begin{array}{ccc} d\_1&&\cr &\ddots&\cr &&d\_n\cr \hline &0& \end{array} \right)$$ donde los $d\_i$ no son nulos ni unidades, y además satisfacen $d\_i|d\_{i+1}$, $1\leq i{<}n$. 

{{% /proof %}}


La descomposición anterior de un $R$-módulo $M$ como producto de $R$-módulos cíclicos se puede agrupar en dos factores, la **parte libre** y la **parte de torsión**,
$$\underbrace{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}}\_{\text{parte de torsión}}\times \underbrace{R^{r}}\_{\text{parte libre}}.$$
Como los isomorfismos preservan la torsión, la parte de torsión es isomorfa a $T(M)$. El siguiente resultado demuestra que el rango de la parte libre solo depende del módulo $M$, no de la descomposición escogida.

{{% corollary %}}
 Si $M$ es un módulo finitamente generado sobre un dominio de ideales principales, el cociente $M/T(M)$ es libre. 
{{% /corollary %}}


{{% proof %}}
 Como los isomorfismos preservan la torsión, basta probarlo para un producto como el de la proposición anterior. En ese caso $$T\left(\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}\right)=\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times \\{0\\},$$ por lo tanto $$\begin{array}{rcl}
\frac{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}}{T\left(\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}\right)}&\cong& \frac{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}}{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times\\{0\\}}\cr
&=&R^r.
\end{array}$$    {{% /proof %}}


{{% watch %}}
 Los $d_i$ del teorema de estructura también son únicos salvo asociados. Esto es cierto en general pero aquí nos limitaremos a probarlo más abajo para $R=\mathbb{Z}$ y a esbozarlo para $R=k[x]$ con $k$ un cuerpo. 
{{% /watch %}}



{{% example name="Teorema chino del resto" %}}
 Si $R$ es un DIP y $\operatorname{mcd}(a,b)=1$ entonces tenemos un isomorfismo $$\begin{array}{rcl}g\colon \frac{R}{(ab)}&\stackrel{\cong}\longrightarrow&\frac{R}{(a)}\times \frac{R}{(b)},\cr(\bar r)&\mapsto &(\bar r,\bar r).\end{array}$$
{{% /example %}}


{{% proof %}}
Consideramos el homomorfismo de $R$-módulos $$f=\phi\_{\\{(\bar 1,\bar 1)\\}}\colon R\longrightarrow\frac{R}{(a)}\times \frac{R}{(b)}$$ definido por $f(1)=(\bar 1,\bar 1)$. Veamos que $\ker f=(ab)$.  En efecto $ab\in\ker f$ ya que $ab\equiv 0$ módulo $(a)$ y módulo $(b)$. Recíprocamente, si $f( r )=(\bar r,\bar r)=(\bar 0,\bar 0)$, es decir si $r\equiv 0$  módulo $(a)$ y módulo $(b)$, entonces $a|r$ y $b|r$ luego $ab=\operatorname{mcm}(a,b)|r$, esto es $r\in (ab)$. Esto nos prueba que el homomorfismo $g$ del enunciado está bien definido y es inyectivo. Para terminar de ver que es un isomorfismo hemos de comprobar que $f$ es sobreyectivo. Esto equivale a resolver el sistema de ecuaciones $$\left\\{\begin{array}{rcl}x&\equiv& c\mod (a),\cr x&\equiv& d\mod (b),\end{array}\right.$$ para $c,d\in R$ cualesquiera. Tomamos una identidad de Bézout $sa+tb=1$ y observamos que $x=sad+tbc$ resuelve la ecuación.
{{% /proof %}}


{{% theorem name="2ª forma del teorema de estructura" %}}
Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ es isomorfo a uno de la forma $$\frac{R}{(p\_1^{m\_1})}\times \cdots \times\frac{R}{(p\_n^{m\_n})}\times R^{r}$$ donde $p\_1,\dots,p\_n\in R$ son primos y $r\_i\geq 1$.
{{% /theorem %}}


{{% proof %}}
 Es consecuencia de la primera forma del teorema de estructura y del teorema chino del resto, el cual permite probar por inducción que si $q\_{1}^{s\_1}\cdots q\_{t}^{s\_t}$ es un producto de potencias de primos no asociados entonces $$\frac{R}{(q\_{1}^{s\_1}\cdots q\_{t}^{s\_t})}\cong \frac{R}{(q\_{1}^{s\_1})}\times\cdots\times \frac{R}{(q\_{t}^{s\_t})}.$$  
{{% /proof %}}


{{% watch %}}
 Las dos formas del teorema de estructura de módulos finitamente generados sobre un DIP son de hecho equivalentes. 
{{% /watch %}}


{{% example name="Grupos abelianos con el mismo número de elementos" %}}
 Los grupos abelianos $$\mathbb{Z}/(4)\times \mathbb{Z}/(4),\qquad\mathbb{Z}/(2)\times \mathbb{Z}/(2)\times \mathbb{Z}/(4),$$ tienen $16$ elementos, pues $4\cdot 4=16=2\cdot 2\cdot 4$, luego existe una biyección entre ambos. Veamos que, a pesar de ello, no son isomorfos. Para verlo jugaremos con la noción de **orden** de un elemento de torsión $a\in A$ de un grupo abeliano $A$, que es el menor entero positivo $n\in\mathbb Z$ tal que $na=0$. El $0\in A$ es el único elemento de orden $1$. Si $A$ es finito, el orden de cualquier $a\in A$ divide al número de elementos de $A$ (este número se conoce como orden de $A$). En particular, todo elemento de $\mathbb Z/(m)$ tiene un orden divisor de $m$. El orden de $-a\in A$ coincide con el de $a\in A$ y el orden de la suma de dos elementos de torsión $a+b\in A$ divide al múltiplo común mínimo de los órdenes de los factores. En particular, para cada entero $n$ el subconjunto $T\_n(A)\subset A$ formado por los elementos cuyo orden divide a $n$ es un subgrupo. Denotaremos $t\_n(A)$ al orden de $T_n(A)$. Además $T\_n(A\times B)=T\_n(A)\times T\_n(B)$, luego $t\_n(A\times B)=t\_n(A)t\_n(B)$, y si $A\cong B$ entonces $T\_n(A)\cong T\_n(B)$, por tanto $t\_n(A)=t\_n(B)$. El orden de $\bar a\in\mathbb Z/(m)$ es $m/\operatorname{mcd}(a,m)$ si $m\neq 0$. Usando esto podemos comprobar que, si $d=\operatorname{mcd}(m,n)$, $$T\_n(\mathbb{Z}/(m))=\left\\{1\cdot\overline{\frac{m}{d}},\dots,(d-1)\cdot \overline{\frac{m}{d}}\right\\}$$ luego $$t\_n(\mathbb{Z}/(m))=\operatorname{mcd}(n,m).$$ Aplicando esto a los dos grupos del principio, vemos que el primero cumple $$t\_2(\mathbb{Z}/(4)\times \mathbb{Z}/(4))=2\cdot 2=4,$$ mientras que el segundo satisface $$t\_2(\mathbb{Z}/(2)\times \mathbb{Z}/(2)\times \mathbb{Z}/(4))=2\cdot 2\cdot 2=8,$$ con lo cual no pueden ser isomorfos.
{{% /example %}}


{{% theorem name="Unicidad en el teorema de estructura" %}}
 La descomposición de un $\mathbb Z$-módulo finitamente generado $M$ dada por cualquiera de las dos formas del teorema de estructura es única. 
{{% /theorem %}}


{{% proof %}}
 Basta verlo para una de las dos formas, pues son equivalentes. Consideremos la primera. Ya hemos visto que el valor de $r\geq 0$ estaba determinado por $M$. Como los isomorfismos preservan la torsión, solo nos queda ver que si $$A=\frac{\mathbb Z}{(d\_1)}\times \cdots \times\frac{\mathbb Z}{(d\_n)}\cong \frac{\mathbb Z}{(e\_1)}\times \cdots \times\frac{\mathbb Z}{(e\_m)}=B,$$ donde los $d\_i$ y los $e\_j$ no son nulos ni unidades y satisfacen $d\_i|d\_{i+1}$ y $e\_j|e\_{j+1}$, entonces $n=m$ y cada $d\_i$ es asociado de $e\_i$. Podemos suponer sin pérdida de generalidad que los $d\_i$ y los $e\_j$ son positivos. Como ambos grupos son finitos y tienen el mismo orden, $$d\_1\cdots d\_n=e\_1\cdots e\_m.$$

En $A$, el orden de cualquier elemento divide a $d\_n$, y en $B$ a $e\_m$. Ambos grupos son isomorfos, por tanto el orden de cualquier elemento de $A$ o de $B$ divide a $d\_n$ y a $e\_m$. En $A$ hay un elemento de orden $d\_n$, el $(\bar 0,\dots,\bar 0,\bar 1)$, por tanto $d\_n|e\_m$. En $B$ hay otro con orden $e\_m$, por tanto $e\_m|d\_n$, así que $d\_n=e\_m$. De aquí deducimos también que $$d\_1\cdots d\_{n-1}=e\_1\cdots e\_{m-1}.$$

Demostremos ahora que $d\_{n-1}=e\_{m-1}$. Por un lado, 
$$t\_{d\_{n-1}}(A)=d\_1\cdots d\_{n-2}\cdot d\_{n-1}^2$$
y por otro
$$\begin{array}{rcl}
t\_{d\_{n-1}}(B)&=&\operatorname{mcd}(d\_{n-1},e\_1)\cdots\operatorname{mcd}(d\_{n-1},e\_{m-1})\operatorname{mcd}(d\_{n-1},e\_{m})\cr
&=&\frac{d\_{n-1}e\_1}{\operatorname{mcm}(d\_{n-1},e\_1)}\cdots\frac{d\_{n-1}e\_{m-1}}{\operatorname{mcm}(d\_{n-1},e\_{m-1})}d\_{n-1}\cr
&=&\frac{e\_1\cdots e\_{m-1}d\_{n-1}^m}{\operatorname{mcm}(d\_{n-1},e\_1)\cdots\operatorname{mcm}(d\_{n-1},e\_{m-1})}\cr
&=&\frac{d\_1\cdots d\_{n-2}\cdot d\_{n-1}^{m+1}}{\operatorname{mcm}(d\_{n-1},e\_1)\cdots\operatorname{mcm}(d\_{n-1},e\_{m-1})}.
\end{array}$$
Como necesariamente $t\_{d\_{n-1}}(A)=t\_{d\_{n-1}}(B)$ deducimos que 
$$d\_{n-1}^{m-1}=\operatorname{mcm}(d\_{n-1},e\_1)\cdots\operatorname{mcm}(d\_{n-1},e\_{m-1}).$$
Pero $d\_{n-1}|\operatorname{mcm}(d\_{n-1},e\_{j})$ para todo $1\leq j\leq m-1$, así que la única posibilidad de que ambos productos coincidan es que en todos los casos $d\_{n-1}=\operatorname{mcm}(d\_{n-1},e\_{j})$, es decir $e\_j|d\_{n-1}$. Los papeles de $A$ y $B$, y en particular los de los $d\_i$ y los $e\_j$, son intercambiables, así que también concluimos que $d\_i|e\_{m-1}$ para todo $1\leq i\leq n-1$. En particular $e\_{m-1}|d\_{n-1}$ y $d\_{n-1}|e\_{m-1}$, por tanto $d\_{n-1}=e\_{m-1}$ y deducimos también que $$d\_1\cdots d\_{n-2}=e\_1\cdots e\_{m-2}.$$ 

Este argumento se puede iterar, probando así que los últimos $d\_i$ coinciden con los últimos $e\_j$. Veamos por reducción al absurdo que $n=m$, con lo cual $d\_i=e\_i$ para todo $1\leq i\leq n$. Si $n\neq m$ podemos suponer sin pérdida de generalidad que $n{<}m$. En ese caso acabaríamos probando que $1=e\_1\cdots e\_{m-n}$, pero esto implicaría que estos primeros $e\_j$ son unidades, lo cual sería una contradicción.
 {{% /proof %}}


{{% example name="$k[x]$-módulos de torsión con la misma dimensión" %}}
 Si $p(x)\in k[x]$ tiene grado $n$, el cociente $k[x]/(p(x))$ tiene dimensión $n$ como $k$-espacio vectorial pues $\\{1,\dots,\bar x^{n-1}\\}$ es una base. Por tanto los $k[x]$-módulos $$\frac{k[x]}{(x^2)}\times \frac{k[x]}{(x^2)},\qquad \frac{k[x]}{(x)}\times \frac{k[x]}{(x)}\times \frac{k[x]}{(x^2)}$$ tienen dimensión $2+2=4=1+1+2$, así que son isomorfos como $k$-espacios vectoriales, pero no como $k[x]$-módulos. En efecto, para verlo, podemos razonar con de **orden** de un elemento de torsión $a\in M$ de un $k[x]$-módulo $M$, que es el polinomio mónico $p(x)\in k[x]$ de menor grado tal que $p(x)\cdot a=0$. Esta noción de orden satisface propiedades formales similares a las de grupos abelianos. Los números relevantes aquí son los $t\_{p(x)}(M)$, que es la dimensión como $k$-espacio vectorial del submódulo $T\_{p(x)}(M)$ formado por los elementos de orden que divide a $p(x)\in k[x]$. En este caso $t\_{p(x)}(M\times N)=t\_{p(x)}(M)+ t\_{p(x)}(N)$ pues la dimensión de un producto de espacios vectoriales es la suma de las dimensiones de los factores. Además $t\_{p(x)}(k[x]/(q(x)))$ es el grado de $\operatorname{mcd}(p(x),q(x))$. Los dos $k[x]$-módulos anteriores no pueden ser isomorfos porque $$\begin{array}{rcl} t\_{x}\left(\frac{k[x]}{(x^2)}\times \frac{k[x]}{(x^2)}\right)&=&1+1=2,\cr t\_{x}\left(\frac{k[x]}{(x)}\times \frac{k[x]}{(x)}\times \frac{k[x]}{(x^2)}\right)&=&1+1+1=3. \end{array}$$ La demostración de la unicidad de las descomposicións de los teoremas de estructura de $R$-módulos finitamente generados para $R=k[x]$ es análoga al caso de $R=\mathbb Z$, usando para $R=k[x]$ los números $t\_{p(x)}(M)$ y el orden de un $k[x]$-módulo $M$ de torsión $M=T(M)$, que es simplemente su dimensión como $k$-espacio vectorial. La dejamos como ejercicio. 
{{% /example %}}


## Sistemas de ecuaciones lineales diofánticas

Consideramos un sistema de $m$ ecuaciones lineales con $n$ incógnitas y coeficientes y términos independientes enteros,
$$\left\\{
\begin{array}{ccl}
a\_{11}x\_1+\cdots+a\_{1n}x\_n&=&b\_1,\cr \vdots&&\vdots \cr
a\_{m1}x\_1+\cdots+a\_{mn}x\_n&=&b\_m.
\end{array}
\right.$$
Estamos interesados en hallar las soluciones enteras, es decir, lo consideramos como un sistema de ecuaciones diofánticas.

Si llamamos $$\begin{array}{ccc}A=
\left(\begin{array}{ccc}a\_{11}&\cdots&a\_{1n}\cr\vdots&&\vdots\cr a\_{m1}&\cdots&a\_{mn}\end{array}\right)
,&\vec{x}=\left(\begin{array}{c}x\_1\cr\vdots\cr x\_n\end{array}\right),
&\vec{b}=\left(\begin{array}{c}b\_1\cr\vdots\cr b\_m\end{array}\right)\end{array},$$
podemos expresar el sistema simplemente como
$$A\vec{x}=\vec{b}.$$

Si $A$ está en forma normal de Smith,
$$A=D=\left( \begin{array}{ccc|c} d\_1&&&\cr &\ddots&&0\cr &&d\_k&\cr \hline &0&&0 \end{array} \right)$$
el sistema se reduce a 
$$\left\\{
\begin{array}{ccl}
d\_1x\_1&=&b\_1,\cr 
\vdots&&\vdots \cr
d\_kx\_k&=&b\_k,\cr
0&=&b\_{k+1},\cr 
\vdots&&\vdots \cr
0&=&b\_{m}.
\end{array}
\right.$$
Este sistema claramente tiene solución si y solo si $d\_i|b\_i$ para todo $1\leq i\leq k$ y $b_i=0$ para $k{<}i\leq m$. En dicho caso las soluciones son 
$$x\_i=\frac{b\_i}{d\_i},\quad 1\leq i\leq k;\qquad x\_{k+1},\dots,x\_n\in\mathbb Z;$$ estos últimos valores paramétricos cualesquiera. Observa que la solución es única si además $k=n$.

En general, $A$ tiene una forma normal de Smith $D$ que satisface $QAP^{-1}=D$, es decir $A=Q^{-1}DP$. Tenemos que
$$A\vec{x}=\vec{b}\Leftrightarrow DP\vec{x}=Q\vec{b}.$$
Llamando $$\vec{y}=P\vec{x},$$ lo cual es un simple cambio de veriables, podemos resolver esta ecuación en $\vec{y}$ como arriba. Las soluciones de la ecuación original se obtienen deshaciendo el cambio de variables $$\vec{x}=P^{-1}\vec{y}.$$


## Operadores lineales

Dado un cuerpo $k$ y un $k$-espacio vectorial $V$, un **operador lineal** en $V$ es un endomorfismo $T\colon V\rightarrow V$.


{{% proposition %}}
 Un $k[x]$-módulo es lo mismo que un $k$-espacio vectorial equipado con un operador lineal.
{{% /proposition %}}


{{% proof %}}
 Un $k[x]$-módulo $M$ es también un $k$-módulo, restringiendo el producto por escalares a $k\subset k[x]$. La multiplicación por $x$ es un homomorfismo de $k[x]$-módulos 
$$\begin{array}{rcl}M&\stackrel{x\cdot}\longrightarrow& M,\cr a&\mapsto &x\cdot a,\end{array}$$
en particular también es un homomorfismo de $k$-módulos, es decir, es un operador lineal en el $k$-espacio vectorial $M$.

Recíprocamente, dado un $k$-espacio vectorial $V$ y un operador lineal $T\colon V\rightarrow V$, podemos definir una estructura de $k[x]$-módulo en $V$ del siguiente modo. Dado $v\in V$ y $p(x)=a\_nx^n+\cdots+a\_1x+a\_0\in k[x]$, definimos el producto por escalares como
$$p(x)\cdot v=a\_nT^n(v)+\cdots+a\_1T(v)+a\_0v.$$ Dejamos como ejercicio comprobar que este producto por escalares satisface las propiedades requeridas.
{{% /proof %}}


{{% proposition %}}
 Un $k[x]$-módulo $M$ finitamente generado es de torsión, $M=T(M)$, si y solo si tiene dimensión finita como $k$-espacio vectorial.
{{% /proposition %}}


{{% proof %}}
 $\Rightarrow$ Si $M$ es de torsión entonces por el teorema de estructura de $k[x]$-módulos finitamente generados, $M$ es isomorfo a un producto de una cantidad finita de $k[x]$-módulos cíclicos $k[x]/(p(x))$ con $p(x)\in k[x]$ un polinomio no trivial. Como $k[x]/(p(x))$ tiene dimensión finita como $k$-espacio vectorial (su dimensión es el grado de $p(x)$), deducimos que $M$ también tiene dimensión finita como $k$ espacio vectorial (la suma de las dimensiones de los factores cíclicos del producto). 

$\Leftarrow$ Recíprocamente, si $M$ tiene dimensión finita como $k$ espacio vectorial, entonces no puede tener parte libre en su descomposición como producto de $k[x]$-módulos cíclicos ya que $k[x]$ no tiene dimensión finita como $k$-espacio vectorial.

 {{% /proof %}}


Una **caja de Jordan** es una matriz cuadrada con una constante $\alpha \in k$, denominada **autovalor**, en todas las entradas diagonal principal, $1$ en todas las entradas de la diagonal que está justo por debajo de la principal y $0$ en el resto, 
$$\left(\begin{array}{cccc}
\alpha&&&\cr
1&\ddots&&\cr
&\ddots&\ddots&\cr
&&1&\alpha
\end{array}\right).$$


{{% theorem name="Forma normal de Jordan" %}}
 Sea $k$ un cuerpo algebraicamente cerrado. Dado un $k$-espacio vectorial de dimensión finita $V$ equipado con un operador lineal $T\colon V\rightarrow V$ existe una base de $V$ respecto de la cual la matriz de $T$ es una matriz diagonal por cajas de Jordan. Esta matriz diagonal por cajas es única salvo permutación de las cajas y se denomina **forma normal de Jordan**.
{{% /theorem %}}


{{% proof %}}
 
Como $k$ es algebraicamente cerrado, los primos en $k[x]$ son los polinomios mónicos de grado $1$ y sus asociados. Sabemos que una base de $$\frac{k[x]}{(x^m)}$$ como $k$-espacio vectorial es  $\\{1,\bar x,\dots,\bar x^{m-1}\\}$. Haciendo un cambio de variables es fácil ver que una base de $$\frac{k[x]}{((x-\alpha)^m)}$$ como $k$-espacio vectorial es  $\\{1,\bar x-\alpha,\dots,(\bar x-\alpha)^{m-1}\\}$. Como 
$$\begin{array}{rcl}
x\cdot(\bar x-\alpha)^j&=&(x-\alpha+\alpha)\cdot(\bar x-\alpha)^j\cr
&=&(x-\alpha)\cdot(\bar x-\alpha)^j+\alpha\cdot(\bar x-\alpha)^j\cr
&=&(\bar x-\alpha)^{j+1}+\alpha\cdot(\bar x-\alpha)^j,
\end{array}$$ 
la matriz de la multiplicación por $x$,
$$\frac{k[x]}{((x-\alpha)^m)}\stackrel{x\cdot}\longrightarrow \frac{k[x]}{((x-\alpha)^m)}$$
respecto de la base anterior es la caja de Jordan de tamaño $m\times m$ y autovalor $\alpha$.

Podemos suponer que $V$ es un producto finito de $k[x]$-módulos cíclicos, cocientes por potencias de primos, y $T$ es la multiplicación por $x$, $T(a)=xa$,
$$V=\frac{k[x]}{((x-\alpha\_1)^{m\_1})}\times\cdots\times \frac{k[x]}{((x-\alpha\_n)^{m\_n})}.$$
Como $k$-espacio vectorial, $V$ tiene base $$\bigcup\_{i=1}^n\\{(\bar x-\alpha_i)^j\\}\_{j=0}^{m\_i-1}.$$ 
Respecto de esta base, la matriz de $T$ es la matriz diagonal por cajas de Jordan de tamaños $m\_i\times m\_i$ y autovalores $\alpha\_i$, $1\leq i\leq n$. 

La unicidad de la forma normal de Jordan se corresponde con la de la segunda forma del teorema de estructura. Observa que, sin embargo, la base respecto de la cual la matriz de $T$ está en forma normal de Jordan no es única.
  {{% /proof %}}




