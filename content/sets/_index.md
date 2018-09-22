+++
title = "Conjuntos"
weight = 10
+++


## Construcciones básicas

Comenzaremos dando una noción intuitiva de uno de los conceptos matemáticos más utilizados: el de conjunto. Sin embargo no daremos una definición rigurosa. ¿Sabes por qué?

{{% definition %}}
Un **conjunto** es a una colección de elementos. Normalmente están caracterizados por compartir alguna propiedad. Para que un conjunto esté bien definido debe ser
posible discernir si un elemento arbitrario está o no en él.
{{% /definition %}}

Los conjuntos pueden definirse de manera **explícita**, citando todos
los objetos de los que consta *entre llaves*, 
$$
A = \\{ 1,2,3,4,5 \\},
$$
o **implícita**, dando una o varias características que
determinen si un objeto dado está o no en el conjunto, 
$$
A = \\{ \text{números naturales del }1\text{ al }5\\}.
$$

{{% watch %}}
Los elementos de un conjunto *no están ordenados*, aunque vengan especificados como una lista, por tanto $A=\\{3,1,2,5,4\\}$.

En una definición explícita *no se pueden repetir elementos*, así que $\\{1,1,2,3,4,5\\}$ sería una manera incorrecta de expresar el conjunto $A$.
{{% /watch %}}

{{% example name="Conjuntos de números" %}}

* $\mathbb{N}$, los números **naturales**: 1, 2, 3, ...

* $\mathbb{N}_0$, los números naturales más el cero: 0, 1, 2, 3, ...

* $\mathbb{Z}$, los números **enteros**: ..., -2, -1, 0, 1, 2, ...

* $\mathbb{Q}$, los números **racionales**: $\frac{p}{q}$.

* $\mathbb{R}$, los números **reales**.

* $\mathbb{C}$, los números **complejos**.

{{% /example %}}

{{% definition %}}
Dado un conjunto $A$, decimos que el elemento $a$ **pertenece** a $A$, y lo denotamos $a\in A$, si $a$ es un elemento del conjunto $A$.
{{% /definition %}}

{{% watch %}}
Muchos símbolos matemáticos son **reversibles**, por ejemplo, $A\ni a$ significa lo mismo que $a\in A$. También muchos son **negables**, así $a\notin A$ significa que $a$ *no* pertenece a $A$.
{{% /watch %}}

Por ejemplo, si $A = \\{ 1,2,3,4,5 \\}$ entonces $1 \in A$ pero $6\notin A$. Otra manera implícita de expresar este conjunto $A$ es la siguiente:
\\[ A = \\{n|n\in\mathbb{N},1\leq n\leq 5\\}.\\]
Se lee del siguiente modo: "$A$ es el conjunto formado por los elementos $n$ tales que $n$ pertenece al conjunto los números naturales, $n$ es mayor o igual que 1 y $n$ es menor o igual que 5."


{{% definition %}}
Dos conjuntos $A$ y $B$ son **iguales** $A=B$ cuando poseen los mismos elementos, es decir, cuando $x\in A\Leftrightarrow x\in B$.
{{% /definition %}}

{{% remark %}}
Deducimos que dos conjuntos $A$ y $B$ son **distintos** $A\neq B$ si bien existe $x\in A$ tal que $x\notin B$ o bien existe $x\in B$ tal que $x\notin A$. En notación matemática: \\(A\neq B\Leftrightarrow(\exists x\in A|x\notin B)\vee(\exists x\in B|x\notin A).\\)
{{% /remark %}}

{{% definition %}}
El **conjunto vacío** $\varnothing$ es el que carece de elementos, es decir $\varnothing=\\{\\}$, o bien $\forall x, x\notin \varnothing$.

Un conjunto es **unitario** si contiene un único elemento, como por ejemplo $\\{0\\}$, $\\{1\\}$, $\\{a\\}$, $\\{$cartón de leche$\\}$, $\\{\mathbb{N}\\}$, ...
{{% /definition %}}

{{% watch %}}
¡Ojo! $x\in\\{x\\}$, pero $x\neq\\{x\\}$, de hecho, como demuestra la [paradoja de Russell](https://es.wikipedia.org/wiki/Paradoja_de_Russell), es imposible que un conjunto pertenezca a sí mismo.
{{% /watch %}}


{{% definition %}}
Dados dos conjuntos $A$ y $B$, decimos que $A$ está **contenido** en $B$ o que $A$ es un **subconjunto** de $B$, y lo denotamos $A\subset B$, si todo elemento de $A$ pertenece a $B$, es decir $x\in A \Rightarrow x\in B$.
{{% /definition %}}

{{% watch %}}
También se puede denotar $A\subset B$ como $A\subseteq B$. Hay que tener cuidado con la negación de estos dos símbolos. Tanto $A\not\subset B$ como $A\not\subseteq B$ significan que $A$ no está contenido en $B$, o no es un subconjunto de $B$. Sin embargo $A\subsetneq B$ solo niega la igualdad, por lo que significa que $A$ es un subconjunto de $B$ pero que $A$ no es igual a $B$. Por ejemplo, $\\{2,3,4\\}\subsetneq\\{1,2,3,4,5\\}$.
{{% /watch %}}

{{% remark %}}
La contención es **transitiva**, $A\subset B\subset C\Rightarrow A\subset C$. También es **reflexiva**, $A\subset A$. Además, el vacío está contenido en cualquier conjunto $\varnothing\subset A$. Los subconjuntos de $A$ distintos de $\varnothing$ y  $A$ se denominan **subconjuntos propios** de $A$.
{{% /remark %}}

![La contención es transitiva](../images/inclusion_transitive.png)

El siguiente resultado caracteriza la igualdad entre dos conjuntos en términos de contenciones. Es la base de una técnica de prueba conocida como **doble inclusión**, que aplicaremos con frecuencia.

{{% proposition %}}
$A=B$ $\Leftrightarrow$ $A\subset B$ y $A\supset B$. 
{{% /proposition %}}

{{% proof %}}
$A\subset B$ es lo mismo que $x\in A \Rightarrow x\in B$ y $A\supset B$ equivale a $x\in A \Leftarrow x\in B$, por tanto ambas simultáneamente significan $x\in A \Leftrightarrow x\in B$, que es lo mismo que $A=B$.
{{% /proof %}}


{{% definition %}}
Dados dos conjuntos $A$ y $B$ la **intersección** $A \cap B$ es el conjunto formado por aquellos elementos
que pertenecen a ambos conjuntos, $A \cap B = \\{ x  |  x \in A  \wedge  x  \in B \\}$.
{{% /definition %}}

![Intersección](../images/intersection.png)

{{% remark %}}
Si $C\subset A$ y $C\subset B$ entonces $C\subset A\cap B$
{{% /remark %}}

{{% theorem %}}
La intersección de conjuntos verifica las siguientes propiedades,
donde $A$, $B$ y $C$ son conjuntos cualesquiera:

* $A \cap B = B \cap A$ (**conmutativa**).
* $(A \cap B) \cap C = A \cap (B \cap C)$ (**asociativa**).
* $A \cap B \subset A$. 
* $A \cap B \subset B$.
* $\varnothing \cap A = \varnothing$.
* $A \subset B\Leftrightarrow A \cap B = A.$
{{% /theorem %}}


{{% proof %}}
Los elementos de $A \cap B$ son los que pertenecen a $A$ y a $B$, que son los mismos que pertenecen a $B$ y a $A$.

Las dos intersecciones triples son el mismo conjunto porque representan a los elementos que están en $A$, $B$ y $C$.

Los elementos que están en $A$ y en $B$ están, en particular, en $A$. También en $B$.

La quinta igualdad la demostramos por doble inclusión. La inclusión $\supset$ es siempre cierta y $\subset$ es consecuencia de un apartado anterior.

Demostremos la equivalencia del último apartado. Probemos primero $\Rightarrow$. Supongamos pues que $A\subset B$. Demostraremos la igualdad de la derecha por doble inclusión. La inclusión $\subset$ es siempre cierta. Veamos $\supset$. Como $A\subset B$, todo elemento de $A$ está también en $B$, y por tanto en la intersección. Probemos ahora $\Leftarrow$. Esto es consecuencia de que $A\cap B\subset B$.
{{% /proof %}}

{{% remark %}}
Estas propiedades nos permiten definir inductivamente la **intersección** de una *cantidad finita* de conjuntos $A_1\cap\cdots\cap A_n$. Consiste en los elementos que están en *todos* ellos.
{{% /remark %}}

Veamos el caso posiblemente infinito.

{{% definition %}}
Dado un conjunto $I$ y una familia de conjuntos $\\{ A\_i \\}\_{i\in I}$ indexada por $I$, su **intersección** se define como $\bigcap_{i\in I}A_i=\\{x|\forall i\in I, x\in A_i\\}$.
{{% /definition %}}

{{% watch %}}
Si $I$ es finito, esta definición coincide con la anterior, basta enumerar los elementos de $I$ para comprobarlo. Esta definición es también válida para $I$ infinito.
{{% /watch %}}


{{% definition %}}
Dos conjuntos $A$ y $B$ son **disjuntos** si $A \cap B = \varnothing$.
{{% /definition %}}

![Disjuntos](../images/disjoint.png)

{{% definition %}}
Dados dos conjuntos $A$ y $B$ la **unión** $A \cup B$es el conjunto formado por aquellos elementos
que pertenecen al menos a uno de estos dos conjuntos, $A \cup B = \\{ x  |  x \in A  \vee  x  \in B \\}$.
{{% /definition %}}

![Unión](../images/union.png)

Observa que $A\cap B\subset A\cup B$.

{{% remark %}}
Si $A\subset C$ y $B\subset C$ entonces $A\cup B\subset C$
{{% /remark %}}

{{% theorem %}}
La unión de conjuntos verifica las siguientes propiedades,
donde $A$, $B$ y $C$ son conjuntos cualesquiera:

* $A \cup B = B \cup A$ (**conmutativa**).
* $(A \cup B) \cup C = A \cup (B \cup C)$ (**asociativa**).
* $\varnothing \cup A = A$ (**elemento neutro**).
* $A \subset A \cup B$. 
* $B \subset A \cup B$.
* $A \subset B\Leftrightarrow B=A \cup B$.

{{% /theorem %}}

{{% proof %}}
Los elementos de $A \cup B$ son los que pertenecen a $A$ o a $B$, que son los mismos que pertenecen a $B$ o a $A$.

Los dos uniones triples coinciden porque ambas representan el conjunto de elementos que pertenecen a $A$, a $B$ o a $C$.

Como el vacío no tiene elementos, los elementos que pertenecen al vacío o a $A$ son los que pertenecen a $A$.

Es obvio, por la propia definición, que tanto los elementos de $A$ como los de $B$ pertenecen a la unión.

Probemos la última equivalencia. Comenzamos demostrando $\Leftarrow$. Esto es una simple consecuencia de la inclusión $A\subset A\cup B$. Probemos ahora $\Rightarrow$. Supongamos pues que $A \subset B$. Tenemos que demostrar que $B=A \cup B$ y lo haremos por doble inclusión. La inclusión $\subset$ es cierta por el apartado anterior. Probemos la otra. Un elemento que está en $A$ o en $B$ ha de estar necesariamente en $B$ ya que $A\subset B$.
{{% /proof %}}


{{% remark %}}
Estas propiedades nos permiten definir inductivamente la **unión** de una *cantidad finita* de conjuntos $A_1\cup\cdots\cup A_n$. Consiste en los elementos que están en *alguno* de ellos.
{{% /remark %}}

Veamos ahora el caso posiblemente infinito.

{{% definition %}}
Dada una familia de conjuntos $\\{ A\_i \\}\_{i\in I}$, su **unión** se define como $\bigcup_{i\in I}A_i=\\{x\;|\;\exists i\in I| x\in A_i\\}$.
{{% /definition %}}

{{% watch %}}
Igual que antes, si $I$ es finito, esta definición coincide con la anterior, pero es también válida para $I$ infinito.
{{% /watch %}}


{{% definition %}}
Dados dos conjuntos $A$ y $B$ se define la **diferencia** $A \setminus B$, como el conjunto formado por los elementos de $A$ que no están en $B$, $ A \setminus B = \\{x  |  x \in A  \wedge  x \notin B\\}$.
{{% /definition %}}

![Diferencia](../images/difference.png)

{{% watch %}}
Observa que $A\setminus B\neq B\setminus A$. De hecho ambos conjuntos son disjuntos.
{{% /watch %}}


{{% definition %}}
La **diferencia simétrica** $A\triangle B$ de dos conjuntos $A$ y $B$ se define como $A\triangle B=(A\setminus B)\cup(B\setminus A)=(A\cup B)\setminus (A\cap B)$.
{{% /definition %}}

![Diferencia simétrica](../images/symmetric_difference.png)


{{% theorem name="Leyes dstributivas" %}}
Dados tres conjuntos $A$, $B$ y $C$:

* $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$.
* $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$.
{{% /theorem %}}

{{% proof %}}
Probamos la primera por doble inclusión. La segunda la dejamos como ejercicio.

Comenzamos demostrando $\supset$. Sabemos que $A\cap B\subset A$ y $A\cap B\subset B\subset B\cup C$, por tanto $A\cap B\subset A\cap (B\cup C)$. También sabemos que $A\cap C\subset A$ y $A\cap C\subset C\subset B\cup C$, por tanto $A\cap C\subset A\cap (B\cup C)$. De aquí se deduce $\supset$.

Veamos ahora $\subset$. Dado $x\in A\cap (B\cup C)$ tenemos que $x\in A$ y $x\in B\cup C$. Por un lado, si $x\in B$ entonces $x\in A\cap B\subset (A \cap B) \cup (A \cap C)$. Por otro lado, si $x\in C$ entonces $x\in A\cap C\subset (A \cap B) \cup (A \cap C)$. De esto se sigue $\subset$.
{{% /proof %}}

![Leyes distributivas](../images/distributive_laws.png)

{{% theorem name="Leyes de De Morgan" %}}
Dados tres conjuntos $A$, $B$ y $C$:

* $C \setminus (A \cup B) = (C \setminus A) \cap (C \setminus B)$.
* $C \setminus (A \cap B) = (C \setminus A) \cup (C \setminus B)$.
{{% /theorem %}}

{{% proof %}}
Probaremos la segunda ley de De Morgan por doble inclusión. La primera queda como ejercicio.

Comenzamos con $\supset$. Sea $x\in C\setminus A$. Tenemos entonces que $x\in C$ pero $x\notin A$, por tanto $x\notin A\cap B$ ya que $A\cap B\in A$. Esto demuestra que $x\in C \setminus (A \cap B)$, por tanto $C\setminus A\subset C \setminus (A \cap B)$. Los papeles de $A$ y $B$ son intercambiables, así que también $C\setminus B\subset C \setminus (A \cap B)$. Esto demuestra $\supset$.

Para probar $\subset$, tomamos $x\in C \setminus (A \cap B)$. Esto quiere decir que $x\in C$ pero $x\notin A\cap B$. Esto último equivale a que bien $x\notin A$ o bien $x\notin B$. Si $x\notin A$ entonces $x\in C\setminus A$ y si $x\notin B$ entonces $x\in C\setminus B$. Por tanto $x\in (C \setminus A) \cup (C \setminus B)$. Esto prueba $\subset$.
{{% /proof %}}

![Leyes de De Morgan](../images/morgan.png)

{{% definition %}}
En una situación concreta, un **conjunto universal** $U$ es quel que contiene a todos los posibles conjuntos que presented el problema que tratamos.
{{% /definition %}}

![Conjunto universal](../images/universal_set.png)

{{% definition %}}
Fijado un conjunto universal $U$, el **complementario** de un conjunto $A$ se denota $\bar{A}$ o $A^c$ y se define como $\bar{A} = \\{ x\in U | x \notin A \\}$.
{{% /definition %}}

![Complementario](../images/complement.png)

{{% proposition %}}
Si tenemos fijado un conjunto universal $U$ entonces $A \setminus B = A \cap \bar{B}$.
{{% /proposition %}}

{{% proof %}}
Como $A,B\subset U$, 
$$
\begin{array}{rcl}
A \setminus B&=&\\{x  |  x \in A  \wedge  x \notin B\\} \cr
&=&\\{x  |  x \in A  \wedge   (x\in U \wedge x \notin B)\\} \cr
&=&\\{x  |  x \in A  \wedge   x\in \bar B\\} \cr
&=&A \cap \bar{B}.
\end{array}
$$
{{% /proof %}}


{{% proposition %}}
Dado un conjunto universal $U$:

* $\bar{\bar{A}}=A$.
* $\bar U=\varnothing$.
* $\bar{\varnothing}=U$.
{{% /proposition %}}

{{% proof %}}
Como $A\subset U$, 
$$
\begin{array}{rcl}
\bar{\bar{A}} &=& \\{ x  |  x \in U \wedge x \notin \overline{A} \\} \cr
&=& \\{ x  |  x \in U \wedge (x\notin U \vee x\in A) \\} \cr
&=& \\{ x  |  x \in U \wedge x\in A \\} \cr
&=& \\{ x  |  x\in A \\} \cr
&=& A
\end{array}
$$

Por otro lado,
$$
\bar U=\\{x\in U|x\notin U\\}=\varnothing,
$$
así que $U=\bar{\bar{U}}=\bar\varnothing$.
{{% /proof %}}


{{% definition %}}
Dado un conjunto $A$, el **conjunto de las partes** de $A$ es $\mathcal{P}(A)=\\{$subconjuntos de $A\\}$.
{{% /definition %}}

{{% watch %}}
$B\subset A\Leftrightarrow B\in\mathcal{P}(A)$.
{{% /watch %}}

{{% example name="Las partes de $A = \\{ 1,2,3 \\}$" %}}
$\mathcal{P}(A) = \\{\varnothing, \\{ 1 \\},  \\{ 2 \\},  \\{ 3 \\}, \\{1,2\\},  \\{1,3\\},  \\{2,3\\}, A \\}$.
{{% /example %}}

{{% watch %}}
Si $A$ es un conjunto con $n$ elementos, ¿cuántos elementos tiene $\mathcal{P}(A)$? ¿Qué ocurre si $A$ es infinito? ¿Es posible que $\mathcal{P}(A)$ sea vacío? ¿Y unitario?
{{% /watch %}}



<!--


## Producto cartesiano y aplicaciones

{{% definition %}}
{Pares ordenados} {Dados dos objetos $x$ e $y$, diremos que $x$ (respectivamente $y$) es la primera (resp. la segunda) componente del {\bf par ordenado} $(x,y)$. Dos pares ordenados son iguales si y sólo si coinciden sus primeras componentes y coinciden sus segundas componentes:
$$ (x,y)=(x',y') \Leftrightarrow \left\\{ \begin{array}{c} x=x' \\ \wedge \\ y=y'.\end{array} \right.
$$}
{{% /definition %}}

{{% definition %}}
{Producto cartesiano} {Dados dos conjuntos $A$ y $B$, se define el {\bf producto cartesiano}
de $A$ y $B$ como el conjunto cuyos elementos son todos los pares ordenados cuya primera componente es un elemento de $A$ y cuya segunda componente es un elemento de $B$ y se denota $A \times B$:
$$
A \times B = \\{ (a,b) \; | \; a \in A, \, b \in B \\}.
$$}
{{% /definition %}}

Nótese que $\varnothing \times B = \varnothing = A \times \varnothing$.

{{% example name="Ejemplo" %}}
 Sean $A= \\{ a,b,c \\}$ y $B=\\{b,1,2,3\\}$. Entonces el conjunto $A \times B$ es igual a:
$$ \\{ (a,b), (a,1), (a,2), (a,3), (b,b), (b,1), (b,2), (b,3), (c,b), (c,1), (c,2), (c,3)\\}$$
{{% /example %}}

\noindent De manera similar, podemos considerar $n$-uplas ordenadas de objetos $(x_1,\dots,x_n)$ y 
definir el producto cartesiano de una familia
finita de conjuntos (no trataremos por ahora el caso de familias infinitas):
$$
A_1 \times ... \times A_n = \prod_{i=1}^n A_i = \left\\{
(a_1,...,a_n) \; | \; a_i \in A_i, \mbox{ para } i=1,...,n \right\\}.
$$
Cuando todos los $A_i$ son iguales a un conjunto dado $A$ notaremos $A^n = A \times \cdots \times A$ ($n$ veces).
\bigskip

En muchas situaciones, dados dos conjuntos $A$ y $B$, nos aparecen reglas o procedimientos para asociar ciertos elementos de $A$ con ciertos elementos de $B$. Damos a continuación la noción matemática que sirve para modelizar este hecho.

{{% definition %}}
{Correspondencia} {Una {\bf correspondencia} $G$ de $A$ en $B$ es un subconjunto del
producto $A \times B$. Una correspondencia de $A$ en $B$ se interpreta como una
regla que asocia algunos elementos de $A$ con algunos elementos de
$B$. Concretamente, entendemos que la correspondencia $G$ "asocia" $a \in A$ con $b \in B$ si y sólo si $(a,b) \in G$.
\smallskip

El conjunto de todas las correspondencias de $A$ en $B$ es pues $\mathcal{P}(A \times B)$.}
{{% /definition %}}

Nótese que toda correspondencia $G$ de $A$ en $B$ determina (y está determinada por) otra correspondencia $G'$ de $B$ en $A$
$$ G' =\\{ (y,x) \in B \times A\; | \; (x,y) \in G\\}.
$$
Así, los conjuntos $A$ y $B$ juegan papeles simétricos, por lo que podríamos hablar de correspondencias \underline{entre} los conjuntos $A$ y $B$ en lugar de correspondencia de $A$ en $B$.

{{% example name="Ejemplo" %}}
 Sean $A= \\{ a,b,c \\}$ y $B=\\{b,1,2,3\\}$ los conjuntos del ejemplo anterior. Entonces $ G = \\{ (a,1), (a,3), (b,b), (b,1), (b,3) \\}$ es una correspondencia de $A$ en $B$.\\

Si $A=B= [-1,1]$ (el intervalo de los números reales $x$ con $-1\leq x \leq 1$), una correspondencia de $A$ en $B$ viene dada por
$$ G = \\{ (x,y) \in [-1,1] \times [-1,1] \; | \;  x^2 + y^2 = 1\\}.
$$
Si denotamos por $A$ al conjunto de los estudiantes de la Facultad de Matemáticas y por $B$ al conjunto de las aulas de la Facultad de Matemáticas,
$$ G = \\{(a,b)\in A \times B \; |\; a\ \text{tiene alguna clase en el aula\ }\ b\\}
$$
es una correspondencia de $A$ en $B$.
{{% /example %}}

Las correspondencias se pueden representar como sigue:

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics[scale=1]{funcion-01.eps}
 }
 \caption{Correspondencia}
 \label{fig:Correspondencia}
\end{figure}

Es claro que la representación del ejemplo anterior es posible por trabajar con conjuntos finitos (y con pocos elementos). Si los conjuntos son infinitos, las correspondencias (no finitas) se tienen que dar definiendo propiedades de los pares que la componen. Por ejemplo, si $A = \Z, B = \N$ una correspondencia de $\Z$ en $\N$ es $G= \\{(x,y) \in \Z \times \N \; | \; x \; \mbox{es par}, y \; \mbox{es impar} \\}.$

{{% example name="Ejemplo" %}}
 Si $A$ (ó $B$) es el conjunto vacío, entonces $A \times B = \varnothing$ y por tanto la única correspondencia de $A$ en $B$, ó entre $A$ y $B$, es la correspondencía vacía.
{{% /example %}}


{{% definition %}}
{Aplicación} {Una {\bf aplicación} $f$ de $A$ en $B$ es una correspondencia $f\subset A\times B$  donde \underline{cada}
elemento de $A$ tiene asociado un \underline{único} elemento de $B$. Esto es,
en notación matemática, la correspondencia $f$ es una
aplicación si y sólo si se verifica que
$$
\forall a \in A \;\;\; \exists ! b \in B \; \mbox{ tal que } (a,b)
\in f.
$$}
{{% /definition %}}


{{% watch %}}
 Para referirnos a una correspondencia $f\subset A\times B$ que sea una aplicación, es habitual denotarla de la forma $f : A \longrightarrow B$. Además, en este caso, dado un $a \in A$, el único $b \in B$ verificando $(a,b) \in f$ se denotará $f(a)$ y
se denominará {\bf imagen} de $a$ (por la aplicación $f$). A veces también llamaremos a $f(a)$ {\bf valor} de $f$ en $a$. Una aplicación $f$ de $A$ en $B$ también se especificará en la forma
$$ a \in A \longmapsto  f(a) \in B.
$$

De esta notación surge la terminologí a, comúnmente usada, de
llamar a $A$ {\bf conjunto de partida} (o dominio) y a $B$ {\bf conjunto de llegada} (o rango) de la aplicación $f$. Nótese que, contrariamente al caso de las correspondencias en general, en una aplicación el conjunto de partida y el conjunto de llegada juegan papeles que no son intercambiables.

Para dar una aplicación debemos pues indicar:

* su conjunto de partida, 
* su conjunto de llegada, y
* la imagen de cada elemento del conjunto de partida, que habrá de ser un elemento bien determinado del conjunto de llegada.

A veces, cuando estamos definiendo una aplicación, para dar la imagen de cada elemento del conjunto de partida utilizamos alguna elección auxiliar. En tal caso hemos de probar que el resultado no depende de esta elección, o dicho de otra forma, que la imagen de cada elemento del conjunto de partida está "bien definida".


\noindent{\bf Importante:} Para probar que dos aplicaciones $f,g:A \longrightarrow B$ son iguales debemos probar es que las imágenes de cualquier elemento de $A$ por $f$ y por $g$ coinciden. Simbólicamente
$$ f=g \Leftrightarrow f(x)=g(x)\quad \forall x\in A.
$$
{{% /watch %}}


{{% example name="Ejemplo" %}}
 1) Sea $X$ un conjunto cualquiera. Siempre se tiene la aplicación $$f: X \rightarrow X, \quad \mbox{definida por} \quad f(x) = x, \, \forall x \in X,$$ que llamaremos aplicación {\bf identidad} y  notaremos por $1_X.$

\noindent 2) Sean $X, Y$ conjuntos cualesquiera e $y_0 \in Y$ un elemento fijo. Siempre se tiene la aplicación $$g: X \rightarrow Y \quad \mbox{definida por} \quad  g(x) = y_0, \; \forall x \in X,$$ que llamaremos aplicación constante (con valor $y_0$).

\noindent 3) Si $X$ es un subconjunto de $Y$, $X\subset Y$, siempre disponemos de una aplicación especial $i_X: X \to Y$, definida por $i_X(x)=x$ para cada $x\in X$. Dicha aplicación se denomina la {\bf inclusión} de $X$ en $Y$.

\noindent 4) Sea $f \subset \RR \times \RR$ la correspondencia dada por $$(a,b) \in f \quad \mbox{si y sólo si} \quad b^2=a.$$ La correspondencia $f$ no es aplicación, pues no todos los elementos de $\RR$ poseen una imagen (si $a < 0$, no existe $b \in \RR$ con $b^2 = a.$)

\noindent 5) Consideremos la correspondencia anterior donde la primera componente la suponemos en $\RR^+$ (los números reales positivos), es decir $f \subset \RR^+ \times \RR.$ En este caso, a todos los elementos de $\RR^+$ les corresponde algún elemento de $\RR$, pero $f$ no es aplicación, pues este elemento no es único. Por ejemplo, $(4,2) \in f$ y $(4,-2) \in f.$

\noindent 6) Si consideramos $f \subset \RR^+ \times \RR^+$, definida por $$(a,b)\in f \quad  \mbox{si y sólo si} \quad b^2=a,$$ entonces sí es aplicación.

\noindent 7)  La correspondencia $$f\subset (\Z -\\{1\\})\times  \Q, \quad  f = \left\\{ \left(n,\frac{n}{n-1}\right)\ |\ n\in \Z -\\{1\\}\right\\}$$ es aplicación.

\noindent 8) Fijemos un conjunto $U$ y un subconjunto $A\subset U$. Definimos las correspondencias $f,g\subset \mathcal{P}(U) \times \mathcal{P}(U)$ por:
$$
f =\\{(B,A\cap B)\ |\ B\in \mathcal{P}(U)\\},\quad g =\\{(B,A\cup B)\ |\ B\in \mathcal{P}(U)\\}.
$$
Ambas son aplicaciones.

\noindent 9) Si $X$ e $Y$ son conjuntos, las aplicaciones $p:X\times Y \to X$, $q:X\times Y \to Y$ dadas por
$$ p(x,y)=x,\quad q(x,y) = y\quad \forall (x,y) \in X\times Y$$
se denominan respectivamente {\bf primera} y {\bf segunda proyección}.

\noindent 10) Si $A=\varnothing$, la única correspondencia de $A$ en $B$ es la correspondencia vacía que es de hecho una aplicación. Si $B=\varnothing$, la única correspondencia de $A$ en $B$ es la correspondencia vacía, pero dicha correspondencia sólo será una aplicación cuando $A$ también sea el conjunto vacío. En particular, si $B=\varnothing$ y $A\neq \varnothing$, no existe ninguna aplicación de $A$ en $B$.
{{% /example %}}

{{% definition %}}
{Exponenciación de conjuntos} {Dados dos conjuntos $X$ e $Y$, el {\bf conjunto $Y$ elevado a $X$}, notado $Y^X$, es por definición el conjunto cuyos elementos son todas las aplicaciones de $X$ en $Y$:
$$ Y^X = \\{f\in \mathcal{P}(X\times Y) \; |\; f\  \text{es una aplicación de $X$ en $Y$.}\\}.
$$
Se tiene pues que $Y^X \subset \mathcal{P}(X\times Y)$.
}
{{% /definition %}}

{{% definition %}}
{Producto cartesiano de aplicaciones} {Dadas dos aplicaciones $f:X\to Y$ y $f':X'\to Y'$, el {\bf producto cartesiano} de $f$ y $f'$ es la aplicación que denotaremos  $f\times f': X\times X' \to Y\times Y'$ definida por
$$ (f\times f')(x,x') = (f(x),f'(x')),\quad \text{\ para cada\ }\ (x,x')\in X\times X'.
$$
}
{{% /definition %}}

{{% definition %}}
{Imagen y anti-imagen} {Sea $f : X \longrightarrow Y$ una aplicación. Dado un subconjunto
$A \subset X$  definimos:


* La {\bf imagen} de $A$ (o imagen directa de $A$), notada $f(A)$, como
$$
f(A) = \\{ y \in Y \; | \; \exists x \in A \mbox{ con } f(x) = y \\}
\subset Y,
$$
esto es, el conjunto de los elementos del conjunto de llegada que son imagen
de algún elemento de $A$.
Si $A=X$ se denota $f(X) = \Imag(f)$ y se denomina {\bf imagen de $f$.}


Dado un subconjunto $B \subset Y$ definimos:

* La {\bf anti--imagen} (o contraimagen, o imagen recí proca o imagen inversa)
de $B$, notada $f^{-1} (B)$, como
$$
f^{-1} (B) = \\{ x \in X \; | \; f(x) \in B \\} \subset X,
$$
esto es, el conjunto de elementos del conjunto de partida cuya imagen
pertenece a $B$.

{{% /definition %}}

{{% watch %}}
 \label{nota:f(?)} En general, si $f: X \rightarrow Y$ es una aplicación, $f(X) \not= Y.$ Basta tomar la última aplicación del ejemplo anterior. Sí se verifica siempre que $f^{-1}(Y) = X.$


Dada una aplicación $f:X \longrightarrow Y$, la notación $f(\cdot)$ se utiliza para dos situaciones distintas:

* Cuando $x \in X$, es decir, $x$ es un \underline{elemento} que pertenece a $X$, $f(x)$ denota la imagen de $x$ por $f$, que es un \underline{elemento} que pertenece a $Y$: $f(x)\in Y$.
* Cuando $A\subset X$, es decir, $A$ es un \underline{subconjunto} de $X$, $f(A)$ denota la imagen (directa) de $A$, que es un \underline{subconjunto} de $Y$: $f(A) \subset Y$.

Siempre debemos saber en qué contexto estamos utilizando $f(\cdot)$. Una posibilidad para evitar confusiones sería usar una notación para la imagen  (o imagen directa) de un subconjunto $A\subset X$ por la aplicación $f$ distinta de la notación de la imagen de un elemento $x\in X$, como por ejemplo $f_*(A)$ ó $f[A]$, pero como no es lo habitual en los textos de Matemáticas, no lo haremos en estas notas.

Nótese que si $x\in X$, $f(\\{x\\}) = \\{f(x)\\}$, donde estamos utilizando la notación $f(\cdot)$ en las dos situaciones mencionadas.

Nótese también que se verificas las siguientes propiedades (se deja como ejercicio su prueba)
\begin{eqnarray*}
 A \subset A' (\subset X) & \Rightarrow & f(A) \subset f(A'),\\
 B \subset B' (\subset Y) & \Rightarrow & f^{-1}(B) \subset f^{-1}(B').\\
\end{eqnarray*}
{{% /watch %}}

{{% example name="Ejemplo" %}}
 En el caso de la aplicación identidad $1_X:X \longrightarrow X$ es claro que $1_X(A)=A$ y $1_X^{-1}(B)=B$ para cualesquiera subconjuntos $A,B\subset X$.
{{% /example %}}

{{% example name="Ejemplo" %}}
 1) Consideremos la aplicación
$$f: \Z \rightarrow \Z \quad \mbox{definida por} \quad f(n)=2n,$$ y $A =\\{-1,0, 4, 5\\}.$ Entonces $f(A)=\\{ -2,0,8,10\\},$ y la imagen de $f$ es $\Imag(f) = \\{ \mbox{enteros pares}\\}.$

\noindent Sean $B_1 = \\{2,3,8, -4,-1\\}, \; B_2 = \\{1,3\\}.$ Se tiene que $$f^{-1}(B_1) = \\{ 1,4,-2\\}, f^{-1}(B_2)= \varnothing.$$

\noindent 2) Sea la aplicación
$$f: \RR \rightarrow \RR \quad \mbox{definida por} \quad  f(x) = x^2,$$ $A = [0,2].$ Entonces $f(A) = [0,4],$ pues $\forall x \in [0,4],$ existe $\sqrt{x} \in [0,2]$ tal que $f(\sqrt{x})=x.$ En este caso, la imagen de $f$ es $\Imag(f) = [0,+\infty),$ los números reales no negativos.
{{% /example %}}

{{% proposition %}}
 Sea $f:X \longrightarrow Y$ una aplicación, $A_1,A_2 \subset
X$ y $B_1,B_2 \subset Y$. Se verifica:

* $f(A_1 \cup A_2) = f(A_1) \cup f(A_2)$, $f(A_1 \cap A_2)
\subset f(A_1) \cap f(A_2)$.
* $f^{-1} (B_1 \cup B_2) = f^{-1} (B_1) \cup f^{-1} (B_2)$,
$f^{-1} (B_1 \cap B_2) = f^{-1} (B_1) \cap f^{-1} (B_2)$.
* $f(f^{-1}(B_1)) \subset B_1$, $A_1 \subset f^{-1}(f(A_1))$.

{{% /proposition %}}

{{% proof %}}
 Vamos a probar la segunda afirmación de (a) y
la primera de (b) y de (c). Las demás son similares.

(a) Consideremos $y \in
f(A_1 \cap A_2)$. Entonces existe $x \in A_1 \cap A_2$ tal que $y =
f(x)$. Por tanto, $y \in f(A_1)$ e $y \in f(A_2)$, por lo que se
tiene el resultado.

Es importante entender que, para afirmar que la otra inclusión no
es cierta, basta con dar un contraejemplo; esto es, un caso
particular donde no sea cierto el enunciado. Para ello consideremos por ejemplo 
$f: \N \longrightarrow \N$ definida por
$$
f(x) = \left\\{ \begin{array}{ll} x/2+1 & \mbox{ si $x$ es par} \\
x+2 & \mbox{ si $x$ es impar} \end{array} \right.
$$
Tomamos $A_1 = \\{ 1,3,5 \\}$, $A_2 = \\{ 2,4,6 \\}$. Claramente $f (A_1
\cap A_2 ) = f (\varnothing ) = \varnothing$, pero $f(A_1) \cap f(A_2) =
\\{ 3 \\}$.

(b) Sea $x$ un elemento de $f^{-1}(B_1 \cup B_2).$ Entonces
$$x \in f^{-1}(B_1 \cup B_2) \Leftrightarrow f(x) \in B_1 \cup B_2 \Leftrightarrow f(x) \in B_1 \; \mbox{ó} \; f(x) \in B_2 \Leftrightarrow$$ $$\Leftrightarrow x \in f^{-1}(B_1) \; \mbox{ó} \; x \in f^{-1}(B_2) \Leftrightarrow x \in f^{-1}(B_1) \cup f^{-1}(B_2).$$

(c) Probemos ahora que $f(f^{-1}(B_1)) \subset B_1$. Si $y \in
f(f^{-1}(B_1))$, es porque existe $x \in f^{-1} (B_1)$ tal que $y =
f(x)$. Pero, al ser $x \in f^{-1} (B_1)$, por definición tenemos
que $y = f(x) \in B_1$.

Para demostrar que la inclusión contraria no es cierta en general
podemos tomar la misma aplicación que en el caso anterior y
considerar $B_1 = \\{ 1,3,5\\}$ nuevamente. Entonces $f^{-1} (B_1) =
\\{0, 1,3,4,8 \\}$. Pero
$f(f^{-1} (B_1)) = \\{ 3,5 \\}$, por lo que hemos acabado.

Veamos que $A_1 \subset f^{-1}(f(A_1))$. Pongamos $C = f(A_1).$ Sea $x \in A_1,$ luego $f(x) \in C.$ Esto quiere decir, por la definición de contraimagen, que $x \in f^{-1}(C) = f^{-1}(f(A_1))$.

Para demostrar que la inclusión contraria no es cierta en general consideramos la aplicación constante $f: X \rightarrow Y$ dada por $f(x) = y_0,$ para un elemento $y_0 \in Y$ fijado. Sea $A$ cualquier subconjunto propio de $X.$ Entonces $$ f^{-1}(f(A)) = f^{-1}(\\{y_0\\})= X \not\subset A.$$
{{% /proof %}}

{{% watch %}}
 \label{nota:antiimag_unitarios} Sea $f:X\to Y$ una aplicación e $\\{y\\}\subset Y$ un subconjunto \underline{unitario} de $Y$. Con objeto de aligerar la notación, en la mayoría de los textos se escribe $f^{-1}(y)$ en lugar de $f^{-1}(\\{y\\})$, es decir, la notación $f^{-1}(y)$ se refiere a:
$$ f^{-1}(y) = \\{ x \in X \; | \; f(x)\in  \\{y\\} \\} = \\{ x \in X \; | \; f(x) = y \\}.
$$
Hemos de tener especial cuidado con esta notación, pues puede confundirse con la imagen de $y$ por la aplicación inversa de $f$, cuando dicha aplicación inversa exista (ver Nota \ref{nota:notaciones_antiimag}). 
{{% /watch %}}

{{% definition %}}
{Aplicaciones inyectivas, sobreyectivas y biyectivas} {Sea una aplicación $f: X \longrightarrow Y$.


* $f$ se dice {\bf inyectiva} si dos elementos distintos de
$X$ siempre tienen imágenes distintas. Dicho de otro modo, si para $x, x' \in X$ se tiene 
$$f(x) = f(x') \Rightarrow x=x'.
$$
* $f$ se dice {\bf sobreyectiva (o sobre)} si todo elemento de
$Y$ es imagen de algún elemento de $X$. O sea, $f$ es sobre si
$f(X)=\Imag(f)=Y$, o dicho de otro modo, si
$$ \forall y\in Y, \exists x\in X\quad \text{tal que}\quad f(x)=y.
$$
* $f$ se dice {\bf biyectiva} si es inyectiva y sobreyectiva.

{{% /definition %}}

{{% example name="Ejemplo" %}}
 1) Sea $f: \RR \rightarrow \RR$ la aplicación definida por $f(x) = x^2.$ Esta aplicación no es inyectiva, pues $f(x) = f(-x).$ Tampoco es sobreyectiva, pues $\Imag(f) = [0,+ \infty) \not= \RR.$

\noindent 2) Sea $f: \Z \rightarrow \Z$ la aplicación definida por $f(n)=2n.$ Esta aplicación es inyectiva ya que, si $f(n) = f(m),$ entonces $2n=2m,$ y de aquí se tiene que $n=m.$ La aplicación no es sobreyectiva pues $\Imag(f) = \\{ \mbox{números pares} \\} \not= \Z.$

\noindent 3) Sean $U, A\subset U, A \not= \varnothing$ unos conjuntos fijos. Sea $f: \mathcal{P}(U) \rightarrow \mathcal{P}(A)$ la aplicación definida por $f(B)=A \cap B.$ Esta aplicación no es inyectiva, pues si $f(B)=f(C),$ tenemos que $A \cap B = A \cap C,$ y de aquí no se deduce que $B=C.$ Basta tomar dos conjuntos distintos $B,C \subset \overline{A}.$ Entonces se verifica que $A \cap B = \varnothing = A \cap C$ y $B \not= C.$

Veamos que esta aplicación es sobreyectiva. Sea $D \in \mathcal{P}(A)$ y pongamos $B=D.$ Entonces $$f(B) = A \cap B = A \cap D = D.$$

Notar que también podemos tomar $B = \overline{A} \cup D,$ pues $$f(B) = A \cap B= A \cap (\overline{A} \cup D) = (A \cap \overline{A}) \cup (A \cap D) = \varnothing \cup D = D.$$
Esto nos da otra forma de ver que la aplicación no es inyectiva.

\noindent 4) La aplicación identidad es biyectiva.

\noindent 5) Sea $f: \Z \rightarrow \Z$ la aplicación definida por $f(n)=n+3.$ Veamos que esta aplicación es biyectiva.

Inyectiva: si $f(n)=f(m) \Rightarrow n+3 =m+3 \Rightarrow n=m.$

Sobreyectiva: si $m \in \Z,$ tomando $n=m-3$ se tiene que $f(n)=m.$

\noindent 6) Si $X\subset Y$, la inclusión $i_X:X \to Y$ es una aplicación inyectiva.

\noindent 7) Si $X$ e $Y$ son conjuntos con $Y\neq \varnothing$, la primera proyección $p:X\times Y \to X$ es sobreyectiva. Se tiene un resultado análogo para la segunda proyección si $X\neq \varnothing$.
{{% /example %}}

La prueba de la siguiente proposición se deja como ejercicio.

{{% proposition %}}
 \label{prop:mn} Sean dos números enteros $m,n \geq 1$. Probar que existe una aplicación biyectiva $f: \\{1,\dots,m\\} \times \\{1,\dots,n\\} \to \\{1,\dots,mn\\}$.
{{% /proposition %}}

{{% watch %}}
 En términos de la imagen inversa de conjuntos unitarios tenemos las siguientes equivalencias:

* $f$ es inyectiva si y sólo si para todo $y \in Y$, el conjunto
$f^{-1} (\\{ y \\})$ consta, a lo más, de un elemento.
* $f$ es sobre si y sólo si para todo $y \in Y$, el conjunto
$f^{-1} (\\{ y \\})$ consta, por lo menos, de un elemento (es decir, es no vacío).
* $f$ es biyectiva si y sólo si para todo $y \in Y$, el conjunto
$f^{-1} (\\{ y \\})$ consta, exactamente, de un elemento.

{{% /watch %}}

{{% watch %}}
 A partir de cualquier aplicación $f:X\to Y$ podemos definir una aplicación sobreyectiva $\widehat{f}: X \to \Imag(f)$ cuya acción sobre los elementos de $X$ coincide con la de $f$:  $\widehat{f}(x)= f(x)$ para cada $x\in X$. Aunque la acción de ambas aplicaciones está definida de la misma manera, debemos considerarlas en general como aplicaciones distintas, pues sus conjuntos de llegada son distintos. Tan sólo serán iguales cuando la aplicación $f$ de partida fuera sobreyectiva.
{{% /watch %}}

{{% definition %}}
{Composición de aplicaciones} {Dadas dos aplicaciones $f: X \longrightarrow Y$ y $g: Y
\longrightarrow Z$ se define la {\bf composición} de $f$ y $g$, notada
$g \circ f: X \longrightarrow Z$, que será una aplicación de $X$ en $Z$, como
$$
(g \circ f) (x) = g(f(x)), \mbox{ para todo } x \in X.
$$}
{{% /definition %}}


Obviamente $g \circ f$ es una aplicación. Es claro también que $g \circ 1_Y= g$ y $1_Y \circ f = f$.

{{% example name="Ejemplo" %}}
 1) Sean las aplicaciones $f: \Z \rightarrow \Q, \; g: \Q \rightarrow \RR$ definidas por
$$f(n) = \frac{n}{2},   \; g(x)=\sqrt{x^2+3} .$$
La composición de $f$ y $g$ es
$$g \circ f: \Z \rightarrow \RR \quad  \mbox{dada por} \quad (g \circ f)(n) = \sqrt{\left(\frac{n}{2}\right)^2+3},$$ pues
$$(g \circ f)(n) = g(f(n)) = g\left(\frac{n}{2}\right)=\sqrt{\left(\frac{n}{2}\right)^2+3}.$$


2) Sea $A$ un conjunto fijo y consideremos las aplicaciones
$$f,g: \mathcal{P}(U) \rightarrow \mathcal{P}(U) \quad \mbox{definidas por} \quad f(B)=A \cap B,g(B) = \overline{A} \cup B.$$ En este caso podemos calcular la composición de $f$ y $g$ y la composición de $g$ y $f$.

Calculamos $g \circ f:$
$$(g \circ f)(B) = g(f(B)) = g( A \cap B) = \overline{A} \cup (A \cap B) = (\overline{A} \cup A) \cap (\overline{A} \cup B) = U \cap (\overline{A} \cup B) = \overline{A} \cup B,$$
luego la composición de $f$ y $g$ es la aplicación
$$g \circ f: \mathcal{P}(U) \rightarrow \mathcal{P}(U), \quad (g \circ f)(B) = \overline{A} \cup B, \; \forall B \in \mathcal{P}(U).$$

Por otro lado, $f \circ g:$

$$(f \circ g)(B) = f(g(B)) = f( \overline{A} \cup B) = A \cap (\overline{A} \cup B) = (A \cap \overline{A}) \cup (A \cap B) = \varnothing \cup (A \cap B) = A \cap B,$$ luego la composición de $g$ y $f$ es
$$f \circ g: \mathcal{P}(U) \rightarrow \mathcal{P}(U), \quad (f \circ g)(B) = A \cap B, \; \forall B \in \mathcal{P}(U).$$

Nótese que $f \circ g \not= g \circ f.$

{{% /example %}}

{{% watch %}}
{\label{asociativa}} Dadas aplicaciones entre conjuntos
$$
X_1 \stackrel{f}{\longrightarrow} X_2 \stackrel{g}{\longrightarrow} X_3 \stackrel{h}{\longrightarrow} X_4,
$$
es elemental comprobar que $(h \circ g) \circ f = h \circ (g \circ f)$ (asociatividad de la composición de aplicaciones).

{{% /watch %}}

{{% definition %}}
{Aplicaciones invertibles} {Diremos que una aplicación $f : X \longrightarrow Y$ es {\bf invertible} cuando exista una aplicación $g : Y \longrightarrow X$ tal que
$$ g \circ f = 1_X,\quad f \circ g = 1_Y.$$}
{{% /definition %}}

{{% proposition %}}
 Si una aplicación $f : X \longrightarrow Y$ es invertible, la aplicación $g : Y \longrightarrow X$ tal que
$ g \circ f = 1_X$ y $ f \circ g = 1_Y$ es única.
{{% /proposition %}} 

A la aplicación $g$ de la proposición anterior se la denomina {\bf aplicación inversa} de $f$ y se denota por $f^{-1}: Y \longrightarrow X$.

{{% example name="Ejemplo" %}}
 1) La aplicación identidad $1_X: X \to X$ es invertible y su inversa es ella misma.

\noindent 2) La aplicación  $$f: \Z \rightarrow \Z \quad \mbox{definida por} \quad f(n)=n+3$$
es invertible y su inversa es la aplicación  $$f^{-1}: \Z \rightarrow \Z \quad \mbox{definida por} \quad  f^{-1}(m) = m-3.$$
{{% /example %}}

{{% proposition %}}
 Sea $f:X \rightarrow Y$ una aplicación. Las propiedades siguientes son equivalentes:
\begin{enumerate}
\item[(a)] $f$ es invertible.
\item[(b)] $f$ es biyectiva.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}
 (a) $\Rightarrow$ (b): Supongamos que $f$ es invertible y consideremos su aplicación inversa $f^{-1}$. Veamos que $f$ es biyectiva:

Inyectiva: si $f(a) = f(b),$ aplicando $f^{-1}$ tenemos $f^{-1}(f(a))=f^{-1}(f(b)),$ luego $a=b$ por ser  $f^{-1} \circ f = 1_X.$

Sobreyectiva: sea $y \in Y$ y consideremos $x=f^{-1}(y) \in X.$ Aplicando $f$ tenemos que $f(x) = f(f^{-1}(y)) = 1_Y(y) = y,$ luego $f$ es sobreyectiva.


\noindent (b) $\Rightarrow$ (a): 
Si $f$ es biyectiva, tomemos la aplicación $g:Y\to X$ definida del siguiente modo: para cada $y\in Y$, $g(y) = x$ siendo $x$ el único (pues $f$ es inyectiva) elemento de $X$ que verifica $f(x) = y$ (que existe, pues $f$ es sobreyectiva). 

Comprobamos sin dificultad que $g \circ f = 1_X$ y $f \circ g = 1_Y$, y por tanto $f$ es invertible.
{{% /proof %}}

{{% watch %}}
 \label{nota:notaciones_antiimag} Al igual que ocurría con la notación $f(\cdot)$ (ver Nota \ref{nota:f(?)}), cuando $f:X\to Y$ es una aplicación, la notación $f^{-1}(\cdot)$ se utiliza para dos situaciones distintas que pueden dar lugar a confusiones de fondo:
\begin{enumerate}
\item[i)] Cuando $B\subset Y$, $f^{-1}(B)$ denota la anti-imagen de $B$ por $f$, que es un \underline{subconjunto} de $X$.
\item[ii)] Cuando $f$ es invertible e $y\in Y$, $f^{-1}(y)$ indica la imagen de $y$ por la inversa de $f$, que es un \underline{elemento} de $X$.
\end{enumerate}
De hecho, tal como indicamos en la Nota \ref{nota:antiimag_unitarios}, la notación $f^{-1}(\cdot)$ es también utilizada en una tercera situación que puede confundirse fácilmente con ii).
Es pues fundamental saber en cada caso en qué situación estamos. En ii) estamos suponiendo que $f$ es invertible (o, equivalentemente, biyectiva), mientras que  i)  tiene sentido para cualquier aplicación $f$, invertible o no.
{{% /watch %}}

{{% definition %}}
{Restricción de una aplicación} {Dada una aplicación $f: X \longrightarrow Y$ y un subconjunto
$A\subset X$, se define la restricción de $f$ a $A$ como la
aplicación
\begin{eqnarray*}
f|_{A}: A & \longrightarrow & Y \\
x\in A & \longmapsto & f|_{A}(x) := f(x) \in Y
\end{eqnarray*}}
{{% /definition %}}

Esto es, $f|_{A}$ actúa exactamente como $f$, pero {\em sólo sobre
los elementos de $A$.} Nótese que la inclusión $i_A: A \longrightarrow X$ no es más que la restricción de la identidad $1_X$ a $A$, y que
la restricción $f|_{A}$ coincide con la composición de $f$ con la inclusión $i_A:A \to X$:
$$ f|_{A} = f \circ i_A.$$

{{% example name="Ejemplo" %}}
 Sean $A\subset U$ conjuntos fijos y consideremos la aplicación $f: \mathcal{P}(U) \rightarrow \mathcal{P}(U)$ definidas por $f(B)=A \cap B.$ La restricción de $f$ a $\mathcal{P}(A),$ $f: \mathcal{P}(A) \rightarrow \mathcal{P}(U)$ es
$$f|_{\mathcal{P}(A)}(B)=f(B)= A \cap B= B, \quad \mbox{ya que} \quad B \subset A.$$
{{% /example %}}

{{% example name="Ejemplo" %}}
 Veamos un ejemplo que pone de manifiesto la importancia de, a la hora de dar una aplicación, precisar
los conjuntos de partida y de llegada y no sólo cómo se determina la
imagen de cada elemento.

Consideremos $f:A \rightarrow B$ dada por $f(x)=x^2.$ Entonces:
\begin{itemize}
\item Si $A=B=\RR,$ la función anterior no es ni inyectiva ni sobreyectiva.

\item Si $A=\RR$ y $B= \RR_+$, $f$ es sobreyectiva y no inyectiva.

\item Si $A=[0,1]$ y $B= \RR$, $f$ es inyectiva y no sobreyectiva.

\item Si $A=B=[0,1],$ $f$ es biyectiva.
\end{itemize}
{{% /example %}}


## Conjuntos cociente

{{% definition %}}
{Relación} {Sea $A$ un conjunto. Una {\bf relación} $R$ definida en $A$ es una
correspondencia de $A$ en sí mismo.}
{{% /definition %}}

Dos relaciones $R$ y $R'$ en el conjunto $A$ son iguales si y sólo si $aRb \Leftrightarrow aR'b$:
$$ R = R' \Leftrightarrow ( aRb \Leftrightarrow aR'b).
$$

{{% example name="Ejemplo" %}}
 Sea $A= \\{ a,b,c \\}.$ Entonces $R= \\{(a,a), (a,c), (b,c)\\}$ es una relación en $A.$
{{% /example %}}

Si el par $(x,y) \in A \times A$ está en $R$, diremos que $x$
está $R$--relacionado con $y$, o que $x$ está relacionado con $y$ por $R$. Esto
se notará normalmente $xRy$ (nótese que el orden es
importante).

{{% definition %}}
{Algunas propiedades de una relación} {Sea $R$ una relación en $A$. Diremos que $R$ es:
\begin{enumerate}
\item[(a)] {\bf Reflexiva} cuando para todo $x \in A$ se tiene que $xRx$.
\item[(b)] {\bf Simétrica} cuando $xRy$ siempre implica $yRx$ (y por tanto $xRy \Leftrightarrow yRx$).
\item[(c)] {\bf Antisimétrica} cuando, si tenemos $xRy$ e $yRx$, entonces $x=y$
necesariamente.
\item[(d)] {\bf Transitiva} cuando, si tenemos $xRy$ e $yRz$, entonces se tiene $xRz$.
\end{enumerate}}
{{% /definition %}}

{{% definition %}}
{Relaciones de orden y de equivalencia}
{Las relaciones que son reflexivas, simétricas y transitivas se denominan
{\bf relaciones de equivalencia}. Las relaciones que son reflexivas,
antisimétricas y transitivas se denominan {\bf relaciones de orden}.}
{{% /definition %}}

{{% example name="Ejemplo" %}}

1) En el conjunto $\Z$ definimos las relaciones siguientes:
$$ xRy \; \Longleftrightarrow \; x \leq y, \quad
xSy \; \Longleftrightarrow \; x-y \mbox{ es par}, \quad xTy \;
\Longleftrightarrow \;x \; \mbox{divide a } \; y
$$
\noindent a) $R$ es una relación de orden (de hecho, las relaciones de
orden se denominan así por ser éste el ejemplo fundamental). En efecto:
\begin{itemize}
\item Reflexiva: $\forall n \in \Z$ se tiene que $ n \leq n,$ luego $nRn.$
\item Antisimétrica: Si $nRm$ y $mRn$ se tiene que $n \leq m$ y $m \leq n,$ luego $n=m.$
\item Transitiva: Si $nRm$ y $mRs$ es $n \leq m \leq s,$ luego $nRs.$
\end{itemize}

\noindent b) $S$ es una relación de equivalencia.
\begin{itemize}
\item Reflexiva: $\forall n \in \Z$ se tiene que $ n- n=0$ es par, luego $nSn.$
\item Simétrica: si $nSm$ es $n-m$ par, luego $m-n$ es par y, por tanto, $mSn.$
\item Transitiva: si $nSm$ y $mSp$ se tiene que $n-m$ y $m-p$ son pares. Sumando se tiene que $n-p$ es par, luego $nSp.$
\end{itemize}

\noindent c) $T$ no es ni de orden ni de equivalencia, pues $T$ no verifica la propiedad antisimétrica ni la simétrica.

Notemos que $S$ es de equivalencia si sustituimos la condición
"$x-y$ es par" por la condición "$x-y$ es múltiplo de $p$",
para cualquier número $p$ que fijemos con antelación.
%Esta relación se estudiará en profundidad más adelante.

\noindent 2) Sea $U$ un conjunto y $A \subset U$ un subconjunto fijo. En $\mathcal{P}(U)$ definimos la relación $\mathcal{R}_A:$
$$ \forall B,C \in \mathcal{P}(U), \quad B \mathcal{R}_A C \quad \mbox{si} \quad A \cap B = A \cap C.$$
Veamos que es una relación de equivalencia.
\begin{itemize}
\item Reflexiva: $\forall B \in \mathcal{P}(U)$, $A \cap B = A \cap B,$ es decir $B \mathcal{R}_A B.$
\item Simétrica: si $B \mathcal{R}_A C,$ es $A\cap B = A \cap C,$ luego $A \cap C = A \cap B$ y $C \mathcal{R}_AB.$
\item Transitiva: si $B \mathcal{R}_AC$ y $C \mathcal{R}_AD$ se tiene que $A\cap B = A \cap C = A \cap D,$ luego $B \mathcal{R}_A D.$
\end{itemize}

\noindent 3) En el conjunto $\Z$ la relación definida por el menor estricto, $ xRy \; \Longleftrightarrow \; x < y,$ {\em verifica} la propiedad antisimétrica ya que {\em no existe ningún par de enteros $n,m$} tales que $nRm$ y $mRn.$ La relación es también transitiva, pero no es reflexiva ni simétrica.
{{% /example %}}

{{% definition %}}
{Clase de equivalencia} {Si $R$ es una relación de equivalencia en $A$, denominamos
{\bf clase de equivalencia} de un elemento $x \in A$, que notaremos $R(x)$, o simplemente $\overline{x}$ (ó $[x]$) si no hay peligro de confusión y no es necesario precisar a $R$,  al conjunto de todos
los elementos de $A$ relacionados con $x$, esto es,
$$
R(x) = \overline{x} = [x] :=  \\{ y \in A \; | \; xRy \\} \left( =\\{ y \in A \; | \; yRx \\}   \right).
$$
}
{{% /definition %}}

{{% example name="Ejemplo" %}}
 Vamos a calcular las clases de equivalencia de las relaciones del ejemplo anterior.

\noindent 1) En $\Z$ consideramos la relación de equivalencia $S$, $nSm$ si $n-m$ es par. Sea $n$ un número par. Entonces $m \in \Z$ está relacionado con $n$ si $m-n=2k$ es par, luego $m=n+2k$ es par. Luego todos los elementos de la clase de equivalencia de $n$ son pares. Recí procamente, si $m$ es par se tiene que $n-m$ es par. Por tanto, la clase de equivalencia de $n$, $S(n)$, es el conjunto de todos los números pares.

Si $n$ es impar, es fácil ver que la clase de equivalencia $S(n)$ es el conjunto de todos los números impares.

Notar que si $n_1$ y $n_2$ son ambos números pares (impares) entonces $S(n_1) = S(n_2).$ De aquí  se sigue que en este ejemplo sólo tenemos dos clases de equivalencia, por ejemplo $S(0) = \\{ \mbox{enteros pares}\\}$ y $S(1) = \\{\mbox{enteros impares} \\}.$ Nótese también que $S(0) \cap S(1) = \varnothing$ y que $\Z = S(0) \cup S(1).$ En el teorema siguiente se probará que estas propiedades se verifican en cualquier relación de equivalencia.

\noindent 2) Calcularemos las clases de equivalencia de la relación, en $ \mathcal{P}(U)$, definida por: $\forall B, C \in \mathcal{P}(U)$, $B\mathcal{R}_A C$ si $A \cap B = A \cap C,$ siendo $A$ un conjunto fijo. Estudiaremos, primero, un caso particular que nos servirá para entender mejor el caso general. Supongamos que el conjunto $A$ que fijamos tiene sólo dos elementos, $A= \\{x,y\\}.$ Veamos que, en este caso, sólo existen 4 clases de equivalencia: $\mathcal{R}_A(\varnothing), \mathcal{R}_A(A), \mathcal{R}_A(\\{x\\})$ y $\mathcal{R}_A(\\{y\\}).$ En efecto: sea $B$ un conjunto cualquiera. Las posibilidades para $A \cap B$ son
\begin{itemize}
\item $A \cap B = \varnothing = A \cap \varnothing,$ de donde $B \mathcal{R}_A \varnothing$ y $B \in \mathcal{R}_A(\varnothing).$
\item $A \cap B = A = A \cap A,$ de donde $B \mathcal{R}_A A$ y $B \in \mathcal{R}_A(A).$
\item $A \cap B = \\{x\\} = A \cap \\{x\\},$ de donde $B \mathcal{R}_A \\{x\\}$ y $B \in \mathcal{R}_A(\\{x\\}).$
\item $A \cap B = \\{y\\} = A \cap \\{y\\},$ de donde $B \mathcal{R}_A \\{y\\}$ y $B \in \mathcal{R}_A(\\{y\\}).$
\end{itemize}

Observemos que en este ejemplo también se tiene que las cuatro clases anteriores no tienen ningún elemento en común y que la unión de todas ellas es $\mathcal{P}(U).$

Pasemos al caso general. Sea $A$ un conjunto cualquiera. Veamos que existen tantas clases de equivalencia como subconjuntos de $A$.

2-1) Si $A_1, A_2 \subset A$ son distintos, entonces $\mathcal{R}_A(A_1) \not= \mathcal{R}_A(A_2).$ En efecto: $A_1$ y $A_2$ no están relacionados ya que $A \cap A_1 = A_1 \not= A_2 = A \cap A_2.$

2-2) Todo conjunto $B$ pertenece a la clase de equivalencia de un subconjunto de $A.$ En efecto: basta tomar$A \cap B \subset A,$ entonces $A \cap (A \cap B)= (A \cap A) \cap B = A \cap B,$ luego $B \in \mathcal{R}_A(A \cap B).$
{{% /example %}}

Hemos visto en los ejemplos anteriores que las clases de equivalencia distintas no tienen ningún elemento
en común, y que la unión de todas la clases es el conjunto total. Veamos que esta es una propiedad de cualquier relación de equivalencia, pero antes daremos una nueva noción.

{{% definition %}}
{Particiones de un conjunto}{Dado un conjunto $A\neq \varnothing$, una {\bf partición} de $A$ es un subconjunto $\mathcal{Q} \subset \mathcal{P}(A)$ (los elementos de $\mathcal{Q}$ son subconjuntos de $A$) que verifica las siguientes propiedades:
\begin{enumerate}
\item[(a)] Todos los elementos de $\mathcal{Q}$ son no vací os.
\item[(b)] La unión de todos los elementos de $\mathcal{Q}$ es $A$.
\item[(c)] Los elementos de $\mathcal{Q}$ son disjuntos entre sí.
\end{enumerate}
O expresado simbólicamente, 
\begin{enumerate}
\item[(a)] $\forall B\in \mathcal{Q}$ se tiene $B\neq \varnothing$ (ó equivalentemente: $\varnothing \notin \mathcal{Q}$).
\item[(b)] $\bigcup \mathcal{Q} =A$ (ó escrito de otro modo: $\forall x\in A$, $\exists B\in \mathcal{Q}$ tal que $x\in B$)\footnote{Nótese que la inclusión $\bigcup \mathcal{Q} \subset A$ siempre se tiene puesto que $\mathcal{Q} \subset \mathcal{P}(A)$.}.
\item[(c)] Si $B,C\in \mathcal{Q}$ y $B\neq C$, entonces $B\cap C=\varnothing$. 
\end{enumerate}
}
{{% /definition %}}

La idea que hay detrás de una partición de un conjunto $A$ (no vacío) es muy sencilla: se trata de una descomposición de $A$ en subconjuntos no vac\'ios y disjuntos.

{{% theorem %}}
 {Las clases de equivalencia como una partición}{Sea $A$ un conjunto y $R$ una relación de equivalencia en
$A$. Entonces el conjunto de las clases de equivalencia de los elementos de $A$ es una partición de $A$.}
{{% /theorem %}}

{{% proof %}}
 La propiedad reflexiva implica que cada elemento $a\in A$ pertenece a su clase de equivalencia, por tanto cada clase de equivalencia es no vacía (propiedad (a)) y la unión de todas las clases de equivalencia es $A$ (propiedad (b)). Para
probar (c) supongamos que tenemos dos clases de equivalencia $R(x)$
y $R(y)$ de tal forma que existe $z \in R(x) \cap R(y)$. Tenemos que
demostrar entonces que $R(x) = R(y)$, y lo haremos por doble
inclusión. De hecho, sólo probaremos que $R(x) \subset R(y)$,
porque la otra inclusión es absolutamente análoga.

Tomamos entonces $a \in R(x)$. Como $z \in R(x)$, tenemos que $aRx$
y $xRz$, por lo que $aRz$. De la misma forma, como $z \in R(y)$, se
verifica que $zRy$. Así tenemos $aRy$, luego $a \in R(y)$.

Observemos que para demostrar (c) hemos usado tanto la propiedad simétrica como la
transitiva de $R$.
{{% /proof %}}

{{% corollary %}}
 Sea $A$ un conjunto, $R$ una relación de equivalencia en
$A,$ $x,y \in A.$ Se tiene que las clases de equivalencia de $x$ y de $y$ son iguales, $R(x) = R(y)$, si y sólo si $xRy.$
{{% /corollary %}}

{{% definition %}}
{Conjunto cociente} {Dada una relación de equivalencia $R$ definida sobre un
conjunto $A$, el conjunto cuyos elementos son las clases de
equivalencia de $A$ por $R$ se denomina {\bf conjunto cociente} de $A$ por
$R$. La notación usual es
$$
A/R = \\{ R(x) \; | \; x \in A \\}.
$$
El conjunto cociente va acompañado de la aplicación 
$$\pi: X \to X/R,\quad \pi(x)=R(x)\  \mbox{ para todo }\ x\in X,$$
que se denomina {\bf aplicación cociente}, o también {\bf proyección natural}, asociada a la relación R. 
}
{{% /definition %}}

El conjunto cociente de $A$ por $R$ es por tanto una partición de $A$. En particular $A/R$ es un subconjunto de $\mathcal{P}(A)$. La proyección natural $\pi: X \to X/R$ es por construcción una aplicación sobreyectiva.


{{% example name="Ejemplo" %}}
 Veamos los conjuntos cocientes de los ejemplos anteriores.

a) Sea la relación de equivalencia $S$, en $\Z$, dada por $nSm$ si $n-m$ es par. Entonces $$\Z / S = \\{S(0), S(1) \\}$$

En general, si fijamos un entero $p$ y consideramos
$$
xSy \; \Longleftrightarrow \; x-y \mbox{ es múltiplo de } p,
$$
se tiene que, para todo $x \in \Z$
$$
S(x) = \\{ y \in \Z \; | \; \mbox{ $x$ e $y$ dan el mismo resto al
dividirlos entre $p$} \\},
$$
por lo que
$$
\Z/S = \\{ S(0),S(1),...,S(p-1) \\}.
$$

b) Consideremos la relación de equivalencia, en $\mathcal{P}(U)$, definida por: $$\forall B, C \in \mathcal{P}(U), \quad B\mathcal{R} C \quad \mbox{si} \quad A \cap B = A \cap C,$$ siendo $A$ un conjunto fijo. En este caso
$$\mathcal{P}(U) / \mathcal{R} = \\{ \mathcal{R}(D) \; | \; D \in \mathcal{P}(A) \\}.$$

{{% /example %}}


### Factorización canónica de una aplicación

La proyección natural $\pi\colon X\to X/R$ verifica la siguiente "propiedad universal".

{{% proposition %}}
 (Propiedad universal de la proyección canónica) Sean $X,Y$ conjuntos no vacíos, $R$ una relación de equivalencia en $X$ y $f\colon X\to Y$ una aplicación. Si se tiene 
$$ a R b \Rightarrow f(a) =f(b),
$$
entonces \underline{existe una única aplicación} $F\colon X/R\to Y$ tal que $f=F\circ\pi$, es decir, tal que el siguiente diagrama es conmutativo:
\[\xymatrix{X\ar[r]^-{f}\ar[d]_-\pi& Y.\\
		X/R \ar@{-->}[ru]^-{F}}
		\]   
{{% /proposition %}}

Hemos visto que toda relación de equivalencia $R$ en un conjunto $X$ da lugar a un nuevo conjunto, el conjunto cociente $X/R$, y a una aplicación, la proyección natural $\pi:X\longrightarrow X/R$. Ahora vamos a ver que cualquier aplicación entre dos conjuntos permite definir una relación de equivalencia especial en el conjunto de partida.

{{% definition %}}
{Relación asociada a una aplicación}
{Dada una aplicación $f\colon X\to Y$, definimos la relación asociada a $f$, que notaremos $R_f$, de la siguiente forma: para $a, b\in X$
$$a R_f b\Leftrightarrow f(a)=f(b).$$}
{{% /definition %}}

Dejamos la demostración de la siguiente proposición como ejercicio.

{{% proposition %}}

La relación $R_f$ asociada a una aplicación es una relación de equivalencia.
{{% /proposition %}}

{{% watch %}}
 Nótese que toda relación de equivalencia $R$ en un conjunto $X$ es de hecho la relación de equivalencia asociada a una cierta aplicación, a saber, a la proyección natural $\pi: X \longrightarrow X/R$, pues sabemos que $xRy \Leftrightarrow R(x) = R(y) \Leftrightarrow \pi(x) = \pi(y)$, y por tanto $R = R_\pi$.
{{% /watch %}}


{{% theorem %}}
{Factorización canónica de una aplicación \label{factorcan}}
{Toda aplicación $f\colon X\to Y$ se descompone de manera canónica como composición $f=i\circ {\bar f}\circ\pi$, 
\[\xymatrix{X\ar[r]^-{f}\ar[d]_-\pi& Y\\
		X/R_f\ar[r]^-{\bar f}& \Imag(f)\ar[u]_-i}\]
donde $\pi$ es la proyección canónica, $i$ es la inclusión de $\Imag(f)$ en $Y$ y ${\bar f}\colon X/R_f\to\Imag (f)$ es la \underline{única} aplicación que hace conmutativo el diagrama anterior, que viene dada por ${\bar f}(R_f(x))=f(x)$.
Además, la aplicación ${\bar f}$ es biyectiva y por tanto 
toda aplicación entre dos conjuntos se descompone canónicamente como composición de una aplicación inyectiva, una aplicación biyectiva y una aplicación sobreyectiva. }
{{% /theorem %}}

El conjunto cociente de un conjunto $A$ por una relación de equivalencia $R$ es una construcción matemática abstracta y en ejemplos concretos nos resulta a veces conveniente "describirlo" de manera más palpable. Esto se puede hacer fundamentalmente de dos modos:
\begin{enumerate}
\item[a)] Encontrando un subconjunto explícito $A' \subset A$ de manera que cada clase de equivalencia de $A$ por $R$ tenga algún representante en $A'$, y que dos elementos distintos de $A'$ no estén relacionados por $R$, o dicho de manera más formal, que la composición de las aplicaciones
\begin{equation*}
\begin{CD}
A' @>{i_{A'}}>{\text{inclusión}}> A @>{\pi}>{\text{proyección canónica}}> A/R
\end{CD}
\end{equation*}
sea una aplicación biyectiva.
\item[b)] Encontrando un conjunto "conocido" $Y$ y una aplicación sobreyectiva  $f:A \longrightarrow Y$ tal que $R = R_f$. En este caso, la factorización canónica de $f$ nos proporciona una biyección $\overline{f}:A/R \xrightarrow{\sim} Y$.
\end{enumerate}
En ambos casos encontramos una biyección entre el conjunto cociente $A/R$, que es un conjunto abstracto, y un conjunto "conocido", $A'$ en el primer caso e $Y$ en el segundo, que nos sirve para "describir" (o "etiquetar") a las clases de equivalencia de $A$ por $R$.

{{% example name="Ejemplo" %}}
 Sea $A=\R$ el conjunto de los números reales y consideremos la relación de equivalencia en $\R$ dada por:
$$  a R b \stackrel{\text{def.}}{\Leftrightarrow} a^2 = b^2.
$$
Siguiendo el modo a) que acabamos de explicar, podemos tomar por ejemplo 
$ A' = \\{ a\in \R \; |\; a\geq 0\\} = [0,+\infty)$. También serviría $ A' = \\{ a\in \R \; |\; a\leq 0\\} = (-\infty,0]$, o incluso
$A' = (-\infty,-1] \cup [0,1)$.


Si seguimos el modo b), podemos tomar $Y=[0,+\infty)$ y $f:\R \longrightarrow [0,+\infty)$ dada por $f(a) = a^2$ para todo $a\in \R$.

{{% /example %}}


## Finitud

Uno de los aspectos que caracterizan a las Matemáticas dentro de las ciencias es el tratamiento riguroso del concepto de {\bf infinito}. De hecho, esto se hace a través de la Teoría de conjuntos y fue precisamente una de las motivaciones principales de Georg Cantor para desarrollar dicha teoría.


En esta sección vamos a dar una introducción a este tema, evitando entrar en detalles técnicos que requerirían un conocimiento más profundo de la Teoría axiomática de conjuntos.


Nuestros prototipos de conjuntos finitos son los de la forma  $\\{1,2,\dots, n\\}$, donde  $n$ es un número natural mayor o igual que $ 1$. Pero en Matemáticas, uno de los conjuntos más importantes, el de los números naturales 
$$\N =\\{0,1,2,3,\dots \\},
$$
cae fuera de los primeros. Se trata de hecho del primer contacto que tenemos con la noción de "infinito".

Otra de las nociones más usadas en la práctica es la de "cantidad" o "número de elementos" de un conjunto finito. Por ejemplo, el conjunto $\\{1,2,\dots, n\\}$ tiene $n$ elementos.

Pero en lugar de comenzar por darle sentido a la "cantidad de elementos" de un conjunto, vamos a comenzar por dar sentido a que dos conjuntos tengan "la misma cantidad de elementos", sin saber qué es la cantidad de elementos de un conjunto.

{{% definition %}}
{Conjuntos equipotentes}{
Decimos que dos conjuntos $X$ e $Y$ son {\bf equipotentes} si existe una aplicación \underline{biyectiva} $f:X\to Y$.}
{{% /definition %}}

Es fácil ver que la relación de equipotencia es una relación de equivalencia en cualquier "conjunto de conjuntos".

{{% proposition %}}
 \label{prop:aplicaciones_entre_m_y_n} Sean dos números enteros $m,n\geq 1$ y sea $f:\\{1,\dots,m\\} \to \\{1,\dots,n\\}$ una aplicación. Se tienen las siguientes propiedades:
\begin{enumerate}
\item Si $f$ es inyectiva, entonces $m\leq n$.
\item Si $f$ es sobreyectiva, entonces $m\geq n$.
\item Si $f$ es biyectiva, entonces $m=n$.
\end{enumerate}
Además, si $m=n$, las propiedades siguientes son equivalentes:
\begin{enumerate}
\item[(a)] $f$ es inyectiva.
\item[(b)] $f$ es sobreyectiva.
\item[(c)] $f$ es biyectiva.
\end{enumerate}
{{% /proposition %}} 

{{% proof %}}
 La prueba se deja como ejercicio.
{{% /proof %}}

{{% proposition %}}
 \label{prop:subconj_m} Sea un número entero  $m\geq 1$ e $Y\subset \\{1,\dots,m\\}$ un subconjunto no vacío. Entonces existe un entero $n\geq 1$ y una aplicación biyectiva $f:\\{1,\dots,n\\} \to Y$. Además, por la proposición anterior se debe tener $n\leq m$.
{{% /proposition %}}

{{% proof %}}
 La prueba se deja como ejercicio.
{{% /proof %}}

{{% corollary %}}
 \label{cor:sobre_finito} Sea un número entero $m\geq 1$, $Y\subset \\{1,\dots,m\\}$ y supongamos que existe una aplicación sobreyectiva $f: Y \to \\{1,\dots,m\\}$. Entonces $Y= \\{1,\dots,m\\}$.
{{% /corollary %}}

{{% proof %}}
 Es una consecuencia inmediata de las dos proposiciones anteriores.
{{% /proof %}}

Para tratar matemáticamente a las nociones de "conjunto finito" y de "conjunto infinito" debemos dar definiciones formales de ellas.

{{% definition %}}
{Conjuntos finitos y conjuntos infinitos}{
Decimos que un conjunto $X$ es {\bf finito} si o bien es vacío, o si no es vacío, existe un número natural $n\geq 1$ tal que $X$ es equipotente a $\\{1,2,\dots, n\\}$.

\noindent Decimos que un conjunto $X$ es infinito, si $X$ es equipotente a algún subconjunto propio de $X$, i.e. a algún $Y\subset X$ con $\varnothing \neq Y \neq X$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}
 (1) Para cada número natural $n\geq 1$, el conjunto $\\{1,2,\dots, n\\}$ es finito (según la definición anterior).

\noindent (2) El conjunto de los números naturales $\N$ es infinito, pues $\N$ es equipotente a $\N_+$:
$$ f: \N \to \N_+,\quad f(x) = x+1,$$
es una aplicación biyectiva, y $\N_+$ es un subconjunto propio de $\N$.

\noindent (3) Si $X$ es un conjunto finito (resp. infinito) e $Y$ es un conjunto equipotente a $X$, entonces $Y$ es también un conjunto finito (resp. infinito).
{{% /example %}}

La proposición siguiente nos garantiza que las definiciones dadas de de conjunto finito y de conjunto infinito son excluyentes y cubren todos los casos.

{{% proposition %}}
 \label{prop:finito_vs_infinito} Sea $X$ un conjunto. Las propiedades siguientes son equivalentes:
\begin{enumerate}
\item[(a)] $X$ es un conjunto finito.
\item[(b)] $X$ no es un conjunto infinito.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}
  (a) $\Rightarrow$ (b): Se prueba sin mucha dificultad a partir del Corolario \ref{cor:sobre_finito}.


\noindent (b) $\Rightarrow$ (a): es equivalente a probar que si $X$ no es finito, entonces $X$ es infinito. 

Supongamos que $X$ no es finito, es decir, no es vacío y no es posible establecer una aplicación biyectiva entre $X$ y ningún conjunto de la forma $\\{1,2,\dots, m\\}$, con $m\geq 1$. Como $X\neq \varnothing$, podemos encontrar un elemento $x_1\in X$. Sea $f_1:\\{1\\} \to X$ la aplicación inyectiva definida por $f_1(1)=x_1$. Como $X$ no es finito, la aplicación $f$ no puede ser sobreyectiva y por tanto podremos encontrar un $x_2\in X$ que no pertenece a la imagen de $f_1$. Consideremos la aplicación $f_2: \\{1,2\\} \to X$ que extiende a $f_1$ y tal que $f_2(2)=x_2$. Por la misma razón anterior $f_2$ no puede ser sobreyectiva.

Continuando con este proceso definimos una familia de aplicaciones 
$$ f_n: \\{1,\dots, n\\} \to X,\quad n\in\N,
$$
todas ellas inyectivas, que cada una prolonga a la anterior, es decir $f_n|_{\\{1,\dots, n-1\\}} = f_{n-1}$. Con esta familia construimos una aplicación $f:\N \to X$ de la siguiente forma:
$$ f(n) = f_n(n)\quad \text{\ para cada\ }\ n\in \N.
$$
Se prueba sin dificultad que $f$ es inyectiva, y como $\N$ es infinito, concluimos aplicando la Proposición \ref{prop:finito_infinito}, 3)\footnote{En esta prueba hemos utilizado un axioma de la Teoría axiomática de conjuntos denominado el "axioma de elección numerable". Al tratarse de una introducción a la Teoría de conjuntos, no entraremos en más detalles.}.
{{% /proof %}}

En la siguiente proposición damos las principales propiedades que se deducen de las definiciones dadas de conjunto finito y de conjunto infinito. Con ellas comprobamos
que dichas definiciones modelizan correctamente las ideas intuitivas previas que teníamos de estas nociones.

{{% proposition %}}
 \label{prop:finito_infinito}  Se tienen las siguientes propiedades:
\begin{enumerate}
\item[1)] Si $X$ es un conjunto finito y $f:X \to Y$ es una aplicación sobreyectiva, entonces $Y$ también es un conjunto finito.
\item[2)] Si $Y$ es un conjunto finito y $f:X \to Y$ es una aplicación inyectiva, entonces $X$ también es un conjunto finito.
\item[3)] Si $X$ es un conjunto infinito y $f:X \to Y$ es una aplicación inyectiva, entonces $Y$ también es un conjunto infinito.
\item[4)] Si $Y$ es un conjunto infinito y $f:X \to Y$ es una aplicación sobreyectiva, entonces $X$ también es un conjunto infinito.
\item[5)] El producto cartesiano de dos conjuntos finitos es un conjunto finito.
\item[6)] $X$ es un conjunto finito si y sólo si $\mathcal{P}(X)$ es un conjunto finito.
\item[7)] $X$ es un conjunto infinito si y sólo si $\mathcal{P}(X)$ es un conjunto infinito.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}
 Nos limitaremos a dar algunas indicaciones.

\noindent 1): Podemos restringirnos al caso en que $X= \\{1,\dots,m\\}$ con $m\geq 1$. Definimos $g:Y \to X= \\{1,\dots,m\\}$ de la siguiente forma: para cada $y\in Y$
$$ g(y) := \min f^{-1} (\\{y\\}) \in X.$$
Se prueba sin dificultad que $f\circ g = 1_Y$, por lo que $g$ es inyectiva e $Y$ será equipotente a $\Imag(g)\subset X= \\{1,\dots,m\\}$. Concluimos aplicando la Proposición \ref{prop:subconj_m}.


\noindent 2): Es una consecuencia casi inmediata de la Proposición \ref{prop:subconj_m}.



\noindent 3): Basta probar que si $X\subset Y$ con $X$ conjunto infinito, entonces $Y$ también es infinito. 

Como $X$ es infinito, existe un subconjunto propio $X'\subsetneq X$ y una aplicación biyectiva $f:X'\to X$. Es claro que $Y':= X' \cup (Y\setminus X) $ es un subconjunto propio de $Y$, y que la aplicación $g: Y' \to Y$ definida por
$$ g(y) = \left\\{ \begin{array}{ccl} f(y) & \text{si} & y\in X'\\
 y & \text{si} & y\in Y\setminus X \end{array} \right.
$$
es biyectiva. Por tanto $Y$ es equipotente a un subconjunto propio y concluimos que $Y$ es infinito. 


\noindent 4): Por reducción al absurdo. Si $X$ fuera finito, deduciríamos que $Y$ también es finito por 1), lo que contradice que $Y$ sea infinito de acuerdo con la Proposición \ref{prop:finito_vs_infinito}.


\noindent 5): Es fácil a partir de la Proposición \ref{prop:mn}.


\noindent 6) y 7): Una idea fundamental es que siempre hay una aplicación inyectiva de $X$ en $\mathcal{P}(X)$:
$$ x\in X \longmapsto  \\{x\\} \in \mathcal{P}(X).
$$
Por tanto, si $X$ es infinito, $\mathcal{P}(X)$ también es infinito (aplicar 3)), y si $\mathcal{P}(X)$ es finito, $X$ también es finito (aplicar 2)).

Para probar $X$ finito $\Rightarrow$ $\mathcal{P}(X)$ finito, 
basta considerar el caso en que $X=\\{1,\dots, m\\}$, con $m\geq 1$. En este caso se procede por inducción probando primeramente que
los conjuntos
$$ \mathcal{P}(\\{1,\dots, n+1\\}) \quad \text{\ y\ }\quad \mathcal{P}(\\{1,\dots, n\\}) \times \\{0,1\\}
$$
son equipotentes.

Por último, si $\mathcal{P}(X)$ fuera infinito, $X$ no podría ser finito y entonces ha de ser infinito por la Proposición \ref{prop:finito_vs_infinito}.
{{% /proof %}}

{{% definition %}}
{Cardinal de un conjunto finito}{Si $X$ es un conjunto finito, o bien es vacío, en cuyo caso decimos que su {\bf cardinal} es $0$, o si no es vacío, existe un entero $n\geq 1$ tal que $X$ es equipotente a $\\{1,\dots,n\\}$. De acuerdo con la Proposición \ref{prop:aplicaciones_entre_m_y_n}, este entero $n$ es único y lo llamaremos {\bf cardinal} de $X$.

El cardinal de un conjunto finito $X$ se denotará por $\sharp(X)$, o también $|X|$ si no hay peligro de confusión con otras notaciones al uso.
}
{{% /definition %}}

{{% watch %}}
 Una de las primeras sorpresas que trajo el estudio matemático de los conjuntos infinitos es que "no todos los infinitos son iguales", o dicho de modo más preciso, no todos los conjuntos infinitos son equipotentes. De hecho, Cantor probó mediante su conocido "método diagonal" que los conjuntos $\N$, de los números naturales, y $\RR$, de los números reales, no son equipotentes. Más generalmente, ningún conjunto $X$ es equipotente al conjunto de sus partes $\mathcal{P}(X)$, lo que nos proporciona "infinitos tipos de infinito". Todo esto lleva a la {\bf Teoría de cardinales} (y de {\bf ordinales}), que no abordaremos en estas notas.
{{% /watch %}}

Para terminar este tema, veamos una prueba de que ningún conjunto $X$ es equipotente al conjunto de sus partes $\mathcal{P}(X)$, así como una ilustración del método diagonal de Cantor.

{{% proposition %}}
 Si $X$ es un conjunto cualquiera, no existe ninguna aplicación sobreyectiva $\varphi: X 
\longrightarrow \mathcal{P}(X)$.
{{% /proposition %}}

{{% proof %}}
 
Sea $\varphi: X \longrightarrow \mathcal{P}(X)$ una aplicación arbitraria. Veamos que $\varphi$ nunca puede ser sobreyectiva. La idea fundamental consiste en considerar el siguiente subconjunto de $X$:


\centerline{\framebox{$ A:=\\{ x\in X\, |\, x\notin \varphi(x)\\} \subset X.
$}}


Como $A\subset X$ se tiene que $A\in \mathcal{P}(X)$. Veamos que $A$ no pertenece a la imagen de $\varphi$.

Procederemos por reducción al absurdo. Si $A\in \Imag (\varphi)$, entonces existirá un $x_0\in X$ tal que $\varphi(x_0)=A$

Nos preguntamos ahora si $x_0\in A$. Lo que está claro es que o bien $x_0\in A$ o bien $x_0\notin A$.


\noindent Si $x_0\in A$, de acuerdo con la definición de $A$ tendríamos que $x_0\notin \varphi(x_0)$, y como $\varphi(x_0) =A$, concluimos $x_0\notin A$, lo cual es un absurdo.


\noindent Si $x_0\notin A$, como $A=\varphi(x_0)$ tendríamos que $x_0\notin \varphi(x_0)$, y de acuerdo con la definición de $A$ concluimos que $x_0\in A$, lo cual es un absurdo.


En ambos casos llegamos a un absurdo, por lo que nuestra suposición es falsa y por tanto $A\notin \Imag (\varphi)$ y por tanto $\varphi$ no es sobreyectiva
{{% /proof %}}

{{% proposition %}}
 No existe ninguna aplicación sobreyectiva $\varphi: \N \longleftarrow \N^\N$.
{{% /proposition %}}

{{% proof %}}
  Sea  $\varphi: \N \longleftarrow \N^\N$ una aplicación. Veamos que $\varphi$ nunca podrá ser sobreyectiva. La idea fundamental es considerar cualquier $f\in \N^\N$ (i.e. cualquier aplicación $f:\N \to \N$) que verifique lo siguiente:
$$  f(n) \neq \varphi(n)(n)\quad \forall n\in \N.
$$
Por ejemplo, podemos tomar $f:\N \to \N$ definida por $f(n) = \varphi(n)(n) + 1$.

Vemos fácilmente que $f$ no pertenece a la imagen de $\varphi$, puesto que si existiera $n_0\in \N$ tal que $f=\varphi(n_0)$ se tendría que 
$$ f(n) = \varphi(n_0)(n)\quad \forall n\in \N,
$$
y en particular $f(n_0) = \varphi(n_0)(n_0)$, lo cual contradice la propiedad con la que hemos elegido $f$. Así pues $\varphi$ no es sobreyectiva.
{{% /proof %}}

{{% watch %}}

Nótese que las pruebas de las dos proposiciones anteriores son muy similares y ambas responden al 
"método diagonal" de Cantor. Para apreciar mejor la similitud de ambas pruebas, podemos tener en cuenta que de hecho la segunda proposición es un corolario de la primera, pues sabemos que hay una biyección natural entre $\mathcal{P}(\N)$ y $\\{0,1\\}^\N$, y por otra parte es fácil encontrar una aplicación sobreyectiva $\N^\N \to \\{0,1\\}^\N$ (para ello basta tomar la composición con cualquier aplicación sobreyectiva $\N \to \\{0,1\\}$), de manera que si existiera alguna aplicación sobreyectiva $\N \to \N^\N$, componiéndola con la aplicación sobreyectiva $\N^\N \to \\{0,1\\}^\N$, obtendríamos una aplicación sobreyectiva $\N \to \\{0,1\\}^\N$, lo que contradeciría la primera proposición.
{{% /watch %}}

-->
