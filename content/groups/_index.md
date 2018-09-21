+++
title = "Grupos"
weight = 20
+++

<!--

## Introducción

### Comencemos con un juego de cartas

Tomemos 9 cartas de un mismo palo numeradas del 1 al 9. Empezamos con ellas ordenadas como se ve en la figura \ref{figura1}.

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics[scale=0.22]{permut1.eps}
 }
 \caption{Cartas ordenadas}
 \label{figura1}
\end{figure}

Ahora las separamos colocándolas alternativamente en dos montones boca abajo. Después montamos uno sobre otro y "cortamos" todas las veces que queramos y por donde queramos ("cortar" es pasar unas cuantas cartas de arriba a abajo sin desordenarlas ni mezclarlas).

Después de hacer esto dos veces las cartas quedan bastante desordenadas, como
puede verse en la figura \ref{figura2}.

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics[scale=0.22]{permut2.eps}
 }
 \caption{Cartas desordenadas}
 \label{figura2}
\end{figure}

Pero, para quedarnos más seguros del desorden, vamos a separarlas una tercera vez y, por supuesto, "cortar" cuantas veces queramos.

Ahora miramos la carta de arriba

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics[scale=0.2]{permut3.eps}
 }
 \caption{Cartas de arriba}
 \label{figura3}
\end{figure}

\noindent
y pasamos de arriba a abajo tantas cartas como indique el número (en el ejemplo de la figura \ref{figura3}, es el 4). Entonces, enseñamos las cartas y {\bf ¡todo está ordenado como al principio!}

?`Qué es lo que ocurre? ?`Dónde está la magia?

Lo que hemos visto es un juego de "magia" que no tiene ningún "truco". Es álgebra y nada más que álgebra lo que hay detrás de este juego. En las siguientes secciones vamos a profundizar en el modelo algebraico que nos va a permitir descubrir por qué se ordenan las cartas: {\bf El grupo de las permutaciones}. Y después volveremos al juego de cartas.

### Permutaciones de un conjunto

En cada paso del juego anterior "separamos" o "cortamos" las cartas, es decir, las cambiamos de orden. De esta manera estamos estableciendo una biyección
entre las posiciones originales en las que se encuentran las cartas, aquellas que ocupan después de barajearlas. %A esto se llama una {\bf permutación}.
Por ejemplo, en la figura \ref{figura2} se observa que la primera carta se ha quedado en su lugar, pero la segunda ahora está la octava, la tercera está la sexta, etcétera. 
La biyección correspondiente es:
$$\begin{array}{ccl} 1 & \rightarrow & 1\\ 2 & \rightarrow & 8\\ 3 & \rightarrow & 6\\ 4 & \rightarrow & 4\\ 5 & \rightarrow & 2\\ 6 & \rightarrow & 9\\ 7 & \rightarrow & 7\\ 8 & \rightarrow & 5\\ 9 & \rightarrow & 3.\end{array}$$.



{{% definition %}}
{Permutación de un conjunto}
{Sea $X$ un conjunto, se llama {\em permutación de }$X$ a cualquier aplicación biyectiva $\sigma\colon X\to X$.}


{{% /definition %}}


El conjunto de todas las permutaciones de un conjunto $X$ %se denomina {\em grupo simétrico de} $X$ y 
se denota por $\Sim (X).$ Cuando trabajamos con permutaciones del conjunto $\\{1,2, \cdots, n\\}$, una manera concisa de representar una permutación es a través de una matriz con dos filas, la primera los números del $1$ al $n$, y la segunda sus imágenes . En nuestro ejemplo, la primera fila  indica la posición inicial y la segunda la nueva posición tras la permutación.
\[
\left(\begin{array}{ccccccccc}
         1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
         1 & 8 & 6 & 4 & 2 & 9 & 7 & 5 & 3
        \end{array}\right)
        \]

Pero  $\Sim (X)$ es más que un conjunto. Las permutaciones son, en particular, aplicaciones, de manera que dadas dos permutaciones $\pi$ y $\sigma$ 
podemos componerlas para obtener una nueva permutación $\pi \circ \sigma$.  (Recuerda que hemos visto que la composición de aplicaciones biyectivas es biyectiva)

La composición de permutaciones satisface las siguientes propiedades.

{{% proposition %}}
{\label{grupo-permutaciones}}
Sea $X$ un conjunto, se verifican las siguientes propiedades:
\begin{enumerate}
\item La composición de permutaciones  de $X$ es una permutación de $X$. Es decir,
para cada par de permutaciones $\sigma ,\tau\in\Sim (X)$,  se tiene  que $\tau\circ\sigma\in\Sim (X).$
\item La aplicación identidad en $X$, que denotaremos por $1_X$ es una permutación. Es decir,
$1_X\in\Sim (X).$
\item La inversa de cualquier permutación de $X$ es  una permutación de $X$. Es decir,
para cada $ \sigma\in\Sim (X),$ su inversa $\sigma^{-1}$ también está en $\Sim (X).$
\item La composición de permutaciones verifica la propiedad asociativa. Es decir,
dadas $ \sigma ,\tau$ y $\rho\in\Sim (X)$, tenemos que  $\rho\circ (\tau\circ\sigma )=(\rho\circ\tau )\circ\sigma.$
\end{enumerate}
{{% /proposition %}}



{{% proof %}}

Ya hemos visto en el tema anterior que la composición de dos aplicaciones biyectivas es también biyectiva, como ambas van de $X$ en $X$, la composición de dos permutaciones es una permutación (1). Sabemos también que $1_X$ es una aplicación biyectiva de $X$ en $X$, luego $1_X\in\Sim (X)$ (2). Cada aplicación biyectiva tiene una aplicación inversa que es también biyectiva, si $\sigma$ es una aplicación biyectiva de $X$ en $X$ entonces $\sigma^{-1}\colon X\to X$ es una permutación (3). Por último, la composición de aplicaciones verifica la propiedad asociativa, en particular la composición de permutaciones también la verifica (4).
{{% /proof %}}





Sin duda nos hemos encontrado anteriormente con estas propiedades. Detengámonos a pensar cuándo. Los conjuntos $\Z$, $\Q$, $\R$ y $\C$ tienen definidos de manera natural dos operaciones, la suma y el producto. Con respecto a la suma, cada uno de ellos satisface las propiedades de la Proposición \ref{grupo-permutaciones}. (Los números naturales $\N$ no las hace ya que, por ejemplo, la inversa de $1$ con respecto a la suma es $-1$, que  no pertenece a $\N$).

Con respecto al producto, ninguno de estos conjunto satisface la tercera propiedad de la Proposición \ref{grupo-permutaciones}, ya que el cero pertenece a todos ellos, pero el cero no tiene inversa. Por otra parte, si quitamos el cero de algunos de estos conjuntos, esto es, si consideramos  $\Q^*=\Q\setminus \\{0\\}$, $\R^*=\R\setminus \\{0\\}$ y $\C^*=\C\setminus \\{0\\}$, entonces se cumplen todas las propiedades de la  Proposición \ref{grupo-permutaciones}. Por otra parte, en el caso de $\Z$ junto con la operación de multiplicación, los único elementos que tienen inversa son $1$ y $-1$. La inversa de $2$ es $1/2$ que no pertenece a $\Z$. 

Una pregunta al lector, ?`por qué no consideramos las operaciones de resta y división? ?`Satisfacen estas operaciones la propiedad asociativa?

Para un ejemplo de naturaleza más geométrica que satisfaga las propiedades de la Proposición \ref{grupo-permutaciones}, el lector está invitado a verificar que el conjunto de las simetrí{}as de un cuadrado, (rotación de ángulo $\frac{\pi}{2}$, simetrí{}a con respecto a las diagonales, etc),  junto con la operación de composición.

?`Qué es lo que ocurre? ?`Qué tienen en común estos ejemplos? Antes de empezar a investigar estas preguntas, introducimos una nueva definición, que nos evitará referirnos una y otra vez a la  Proposicion \ref{grupo-permutaciones}.

Para esto, observemos que  en todos los ejemplos anteriores, tenemos tanto un conjunto $G$, como una operación (suma, producto, composición) entre sus elementos. Esto nos motiva a hacer la siguiente definición.

{{% definition %}}
{Operación} { 
Una aplicación de $G\times G$ en $G$  tal que  a cada par ordenado $(a,b)\in G \times G$  le asocia un único elemento $a\star b$ de $G$
se denomina {\bf{operación.}}}
{{% /definition %}}

Por ejemplo, en la discusión anterior, la operación  considerada para $Sim$ era la composición de aplicaciones, para $\Z$ la suma y para $\Q*$ el producto.

En otros contextos es necesario trabajar con otros tipos de operaciones. Por esta razón, con frecuencia se dice que la  operación de grupo es binaria e interna.
 En este caso, el adjetivo binario se refiere a que el conjunto de partida es un producto cartesiano, y el adjetivo interno a que la aplicación se define entre $G \times G$ y $ G$. 
 Por ejemplo, la multiplicación de un vector por un escalar es una operación que no es interna.


{{% definition %}}
{Grupo} {Un {\bf grupo} es un par $(G, \star )$,
donde $G$ es un conjunto y $\star$ es una operación 
 sobre $G$ verificando
 las siguentes propiedades:
 \begin{enumerate}
  \item La operación es asociativa.
  \item La operación tiene elemento neutro. Es decir, existe un elemento $ e\in G $  tal que  para todo  $x\in G$ se tiene que $ x\star e=e\star x=x.$
  \item Cada elemento de $G$ posee un simétrico. Es decir,
para cada $ x\in G$ existe un elemento $\inv{x}\in G$  tal que $x\star \inv{x}=\inv{x}\star x=e.$
 \end{enumerate}}
{{% /definition %}}

Una manera equivalente de presentar los resultados obtenidos en la Proposición \ref{grupo-permutaciones} es entonces la siguiente.

{{% theorem %}}
{El grupo simétrico}{El conjunto $\Sim (X)$ de las permutaciones de un conjunto $X$, junto con la composición de permutaciones, es un grupo.

%Además, si $X$ tiene al menos tres elementos el grupo no es conmutativo.
}
{{% /theorem %}}



Aprender matemáticas es un proceso activo. Cuando vemos una nueva definición es indispensable detenerse y pensar, buscar ejemplos, pensar en la motivación detrás de ella. ?`Por qué se introduce? ?`Qué nos dice? ?`Qué caracteristicas comparten (o no comparten) los diferentes ejemplos que lo satisfacen?



{{% example name="Ejemplo" %}}
\label{ejemplo-grupos} Hagamos una lista de algunos grupos que conocemos bien:
 \begin{enumerate}
  \item $\Z$, $\Q$, $\R$ y $\C$ son grupos con la suma. En este caso el elemento neutro es el cero. El simétrico de un elemento $a$ es su opuesto $-a$. 
  
  Es importante señalar esto porque en la definición de grupo se usa una {\bf notación multiplicativa} para el simétrico (el simétrico de $x$ es $\inv{x}$). Este debe ser modificado naturalmente cuando la operación del grupo es la suma (el simétrico de $a$ es $-a$).
  
  \item $\Q^*=\Q\setminus\\{ 0\\}$, $\R^*=\R\setminus\\{ 0\\}$ y $\C^*=\C\setminus\\{ 0\\}$
  son grupos  con la multiplicación.
  \item El conjunto $\\{ -1,1\\}$ con el producto es un grupo con dos elementos.
  \item El conjunto de las matrices $n\times n$, con elementos en un cuerpo $k$ y
  determinante no nulo, GL$(n,k)$, es un grupo
  con la multiplicación de matrices.
  \item Las simetrí{}as de un poligono regular (triángulo, cuadrado, pentágono, etc), junto con la operación de composición es un grupo.
 \end{enumerate}
{{% /example %}}

Una ventaja de trabajar con la definición de grupos, es que cualquier propiedad que podamos deducir de la definición será válida en cada uno de los ejemplos anteriores (y en cualquier otro grupo). Por ejemplo, algunas propiedades importantes que se deducen directamente de la definición de grupo son las siguientes:

{{% proposition %}}

El elemento neutro de un grupo $(G,\star)$ es único.
{{% /proposition %}}

{{% proof %}}

Si $e$ y $e'$ son elementos neutros de $(G,\star)$, entonces se tiene:
$$
   e = e\star e' = e',
$$
donde la primera igualdad se tiene por ser $e'$ elemento neutro, y la segunda se tiene por ser $e$ elemento neutro.
{{% /proof %}}

{{% proposition %}}

En un grupo $(G,\star)$, el simétrico de un elemento $x\in G$ es único.
{{% /proposition %}}

{{% proof %}}

Sea $x\in G$, y sean $y$, $z$ elementos simétricos de $x$. Se tiene:
$$
    y= y\star e = y \star (x \star z) = (y \star x) \star z = e \star z = z.
$$
{{% /proof %}}

En el capí{}tulo 1 demostramos esta proposición para el ejemplo particular de las aplicaciones biyectivas. Ahora vemos que la propiedad la comparten todos los grupos. Gracias a este resultado, podemos denotar al simétrico de $x$ por $x^{-1}$ (o por $-x$ si estamos usando notación aditiva) sin ambig\"uedad, puesto que sólo hay un elemento simétrico. 
Más aún, para comprobar que un elemento $y$ es el simétrico de un elemento $x$, no es necesario ver que $x\star y =e$ y que $y\star x=e$; bastará con comprobar una de estas dos condiciones:

{{% proposition %}}

Si $x$, $y$ son elementos de un grupo $(G,\star)$ tales que $x\star y=e$, entonces $y=x^{-1}$ y $x=y^{-1}$.
{{% /proposition %}}

{{% proof %}}

A partir de $x\star y= e$, si multiplicamos esta igualdad desde la izquierda por $x^{-1}$, obtenemos $y = x^{-1}$.  Y si la multiplicamos desde la derecha por $y^{-1}$, obtenemos $x=y^{-1}$.
{{% /proof %}}


Es imposible evitar preguntarse: ?`Qué sucede con la propiedad conmutativa? Ya que estamos en esto, ?`Todos los grupos satisfacen la propiedad conmutativa?
La respuesta es un rotundo no, y esta es una observación muy importante. Por ejemplo, la composición de permutaciones no verifica la propiedad conmutativa.

{{% example name="Ejemplo" %}}
{\label{conmutativa}}
Sea $X=\\{ 1,2,3\\}$ y sean las permutaciones de $X$
$$\sigma\colon\left(\begin{array}{cccc}
                     1 & 2 & 3\\
                     2 & 1 & 3
                    \end{array}\right)\mbox{ y }
   \tau\colon\left(\begin{array}{cccc}
                     1 & 2 & 3\\
                     2 & 3 & 1
                    \end{array}\right) .$$
Es decir, $\sigma$ es la permutación que intercambia los números 1 y 2, dejando 3 invariante, y $\tau$ es la que lleva 1 en 2, 2 en 3 y 3 en 1.

Entonces las composiciones de $\sigma$ y $\tau$ son
$$\tau\circ\sigma\colon\left(\begin{array}{cccc}
                              1 & 2 & 3\\
                              3 & 2 & 1
                             \end{array}\right)\mbox{ y }
  \sigma\circ\tau\colon\left(\begin{array}{cccc}
                              1 & 2 & 3\\
                              1 & 3 & 2
                             \end{array}\right) .$$
Como son permutaciones distintas, esto demuestra que la composición de permutaciones no es conmutativa {\em en general}\footnote{"En general" quiere decir que no negamos la posibilidad de que existan pares de permutaciones cuya composición sí conmute. Animamos al lector a buscar algún ejemplo de este hecho.}.


De este ejemplo concluimos que  si $X$ tiene al menos tres elementos el grupo $Sim(X)$ no es conmutativo.

{{% /example %}}

{{% definition %}}
{Grupo abeliano} {Dado un grupo $G$, si  la operación de grupo es conmutativa entonces se dice que el grupo es {\bf abeliano} o {\bf conmutativo}.}
{{% /definition %}}

?`Cuáles de los grupos que aparecen en el Ejemplo 2.1.3 son abelianos?

En esta breve introducción hemos observado que existen grupos finitos y grupos infinitos. Por otra parte, que existen grupos conmutativos (abelianos) y grupos no conmutativos. ?`Qué más podemos decir? La respuesta a esta pregunta es uno de los capí{}tulos más elegantes de las matemáticas, que empezaremos a estudiar ahora. 



%En el caso de las permutaciones de un conjunto $X$, la proposición \ref{grupo-permutaciones} demuestra que la composición es una operación   binaria sobre $\Sim (X)$, que verifica la propiedad asociativa, que $1_X$ es el elemento neutro, y que cada permutación $\sigma\in\Sim (X)$ tiene un elemento simétrico que es su inversa $\sigma^{-1}$. Además, si $X$ tiene al menos tres elementos, la composición no es conmutativa (ejemplo \ref{conmutativa}). Por tanto:



## Ciclos y trasposiciones. El grupo $S_n$

### Ciclos y trasposiciones
Sean $X$ un conjunto y $\sigma$ una permutación de $\Sim (X)$. Llamamos {\em soporte} de $\sigma$ al conjunto
$$\sop (\sigma )=\\{ x\in X\mid \sigma (x)\ne x\\} .$$

{{% definition %}}
{Ciclos y trasposiciones}
{Se dice que $\sigma\in \Sim(X)$  es un {\bf ciclo de longitud $0$}, o un {\bf $0$-ciclo}, si es la identidad.


Se dice que $\sigma\in \Sim(X)$ es un {\bf ciclo de longitud $r$}, o un {\bf $r$-ciclo} (con $r\geq 2$), si su soporte es un conjunto finito de $r$ elementos
$$\sop (\sigma )=\\{ i_1,i_2,\ldots ,i_r\\}$$
donde $\sigma (i_1)=i_2$, $\sigma (i_2)=i_3$, $\ldots$, $\sigma (i_{r-1})=i_r$ y $\sigma (i_r)=i_1$.



Decimos que $\sigma\in\Sim (X)$ es una {\bf trasposición} si es un ciclo de longitud 2.}
{{% /definition %}}

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics[scale=0.5]{Ciclo.eps}
 }
 \caption{Ciclo}
 \label{ciclo}
\end{figure}

{{% watch %}}
{\label{nota231}}
Sea $\sigma\in\Sim (X)$ un ciclo tal que $\sop (\sigma )=\\{ i_1,i_2,\ldots ,i_r\\}$ donde $\sigma (i_1)=i_2$, $\sigma (i_2)=i_3$, $\ldots$, $\sigma (i_r)=i_1$. Entonces escribiremos $\sigma$ de la siguiente forma
$$\sigma =(i_1i_2\ldots i_r)$$
sabiendo que si $x\in X$ no aparece en la lista entonces $\sigma (x)=x$.

Obsérvese que con esta notación tenemos diferentes representaciones de un mismo ciclo:
$$\sigma =(i_1i_2\ldots i_r)=(i_2i_3\ldots i_ri_1)=\cdots =(i_ri_1\ldots i_{r-1}).$$

Siguiendo esta notación podemos escribir el ciclo identidad como
$$1_X=(),$$
pues $\sop (1_X)=\emptyset$ y todos los elementos que no aparecen entre los paréntesis (o sea, todos los elementos de $X$) quedan invariantes.
{{% /watch %}}

{{% example name="Ejemplo" %}}

\begin{enumerate} Veamos algunos ejemplos:
\item La permutación del conjunto $\\{ 1,2,3,4,5\\}$ definida por
$$\sigma\colon \left(\begin{array}{ccccc}
                     1 & 2 & 3 & 4 & 5\\
                     2 & 5 & 3 & 4 & 1
                    \end{array}\right)$$
es el $3$-ciclo $(1\ 2\ 5)$.
\item La permutación del conjunto $\\{ 1,2,3,4,5,6,7,8\\}$ definida por
$$\sigma\colon \left(\begin{array}{cccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7 & 8\\
                     6 & 1 & 5 & 8 & 7 & 2 & 3 & 4
                    \end{array}\right)$$
no es un ciclo. Sin embargo $\tau =(1\ 6\ 2)\circ (3\ 5\ 7)\circ (4\ 8)$ es composición de ciclos, veremos más adelante que este es un hecho general para permutaciones de conjuntos finitos.
\end{enumerate}
{{% /example %}}

{{% watch %}}

En adelante, siempre que no haya posibilidad de equívoco, prescindiremos en un grupo $(G,\star )$ del símbolo "$\star$" para la operación de dos (o más) elementos. Escribiremos por yuxtaposición $xy$ en lugar de $x\star y$.

\noindent En particular, en el caso de permutaciones, escribiremos $\tau\sigma$ en lugar de $\tau\circ\sigma$.
{{% /watch %}}

{{% definition %}}
{Permutaciones disjuntas}
{Dos permutaciones $\sigma ,\tau\in\Sim (X)$ se dicen {\bf disjuntas} si sus soportes son disjuntos.}
{{% /definition %}}

{{% theorem %}}
{Permutaciones disjuntas y conmutatividad}
{Si $\sigma,\tau\in\Sim (X)$ son permutaciones disjuntas entonces $$\tau\sigma =\sigma\tau.$$}
{{% /theorem %}}

{{% proof %}}

Dado $x\in X$ tenemos que demostrar que $\tau\sigma (x)=\sigma\tau (x)$. Si $x\notin\sop (\sigma )\cup\sop (\tau )$ entonces
$$\tau\sigma (x)=x=\sigma\tau (x).$$
Si $x\in\sop (\tau )$ entonces $x\notin\sop (\sigma )$, luego $\tau\sigma (x)=\tau (x)$.
Por otra parte, como $\tau(x)\neq x$ y $\tau$ es biyectiva, tenemos $\tau(\tau(x))\neq \tau(x)$. Es decir, $\tau(x)\in\sop (\tau )$. Por tanto, $\tau(x)\not\in\sop (\sigma)$, lo que implica $\sigma\tau(x)=\tau(x)$.
%Tenemos que demostrar que $\sigma\tau (x)=\tau (x)$, si no es así entonces $\tau (x)\in\sop (\sigma )$ y por tanto $\tau (x)\notin\sop (\tau )$, lo cual lleva a $\tau (\tau (x))=\tau (x)$. Aplicando $\tau^{-1}$ en la expresión anterior obtenemos $\tau (x)=x$. Pero esto es contradictorio, pues $x\in\sop (\tau )$.
Luego
$$\tau\sigma (x)=\tau (x)=\sigma\tau (x).$$
Análogamente, si $x\in\sop (\sigma )$ se demuestra que
$$\sigma\tau (x)=\sigma (x)=\tau\sigma (x).$$
{{% /proof %}}

El recíproco no es cierto, es decir, si dos permutaciones conmutan no tienen por qué ser disjuntas. Veámoslo con un ejemplo.

{{% example name="Ejemplo" %}}

Sea $X=\\{ 1,2,3,4,5\\}$ y sean las permutaciones de $\Sim (X)$
$$\sigma\colon\left(\begin{array}{ccccc}
                     1 & 2 & 3 & 4 & 5\\
                     3 & 4 & 5 & 2 & 1
                    \end{array}\right)\mbox{ y }
   \tau\colon\left(\begin{array}{ccccc}
                     1 & 2 & 3 & 4 & 5\\
                     5 & 2 & 1 & 4 & 3
                    \end{array}\right) .$$
Ambas permutaciones no son disjuntas, pues $\sop (\sigma )\cap\sop (\tau )=\\{ 1,3,5\\}$. Sin embargo, no es difícil comprobar que
$$\tau\sigma=\sigma\tau\colon \left(\begin{array}{ccccc}
                                     1 & 2 & 3 & 4 & 5\\
                                     1 & 4 & 3 & 2 & 5
                                    \end{array}\right) .$$
{{% /example %}}

{{% watch %}}

De igual manera que hemos decidido usar la yuxtaposición, $xy$, para expresar la operación de dos elementos de un grupo $(G,\star )$, es natural definir potencias de elementos de $G$. Sean $x\in G$ e $i$ un entero no negativo. La $i$-ésima potencia de $x$, $x^i$, se define mediante la siguiente regla recursiva:
$$x^0=e,\ x^{i}=x^{i-1}x.$$
Esta definición la podemos extender a potencias negativas poniendo
$$x^{-i}=(x^{-1})^{i}.$$
En adelante se usará esta notación también para permutaciones.
{{% /watch %}}

Aprovecharemos que estamos hablando de potencias de permutaciones para definir, en general, el concepto de orden de un elemento de un grupo.


{{% definition %}}
{Orden de un elemento}
{Sea $(G,\star )$ un grupo.

Diremos que un elemento $x\in G$ tiene {\bf orden finito} si existe un número entero positivo $m$ tal que $x^m=e$. En este caso, el {\bf orden de $x$}, que denotaremos $o(x)$, es el menor entero positivo que cumple esta propiedad.

 Diremos que $x\in G$ tiene {\bf orden infinito} si $x^m\neq e$ para todo $m>0$.}
{{% /definition %}}


{{% proposition %}}

Un elemento $x\in G$ tiene orden infinito si y sólo si todas sus potencias $x^k$ con $k\in \mathbb Z$ son distintas.
{{% /proposition %}}

{{% proof %}}

Si $x$ tiene dos potencias iguales, digamos $x^r=x^s$ con $r<s$, entonces podemos multiplicar esta igualdad por $x^{-s}$ (desde la izquierda o desde la derecha) y obtendremos $x^{r-s}=e$, por lo que $x$ tendrá orden finito. Recíprocamente, si todas sus potencias son distintas, entonces $x^m\neq x^0 = e$ para todo $m>0$, luego $x$ tendrá orden infinito.
{{% /proof %}}


El orden de un elemento satisface las siguientes propiedades cuya demostración dejaremos como ejercicio:

{{% proposition %}}
 Sean $G$ un grupo y $x\in G$. Se tienen las siguientes propiedades:
 \begin{enumerate}
  \item $o(x)=1$ si y solamente si $x=e$.
  \item Si $x\in G$ tiene orden finito, entonces $\inv{x}$ también y $o(x)=o(\inv{x})$.
  \item Si $x\in G$ tiene orden infinito, $\inv{x}$ tiene orden infinito.
  \item Si $G$ es finito, todo elemento de $G$ tiene orden finito.
  \item Si $o(x)=m$ y $x^n=e$, entonces $m$ es un divisor de $n$.
        Dicho de otra forma, las potencias de $x$ iguales a $e$ son exactamente las de la forma $x^{km}$ con $k\in \mathbb Z$.
 \end{enumerate}
{{% /proposition %}}

En el caso de permutaciones, es fácil comprobar que el orden de un ciclo coincide con su longitud.

{{% theorem %}}
{Orden de un ciclo}
{El orden de un ciclo de longitud $m\geq 1$ es $m$.}
{{% /theorem %}}

El siguiente resultado
%dice que toda permutación con soporte finito se puede escribir como producto de ciclos disjuntos. Este resultado
será muy importante para el estudio de las permutaciones de conjuntos finitos.

{{% theorem %}}
{Expresión en ciclos disjuntos}
{Toda permutación con soporte finito puede expresarse como producto de ciclos disjuntos, además esta descomposición es única salvo el orden de los ciclos.}
{{% /theorem %}}

%{{% proof %}}

%Sean $X$ un conjunto y $\sigma\in\Sim (X)$ una permutación con soporte finito. Si $\sigma =1_X$ es un ciclo, luego ya está. Supongamos que $\sigma\ne 1_X$ y que
%$$\sop (\sigma )=\\{ i_1,\ldots ,i_n\\} .$$
%Tomemos ahora los elementos $i_1$, $\sigma (i_1)$, $\sigma^2(i_1)$,... pertenecientes al conjunto finito $\\{ i_1,\ldots ,i_n\\}$. Luego no todos pueden ser diferentes, digamos $\sigma^r(i_1)=\sigma^s(i_1)$ con $r>s\geq 0$. Aplicando $(\sigma^{-1})^s$ a ambos miembros de la igualdad anterior tenemos $\sigma^{r-s}(i_1)=i_1$. Sea $m_1$ el menor entero positivo tal que $\sigma^{m_1}(i_1)=i_1$.
%
%Los elementos $i_1$, $\sigma (i_1)$, $\sigma^2(i_1)$,... $\sigma^{m_1-1}(i_1)$ son todos diferentes. En efecto, si ocurriera $\sigma^r(i_1)=\sigma^s(i_1)$ con $m_1>r>s\geq 0$, tendríamos $\sigma^{r-s}(i_1)=i_1$ donde $r-s<m_1$. Pero esto es una contradicción, pues $m_1$ es el menor tal que $\sigma^{m_1}(i_1)=i_1$. Luego el $m_1$-ciclo $(i_1\ \sigma (i_1)\ \sigma^2(i_1)\cdots \sigma^{m_1-1}(i_1))$ es un factor de $\sigma$.
%
%Si $\sop (\sigma )=\\{ i_1,\sigma (i_1),\sigma^2(i_1),\ldots\sigma^{m_1-1}(i_1)\\}$ entonces $\sigma$ debe ser el $m_1$-ciclo $\left( i_1\ \sigma (i_1)\ \sigma^2(i_1)\cdots \sigma^{m_1-1}(i_1)\right)$. En otro caso, existe un elemento $i_2\in\sop (\sigma )\setminus\\{ i_1,\sigma (i_1),\sigma^2(i_1),\ldots\sigma^{m_1-1}(i_1)\\}$. Procediendo como arriba, obtenemos un $m_2$-ciclo $(i_2\ \sigma (i_2)\ \sigma^2(i_2)\cdots \sigma^{m_2-1}(i_2))$ disjunto con el anterior y que también es un factor de $\sigma$.
%
%Dado que el soporte de $\sigma$ es finito, repitiendo el procedimiento, en un número finito de pasos obtenemos una descomposición de $\sigma$ en $\ell$ ciclos disjuntos:
%$$\sigma = \left( i_1\ \sigma (i_1)\ \sigma^2(i_1)\cdots \sigma^{m_1-1}(i_1)\right) \left( i_2\ \sigma (i_2)\ \sigma^2(i_2)\cdots \sigma^{m_2-1}(i_2)\right)\cdots$$
%$$\cdots\left( i_\ell\ \sigma (i_\ell)\ \sigma^2(i_\ell)\cdots \sigma^{m_\ell -1}(i_\ell)\right) .$$
%
%Demostremos ahora la unicidad. Sean
%$$\sigma = \left( i_1\ \sigma (i_1)\ \sigma^2(i_1)\cdots \sigma^{m_1-1}(i_1)\right) \cdots\left( i_\ell\ \sigma (i_\ell)\ \sigma^2(i_\ell)\cdots \sigma^{m_\ell -1}(i_\ell)\right) =$$
%$$=\left( j_1\ \sigma (j_1)\ \sigma^2(j_1)\cdots \sigma^{n_1-1}(j_1)\right) \cdots\left( j_p\ \sigma (j_p)\ \sigma^2(j_p)\cdots \sigma^{n_p-1}(j_p)\right)$$
%dos representaciones de $\sigma$ como producto de ciclos disjuntos. Dado que $i_1\in\sop (\sigma )$, debe pertenecer a alguno de los ciclos de la segunda expresión de $\sigma$. Dado que el producto de ciclos disjuntos conmuta podemos suponer, sin pérdida de generalidad, que está en el primer ciclo. Además, por lo dicho al final de la nota \ref{nota231}, cada ciclo se puede escribir de diferentes formas. Luego podemos suponer, escogiendo la representación adecuada del ciclo $\left( j_1\ \sigma (j_1)\ \sigma^2(j_1)\cdots \sigma^{n_1-1}(j_1)\right)$, que $i_1=j_1$. Automáticamente se obtiene que $\sigma (i_1)=\sigma (j_1)$, $\sigma^2(i_1)=\sigma^2(j_1)$,... de donde se deduce $m_1=n_1$ y
%$$ \left( i_1\ \sigma (i_1)\ \sigma^2(i_1)\cdots \sigma^{m_1-1}(i_1)\right) = \left( j_1\ \sigma (j_1)\ \sigma^2(j_1)\cdots \sigma^{n_1-1}(j_1)\right) .$$
%Haciendo lo mismo con $i_2$,...,$i_\ell$ se concluye que $\ell =p$ y que ambas descomposiciones coinciden.
%{{% /proof %}}

{{% proof %}}

Sea $\sigma\in\Sim (X)$ una permutación. Definimos la {\bf órbita} de un elemento $x\in X$ respecto de $\sigma$ como
$$\overline{x}=\\{\sigma^n(x); n\geq 0\\}.$$
Si $x\notin\sop (\sigma )$, entonces $\overline{x}=\\{ x\\}$. Si $x\in\sop (\sigma )$, entonces $\overline{x}\subset\sop (\sigma )$ es un conjunto finito. Es decir, existe un (primer) $m>0$ tal que $\sigma^m(x)=x$ y a partir de ahí los elementos $\sigma^n (x)$ se van repitiendo.

%  Como $\sigma$ tiene soporte finito, una potencia de $\sigma$ es la identidad, luego las potencias de $\sigma$ se van repitiendo y $\overline{x}$ es siempre un conjunto finito.

Ahora podemos definir la siguiente relación en $X$: $x$ está relacionado con $y$ si $y\in \overline{x}$. Se demuestra fácilmente que ésta es una relación de equivalencia, y que las clases de equivalencia son las órbitas de los elementos de $X$.

Observamos ahora que cada clase de equivalencia, cada órbita $\overline{x}$, corresponde a un ciclo que es, bien $()$ si $\overline{x}=\\{ x\\}$, bien $(x\ \sigma (x)\cdots\sigma^{m-1}(x))$ si $m>1$ es el menor tal que $\sigma^m(x)=x$. Estos ciclos son disjuntos, pues son clases de equivalencia. Además, si $\sigma\ne ()$, debe ser la composición de estos ciclos disjuntos no triviales. El número de ciclos de orden $>1$ es finito, porque el soporte de $\sigma$ es finito.

Por otra parte, si descomponemos $\sigma$ como producto de ciclos disjuntos, cada ciclo es una órbita, luego es una clase de equivalencia para la relación anterior. Y deben estar todas las órbitas, o el producto de los ciclos no sería igual a $\sigma$. Luego esta descomposición debe coincidir con la descomposición anterior, que es por tanto única.
{{% /proof %}}

{{% example name="Ejemplo" %}}

En $X=\\{ 1,2,3,4,5,6,7\\}$ consideremos la permutación
$$\sigma\colon\left(\begin{array}{ccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7\\
                     3 & 6 & 5 & 1 & 4 & 2 & 7
                    \end{array}\right) .$$
Calculando las órbitas de los elementos de $X$ se obtiene:
$$\overline{1}=\\{ 1,3,5,4\\} =\overline{3}=\overline{5}=\overline{4}\rightsquigarrow (1354),$$
$$\overline{2}=\\{ 2,6\\} =\overline{6}\rightsquigarrow (26),$$
$$\overline{7}=\\{ 7\\}\rightsquigarrow ().$$
La expresión de $\sigma$ como producto de ciclos disjuntos es
$$\sigma =(1354)(26).$$
{{% /example %}}

{{% corollary %}}

Sea $X$ un conjunto con al menos dos elementos. Toda permutación de $\Sim (X)$ con soporte finito puede expresarse como producto de trasposiciones.
{{% /corollary %}}

{{% proof %}}

La permutación identidad se puede escribir como $()=\tau\tau$, siendo $\tau$ cualquier trasposición. Si la permutación no es la identidad, dado que toda permutación con soporte finito puede expresarse como producto de ciclos disjuntos, es suficiente demostrar que los ciclos  de longitud $\geq 2$ pueden expresarse como producto de trasposiciones. Es fácil comprobar que se satisface la siguiente igualdad:
$$ (i_1i_2\ldots i_{r-1}i_r)=(i_1i_2)(i_2i_3)\cdots (i_{r-1}i_r).$$
{{% /proof %}}

{{% example name="Ejemplo" %}}

En el ejemplo anterior, donde $\sigma =(1354)(26)$, se tiene que
$$(1354)=(13)(35)(54).$$
Luego $\sigma =(13)(35)(54)(26)$. Aprovechamos este ejemplo para comprobar además que {\bf la descomposición en producto de trasposiciones no es única}, pues también se verifica
$$\sigma =(14)(23)(15)(23)(13)(26) .$$
{{% /example %}}

{{% corollary %}}

Toda permutación con soporte finito tiene orden finito.
{{% /corollary %}}

{{% proof %}}

Sea $\sigma\in\Sim (X)$ una permutación con soporte finito. Si $\sigma =()$ su orden es $1$. Si $\sigma\ne ()$ se descompone como producto de $r\geq 1$ ciclos disjuntos
$$\sigma =\sigma_r\cdots\sigma_1.$$
Cada ciclo $\sigma_i$ tiene orden finito $n_i$. Además, como el producto de ciclos disjuntos es conmutativo
$$\sigma^p=(\sigma_r\cdots\sigma_1)^p=\sigma_r^p\cdots\sigma_1^p.$$
Sea $n=\prod_{i=1}^r n_i$, entonces
$$\sigma^n=\sigma_r^n\cdots\sigma_1^n=().$$
Luego el orden de $\sigma$ es finito.
{{% /proof %}}

{{% watch %}}

¡Ojo! En la demostración anterior {\bf no hemos probado} que el orden de $\sigma$ sea el producto de los órdenes de los ciclos en los que se descompone. De hecho es un buen ejercicio para el próximo tema (El anillo de los números enteros) demostrar que el orden de $\sigma$ es el {\bf mínimo común múltiplo de los $n_i$}.
{{% /watch %}}

### El grupo $S_n$

En este apartado vamos a estudiar las permutaciones de conjuntos finitos. Sea entonces el conjunto $X=\\{ 1,2,\ldots ,n\\}$, y denotemos por $S_n$ al grupo $\Sim(X)$ de permutaciones de estos $n$ elementos.

{{% definition %}}
{Orden de un grupo} {Sea $(G,\star)$ un grupo. Definimos su {\bf orden}, que notaremos por $|G|$, como el cardinal
del conjunto $G$.}
{{% /definition %}}

{{% theorem %}}
{Orden de $S_n$}
{El orden del grupo $S_n$ es $|S_n|=n!$}
{{% /theorem %}}

{{% proof %}}

Sea $\sigma$ una permutación cualquiera de $S_n$, podemos escribir
$$\sigma\colon\left(\begin{array}{cccccc}
                     1 & 2 & \cdots & n\\
                     i_1 & i_2 & \cdots & i_n
                    \end{array}\right) .$$
Hay $n$ posibles elecciones para $i_1$, pero sólo $n-1$ posibilidades para $i_2$, pues $i_1$ no puede ser elegido de nuevo. Fijados $i_1$ e $i_2$ hay $n-2$ posibles elecciones para $i_3,\ldots$ y así sucesivamente hasta llegar a $i_n$, cuya elección ya está fijada por la de los elementos anteriores. Luego contando todas las posibilidades el número de permutaciones distintas de $S_n$ es
$$n(n-1)\cdots 1=n!$$
{{% /proof %}}

{{% example name="Ejemplo" %}}

Siguiendo el procedimiento anterior podemos dar la lista de todas las permutaciones de $S_3$:
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         1 & 2 & 3
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         1 & 3 & 2
        \end{array}\right) ,
$$
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         2 & 1 & 3
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         2 & 3 & 1
        \end{array}\right),
$$
$$\left(\begin{array}{ccc}
         1 & 2 & 3\\
         3 & 2 & 1
        \end{array}\right) ,\ \ \ \
  \left(\begin{array}{ccc}
         1 & 2 & 3\\
         3 & 1 & 2
        \end{array}\right) .
$$
Expresadas como productos de ciclos las permutaciones de $S_3$ son
$$S_3=\\{ (), (23), (12), (123), (13), (132)\\} .$$
{{% /example %}}

%{{% watch %}}

%En adelante para el conjunto $X=\\{ 1,2,\ldots ,n\\}$ notaremos $1_X=(1)$, como el ciclo que deja invariante al $1$ y a todos los demás elementos.
%{{% /watch %}}

Dado que $X=\\{ 1,2,\ldots ,n\\}$ es un conjunto finito, todas las permutaciones de $S_n$ tienen soporte finito y los resultados enunciados anteriormente se aplican a $S_n$, es decir,

{{% theorem %}}
{Descomposición en ciclos disjuntos y trasposiciones}
{Toda permutación de $S_n$ se descompone de manera única, salvo orden, como producto conmutativo de ciclos disjuntos. Además toda permutación de $S_n$ se puede expresar como producto de trasposiciones, esta vez {\bf no} de manera única.}
{{% /theorem %}}

### Explicación del juego inicial

Llegados a este punto podemos explicar cuál es la "magia" del juego de cartas. Teníamos cartas del mismo palo numeradas del 1 al 9 y las vamos "desordenando" hasta llegar a la posición inicial. Se trata por tanto de una combinación de permutaciones de $S_9$ que, "mágicamente", llegan a la identidad.

La {\bf separación de cartas} es la siguiente permutación\footnote{En realidad hay dos posibles separaciones, pues nosotros decidimos qué montón ponemos encima del otro, habría que estudiar varios casos que serían análogos a éste y que concluyen de igual forma.}:
$$\sigma\colon\left(\begin{array}{ccccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
                     9 & 4 & 8 & 3 & 7 & 2 & 6 & 1 & 5
                    \end{array}\right) .$$
Que es $\sigma =(195762438)$ un ciclo de longitud $9$. Si no cortáramos, separar dos veces es
$$\sigma^2=(156489723).$$
Y separar tres veces
$$\sigma^3=(174)(285)(396).$$

%Cortar una carta es la permutación
$$\kappa\colon\left(\begin{array}{ccccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9\\
                     2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 1
                    \end{array}\right) .$$
Que en forma de ciclo es $\kappa =(123456789)$. Cortar dos cartas es igual a cortar una carta y luego otra, es decir,
$$\kappa^2=(135792468).$$
Y cortar varias cartas es:
$$\kappa^3=(147)(258)(369),\ \kappa^4=(159483726),\ \kappa^5=(162738495),$$
$$\kappa^6=(174)(285)(396),\ \kappa^7=(186429753),\ \kappa^8=(198765432)\mbox{ y }\kappa^9=().$$

\noindent {\bf Primer "hechizo mágico":} Separar tres veces seguidas es igual a cortar seis cartas\footnote{Es aquí donde sí tiene influencia relativa el hecho de poder decidir qué montón ponemos encima del otro. En cualquier caso, hagamos la elección que hagamos, separar tres veces es igual a cortar varias cartas.}.
$$\sigma^3=\kappa^6.$$

Sabemos que en el caso de las permutaciones el orden de los factores sí altera el producto. Cortar y separar no es lo mismo que separar y cortar:
$$\sigma\kappa =(147)(285),$$
$$\kappa\sigma =(258)(396).$$
Si embargo, cortar siete cartas y separar es
$$\sigma\kappa^7=(195762438)(186429753)=(258)(396)=\kappa\sigma .$$

\noindent {\bf Segundo "hechizo mágico":} Cortar siete cartas y separar es lo mismo que separar y después cortar una carta\footnote{Al igual que anteriormente, si al separar elegimos poner otro montón encima, siempre obtendremos una relación parecida en la que cortar varias cartas y separar equivale a separar y después cortar una carta.}.
$$\kappa\sigma =\sigma\kappa^7.$$
Por lo tanto, si bien es cierto que la composición no es conmutativa, sí tenemos ciertas reglas que nos permiten cambiar de posición "separar" y "cortar". En efecto:
$$\kappa^2\sigma =\kappa (\kappa\sigma )= \kappa \sigma \kappa^7 = (\kappa\sigma )\kappa^7=\sigma\kappa^7\kappa^7=\sigma\kappa^5.$$
$$\kappa^3\sigma =\kappa (\kappa^2\sigma )=\kappa \sigma \kappa^5=(\kappa\sigma )\kappa^5=\sigma\kappa^7\kappa^5=\sigma\kappa^3.$$
$$\kappa^4\sigma =\kappa (\kappa^3\sigma )=\kappa\sigma\kappa^3=(\kappa\sigma )\kappa^3=\sigma\kappa^7\kappa^3=\sigma\kappa.$$
$$\kappa^5\sigma =\cdots =\sigma\kappa^8.$$
$$\kappa^6\sigma =\cdots =\sigma\kappa^6.$$
$$\kappa^7\sigma =\cdots =\sigma\kappa^4 .$$
$$\kappa^8\sigma =\cdots =\sigma\kappa^2.$$

Ya tenemos las herramientas y "hechizos" necesarios para la explicación del juego. Inicialmente tenemos las $9$ cartas ordenadas y lo que hacemos en el juego es separar las cartas, cortar varias veces, separar otra vez las cartas, cortar varias veces y separar por tercera vez las cartas y cortar varias veces. Esto es:
$$(\kappa^r\sigma )(\kappa^q\sigma )(\kappa^p\sigma )= (\sigma\kappa^{r'})(\sigma\kappa^{q'})(\sigma\kappa^{p'})=\sigma (\kappa^{r'}\sigma )(\kappa^{q'}\sigma )\kappa^{p'}=$$
$$=\sigma (\sigma\kappa^{r"})(\sigma\kappa^{q"})\kappa^{p'} =\sigma^2(\kappa^{r"}\sigma )\kappa^{q"+p'}=\sigma^2(\sigma\kappa^{r"'})\kappa^{q"+p'}=\sigma^3\kappa^{r"'+q"+p'}=$$
$$=\kappa^6\kappa^{r"'+q"+p'}=\kappa^{6+r"'+q"+p'}.$$
Por tanto, después de realizar el juego lo que nos queda es {\bf un simple corte}. Al mirar la primera carta sabemos cuántas cartas tenemos que cortar para dejar nuestras nueve cartas ordenadas como al principio.

### Permutaciones pares e impares

Si $\sigma$ es una permutación de $S_n$ entonces $\sigma$ sustituye el orden natural de los enteros $1,2,\ldots ,n$ por el nuevo orden $\sigma (1),\sigma (2),\ldots ,\sigma (n)$. Así que la acción de $\sigma$ puede causar {\em inversiones} del orden natural.

{{% definition %}}
{Inversiones en una permutación}
{Se dice que un par $(i,j)$ es una {\bf inversión} de $\sigma\in S_n$, si
$$i<j \qquad y \qquad \sigma (i)>\sigma (j).$$}
{{% /definition %}}


{{% definition %}}
{Signo de una permutación}
{Si $\sigma\in S_n$ tiene un número par de inversiones, diremos que $\sigma$ es {\bf par}, y que $\signo(\sigma)=1$.


Si $\sigma\in S_n$ tiene un número impar de inversiones, diremos que $\sigma$ es {\bf impar}, y que $\signo(\sigma)=-1$.
}
{{% /definition %}}

{{% example name="Ejemplo" %}}

Las permutaciones pares de $S_3$ son $()$, $(123)$ y $(132)$, mientras que las impares son $(12)$, $(13)$ y $(23)$.
{{% /example %}}

Para decidir si una permutación (no demasiado grande) es par o impar es útil hacer un diagrama de cruces. Veamos esto con un ejemplo:

{{% example name="Ejemplo" %}}

?`Es la permutación
$$\sigma\colon\left(\begin{array}{ccccccc}
                     1 & 2 & 3 & 4 & 5 & 6 & 7\\
                     6 & 3 & 1 & 5 & 4 & 7 & 2
                    \end{array}\right) $$
par o impar?

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics{diagrama_inversiones.eps}
 }
 \caption{Inversiones de $\sigma$}
 \label{inversiones}
\end{figure}

Simplemente ponemos en dos filas los números del 1 al 7, y unimos el número $i$ de la fila superior al número $\sigma(i)$ de la fila inferior, teniendo cuidado de evitar intersecciones múltiples o innecesarias. Un cruce indica una inversión del orden natural.

Hay $11$ cruces, luego $\signo (\sigma )=-1$ y $\sigma$ es una permutación impar.
{{% /example %}}

El próximo resultado es es una propiedad significativa de las trasposiciones.

{{% proposition %}}
 Las trasposiciones son siempre impares.
{{% /proposition %}}

{{% proof %}}

Consideremos el diagrama de cruces (figura \ref{trasposicion-cruces}) para la trasposición $\tau =(ij)$ donde $i<j$. Contando obtenemos $2(j-i-1)+1$ cruces, que siempre es impar. Luego $\tau =(ij)$ es una permutación impar.
{{% /proof %}}

\begin{figure}[htbp]
 \centering
 {
 %\includegraphics*[bb=0mm 0mm 109mm 103mm, scale=.5, angle=-90]{kakuro01.eps}
 \includegraphics{diagrama_trasposicion.eps}
 }
 \caption{Diagrama de cruces de $\tau =(ij)$}
 \label{trasposicion-cruces}
\end{figure}

Las siguientes son propiedades básicas de la función $\signo$.

{{% proposition %}}

Sean $\sigma ,\tau\in S_n$. Se satisfacen las siguientes propiedades:
\begin{enumerate}
\item $\signo (\sigma\tau )=\signo (\sigma )\signo (\tau )$.
\item $\signo (\sigma^{-1})=\signo (\sigma )$.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}

\begin{enumerate}

\item Consideremos el diagrama que se obtiene dibujando el diagrama de cruces de $\tau$ encima del de $\sigma$. Este diagrama representa a la permutación $\sigma\tau$, aunque hay pares de líneas que se pueden cruzar dos veces (una en $\tau$ y otra en $\sigma$).

    Un par $(i,j)$ será una inversión de $\sigma\tau$ si y sólo si las líneas correspondientes se cruzan sólo en $\sigma$ o sólo en $\tau$, pero no en ambas. Por tanto, para obtener el número de inversiones de $\sigma\tau$, sólo hay que sumar los cruces del diagrama de $\sigma$ y los cruces del diagrama de $\tau$, y a continuación restar un número par de cruces (los que aparecen en los dos). Por tanto, el número de inversiones de $\sigma\tau$ tiene la misma paridad que la suma del número de inversiones de $\sigma$ y el número de inversiones de $\tau$. Así, $\sigma\tau$ es par si $\sigma$ y $\tau$ son ambos pares o ambos impares, y es impar en caso contrario. Esto equivale a decir que $\signo(\sigma\tau)=\signo(\sigma)\signo(\tau)$.

\item Esto se deduce de la propiedad anterior, tomando $\tau=\sigma^{-1}$, aunque se puede ver directamente: los diagramas de cruces de $\sigma$ y $\sigma^{-1}$ son simétricos, luego el número de cruces es el mismo en ambos diagramas. Por tanto $\sigma$ y $\sigma^{-1}$ tienen el mismo número de inversiones, y por ello el mismo signo.
\end{enumerate}
{{% /proof %}}

{{% corollary %}}

Una permutación $\sigma\in S_n$ es par (impar) si y sólo si es producto de un número par (impar) de trasposiciones.
{{% /corollary %}}

{{% proof %}}

En efecto, si $\sigma =\tau_1\cdots\tau_r$ donde cada $\tau_i$ es una trasposición, entonces
$$\signo (\sigma )=\prod_{i=1}^r\signo (\tau_i)=(-1)^r.$$
{{% /proof %}}

Finalizamos esta sección con la fórmula de {\em Cauchy} que relaciona el signo de una permutación con su descomposición en ciclos disjuntos.

{{% theorem %}}
{Fórmula de Cauchy}
{Sea $\sigma\in S_n$ el producto de $c$ ciclos disjuntos entonces
$$\signo (\sigma )=(-1)^{m-c},$$
siendo $m=\#(\sop (\sigma ))$ el número de elementos del soporte de $\sigma$.}
{{% /theorem %}}

{{% proof %}}

Sea $\sigma =\sigma_1\cdots\sigma_c$ la descomposición de $\sigma$ en ciclos disjuntos, supongamos que cada $\sigma_j$ tiene longitud $\ell_j$. Sabemos que $\sigma_j$ es producto de $\ell_j-1$ trasposiciones. Luego $\signo (\sigma_j)=(-1)^{\ell_j-1}$ y
$$\signo (\sigma )=\prod_{j=1}^c\signo (\sigma_j)=\prod_{j=1}^c(-1)^{\ell_j-1}=(-1)^{m-c},$$
pues $\sum_{j=1}^c\ell_j=m$.
{{% /proof %}}

{{% watch %}}

En particular, el signo de un ciclo de longitud $m$ es $(-1)^{m-1}$. Luego la paridad del ciclo está cambiada respecto de su longitud: {\bf un ciclo de longitud par es impar y un ciclo de longitud impar es par}.
{{% /watch %}}

## Subgrupos. Teorema de Lagrange

{{% definition %}}
{Subgrupo} {Sea $(G,\star)$ un grupo. Un subconjunto $H$ de $G$ se dice que es un {\bf subgrupo} de
$(G,\star)$ si  $(H,\star)$ es un grupo. Es decir, si el conjunto $H$, y la operación definida en $G$, cumplen las propiedades de la definición de grupo.


Un subgrupo es, por tanto, un grupo dentro de otro grupo con la misma operación.}
{{% /definition %}}

{{% example name="Ejemplo" %}}

Veamos algunos ejemplos de subgrupos:
\begin{enumerate}
\item Vimos en el ejemplo \ref{ejemplo-grupos} que los conjuntos de números $\Z ,\Q ,\R$ y $\C$ son grupos abelianos con la suma. De hecho es una cadena de subgrupos $\Z\subset\Q\subset\R\subset\C$.
\item Lo mismo ocurre con los grupos $\Q^*=\Q\setminus\\{ 0\\}$, $\R^*=\R\setminus\\{ 0\\}$ y $\C^*=\C\setminus\\{ 0\\}$ con la multiplicación. Es también una cadena de subgrupos $\Q^*\subset\RR^*\subset\C^*$.
\item Sabemos que GL$(n,k)$, el conjunto de las matrices $n\times n$, con elementos en un cuerpo $k$ y determinante no nulo, es un grupo con la multiplicación de matrices. Sea $\text{SL}(n,k)$ el subconjunto de GL$(n,k)$ formado por las matrices con determinante igual a $1$. Comprobemos que $\text{SL}(n,k)$ es un subgrupo de GL$(n,k)$. En efecto, si $A,B\in \text{SL}(n,k)$ entonces $\det (AB)=\det (A)\det (B)=1$, luego $AB\in \text{SL}(n,k)$. La matriz identidad, $I_n$ tiene determinante igual a $1$, luego pertenece a $\text{SL}(n,k)$. Si $A\in \text{SL}(n,k)$, como $\det (A^{-1})=\det (A)^{-1}$ se tiene que $A^{-1}\in \text{SL}(n,k)$. Por último, como el producto en GL$(n,k)$ verifica la propiedad asociativa, en particular, también la satisface en $\text{SL}(n,k)$. Así que la multiplicación de matrices en $\text{SL}(n,k)$ es una operación  asociativa, con elemento neutro y cada matriz de $\text{SL}(n,k)$ tiene su inversa en el conjunto, luego es un grupo.
\item El subconjunto de $S_4$, $C=\\{ (), (1234), (13)(24), (1432)\\}$, es un subgrupo con la composición de permutaciones. Para comprobar que se satisfacen todas las propiedades de grupo, vamos a hacer la tabla de multiplicar de los elementos de $C$:
\begin{center}
 \begin{tabular}{|c||c|c|c|c|}
   \hline
   $\circ$ & $()$ & $(1234)$ & $(13)(24)$ & $(1432)$\\
   \hline\hline
   $()$ &  $()$ & $(1234)$ & $(13)(24)$ & $(1432)$\\
   \hline
   $(1234)$ & $(1234)$ & $(13)(24)$ & $(1432)$ & $()$\\
   \hline
   $(13)(24)$ & $(13)(24)$ & $(1432)$ & $()$ & $(1234)$\\
   \hline
   $(1432)$ & $(1432)$ & $()$ & $(1234)$ & $(13)(24)$\\
   \hline
 \end{tabular}
\end{center}
En la tabla se observa que la multiplicación es una operación de $C\times C \to C$, que está el elemento neutro $()$ y que cada elemento tiene un simétrico. Además, el producto en $C$ es asociativo, pues lo es en $S_4$. Luego es subgrupo. El hecho de que la tabla sea simétrica nos permite deducir que en este caso el subgrupo $C$ es conmutativo. Se da así la circunstancia de que un subgrupo de un grupo no conmutativo, como $S_4$, puede ser conmutativo.
\end{enumerate}
{{% /example %}}

{{% watch %}}

Si $G$ es un grupo y $H\subset G$ es finito, para comprobar que es subgrupo es suficiente hacer la tabla de multiplicar y razonar como en el ejemplo anterior. Si $H$ es infinito hay que demostrar que la operación entre elementos de $H$ está bien definida, que el elemento neutro pertenece a $H$ y que el simétrico de cada elemento de $H$ está también en $H$. En cualquier caso, la propiedad asociativa se "hereda" de $G$.
{{% /watch %}}

El siguiente resultado nos permite "ahorrarnos" verificar alguna propiedad a la hora de demostrar que un subconjunto es subgrupo.

{{% proposition %}}
{\label{subgrupo}}  Sean $(G,\star)$ un grupo y $H\subset G$ un subconjunto no vacío. Las condiciones siguientes son equivalentes:
 \begin{itemize}
  \item[$(1)$] $H$ es un subgrupo de $(G,\star)$.
  \item[$(2)$] Para cada par de elementos $x,y\in H$, tenemos que $x \inv{y}\in H$.
 \end{itemize}
{{% /proposition %}}

{{% proof %}}
 Veamos primero $(1)\Rightarrow (2)$. Sean $x,y\in H$. Como $H$ es subgrupo, contiene los simétricos de todos sus elementos. En particular $\inv{y}\in H$. De nuevo como $H$ es subgrupo la operación esta bien definida, de donde $x\inv{y}\in H$, como queríamos.



Probemos ahora $(2)\Rightarrow (1)$. Como $H \subset G$, los elementos
de $H$ verifican la propiedad asociativa. Como $H$ es no vacío, sea
$a\in H$. Aplicando (2) con $x=a$ e $y=a$, obtenemos
$$
a\inv{a}=e\in H,
$$
luego $H$ tiene un elemento neutro (el mismo que $G$).

Si $a\in H$, aplicando de nuevo (2) con $x=e$ e $y=a$, tenemos
$$
e \inv{a} =\inv{a}\in H,
$$
luego $H$ contiene los simétricos de todos sus elementos.

Sólo falta demostrar que la operación de $G$ es una operación en $H$. Sean
$a,b\in H$. Aplicando (2) esta vez con $x=a$ e $y=\inv{b}$ se tiene
$$
 a\inv{(\inv{b})}=a b\in H.
$$
Luego $H$ es subgrupo de $G$.
{{% /proof %}}

{{% watch %}}

Sea $(G,\star )$ un grupo y sea $x=x_1\cdots x_n$ un elemento de $G$, entonces el simétrico de $x$ es
$$\inv{x}=\inv{x_n}\cdots\inv{x_1}.$$
Así, si $\sigma =\rho_1\cdots\rho_n$ es una permutación, entonces su inversa es
$$\sigma^{-1}=\rho_n^{-1}\cdots\rho_1^{-1}.$$
Por otro lado, como el inverso de una trasposición es la misma trasposición, si $\delta =\tau_1\cdots\tau_m$ es una permutación producto de trasposiciones, su inversa es
$$\delta^{-1}=\tau_m\cdots\tau_1.$$
{{% /watch %}}

{{% theorem %}}
{El grupo alternado $A_n$}
{El conjunto $A_n$ de las permutaciones pares de $S_n$ es un subgrupo llamado {\bf grupo alternado}.}
{{% /theorem %}}

{{% proof %}}

Desde luego $()$ es una permutación par, luego $A_n$ es no vacío.
%Por otro lado, si la permutación $\sigma$ se escribe $\sigma =\tau_1\cdots\tau_r$ como producto de trasposiciones, entonces $\sigma^{-1}=\tau_r\cdots\tau_1$. Por tanto, la permutación inversa de una permutación par también es par.

Si $\sigma =\tau_1\cdots \tau_{2r}$ y $\rho=\pi_1\cdots \pi_{2s}$ son permutaciones pares, donde $\tau_i$ y $\pi_j$ son trasposiciones, entonces
$$\sigma\rho^{-1}=\tau_1\cdots \tau_{2r}\pi_{2s}\cdots\pi_1$$
es también una permutación par.

Luego por la proposición \ref{subgrupo} se concluye que $A_n$ es un subgrupo de $S_n$.
{{% /proof %}}

{{% proposition %}}

Sea $H\in S_n$ un subgrupo que tiene alguna permutación impar, entonces $H$ posee tantas permutaciones pares como impares.
{{% /proposition %}}

{{% proof %}}

Sean $P$ e $I$ los subconjuntos de $H$ formados por las permutaciones pares e impares, respectivamente. Sea $\rho\in H$ una permutación impar. Consideremos la aplicación
$$\begin{array}{rcl}
   \varphi\colon P&\to&I\\
   \sigma & \mapsto & \rho\sigma  .
  \end{array}$$
Efectivamente $\varphi$ es una aplicación bien definida, pues si $\sigma$ es una permutación par, como $\rho$ es impar, el producto $\rho\sigma$ es también impar.

Si $\varphi (\sigma )=\varphi (\tau )$ entonces $\rho\sigma =\rho\tau$, multiplicando desde la izquierda por $\rho^{-1}$ obtenemos $\sigma =\tau$. Luego $\varphi$ es una aplicación inyectiva.

Por otro lado, si $\sigma\in I$, como $\rho^{-1}$ es impar, entonces $\rho^{-1}\sigma \in P$ y además $\varphi (\rho^{-1}\sigma )=\rho\rho^{-1}\sigma =\sigma$. Luego $\varphi$ es sobreyectiva.

Por tanto la aplicación $\varphi$ es biyectiva y hay tantas permutaciones pares como impares en $H$.
{{% /proof %}}

{{% corollary %}}

Si $n\geq 2$, el número de elementos de $A_n$ es $|A_n|=n!/2$, es decir, en $S_n$ hay tantas permutaciones pares como impares.
{{% /corollary %}}

{{% proof %}}

$S_n$ es un subgrupo de $S_n$ que, como $n\geq 2$, contiene a la permutación impar $(12)$. Luego podemos aplicar la proposición anterior para deducir que hay tantas permutaciones pares como impares.
{{% /proof %}}

{{% theorem %}}
{Subgrupo generado}
{Sean $(G,\star )$ un grupo y $A\subset G$ un subconjunto no vacío. Sea $\inv{A}=\\{\inv{x}\in G\mid x\in A\\}$ el conjunto de los elementos simétricos a los de $A$. Entonces el conjunto que se obtiene al operar sucesiones arbitrarias de elementos de $A$ y $\inv{A}$,
$$\langle A\rangle =\\{ x_1\cdots x_n\mid x_i\in A\cup \inv{A},n\geq 1\\} ,$$
es un subgrupo de $G$ llamado {\bf subgrupo generado por $A$}.}
{{% /theorem %}}

{{% proof %}}

Como $A\ne\emptyset$, entonces $\langle A\rangle$ también es no vacío.

Por otro lado, sean $x=x_1\cdots x_n$ e $y=y_1\cdots y_m$ dos elementos de $\langle A\rangle$, es decir, tales que $x_i,y_j\in A\cup \inv{A}$. Es evidente que cada $\inv{y_j}$ también pertenece a $A\cup \inv{A}$. Luego
$$x\inv{y}=(x_1\cdots x_n) \inv{(y_1\cdots y_m)}=x_1\cdots x_n \inv{y_m}\cdots \inv{y_1}$$
es un elemento de $\langle A\rangle$.
{{% /proof %}}

{{% example name="Ejemplo" %}}

En el grupo $S_4$ calcular todos los elementos del subgrupo $H=\langle (124),(12)\rangle$. Hay que ir operando los elementos $(123)$, $(12)$ y sus inversos, adjuntando a la lista los nuevos elementos que se obtengan. Hasta estar seguros de haberlos encontrado todos. Una buena forma de hacer esto es ir haciendo la tabla de multiplicar del conjunto, hasta que no se incorpore ningún nuevo elemento:
\begin{center}
\begin{tabular}{|c||c|c|c|c|c|c|}
\hline
$\circ$ & $()$ & $(124)$ & $(142)$ & $(12)$ & $(14)$ & $(24)$\\
\hline\hline
$()$ & $()$ & $(124)$ & $(142)$ & $(12)$ & $(14)$ & $(24)$\\
\hline
$(124)$ & $(124)$ & $(142)$ & $()$ & $(14)$ & $(24)$ & $(12)$\\
\hline
$(142)$ & $(142)$ & $()$ & $(124)$ & $(24)$ & $(12)$ & $(14)$\\
\hline
$(12)$ & $(12)$ & $(24)$ & $(14)$ & $()$ & $(142)$ & $(124)$\\
\hline
$(14)$ & $(14)$ & $(12)$ & $(24)$ & $(124)$ & $()$ & $(142)$\\
\hline
$(24)$ & $(24)$ & $(14)$ & $(12)$ & $(142)$ & $(124)$ & $()$\\
\hline
\end{tabular}
\end{center}
En este caso $H=\\{ (), (124), (142), (12), (14), (24)\\}$.

Claro que este método es operativo si el grupo no es demasiado grande. Por ejemplo, si calculamos los elementos de $\langle (123),(234)\rangle$, obtenemos el grupo alternado $A_4$. Este grupo tiene $12$ elementos, como hemos visto, luego su tabla de multiplicar tiene ¡$144$ entradas! Sin embargo, usando las propiedades que conocemos de permutaciones podemos ahorrar algunos cálculos. En este último caso sabemos que las permutaciones $(123)$ y $(234)$ son pares, así que lo serán también todas las permutaciones que calculemos a partir de ellas, esto quiere decir que el grupo $\langle (123),(234)\rangle$ tiene como mucho $12$ elementos. Así que en cuanto obtengamos $12$ distintos ya sabemos que hemos terminado.

Otra propiedad que podemos usar si es pertinente, aunque en este último ejemplo no, es que sabemos que si un grupo tiene elementos impares entonces tiene la misma cantidad de pares que de impares.
{{% /example %}}

{{% definition %}}
{Grupo cíclico} {Se dice que un grupo $G$ es {\bf cíclico} si existe $a\in G$ tal que
 $$
G=\langle a \rangle =\langle\\{ a\\}\rangle =\\{ a^m\mid m\in \Z\\} .
$$}
{{% /definition %}}

{{% example name="Ejemplo" %}}

El grupo $S_3$ no es cíclico, pues no existe ninguna permutación que genere todo el grupo. El grupo alternado $A_3=\\{ (),(123),(132)\\}$ es cíclico, pues $A_3=\langle (123)\rangle =\langle (132)\rangle$.

De hecho, para comprobar si un grupo finito de orden $m$ es o no cíclico, hay que verificar si existe o no en el grupo algún elemento de orden $m$. En $S_3$ no hay elementos de orden $6$ mientras que en $A_3$ hay un par de elementos de orden $3$,

El grupo de los enteros con la suma, $(\Z , +)$, es cíclico infinito, pues $\Z =\langle 1\rangle =\langle -1\rangle$.
{{% /example %}}

### El teorema de Lagrange

Para finalizar vamos a demostrar el teorema de Lagrange, que también puede ser de utilidad a la hora de calcular los elementos de un subgrupo de $S_n$, pues acota los posibles órdenes de los subgrupos de un grupo finito. Si $G$ es un grupo finito el teorema dice que el orden de cualquier subgrupo de $G$ divide al orden de $G$.

\begin{defn}{\label{relizq}} Sean $G$ un grupo y $H\subset G$ un subgrupo. Sobre $G$ definimos la relación
 $\sim_H$ de la manera siguiente: Dados $x,y\in G$,
$$
x\sim_H y \; \Leftrightarrow \; \inv{x} y\in H.
$$
\end{defn}

{{% proposition %}}
 En las condiciones de la definición anterior, las relación $\sim_H$ es de equivalencia.
{{% /proposition %}}

{{% proof %}}
 Se comprueba que la relación $\sim_H$ verifica las siguientes propiedades:
\begin{enumerate}
 \item Reflexiva: Para cada elemento $x\in G,\ x\sim_H x$ ya  que $\inv{x} x = e \in H$.
 \item Simétrica: Dados  $x,y\in G,\ x\sim_H y$ implica que $ y\sim_H x$, ya que $\inv{y} x = \inv{(\inv{x} y)} \in H$.
 \item Transitiva: Dados $x,y,z\in G$ si se tiene que $\ x\sim_H$  y que $y\sim_H z$, entonces se tiene que $x\sim_H z$. Esto se debe a que  $\inv{x} z = (\inv{x} y)(\inv{y} z)\in H$.
\end{enumerate}
{{% /proof %}}

{{% watch %}}

Lo usual es notar al conjunto cociente de $G$ por la relación de equivalencia $\sim_H$ como
$$G/H:=G/\sim_H.$$
Más adelante veremos que para algunos subgrupos $H$ (los {\em subgrupos normales}), la operación $\star$ de $G$ induce una operación $\bar{\star}$ que dota al conjunto cociente $G/H$ de estructura de grupo.
{{% /watch %}}

{{% proposition %}}
  Sean $G$ un grupo y $x\in G$. El conjunto
 $$
x H=\\{ x h\mid h\in H\\}
$$
es la clase de equivalencia de $x$ para la relación $\sim_H$.
{{% /proposition %}}

{{% proof %}}
 Sea $x\in G$ y llamemos $\bar{x}$ a su
clase de equivalencia por $\sim_H$, es decir,
$$
 \bar{x}=\\{ y\in G\mid x\sim_H y\\} =\\{ y\in G\mid \inv{x} y\in H\\} .
$$

Probaremos por doble inclusión que $\bar{x}=x H$. Si $y\in\bar{x}$,
entonces $\inv{x} y\in H$, es decir, existe $h\in H$ tal que $\inv{x} y=h$, de donde
$$
y=x h\in x H.
$$

Si $y\in x H$, existe $h\in H$ tal que $y=x h$, de donde
$$
\inv{x} y=h\in H\Rightarrow x\sim_H y.
$$
{{% /proof %}}

{{% watch %}}

Las clases de equivalencia para $\sim_H$, de la forma $xH$, se llaman {\it clases a izquierda}. Observemos que podríamos haber definido otra relación de equivalencia $\prescript{}{H}\sim$ de la siguiente forma:  
$$
  x \prescript{}{H}\sim y \Leftrightarrow yx^{-1}\in H.
$$ 
En este caso las clases de equivalencia son de la forma $Hx$, con $x\in G$, y se llaman {\it clases a derecha}.  En principio, las clases a izquierda no tienen por qué coincidir con las clases a la derecha (salvo en el caso evidente $1H=H1=H$). Cuando coinciden, se dice que el grupo $H$ es {\it normal}: esto se estudiará al final de este tema. 
{{% /watch %}}


{{% definition %}}
{\'Indice de un subgrupo} {Dado un grupo $G$ y un subgrupo $H\subset G$, el {\bf índice} de $H$ en $G$, denotado $|G:H|$, es el número de clases de equivalencia, en $G$, para la relación $\sim_H$. Es decir:
$$
    |G:H|=\#(G/H)
$$
}
{{% /definition %}}

{{% theorem %}}
 {Teorema de Lagrange} {Si $G$ es un grupo finito y
$H\subset G$ es un subgrupo, entonces $\vert H\vert$ divide a $\vert
G\vert$.}
{{% /theorem %}}

{{% proof %}}
 Consideremos la relación $\sim_H$
sobre $G$. Como $G$ es finito, habrá sólo un número finito de
clases de equivalencia distintas. Sean éstas $a_1 H,\ldots,
a_r H$. Como $G$ es unión disjunta de estas clases, será
$$
 \vert G\vert =\# (a_1 H)+\cdots +\# (a_r H).
$$
Sea $H=\\{ h_1,\ldots ,h_n\\}$. Para todo $i=1,\ldots,r$, tendremos $a_i H = \\{a_i h_1, \dots, a_i h_n \\}$. Estos elementos son todos distintos, ya que si $a_i h_j=a_i h_l$, multiplicando desde la izquierda por el simétrico de $a_i$ se obtiene $h_j=h_l$. Por tanto $\#(a_i H)= n =\vert H\vert$ para todo $i=1,\ldots,r$. Luego $\vert G\vert=r\cdot n=r\cdot\vert
H\vert$.
{{% /proof %}}

Hemos visto que si $G$ es un grupo finito y $H$ es un subgrupo, las clases de equivalencia $aH$ tienen todas el mismo tamaño. Por tanto, tenemos:

{{% theorem %}}
 {\'Indice de un subgrupo en un grupo finito} {Si $G$ es un grupo finito y
$H\subset G$ es un subgrupo, entonces
$$
 |G:H|=\frac{|G|}{|H|}
$$}
{{% /theorem %}}



{{% corollary %}}

Sea $G$ un grupo finito y sea $x\in G$, entonces el orden de $x$ divide al orden de $G$.
{{% /corollary %}}

{{% proof %}}

El orden del elemento $x$ coincide con el del subgrupo $\langle x\rangle$, que a su vez divide al de $G$.
{{% /proof %}}

Del siguiente resultado dejamos la demostración como ejercicio.

{{% corollary %}}

Si $G$ es un grupo cuyo orden es un número primo, entonces $G$ es cíclico.
{{% /corollary %}}

{{% example name="Ejemplo" %}}

Volviendo al ejemplo en el que el subgrupo de $S_4$, $\langle (123),(234)\rangle$, resulta ser $A_4$, el teorema de Lagrange nos evita algún cálculo. Conforme van apareciendo nuevos elementos del subgrupo, en cuanto aparezca el noveno elemento, como el orden debe ser un divisor de $24$, sabemos que $\langle (123),(234)\rangle$ tiene 12 o 24 elementos. Al tratarse de permutaciones pares exclusivamente, se deduce que el subgrupo es $A_4$.

Es más, sabiendo que $\langle (123),(234)\rangle\subset A_4$, como el orden de $A_4$ es 12, basta con llegar al séptimo elemento para decidir que $\langle (123),(234)\rangle = A_4$
{{% /example %}}

{{% watch %}}
Terminamos el estudio del teorema de Lagrange proponiendo el ejercicio siguiente. Sabemos que el orden de cualquier subgrupo de $G$ divide a su orden. Recíprocamente, si $m$ divide a $|G|$, ?`existe algún subgrupo de $G$ de orden $m$? Te animamos a reflexionar esta cuestión en el grupo $S_4$ o en sus subgrupos.
{{% /watch %}}

## Homomorfismos de grupos

{{% definition %}}
{Homomorfismo de grupos}{
	Dados dos grupos $(G,\star)$ y $(H,\ast)$, un {\bf homomorfismo}
	\[f\colon (G,\star)\To (H,\ast)\]
	es una aplicación $f\colon G\to H$ que satisface
que para cada  $x_1,x_2\in G$, 
\[ f(x_1\star x_2)=f(x_1)\ast f(x_2).\]}
{{% /definition %}}

{{% watch %}}

Mientras no haya equívocos seguiremos usando la yuxtaposición para expresar la operación entre dos elementos. Aunque ahora intervienen dos grupos con operaciones que pueden ser distintas, normalmente por el contexto sabremos si los elementos que intervienen están en el primer grupo o en el segundo. Así, escribiremos por ejemplo
$$f(x_1 x_2)=f(x_1) f(x_2),\qquad  \text{ para cada } x_1,x_2\in G.$$
Igualmente, mientras no haya equívocos, se notará por $e$ tanto al elemento neutro de $G$ como al de $H$. Si hiciera falta distinguir, para evitar confusiones, se usará $e_G$ y $e_H$ respectivamente.
{{% /watch %}}

{{% example name="Ejemplo" %}}
\label{ejemplosdehomomorfismos}
	Ejemplos de homomorfismos:
	\begin{enumerate}
		\item La \emph{identidad}, $\id{G}\colon (G,\star)\to (G,\star)$.
		\item La inclusión de un subgrupo $K\subset G$, $i\colon (K,\star)\to (G,\star)$.
		\item El signo de una permutación, $\sign\colon\perm{n}\to\\{\pm1\\}$.
		\item La aplicación $f\colon \mathbb Z\to\mathbb Z$ definida como $f(x)=n\cdot x$ es un homomorfismo  $f\colon (\mathbb Z,+)\to (\mathbb Z,+)$ para todo entero $n$.
		\item Si $(G,\ast)$ es un grupo abeliano, la exponenciación $f\colon G\to G$, definida como $f(g)=g^n$ es un homomorfismo $f\colon (G,\ast)\to (G,\ast)$ para todo entero $n$.
		\item Si $\gl{n}{\mathbb R}$ es el grupo de matrices invertibles $n\times n$ de números reales, el determinante $\det\colon \gl{n}{\mathbb R}\to \mathbb R\setminus\\{0\\}$ es un homomorfismo (donde la operación en ambos grupos es la multiplicación).
		\item La aplicación exponencial $f\colon\mathbb R\to (0,+\infty)$, $f(x)=e^x$, es un homomorfismo $f\colon(\mathbb R,+)\to ((0,+\infty),\cdot)$.
        \item Dado un grupo $(G,\star)$ y un elemento $x\in G$, la aplicación $c_x\colon G\rightarrow G$ dada por $c_x(y)=x^{-1}yx$ es un homomorfismo, llamado {\it conjugación por $x$}.	\end{enumerate}
	Ejemplos de aplicaciones que no son homomorfismos:
	\begin{enumerate}
		\item Si $(G,\ast)$ no es abeliano, la exponenciación $f\colon G\to G$ definida en el anterior punto 5 no es un homomorfismo, al menos para $n=2$.
		\item La aplicación $f\colon \mathbb Z\to\mathbb Z$ definida como $f(x)=x^n$ no es un homomorfismo  $f\colon (\mathbb Z,+)\to (\mathbb Z,+)$ para ningún $n\geq 2$.
	\end{enumerate}
{{% /example %}}

Los homomorfismos preservan el elemento neutro y los simétricos.

{{% proposition %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un homomorfismo, entonces $	f(e)=e$, y además para cada $ x \in G$,
		$f(\inv{x})=\inv{f(x)}$.
{{% /proposition %}}

{{% proof %}}

	Como $e=e e$,
	\[f(e)=f(e e)=f(e) f(e).\]
	Cancelando un $f(e)$ de cada lado deducimos que $e=f(e)$.
%	Multiplicando por la izquierda por $\inv{f(e)}$ obtenemos
%	\[e=f(e)\ast\inv{f(e)}=f(e)\ast f(e)\ast\inv{f(e)}=f(e).\]

	Ahora que hemos probado la primera ecuación, deducimos la segunda de $e=x \inv{x}$ del siguiente modo,
	\[e=f(e)=f(x \inv{x})=f(x) f(\inv{x}).\]
	Despejando de aquí deducimos que $\inv{f(x)}=f(\inv{x})$.
%	Multiplicando por $\inv{f(x)}$ por la izquierda obtenemos,
%	\[\inv{f(x)}=\inv{f(x)}\ast e=\inv{f(x)}\ast f(x)\ast f(\inv{x})=f(\inv{x}).\]
{{% /proof %}}

La composición de dos homomorfismos es un homomomorfismo.

{{% proposition %}}

	Dados tres grupos y dos homomorfismos como en el siguiente diagrama,
	\[(G,\star)\stackrel{f}\To (H,\ast)\stackrel{g}\To (K,\bullet),\]
	la composición
	\[g\circ f\colon (G,\star)\To (K,\bullet)\]
	también es un homomorfismo.
{{% /proposition %}}

{{% proof %}}

	Basta observar que, aplicando las definiciones, dados $x_1,x_2\in G$,
	\begin{align*}
		(g\circ f)(x_1 x_2)&=g(f(x_1 x_2))\\
		&=g(f(x_1) f(x_2))\\
		&=g(f(x_1)) g(f(x_2))\\
		&=(g\circ f)(x_1) (g\circ f)(x_2).
	\end{align*}
{{% /proof %}}

{{% definition %}}
{Monomorfismos, epimorfismos e isomorfismos}{
	Decimos que un homomorfismo $f\colon (G,\star)\to (H,\ast)$ es un {\bf monomorfismo}, {\bf epimorfismo} o {\bf isomorfismo} si la aplicación $f$ es inyectiva, sobreyectiva o biyectiva, respectivamente. Los isomorfismos se denotan del siguiente modo
	 \[f\colon (G,\star)\stackrel{\cong}\To (H,\ast).\]}
{{% /definition %}}

{{% example name="Ejemplo" %}}

	De los homomorfismos del Ejemplo \ref{ejemplosdehomomorfismos}, 2 y 4 son  monomorfismos, 3 y 6 son epimorfismos y 1, 7 y 8 son isomorfismos. En general 5 no es un monomorfismo ni un epimorfismo.
{{% /example %}}

{{% proposition %}}

	La composición de dos isomorfismos es un isomorfismo.
{{% /proposition %}}

{{% proof %}}

	Se deduce de que ya sabemos que la composición de dos homomorfismos es un homomorfismo y que la composición de dos aplicaciones biyectivas es biyectiva.
{{% /proof %}}


{{% proposition %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un isomorfismo la aplicación inversa $f^{-1}\colon H\to G$ es un isomorfismo
	\[f^{-1}\colon (H,\ast) \To  (G,\star).\]
{{% /proposition %}}

{{% proof %}}

	Queremos demostrar que para cada $ y_1,y_2\in H$ se cumple que 
	\[f^{-1}(y_1 y_2)=f^{-1}(y_1) f^{-1}(y_2).\]
	Como $f$ es inyectivo, bastará comprobar que
	\[f(f^{-1}(y_1 y_2))=f(f^{-1}(y_1) f^{-1}(y_2)).\]
	Por un lado, por ser $f^{-1}$ la inversa de $f$,
	\[f(f^{-1}(y_1 y_2))=(f\circ f^{-1})(y_1 y_2)=y_1 y_2.\]
	Por otro lado, usando además que $f$ es un homomorfismo,
	\begin{align*}
	f(f^{-1}(y_1) f^{-1}(y_2))&=f(f^{-1}(y_1)) f(f^{-1}(y_2))\\
	&=(f\circ f^{-1})(y_1)(f\circ f^{-1})(y_2)\\
	&=y_1 y_2.
	\end{align*}
{{% /proof %}}

{{% example name="Ejemplo" %}}

	Los inversos de los isomorfismos 1, 7 y 8 del Ejemplo \ref{ejemplosdehomomorfismos} son, respectivamente, $\id{G}^{-1}=\id{G}$, el isomorfismo $f^{-1}\colon((0,+\infty),\cdot)\to(\mathbb R,+)$ definido por $f^{-1}(x)=\log(x)$, y el isomorfismo $(c_x)^{-1}=c_{x^{-1}}$ definido por $c_{x^{-1}}(y)=xyx^{-1}$.
{{% /example %}}

{{% definition %}}
{Grupos isomorfos}
{	Dos grupos $(G,\star)$ y $(H,\ast)$ son {\bf isomorfos} si existe un isomorfismo \[f\colon (G,\star)\stackrel{\cong}\To (H,\ast).\]}
{{% /definition %}}

{{% corollary %}}

	La relación de ser isomorfos es de equivalencia.
{{% /corollary %}}

{{% proof %}}

	Es reflexiva porque la identidad es un homomorfismo de todo grupo en sí mismo. Es transitiva porque la composición de dos isomorfismos es un isomorfismo. Es simétrica porque el inverso de un isomorfismo es un isomorfismo.
{{% /proof %}}

{{% definition %}}
{Núcleo de un homomorfismo}
{	Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, el {\bf núcleo} de $f$ es
	\[\ker(f)=\\{x\in G\,;\,f(x)=e\\}\subset G.\]}
{{% /definition %}}

{{% example name="Ejemplo" %}}

	El núcleo de $\sign\colon\perm{n}\to\\{\pm1\\}$ es el grupo alternado.
{{% /example %}}

La demostración de la siguiente propiedad la dejamos como ejercicio:

{{% proposition %}}

 Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, su núcleo $(\ker(f),\star)$ es un subgrupo de $(G, \star)$, y su imagen $(\im(f),\ast)$ es un subgrupo de $(H,\ast)$.
{{% /proposition %}}

{{% proposition %}}

	Dado un homomorfismo $f\colon (G,\star)\to (H,\ast)$, se tiene:
\begin{enumerate}
  \item $f$ es inyectivo si y sólo si $\ker(f)=\\{e\\}$.

  \item $f$ es sobreyectivo si y sólo si $\im(f)=H$.
\end{enumerate}
{{% /proposition %}}

{{% proof %}}

    La segunda propiedad es simplemente la definición de aplicación sobreyectiva, así que basta demostrar la primera propiedad.

	Supongamos que $f$ es inyectivo. En primer lugar, como $f(e)=e$ se tiene $\\{e\\}\subset \ker(f)$. Por otra parte, dado $x\in \ker f$ se tiene \[f(x)=e=f(e).\]
	Pero entones, como $f$ es inyectivo, se sigue que $x=e$. Por tanto $\ker(f)\subset \\{e\\}$, luego $\ker(f)=\\{e\\}$.

	Recíprocamente, supongamos que $\ker(f)=\\{e\\}$. Si $x, y\in G$ son tales que $f(x)=f(y)$ entonces, por ser $f$ un homomorfismo,
	\[f(x\inv{y})=f(x) f(\inv{y})=f(x) \inv{f(y)}=f(y) \inv{f(y)}=e.\]
	Luego $x\inv{y}\in \ker(f)=\\{e\\}$, es decir $x\inv{y}=e$. Multiplicando desde la derecha por $y$, obtenemos $x=y$. Por tanto $f$ es inyectiva.
{{% /proof %}}



## Subgrupos normales. Grupo cociente

Dado un grupo $(G,\star)$ y un elemento $x\in G$, recordemos el isomorfismo $c_x\colon G\rightarrow G$ que {\it conjuga por $x$} a los elementos de $G$, es decir, $c_x(y)=x^{-1}yx$ para todo $y\in G$.

Dado un subgrupo $K\subset G$, podemos aplicarle el isomorfismo $c_x$ a todos sus elementos y obtendremos un subgrupo de $G$ (el conjugado de $K$ por $x$):
$$
    c_x(K)=x^{-1}Kx =\\{x^{-1}yx;\ y\in K\\}.
$$
El grupo $x^{-1}Kx$ podría ser el propio $K$, o podría ser distinto. Diremos que $K$ es {\it normal en $G$} cuando obtenemos siempre el propio $K$, sea cual sea el elemento $x\in G$ escogido:


{{% definition %}}
{Subgrupos normales}
{	Dado un grupo $(G,\star)$ y un subgrupo $K\subset G$, decimos que $K$ es {\bf normal} en $G$ si para todo $x\in G$ se tiene que 
	\[\inv{x} K x\subset K.\]}
{{% /definition %}}



\begin{lema}
	Si $K\subset G$ es un subgrupo normal, la inclusión de la definición anterior es de hecho una igualdad.
\end{lema}

{{% proof %}}

    Fijemos un elemento cualquiera $a\in G$. Como $K$ es normal, tomando $x=a$ tenemos $a^{-1}Ka\subset K$. Pero también, tomando $x=a^{-1}$ tenemos $aKa^{-1}\subset K$. Esto quiere decir que dado cualquier $k\in K$ se tiene $aka^{-1}=k'\in K$, es decir, $k=a^{-1}k'a$, luego $k\in a^{-1}Ka$. Por tanto $K\subset a^{-1}Ka$, luego $a^{-1}Ka=K$. Como esto lo hemos hecho para todo $a\in G$, el resultado queda demostrado.
{{% /proof %}}

{{% watch %}}

Del lema anterior se deduce que un subgrupo $K$ es normal en $G$ si y sólo si $aK=Ka$ para todo $a\in G$. En otras palabras, un subgrupo $K$ es normal en $G$ si y sólo si las clases a izquierda (definidas para $K$) coinciden con las clases a derecha.
{{% /watch %}}

Es importante observar que la igualdad $x^{-1}Kx=K$ no implica que los elementos de $K$ quedan fijos al conjugarlos por $x$. Lo que queda fijo es el conjunto $K$, pero sus elementos pueden permutarse. Por tanto, $K$ es normal si y sólo si conjugar $K$ por $x$ corresponde a una {\it permutación} de $K$, para todo $x\in G$.

Esta permutación puede ser trivial o no. En el siguiente caso, la permutación sí es trivial para todo $x$:


{{% proposition %}}

Si $(G,\star)$ es abeliano, todo subgrupo $K\subset G$ es normal.
{{% /proposition %}}

{{% proof %}}

	Si $G$ es abeliano, $x^{-1}kx=k$ para todo $k\in K$ y para todo $x\in G$. Por tanto, conjugar un subgrupo $K$ por un elemento $x$ induce la permutación trivial en $K$. Luego todo subgrupo de $G$ es normal en $G$.
{{% /proof %}}

{{% example name="Ejemplo" %}}

	Los subgrupos trivial y total $\\{e\\}$ y $G$, son normales en cualquier grupo $G$. El subgrupo $K=\\{\id{},(1\; 2)\\}\subset \perm{3}$ no es normal puesto que
	\[\inv{(1\;3)}(1\;2)(1\;3)=(1\;3)(1\;2)(1\;3)=(2\;3)\notin K.\]
{{% /example %}}

Hay una relación muy estrecha entre {\it subgrupos normales} de un grupo $G$ y {\it núcleos} de homomorfismos que parten de $G$. De hecho, todo núcleo es un subgrupo normal, y todo subgrupo normal es el núcleo de un homomorfismo. Veamos lo primero:

{{% proposition %}}

	El núcleo de un homomorfsimo $f\colon (G,\star)\to (H,\ast)$ es un subgrupo normal de $G$.
{{% /proposition %}}

{{% proof %}}

	Dado $x\in G$, veamos que $\inv{x} \ker(f) x\subset \ker(f)$. Dado un elemento del primer conjunto, será de la forma $x^{-1}yx$ con $y\in\ker(f)$. Y tendremos:
	\[f(\inv{x} y x)=f(\inv{x}) f(y) f(x)=\inv{f(x)} e f(x)=\inv{f(x)}  f(x)=e,\]
	luego $\inv{x} y x\in\ker(f)$.
{{% /proof %}}


La propiedad más importante de los subgrupos normales $K\subset G$ es que sirven para definir una operación de grupo, de la forma más natural posible, en el conjunto cociente $G/K$.


{{% theorem %}}
{Grupo cociente}
{	Si $(G,\star)$ es un grupo y $K\subset G$ es un subgrupo normal, entonces el conjunto cociente $G/K$ posee una única estructura de grupo $(G/K,\bar \star)$ tal que la proyección natural $p\colon G\to G/K$ es un homomorfismo
	\[p\colon (G,\star)\To (G/K,\bar \star).\]}
{{% /theorem %}}

{{% proof %}}

	Definimos el producto de dos clases como \[(x K)\bar\star(y K)=(x y) K.\]
	Tenemos que demostrar que $\bar{\star}$ está bien definido, es decir que esta definición de $\bar{\star}$ no depende de los representantes tomados. Para ello hemos de probar que si $x K=\tilde x K$ e $y K=\tilde y K$ entonces
	\[(x K)\bar\star(y K)=(\tilde x  K)\bar\star(\tilde y K).\]
Es decir, debemos probar que
	\[x y K=\tilde x \tilde y K,\]
  os lo que es lo mismo, que $y^{-1}x^{-1}\tilde x \tilde y\in K$.

	Por un lado, como $xK=\tilde xK$, tenemos $x^{-1}\tilde x = z_1 \in K$, y como $yK=\tilde yK$, tenemos $y^{-1}\tilde y = z_2 \in K$. Por otro lado, como $K$ es normal en $G$ y $z_1\in K$, se tiene $y^{-1}z_1 y\in K$. Por tanto,
   $$
      y^{-1}x^{-1}\tilde x \tilde y= y^{-1} x^{-1} x z_1 y z_2 = (y^{-1} z_1 y) z_2\in K,
   $$
  como queríamos demostrar.

	Con la definición anterior de $\bar{\star}$ es inmediato comprobar que $\bar{\star}$ es asociativo por serlo $\star$, que el elemento neutro del cociente es $e K$ y que el inverso de un elemento del cociente es $\inv{(x K)}=\inv{x} K$. Es más, $p$ es un homomorfismo puesto que dados $x_1,x_2\in G$,
	\[p(x_1 x_2)=(x_1 x_2) K=(x_1\ K)\bar{\star}(x_2 K)=p(x_1)\bar \star p(x_2).\]
	Además $\bar \star$ es el único producto que satisface esta propiedad puesto que la proyección natural $p$ es sobreyectiva.
{{% /proof %}}


Observemos que, en el grupo cociente $G/K$, el elemento neutro es la clase $eK$, es decir, el propio $K$. Además, el inverso del elemento $xK$ es el elemento $x^{-1}K$.


Como vimos antes, el núcleo de un homomorfismo es un subgrupo normal. Ahora ya podemos demostrar que todo subgrupo normal es núcleo de un homomorfismo.

{{% proposition %}}

	Sea $K$ un subgrupo normal en $G$. El núcleo de la proyección natural $p\colon (G,\star)\to (G/K,\bar \star)$ es precisamente $\ker(p)=K$.
{{% /proposition %}}

{{% proof %}}

	Basta observar que $p(x)=x K=e K$ si y solo si $x\in K$.
{{% /proof %}}

Hemos identificado entonces subgrupos normales con núcleos de homomorfismos. No podemos hacer lo mismo con las imágenes de homomorfismos:

{{% example name="Ejemplo" %}}

	Si $(G,\star)$ es un grupo y $F\subset G$ es un subgrupo \emph{cualquiera}, la imagen de la inclusión $i\colon (F,\star)\to (G,\star)$ es $\im(i)=F$, por tanto la imagen de un homomorfismo, en general, no es normal en el grupo de llegada.
{{% /example %}}

{{% theorem %}}
{Factorización canónica}
{	Todo homomorfismo $f\colon (G,\star)\to (H,\ast)$ factoriza como la composición $f=i\circ\bar f\circ p$ de un epimorfismo $p$,  un isomorfismo $\bar f$ y un monomorfismo $i$ del siguiente modo
	\[\xymatrix{(G,\star)\ar[r]^-{f}\ar[d]_-p& (H,\ast)\\
		(G/\ker(f),\bar \star)\ar[r]^-\cong_-{\bar f}& (\im(f),\ast)\ar[u]_-i}\]
	Aquí $p$ es la proyección natural sobre el cociente e $i$ es la inclusión del subgrupo imagen.}
{{% /theorem %}}

{{% proof %}}

	La factorización es la misma que la de una aplicación cualquiera. Ya sabemos que $p$ e $i$ son homomorfismos. Sabemos también que $p$ es sobreyectiva, $i$ es inyectiva y que $\bar f$, definida por ${\bar f}(x \ker(f))=f(x)$, es biyectiva. Basta por tanto ver que $\bar f$ es un homomorfismo. Por comodidad, llamaremos $K=\ker(f)$. Al ser $f$ un homomorfismo,
	\begin{align*}
		\bar f((x_1  K )\bar \star (x_2  K ))&= \bar f(x_1 x_2  K )\\
		&=f(x_1 x_2) \\
		&=f(x_1)\ast f(x_2) \\
		&=\bar f(x_1  K )\ast\bar f(x_2  K ).
	\end{align*}
	Luego $\bar f$ es también un homomorfismo.
{{% /proof %}}

{{% corollary %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un epimorfismo entonces $\bar f\colon (G/\ker(f),\bar \star)\to (H,\ast)$ es un isomorfismo.
{{% /corollary %}}

{{% corollary %}}

	Si $f\colon (G,\star)\to (H,\ast)$ es un monomorfismo entonces $\bar f\colon (G,\star)\to (\im(f),\ast)$ es un isomorfismo.
{{% /corollary %}}

{{% theorem %}}
{Teorema de Cayley}
{	Todo grupo $G$ es isomorfo a un subgrupo de un grupo de permutaciones. Si $G$ es finito de orden $n$, es isomorfo a un subgrupo de $S_n$.}
{{% /theorem %}}

{{% proof %}}

	Por el corolario anterior, basta construir un homomorfismo inyectivo $f\colon G\to\Sim (G)$.
	
	Dado $y\in G$ definimos $f(y)\in \Sim (G)$ como la aplicación $m_y\colon G\to G$ definida como $m_y(x)=y x$. Esta aplicación es biyectiva y su inversa es $m_y^{-1}=m_{y^{-1}}$. Así definido, $f$ es un homomorfismo pues dados $x,y,z\in G$,
	\[m_{zy}(x)=(zy) x=z (y x)=z m_y(x)=m_z(m_y(x))=(m_z\circ m_y)(x),\]
	luego $f(zy)=f(z)\circ f(y)$.
	
	Además $f$ es inyectivo pues si $f(y)=m_y=1$, la permutación identidad en $\Sim(G)$, entonces $y=ye=m_y(e)=1(e)=e$, luego $\ker(f)=\\{e\\}$.
	
	Si $G$ es finito de orden $n$, etiquetamos los elementos de $G=\\{ x_1,\ldots ,x_n\\}$ para identificar cada aplicación $m_{x_i}\in\Sim (G)$ con una permutación de los índices de los elementos de $G$.
{{% /proof %}}

Con esto vemos que los grupos simétricos no son un simple ejemplo particular de grupos, sino {\it el caso general}, puesto que todo grupo puede verse como subgrupo de un grupo de permutaciones.

-->
