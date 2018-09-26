+++
title = "Conjuntos"
weight = 10
+++


## Construcciones básicas

Comenzaremos dando una noción intuitiva de uno de los conceptos matemáticos más utilizados: el de conjunto. Sin embargo no daremos una definición rigurosa. ¿Sabes por qué?

{{% definition %}}
Un **conjunto** es una colección de **elementos**. Normalmente están caracterizados por compartir alguna propiedad. Para que un conjunto esté bien definido debe ser
posible discernir si un elemento arbitrario está o no en él.
{{% /definition %}}

Los conjuntos pueden definirse de manera **explícita**, citando todos
los elementos de los que consta *entre llaves*, 
$$
A = \\{ 1,2,3,4,5 \\},
$$
o **implícita**, dando una o varias características que
determinen si un elemento dado está o no en el conjunto, 
$$
A = \\{ \text{números naturales del }1\text{ al }5\\}.
$$

{{% watch %}}
Los elementos de un conjunto *no están ordenados*, aunque vengan especificados como una lista, por tanto $A=\\{3,1,2,5,4\\}$. En una definición explícita *no se pueden repetir elementos*, así que $\\{1,1,2,3,4,5\\}$ sería una manera incorrecta de expresar el conjunto $A$.
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
También se puede denotar $A\subset B$ como $A\subseteq B$. Hay que tener cuidado con la negación de estos dos símbolos. Tanto $A\not\subset B$ como $A\not\subseteq B$ significan que $A$ no está contenido en $B$, o no es un subconjunto de $B$. Sin embargo $A\subsetneq B$ solo niega la igualdad, por lo que significa que $A$ es un subconjunto de $B$ pero que $A$ no es igual a $B$, es decir, la contención es **estricta**. Por ejemplo, $\\{2,3,5\\}\subsetneq\\{1,2,3,4,5\\}$.
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

{{% watch %}}
Cualquier enunciado matemático debe venir seguido de una prueba. Se usan diversos términos para denominar a los enunciados matemáticos, de acuerdo con la percepción que tengamos de su importancia o dificultad. De mayor a menor:

* Teorema.
* Proposición.
* Lema.
* Corolario.

Los lemas suelen tener un carácter técnico y presentarse como pasos intermedios en la demostración de un resultado de mayor envergadura. Los corolarios se enuncian habitualmente después de un resultado más importante y su prueba suele ser obvia y omitirse.
{{% /watch %}}

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
Dado un conjunto $I$, una **familia de conjuntos** indexada por $I$ consiste en dar un conjunto $A_i$ para cada $i\in I$. Se denota como $\\{ A\_i \\}\_{i\in I}$.

La **intersección** de una familia de conjuntos se define como $\bigcap_{i\in I}A_i=\\{x|\forall i\in I, x\in A_i\\}$.
{{% /definition %}}

Si $I$ es finito, esta definición coincide con la anterior, basta enumerar los elementos de $I$ para comprobarlo. Esta definición es también válida para $I$ infinito.


{{% definition %}}
Dos conjuntos $A$ y $B$ son **disjuntos** si $A \cap B = \varnothing$.
{{% /definition %}}

![Disjuntos](../images/disjoint.png)

{{% definition %}}
Dados dos conjuntos $A$ y $B$ la **unión** $A \cup B$ es el conjunto formado por aquellos elementos
que pertenecen al menos a uno de estos dos conjuntos, $A \cup B = \\{ x  |  x \in A  \vee  x  \in B \\}$.
{{% /definition %}}

![Unión](../images/union.png)

Observa que $A\cap B\subset A\cup B$.

{{% remark %}}
Si $A\subset C$ y $B\subset C$ entonces $A\cup B\subset C$.
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
La **unión** de una familia de conjuntos $\\{ A\_i \\}\_{i\in I}$ se define como $\bigcup_{i\in I}A_i=\\{x\;|\;\exists i\in I| x\in A_i\\}$.
{{% /definition %}}

Igual que antes, si $I$ es finito, esta definición coincide con la anterior, pero es también válida para $I$ infinito.


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


{{% theorem name="Leyes distributivas" %}}
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
Dado un conjunto $A$, el **conjunto de las partes** de $A$ es $\mathcal{P}(A)=\\{$subconjuntos de $A\\}$.
{{% /definition %}}

{{% watch %}}
$B\subset A\Leftrightarrow B\in\mathcal{P}(A)$.
{{% /watch %}}

{{% example name="Las partes de $A = \\{ 1,2,3 \\}$" %}}
$\mathcal{P}(A) = \\{\varnothing, \\{ 1 \\},  \\{ 2 \\},  \\{ 3 \\}, \\{1,2\\},  \\{1,3\\},  \\{2,3\\}, A \\}$.
{{% /example %}}

{{% exercise %}}
Si $A$ es un conjunto con $n$ elementos, ¿cuántos elementos tiene $\mathcal{P}(A)$? ¿Qué ocurre si $A$ es infinito? ¿Es posible que $\mathcal{P}(A)$ sea vacío? ¿Y unitario?
{{% /exercise %}}

{{% definition %}}
En una situación concreta, un **conjunto universal** $U$ es el que contiene a todos los posibles conjuntos del problema que tratamos.
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




## Producto cartesiano y aplicaciones

{{% definition %}}
El **producto cartesiano** de dos conjuntos $A$ y $B$ es el conjunto $A\times B$ cuyos elementos son los **pares ordenados** $(a,b)$ cuya primera **coordenada** está en $A$, $a\in A$, y la segunda en $B$, $b\in B$, es decir $A \times B = \\{ (a,b)  |  a \in A \wedge b \in B \\}$.
{{% /definition %}}

{{% example name="Un producto cartesiano" %}}
Si $A= \\{ 1,2,3 \\}$ y $B=\\{a,b\\}$ entonces $A \times B=\\{(1,a), (1,b), (2,a), (2,b), (3,a), (3,b)\\}$.
{{% /example %}}

{{% remark %}}
El vacío hace el papel de cero $A \times \varnothing = \varnothing = \varnothing \times B$. 
{{% /remark %}}

{{% watch %}}
En general, el producto cartesiano no es conmutativo $A\times B\neq B\times A$. 
{{% /watch %}}

{{% exercise %}}
Si $A$ y $B$ son finitos, ¿cuántos elementos tiene $A\times B$?
{{% /exercise %}}

{{% remark %}}
Análogamente, podemos definir el **producto cartesiano** de una cantidad finita de conjuntos $A\_1\times\cdots\times A\_n$ como el formado por las **$n$-uplas** $(a\_1,\dots, a\_n)$ tales que $a\_i\in A\_i$. Más generalmente,  podemos definir el producto cartesiano de una familia arbitraria de conjuntos $\\{A\_i\\}\_{i\in I}$, $\prod\_{i\in I}A\_i=\\{(a\_i)\_{i\in I}|a\_i\in A\_i\\}$.
{{% /remark %}}



{{% definition %}}
Dados dos conjuntos $A$ y $B$, una **correspondencia** $C$ de $A$ en $B$ es un subconjunto $C\subset A \times B$.
{{% /definition %}}

Las correspondencias se suelen representar del siguiente modo

![Correspondence](../images/correspondence.png)

Esta correspondencia es $C=\\{(1,a), (1,b), (2,b), (3, b)\\}\subset A\times B$. Pensamos en las correspondencias como reglas que asocian elementos del segundo conjunto a elementos del primero. En este ejemplo al $1$ se le asocian el $a$ y el $b$, y al $2$ y al $3$ solo el $b$. Al $4$ no se le asocia ningún elemento de $B$ y $c\in B$ no está asociado a ningún elemento de $A$.

{{% exercise %}}
¿Cuántas correspondencias hay de $\varnothing$ en $A$? ¿Y de $A$ en $\varnothing$?
{{% /exercise %}}

{{% definition %}}
Dados dos conjuntos $A$ y $B$, una **aplicación** $f$ de $A$ en $B$, que se denota $f\colon A\rightarrow B$, es una correspondencia que asocia a cada elemento de $A$ un único elemento de $B$, es decir $ \forall a \in A \; \exists ! \; b \in B | (a,b)\in f$.
{{% /definition %}}

La correspondencia del diagrama anterior no es una aplicación, pero la siguiente sí:

![Aplicación](../images/map.png)

Como conjunto, $f=\\{(1,a), (4,b), (2,b), (3, b)\\}\subset A\times B$.

{{% definition %}}
Dada una aplicación $f\colon A\rightarrow B$ y $a \in A$, denotaremos $f(a)\in B$ al único elemento tal que $(a,f(a))\in f$ y lo denominaremos **imagen** de $a$ por $f$. También diremos que $f(a)$ es el **valor** de $f$ en $a$. 
{{% /definition %}}

{{% watch %}}
Para definir una aplicación hay que especificar lo siguiente:

* El conjunto de partida, también llamado **dominio**.
* El de llegada, o **codominio**.
* La imagen de cada elemento del conjunto de partida.

Si dos aplicaciones difieren en alguno de estos tres puntos se consideran diferentes.
{{% /watch %}}

{{% example name="Aplicaciones parecidas pero diferentes" %}}
La aplicación $f\colon \mathbb{N}\rightarrow \mathbb{N}$ definida como $f(n)=n$ para todo $n\in\mathbb{N}$ es diferente de la aplicación $g\colon \mathbb{N}\rightarrow \mathbb{Z}$ definida como $g(n)=n$ para todo $n\in\mathbb{N}$.
{{% /example %}}


{{% watch %}}
Dada una aplicación $f\colon A\rightarrow B$, una manera habitual de denotar que $b=f(a)$ es $a\mapsto b$.
{{% /watch %}}


La aplicación del diagrama anterior se puede definir también del siguiente modo:
$$
\begin{array}{rcl}
A&\stackrel{f}\longrightarrow& B,\cr
1&\mapsto&a,\cr
2&\mapsto&b,\cr
3&\mapsto&b,\cr
4&\mapsto&b.
\end{array}
$$
Observa que el nombre de la aplicación se puede poner sobre la flecha.




{{% example name="Algunas aplicaciones importantes" %}}
* La **identidad** $1_A\colon A\rightarrow A$ se define como $1_A(a)=a$ para todo $a\in A$. Esta aplicación está definida para cualquier conjunto $A$.

* Dado un subconjunto $B\subset A$, la **inclusión** $i\colon B\rightarrow A$ se definie como $i(b)=b$ para todo $b\in B$. 

* Dados dos conjuntos $A$ y $B$ y un elemento $b\in B$, la aplicación **constante** $c_b\colon A\rightarrow B$ se define como $c_b(a)=b$ para todo $a\in A$.
{{% /example %}}

{{% exercise %}}
Dado un conjunto $A$, ¿hay algun aplicación $\varnothing\rightarrow A$? ¿Y $A\rightarrow\varnothing$?.
{{% /exercise %}}


{{% definition %}}
Dadas dos aplicaciones 
$$A\stackrel{f}\longrightarrow B\stackrel{g}\longrightarrow C$$
su **composición** $g\circ f\colon A\rightarrow C$ es la aplicación definida como $(g\circ f)(a)=g(f(a))$.
{{% /definition %}}


{{% proposition %}}
La composición de aplicaciones satisface las propiedades siguientes:

* Dadas tres aplicaciones $$A\stackrel{f}\longrightarrow B\stackrel{g}\longrightarrow C\stackrel{h}\longrightarrow D$$
se verifica que $h\circ (g\circ f)=(h\circ g)\circ f$ (**asociativa**).
* Dada una aplicación $f\colon A\rightarrow B$, se tiene que $f\circ 1_A=f=1_B\circ f$ (**elemento neutro**).
{{% /proposition %}}

{{% proof %}}
Las aplicaciones cuya igualdad se plantea tienen el mismo dominio y condominio, por tanto bastará comprobar que las imágenes de los elementos del dominio coinciden.

Dado $a\in A$, por un lado
$$
\begin{array}{rcl}
(h\circ (g\circ f))(a)&=&h((g\circ f)(a))\cr
&=&h(g(f(a)),\cr
((h\circ g)\circ f)(a)&=&(h\circ g)(f(a))\cr
&=&h(g(f(a)).
\end{array}
$$

Por otro lado
$$
\begin{array}{rcl}
(f\circ 1_A)(a)&=&f(1_A(a))\cr
&=&f(a)\cr
&=&1_B(f(a))\cr
&=&(1_B\circ f)(a).
\end{array}
$$
{{% /proof %}}

{{% definition %}}
Una aplicación $f \colon  A \rightarrow B$ es **invertible** si existe $g \colon B \rightarrow A$ tal que
$g \circ f = 1_A$ y $f \circ g = 1_B$.
{{% /definition %}}

{{% proposition %}}
La aplicación $g$ de la definición anterior, si existe, es única.
{{% /proposition %}}

{{% proof %}}
Si hubiera otra $g' \colon B \rightarrow A$ entonces 
$$
\begin{array}{rcl}
g&=&g\circ 1_B\cr
&=&g\circ (f\circ g')\cr
&=&(g\circ f)\circ g'\cr
&=&1_A\circ g'=g'.
\end{array}
$$
{{% /proof %}}

{{% definition %}}
Si $f \colon  A \rightarrow B$ es invertible su aplicación **inversa**  $f^{-1} \colon B \rightarrow A$ es la única que satisface
$f^{-1} \circ f = 1_A$ y $f \circ f^{-1} = 1_B$.
{{% /definition %}}


{{% remark %}}
La identidad $1_A\colon A\rightarrow A$ es invertible y $1_A^{-1}=1_A$. Si $f\colon A\rightarrow B$ es invertible entonces $f^{-1} \colon B \rightarrow A$ también y $(f^{-1})^{-1}=f$.
{{% /remark %}}

{{% proposition %}}
Si tenemos dos aplicaciones invertibles
$$A\stackrel{f}\longrightarrow B\stackrel{g}\longrightarrow C$$ entonces $g\circ f$ es invertible y $(g\circ f)^{-1}=f^{-1}\circ g^{-1}$.
{{% /proposition %}}

{{% proof %}}
Basta observar que
$$
\begin{array}{rcl}
(g\circ f)\circ (f^{-1}\circ g^{-1})
&=&
g\circ (f\circ f^{-1})\circ g^{-1}\cr
&=&
g\circ 1_B\circ g^{-1}\cr
&=&
g\circ g^{-1}\cr
&=&
1_C,
\end{array}
$$
y que
$$
\begin{array}{rcl}
(f^{-1}\circ g^{-1})\circ (g\circ f)
&=&
f^{-1}\circ (g^{-1}\circ g)\circ f\cr
&=&
f^{-1}\circ 1_B\circ f\cr
&=&
f^{-1}\circ f\cr
&=&
1_A.
\end{array}
$$
{{% /proof %}}

Nos disponemos a dar una caracterización más asequible de las aplicaciones invertibles.

{{% definition %}}
Sea $f\colon A \rightarrow B$ una aplicación. 

* $f$ es **inyectiva** o **uno-a-uno** si no existen dos elementos diferentes de $A$ con la misma imagen.
* $f$ es **sobreyectiva** si todo elemento de $B$ es la imagen de algún elemento de $A$.
* $f$ es **biyectiva** si es inyectiva y sobreyectiva.
{{% /definition %}}

En una aplicación inyectiva no puede ocurrir los siguiente:

![Aplicación no inyectiva](../images/noinjective.png)

En una sobreyectiva está prohibida la siguiente situación:

![Aplicación no sobreyectiva](../images/nosurjective.png)

{{% remark %}}
En notación matemática, $f\colon A\rightarrow B$ es **inyectiva** si, dados $a,a'\in A$, $f(a)=f(a')\Rightarrow a=a'$, y $f$ es **sobreyectiva** si $\forall b\in B\;\exists a\in A|f(a)=b$.
{{% /remark %}}

{{% watch %}}
Es un error tristemente común el confundir la caracterización anterior de la inyectividad con la implicación $\Leftarrow$. En realidad esta impliciación es cierta para cualquier aplicación por la propia definición.
{{% /watch %}}

{{% lemma %}}
Una aplicación $f\colon A \rightarrow B$ es biyectiva $\Leftrightarrow$ $\forall b\in B\;\exists! a\in A|f(a)=b$.
{{% /lemma %}}

{{% proof %}}
Veamos $\Rightarrow$. Supongamos pues que $f$ es biyectiva. Si excluimos la condición de unicidad, el enunciado de la derecha es cierto por ser $f$ sobreyectiva. La unicidad se deduce de ser $f$ inyectiva, pues si existieran $a,a'\in A$ tales que $f(a)=b=f(a')$ entonces tendríamos que $a=a'$.

Veamos ahora $\Leftarrow$. Como ya hemos comentado, el enunciado de la derecha implicia la sobreyectividad de $f$ ya que incluso la condición de unicidad no sería necesaria para esto. Para ver que $f$ es inyectiva tomamos $a,a'\in A$ y suponemos que $f(a)=f(a')$. Tomando $b=f(a)$ tenemos que $f(a)=b$ y $f(a')=b$, así que por la unicidad $a=a'$, que es lo que teníamos que probar.
{{% /proof %}}

{{% exercise %}}
Si $f\colon A\rightarrow B$ es biyectiva y $A$ es finito, ¿qué podemos decir de $B$?
{{% /exercise %}}

El siguiente tema versará en buena parte sobre el estudio de las aplicaciones biyectivas de un conjunto finito en sí mismo.

{{% theorem %}}
Una aplicación $f\colon A \rightarrow B$ es invertible $\Leftrightarrow$ es biyectiva.
{{% /theorem  %}}

{{% proof %}}
Supongamos que $f$ es invertible. Veamos que es sobreyectiva. Dado $b\in B$ tenemos que $f(f^{-1}(b))=(f\circ f^{-1})(b)=1_B(b)=b$, con lo que $f$ es sobreyectiva. Si, dados $a,a'\in A$, $f(a)=f(a')$, entonces $f^{-1}(f(a))=f^{-1}(f(a'))$. Como $f^{-1}\circ f=1_A$ deducimos que $a=a'$, luego $f$ es inyectiva.

Supongamos ahora que $f$ es biyectiva. Definimos $g\colon B\rightarrow A$ del siguiente modo. Dado $b\in B$, $g(b)\in A$ es el único elemento tal que $f(g(b))=a$. Esto implica que $f\circ g=1_B$. Veamos que $g\circ f=1_A$. Para ello tomamos $a\in A$ cualquiera y calculamos
$$
\begin{array}{rcl}
(f\circ(g\circ f))(a)&=&f((g\circ f)(a)),\cr
((f\circ g)\circ f)(a)&=&(1_B\circ f)(a),\cr
&=&f(a).
\end{array}
$$
Por la asociatividad de la composición $f((g\circ f)(a))=f(a)$ y por la inyectividad de $f$ tenemos que $(g\circ f)(a)=a$. Esto es lo que había que probar.
{{% /proof %}}

{{% remark %}}
Las aplicaciones invertibles juegan en el ámbito de los conjuntos el mismo papel que las igualdades en el campo de los números, es por eso que se denotan  $$f\colon A\stackrel{\cong}\longrightarrow B$$ o simplemente $f\colon A\cong B$. Por ejemplo, el producto cartesiano $A\times B$ no es conmutativo estrictamente hablando, pero hay una biyección
$$
\begin{array}{rcl}
A\times B&\cong &B\times A,\cr
(a,b)&\mapsto &(b,a).
\end{array}
$$
Decimos pues que el producto cartesiano es conmutativo *salvo biyección*. Lo mismo ocurre con la asociatividad del producto cartesiano,
$$
\begin{array}{rcl}
(A\times B)\times C&\cong &A\times(B\times C),\cr
((a,b),c)&\mapsto &(a,(b,c)).
\end{array}
$$
Es más, ambos están en biyección con el producto triple, por ejemplo
$$
\begin{array}{rcl}
(A\times B)\times C&\cong &A\times B\times C,\cr
((a,b),c)&\mapsto &(a,b,c).
\end{array}
$$
{{% /remark %}}

{{% definition %}}
Sea $f \colon  A \longrightarrow B$ una aplicación. 

* La **imagen directa** de un subconjunto del dominio $U\subset A$ 
es el subconjunto del codominio $f(U)=\\{b\in B\:|\;\exists a\in U|f(a)=b\\}\subset B$. 
* La **imagen inversa** de un subconjunto del codominio $V\subset B$ es subconjunto del dominio $f^{-1}(V)=\\{a\in A| f(a)\in V\\}$.

La **imagen** de la aplicación $A$ se define como $\operatorname{Im}f=f(A)$.
{{% /definition %}}

La imagen inversa recible otros nombres como **contraimagen**, **preimagen** o **anti-imagen**. La imagen directa también se denomina simplemente **imagen**.

{{% watch %}}
Dada una aplicación $f\colon A\rightarrow B$, conviene no confundir la imagen de un elemento de $A$ con la imagen directa de un subconjunto de $A$, aunque obviamente son conceptos relacionados. Observa que $f(\\{a\\})=\\{ f(a) \\}$.
{{% /watch %}}


{{% exercise %}}
¿Cuál es la imagen directa del subconjunto vacío? ¿Y su imagen inversa?
{{% /exercise %}}

{{% watch %}}
La notación $f^{-1}(V)$ para la imagen inversa es confusa porque incorpora la notación usada para la inversa de la aplicación $f$, cuando esta existe. La imagen inversa está siempre definida, aun cuando $f$ no es invertible y por tanto $f^{-1}$ no existe. Si $f$ es invertible, no hay ambigüedad ya que en este caso la imagen inversa $f^{-1}(V)$ de $V$ a través de $f$ coincide con la imagen directa de $V$ a través de $f^{-1}\colon B \rightarrow A$. Para añadir aún más confusión, es habitual abusar de la terminología y denotar al subconjunto $f^{-1}(\\{b\\})\subset A$ simplemente por $f^{-1}(b)$. El significado de esta expresión en cada caso se deducirá del contexto. 
{{% /watch %}}


{{% remark %}}
Una aplicación $f\colon A\rightarrow B$ es sobreyectiva si y solo si $\operatorname{Im}f=f(A)=B$.

Para toda aplicación $f\colon A\rightarrow B$, $f^{-1}(B)=A$. 

A partir de cualquier aplicación $f\colon A\to B$ podemos definir una sobreyectiva $\bar{f}\colon  A \to \Imag(f)$ como $\bar{f}(a)=f(a)$ para todo $a\in A$. ¿En qué se diferencian $f$ y $\bar{f}$?
{{% /watch %}}

{{% exercise %}}
Prueba como ejercicio que las imágenes directa e inversa preservan inclusiones, es decir, 
dada una aplicación $f\colon A\rightarrow B$: 

* $U\subset U'\subset A\Rightarrow f(U)\subset f(U')\subset B$
* $V \subset V'\subset B\Rightarrow f^{-1}(V)\subset f^{-1}(V')\subset A$.

¿Son ciertos los recíprocos?
{{% /exercise %}}


{{% proposition %}}
Dada una aplicaicón $f\colon A \rightarrow B$ y subconjuntos $U\subset
A$ y $V\subset B$, se verifican las siguientes propiedades:

* $U \subset f^{-1}(f(U))$.
* $f(f^{-1}(V)) \subset V$. 
{{% /proposition %}}

{{% proof %}}
Probaremos la segunda propiedad y dejaremos la primera como ejercicio. Dado $y\in f(f^{-1}(V))$ existe $x\in f^{-1}(V)$ tal que $y=f(x)$. Como $x\in f^{-1}(V)$, $f(x)\in V$, así que $y\in V$. Esto es lo que había que demostrar.
{{% /proof %}}

{{% proposition %}}
Dada una aplicaicón $f\colon A \rightarrow B$ y subconjuntos $U_1,U_2 \subset
A$ y $V_1,V_2 \subset B$, se verifican las siguientes propiedades:

1. $f(U_1 \cup U_2) = f(U_1) \cup f(U_2)$. 
2. $f(U_1 \cap U_2) \subset f(U_1) \cap f(U_2)$.
3. $f^{-1} (V_1 \cup V_2) = f^{-1} (V_1) \cup f^{-1} (V_2)$.
4. $f^{-1} (V_1 \cap V_2) = f^{-1} (V_1) \cap f^{-1} (V_2)$.
{{% /proposition %}}

{{% proof %}}
Vamos a probar 2 y 3. Los demás apartados son similares y quedan como ejercicio.

Dado $y \in
f(U_1 \cap U_2)$ existe $x \in U_1 \cap U_2$ tal que $y =
f(x)$. Como $x\in U_1$ y $x\in U_2$ deducimos que $y \in f(U_1)$ e $y \in f(U_2)$, por tanto  $y\in f(U_1) \cap f(U_2)$.

Tenemos que $x\in f^{-1}(V_1 \cup V_2)$ si y solo si $f(x)\in V_1\cup V_2$. Esto equivale a decir que $f(x)\in V_1$ o $f(x)\in U_2$, lo que es lo mismo, $x\in f^{-1}(V_1)$ o $x\in f^{-1}(V_2)$. Esto último es idéntico a afirmar que $x\in f^{-1}(V_1)\cup f^{-1}(V_1)$.
{{% /proof %}}




{{% definition %}}
La **restricción** de una aplicación $f\colon A \rightarrow B$ a un subconjunto
$U\subset A$ es la aplicación $f|_U\colon U\rightarrow B$ definida como $f|_U(u)=f(u)$ para todo $u\in U$.
{{% /definition %}}

{{% exercise %}}
¿En qué se diferencian $f$ y su restricción $f|_U$?
{{% /exercise %}}


{{% definition %}}
Dados dos conjuntos $A$ y $B$, el **conjunto exponencial** es $B^A=\\{$aplicaciones $A\rightarrow B\\}$.
{{% /definition %}}


{{% exercise %}}
Si $A$ y $B$ son finitos, ¿puedes acotar el número de elementos de $B^A$?
{{% /exercise %}}

{{% exercise %}}
Dado un conjunto cualquiera $A$ y otro unitario $\\{e\\}$, describe $A^{\\{e\\}}$ y $\\{e\\}^A$.
{{% /exercise %}}



<!--





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
