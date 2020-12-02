+++
title = "Finitud"
weight = 20
+++

Los espacios vectoriales de dimensión finita están clasificados por su dimensión. ¿Qué ocurre con los módulos sobre un anillo que no sea un cuerpo? En general no es posible contestar a esta pregunta, pero sobre anillos manejables, tales como los dominios euclídeos, sí lo es bajo condiciones de finitud adecuadas. Esto es lo que vamos a ver aquí junto con algunas aplicaciones de interés.


## Generadores y relaciones

Supongamos que deseamos construir un $\mathbb Z$-módulo $M$ generado por tres elementos $\\{a\_1,a\_2,a\_3\\}\subset M$ que satisfagan las siguientes ecuaciones (relaciones):

$$\begin{array}{rcrcrcl}
3a\_1&+&2a\_2&+&a\_3&=&0,\cr
8a\_1&+&4a\_2&+&2a\_3&=&0,\cr
7a\_1&+&6a\_2&+&2a\_3&=&0,\cr
9a\_1&+&6a\_2&+&a\_3&=&0.
\end{array}$$

¿Cómo hacerlo? Las relaciones anteriores pueden ser codificadas en una matriz que tiene por columnas a los coeficientes de cada una de las ecuaciones,

$$A=\left(\begin{array}{cccc}
3&8&7&9\cr
2&4&6&6\cr
1&2&2&1
\end{array}\right).$$

Esta matriz define un homomorfismo

$$\mathbb{Z}^4\stackrel{A}\longrightarrow \mathbb{Z}^3$$

Veamos que el cociente

$$M=\frac{\mathbb{Z}^3}{\operatorname{im}A}$$

satisface las condiciones deseadas. En efecto, está generado por las clases de los elementos de la base canónica de $\mathbb{Z}^3$,

$$\begin{array}{rcl}
a\_1&=&\bar{e}\_1,\cr
a\_2&=&\bar{e}\_2,\cr
a\_3&=&\bar{e}\_3.
\end{array}$$

Además $\operatorname{im}A$ está generado por las imágenes de los elementos de la base canónica de $\mathbb{Z}^4$,

$$\begin{array}{rcrcrcr}
Ae\_1&=&3e\_1&+&2e\_2&+&e\_3,\cr
Ae\_2&=&8e\_1&+&4e\_2&+&2e\_3,\cr
Ae\_3&=&7e\_1&+&6e\_2&+&2e\_3,\cr
Ae\_4&=&9e\_1&+&6e\_2&+&e\_3,
\end{array}$$

cuyas clases en el cociente se anulan, lo cual equivale a las ecuaciones del principio. Más aún, esta construcción es universal ya que, por la [proposición](../generalities/#factorquotientmodules) de factorización de homomorfismos a través de cocientes, dado un $\mathbb Z$-módulo $N$ y tres elementos $\\{b\_1,b\_2,b\_3\\}\subset N$ que satisfacen las ecuaciones 

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

Este homomorfismo es la factorización de $\phi\_{\\{b\_1,b\_2,b\_3\\}}\colon\mathbb{Z}^3\rightarrow N$ a través de la proyección natural al cociente $M=\mathbb{Z}^3/\operatorname{im}A$. Tendríamos que comprobar que las hipótesis de la [proposición](../generalities/#factorquotientmodules) mencionada se cumplen, es decir que $\operatorname{im} A\subset \ker \phi\_{\\{b\_1,b\_2,b\_3\\}}$. Como $\operatorname{im} A$ está generado por $\\{Ae\_1,Ae\_2,Ae\_3,Ae\_4\\}$, basta ver que $Ae\_i\in \ker \phi\_{\\{b\_1,b\_2,b\_3\\}}$ para todo $i$, es decir que $\phi\_{\\{b\_1,b\_2,b\_3\\}}(Ae\_i)=0$, $i=1,2,3,4$. Esto equivale a las cuatro ecuaciones anteriores para los $b_i$.

Esta construcción se puede generalizar de manera obvia del siguiente modo. Dado un anillo cualquiera $R$, queremos construir un $R$-módulo $M$ con *generadores* $\\{a\_1,\dots,a\_m\\}\subset M$ donde se satisfagan las ecuaciones (*relaciones*)

$$r\_{1j}a\_1+\cdots+r\_{mj}a\_m=0,\quad 1\leq j\leq n,$$

donde $r\_{ij}\in R$, $1\leq i\leq m$, $1\leq j\leq n$. Estas relaciones están determinadas por la matriz $A=(r\_{ij})$, que define un homomorfismo

$$R^n\stackrel{A}\longrightarrow R^m.$$

Podemos tomar

$$M=\frac{R^m}{\operatorname{im}A}$$

ya que las clases de los elementos de la base canónica de $R^m$ generan $M$,

$$a\_i=\bar{e}\_i,\quad 1\leq i\leq m,$$

y las imágenes de los elementos de la base canónica de $R^n$ generan $\operatorname{im}A$,

$$Ae\_j=r\_{1j}e\_1+\cdots+r\_{mj}e\_m,\quad 1\leq j\leq n.$$

Estas imágenes se anulan en el cociente, lo cual equivale a las ecuaciones (relaciones) del principio. Esta construcción es universal en virtud de la [proposición](../generalities/#factorquotientmodules) de factorización de homomorfismos a través de cocientes, ya que dado un $R$-módulo $N$ y elementos $\\{b\_1,\dots,b\_m\\}\subset N$ que satisfacen 

$$r\_{1j}b\_1+\cdots+r\_{mj}b\_m=0,\quad 1\leq j\leq n,$$

existe un único homomorfismo

$$g\colon M\longrightarrow N$$

que satisface 

$$g(a\_i)=b\_i,\quad 1\leq i\leq m,$$

que es la factorización de $\phi\_{\\{b\_1,\dots,b\_m\\}}\colon R^m\rightarrow N$ a través de la proyección natural al cociente $M=R^m/\operatorname{im}A$. Las hipótesis de la [proposición](../generalities/#factorquotientmodules) mencionada se cumplen porque $\operatorname{im}A\subset \ker \phi\_{\\{b\_1,\dots,b\_m\\}}$ ya que $\operatorname{im}A$ está generado por los $Ae_i$ y $\phi\_{\\{b\_1,\dots,b\_m\\}}(Ae_i)=0$ debido a que los $b_i$ satisfacen las mismas ecuaciones (relaciones) que los $a_i$.

{{% definition %}}
Una **presentación** de un $R$-módulo $M$ consiste en dos homomorfismos

$$R^n\stackrel{A}\longrightarrow R^m\stackrel{f}\twoheadrightarrow M$$

tales que $f$ es sobreyectivo e $\operatorname{im} A=\ker f$. Esto, en virtud del primer [teorema](../generalities/#isomodules) de isomorfía, equivale a dar una matriz $A$ y un isomorfismo

$$\bar{f}\colon \frac{R^m}{\operatorname{im} A}\stackrel{\cong}\longrightarrow M.$$

Decimos que un módulo es **finitamente presentado** si admite una presentación. 
{{% /definition %}}


{{% remark %}}
En las condiciones de la definición, el $R$-módulo $M$ está generado por $\\{f(e\_1),\dots,f(e\_m)\\}\subset M$, y estos generadores satisfacen las relaciones determinadas por la matriz $A$. 
{{% /remark %}}



{{% proposition label="fgfp" %}}
Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ admite una presentación. 
{{% /proposition %}}


{{% proof %}}
Sea $S=\\{a\_1,\dots,a\_m\\}\subset M$ un conjunto de generadores. Por serlo, el homomorfismo $\phi\_S\colon R^m\rightarrow M$ es sobreyectivo, así que

$$\frac{R^m}{\ker\phi\_{S}}\cong M.$$

Según hemos visto anteriormente, el submódulo $\ker \phi\_S\subset R^m$ es finitamente generado. Escogemos un conjunto de generadores $S'=\\{b\_1,\dots,b\_n\\}\subset \ker \phi\_{S}$, que por tanto inducen otro homomorfismo sobreyectivo $\phi\_{S'}\colon R^n\rightarrow \ker \phi\_{S}$. Consideramos su composición con la inclusión,

$$A\colon R^n\stackrel{\phi\_{S'}}\twoheadrightarrow \ker \phi\_S\hookrightarrow R^m,$$

que estará definida por una matriz $A$. Al ser $\phi\_{S'}$ sobreyectiva, $\operatorname{im}A=\ker \phi\_{S}$, con lo que $A$ es una presentación de $M$.
{{% /proof %}}


Una presentación de un módulo se puede modificar y simplificar de los siguientes modos.

{{% proposition label="simplify" %}}
Si el $R$-módulo $M$ está presentado por la matriz $A$ de tamaño $m\times n$ entonces también está presentado por la matriz $A'$ en los siguientes casos: 

* Si $A'=QAP^{-1}$ siendo $P$ y $Q$ matrices invertibles.

* Si $A'$ se obtiene a partir de $A$ eliminando una columna de ceros,

$$
A=\left(
\begin{array}{cccc}
&&0&\cr
&&\vdots&\cr
&&0&
\end{array}
\right).
$$

* Si la $j$-ésima columna de $A$ es $ue_i$, donde $u\in R^\times$ es una unidad, y $A'$ se obtiene borrando la $i$-ésima fila y la $j$-ésima columna de $A$,

$$
A=\left(
\begin{array}{cccc}
&&0&\cr
&&\vdots&\cr
\cdots&\cdots&u&\cdots\cr
&&\vdots&\cr
&&0&\cr
\end{array}
\right).
$$

{{% /proposition %}}

{{% proof %}}

* Las matrices invertibles $P$ y $Q$ se corresponden con meros cambios de base en $R^m$ y $R^n$, respectivamente, con lo cual tenemos un isomorfismo

$$\begin{array}{rcl}
R^m/\operatorname{im}A&\stackrel{\cong}\longrightarrow& R^m/\operatorname{im}A'\\\ [ x ]&\mapsto& [Qx].\end{array}$$

Usando el primer [teorema](../generalities/#isomodules) de isomorfía, podemos comprobar que esta aplicación está en efecto bien definida y es un isomorfismo.

* Una columna de ceros se corresponde con la relación $0=0$, que no aporta nada, con lo cual puede eliminarse.

* En este caso la $j$-ésima columna se corresponde con la relación $ua_i=0$, que equivale a $a\_i=0$, pues $u$ es una unidad, así que podemos simplemente eliminar $a\_i$ de la lista de generadores y $a\_i=0$ de la de relaciones. Esto se corresponde con la eliminación de la $i$-ésima fila y la $j$-ésima columna de $A$.

{{% /proof %}}


Cuando una matriz es especialmente sencilla resulta fácil identificar el módulo que presenta.

{{% proposition label="easy" %}}
El $R$-módulo $R^m/\operatorname{im}D$ presentado por la matriz

$$D=\left( \begin{array}{ccc} d\_1&&\cr &\ddots&\cr &&d\_n\cr \hline &0& \end{array} \right)$$

de tamaño $m\times n$ con una caja superior diagonal de tamaño $n\times n$ y una caja inferior trivial de tamaño $(m-n)\times n$, es isomorfo a

$$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{m-n}.$$

{{% /proposition %}}


{{% proof %}}
Es obvio, ya que este módulo está generado por $\\{a\_1,\dots,a\_m\\}$, donde $a\_i=\bar e\_i$, y las relaciones correspondientes a la matriz $D$ son

$$d\_ia\_i=0,\quad 1\leq i\leq n.$$

Por tanto las únicas relaciones existentes nos dicen que hemos de considerar la $i$-ésima coordenada módulo $(d\_i)$, $1\leq i\leq n$. El isomorfismo está simplemente definido por

$$
\begin{array}{rcl}
\frac{R^m}{\operatorname{im} D}
&\stackrel{\cong}\longrightarrow&
\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{m-n},\cr
{[(r\_1,\dots,r\_m)]}&\mapsto&(\bar{r}\_1,\dots, \bar{r}\_n,r\_{n+1},\dots,r\_m).
\end{array}
$$

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


{{% remark %}}
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
A&\stackrel{F\_i\leftrightarrow F\_j}\longrightarrow &E\_{ij}A,&  A&\stackrel{C\_i\leftrightarrow C\_j}\longrightarrow& AE\_{ij},\cr
A&\stackrel{uF\_i}\longrightarrow& E\_{ii}(u)A,& A&\stackrel{uC\_i}\longrightarrow& AE\_{ii}(u).
\end{array}$$

Por tanto, si $A'$ se obtiene a partir de $A$ a través de operaciones elementales por filas y columnas, entonces existen matrices invertibles $P$ y $Q$ tales que

$$A'=QAP^{-1}.$$

En particular $A$ y $A'$ presentan el mismo módulo.

También deducimos que el determinante de una matriz no varía cuando se realiza una operación elemental de tipo 1, cambia de signo al hacer una operación elemental de tipo 2, y pasa a ser un asociado al realizar una operación elemental de tipo 3.
{{% /remark %}}



{{% theorem name="Forma normal de Smith" label="smith" %}}
Dada una matriz $A$ de tamaño $m\times n$ sobre un dominio euclídeo $R$, existen matrices invertibles $P$ y $Q$, que son de hecho productos de matrices elementales, tales que

$$QAP^{-1}=D=\left( \begin{array}{ccc|c} d\_1&&&\cr &\ddots&&0\cr &&d\_k&\cr \hline &0&&0 \end{array} \right)$$

es una matriz con una descomposición de tamaño $2\times 2$ por cajas cuya única caja no trivial es la superior izquierda, que es diagonal con entradas diagonales no nulas y satisface $d\_i|d\_{i+1}$ para todo $1\leq i {<} k$. Esta matriz $D$ se denomina **forma normal de Smith** de $A$. <!--- el número $k$ de entradas no nulas es único y los $d_i$ son únicos salvo asociados. --> 
{{% /theorem %}}


{{% proof %}}
La estrategia para probar la existencia consiste en aplicarle a $A$ una serie de operaciones elementales para llegar a una matriz de la forma 

$$\left(\begin{array}{c|c}
d_1&0\cr \hline 0&B
\end{array}\right)$$

donde $d_1$ divide a todas las entradas de $B$. Una vez hecho esto, pasamos a trabajar del mismo modo con la matriz $B$. De este modo obtenemos el resultado por inducción ya que si un elemento de $R$ divide a todas las entradas de una matriz $B$ entonces también divide a las entradas de una matriz obtenida a partir de $B$ mediante una operación elemental.

Sea $A$ una matriz no nula (si fuera nula no habría nada que hacer). Para llegar a una matriz como la anterior a partir de $A$ aplicamos el siguiente procedimiento:

1. Permutando filas y columnas, mueve la entrada no nula de menor tamaño a la esquina superior izquierda.

2. Dada una entrada no nula de la primera columna $a\_{i1}$, $i>1$, realiza la división euclídea $a\_{i1}=c\cdot a\_{11}+r$ y la operación $F\_{i}-c\cdot F\_1$. La entrada $(i,1)$ de la nueva matriz es el resto $r$. Si este resto es no nulo entonces tiene tamaño menor que $a\_{11}$, así que volvermos al paso 1. Si no, continuamos con otra entrada no nula de la primera columna. Si el resto de entradas de la primera columna son $0$, pasamos a hacer lo análogo con la primera fila, es decir, buscamos una entrada $a\_{1j}$ no nula, $j>1$, realizamos la división euclídea $a\_{1j}=c\cdot a\_{11}+r$ y la operación $C\_{j}-c\cdot C\_1$. La entrada $(1,j)$ de la nueva matriz es el resto $r$. Si este resto no es nulo entonces tiene tamaño menor que el de $a\_{11}$ y pasamos al paso 1. Si no, realizamos el mismo procedimiento con otra entrada no nula de la primera fila.

3. Cuando lleguemos aquí es porque el único elemento no nulo de la primera fila y de la primera columna es el $a\_{11}$. Si hay algún elemento no nulo $a\_{ij}$ que no es divisible por $a\_{11}$ realizamos la operación $F\_{1}+F\_{i}$. La matriz resultante tiene el mismo $a\_{11}$, pero en la entrada $(1,j)$ nos encontramos con $a\_{ij}$, que no es múltiplo de $a\_{11}$, así que volvemos al paso 1. (También podríamos hacer la operación $C\_{1}+C\_{j}$ y pasar al paso 1.) Si no lo hay, es porque nuestra matriz ya es de la forma

$$\left(\begin{array}{c|c}
d_1&0\cr \hline 0&B
\end{array}\right)$$

y $d_1$ divide a todas las entradas de $B$.

Este procedimiento termina porque cada vez que realizamos una división euclídea con resto no nulo, el mínimo de los tamaños de los elementos no nulos disminuye. Como este número es un entero no negativo, no puede disminuir indefinidamente. Esto asegura que el procedimiento acaba tras un número finito de pasos.

Este método para llegar a la forma normal de Smith se conoce como  **algoritmo de diagonalización** de matrices con entradas en $R$.

En virtud de la correspondencia entre operaciones y matrices elementales, la matriz $Q$ del enunciado se obtiene al realizar sobre la matriz identidad $I_m$ de tamaño $m\times m$ todas las operaciones elementales por filas que hemos usado para hallar $D$, en el mismo orden. Análogamente, $P^{-1}$ se obtiene al aplicarle a $I_n$ todas las operaciones elementales por columnas realizadas para calcular $D$.

<!--- La unicidad de la forma normal de Smith se observa del siguiente modo. Si $d$ divide a todas las entradas de una matriz $A$ entonces también dividirá a todas las entradas de cualquier otra matriz obtenida a partir de $A$ mediante una operación elemental. Las operaciones elementales son reversibles, por tanto el divisor máximo común de las entradas de una matriz no varía al realizar operaciones elementales. La forma normal de Smith se obtiene a partir de $A$ mediante operaciones elementales y el divisor máximo común de sus entradas es $d\_1$, por tanto $d\_1$ también es el divisor máximo común de las entradas de $A$, que es único salvo asociados.

Un **menor** de orden $r$ de una matriz $m\times n$ es el determinante de una submatriz de tamaño $r\times r$, 

$$\left|\begin{array}{ccc}
a\_{i\_1j\_1}&\cdots & a\_{i\_1j\_r}\cr
\vdots&\ddots&\vdots\cr
a\_{i\_rj\_1}&\cdots & a\_{i\_rj\_r}
\end{array}\right|,\qquad 1\leq i\_1{<}\cdots{<}i\_r\leq m,\quad 1\leq j\_1{<}\cdots{<}j	\_r\leq n.$$

Los menores de orden $1$ son simplemente las entradas de la matriz. El razonamiento anterior es igualmente cierto si reemplazamos entradas por menores, es decir, el divisor máximo común de los menores de orden $r$ no varía al hacer operaciones elementales. Para la forma normal de Smith, dicho divisor máximo común es $d\_1\cdots d\_r$ si $1\leq r\leq k$ y $0$ si $r>k$. De aquí se deduce la unicidad de $k$ y de los $d\_i$ salvo asociados. -->
{{% /proof %}}

Hemos puesto a tu disposición una [calculadora](../../interactions/#forma-normal-de-smith) de la forma normal de Smith paso a paso en el anillo $\mathbb{Z}$ para que puedas practicar y contrastar tus cálculos.

El teorema de la forma normal de Smith es cierto más generalmente para dominios de ideales principales. La demostración es análoga pero hace uso de la identidad de Bézout en lugar de la división euclídea y de un tipo más general de operación elemental. La forma normal de Smith es única salvo asociados, aunque no lo hemos probado. <!--- Si $R=\mathbb Z$ hay una única forma normal de Smith que donde todos los $d\_i$ son positivos, ya que todo entero no nulo es asociado de un único entero positivo. A esta forma normal de Smith se que llega usando también operaciones elementales de tipo $3$. Análogamente, si $R=k[ x ]$, con $k$ un cuerpo, hay una única forma normal de Smith que donde todos los polinomios $d\_i$ son mónicos. -->



{{% corollary %}}
Toda matriz invertible con entradas en un dominio euclídeo es producto de matrices elementales. 
{{% /corollary %}}


{{% proof %}}
El determinante de una matriz $A$ de tamaño $n\times n$ es asociado del determinante de cualquier otra matriz que se obtenga a partir de $A$ tras realizar una operación elemental. En particular, $|A|$ es asociado del determinante de su forma normal de Smith $D$. El determinante $|D|$ es $0$ si $k{<}n$ y $d\_1\cdots d\_n$ si $k=n$. Si $A$ es invertible entonces $|A|$ es una unidad, luego necesariamente $k=n$ y $d\_1\cdots d\_n$ también es una unidad. En particular todos los $d_i$ son unidades, es decir, la forma normal de Smith es un producto de matrices elementales tipo 3, $D=E\_{11}(d\_1)\cdots E\_{nn}(d\_n)$. Despejando $A=Q^{-1}DP$ vemos que $A$ es producto de matrices elementales.
{{% /proof %}}

{{% proposition %}}
Sea $A$ una matriz de tamaño $m\times n$ con entradas en $R$ y forma normal de Smith

$$D=\left( \begin{array}{ccc|c} d\_1&&&\cr &\ddots&&0\cr &&d\_k&\cr \hline &0&&0 \end{array} \right).$$

Si $Q$ y $P$ son matrices invertibles tales que $QAP^{-1}=D$, el núcleo del homomorfismo $A\colon R^n\rightarrow R^m$ definido por $A$ tiene por base a las últimas $n-k$ columnas de $P^{-1}$. Su imagen tiene base $\\{d_1Q^{-1}e_1,\dots, d_kQ^{-1}e_k\\}$.
{{% /proposition %}}

{{% proof %}}
La ecuación $D=QAP^{-1}$ equivale a $DP=QA$, que es lo mismo que decir que el siguiente diagrama de $R$-módulos libres conmuta,

![Cuadrado conmutativo](../../images/libres.svg)

Como $P$ y $Q$ son invertibles, los homomorfismos que definen son isomorfismos.

Al ser $D\vec{v}=(d\_1v\_1,\dots,d\_kv\_k,0,\dots,0)$, el núcleo de $D$ es el submódulo formado por los elementos de $R^n$ cuyas primeras coordenadas son nulas, es decir, los de la forma $(0,\dots, v\_{k+1},\dots,v\_n)$. Claramente $\\{e\_{k+1},\dots,e\_n\\}$ es una base de este submódulo, así que la imagen de esta base por el isomorfismo inverso de $P$ es una base del núcleo de $A$. 

Del cálculo anterior también deducimos que la imagen de $D$ es el submódulo de $R^m$ formado por los elementos tales que la $i$-ésima coordenada, $1\leq i\leq k$, es divisible por $d\_i$ y el resto son nulas. Deducimos que una base de la imagen de $D$ está formada por los vectores $\\{d\_1e\_1,\dots,d\_ke\_k\\}$, luego la imagen de esta base por el isomorfismo inverso de $Q$ es una base de la imagen de $A$. 
{{% /proof %}}


{{% corollary %}}
Dado un dominio de ideales principales $R$, todo submódulo de $R^m$ es libre de rango $\leq m$. 
{{% /corollary %}}


{{% proof %}}
Sea $M\subset R^m$ un submódulo. Al [demostrar](#fgfp) que todo $R$-módulo finitamente generado es finitamente presentado vimos que se puede suponer sin pérdida de generalidad que $M=\operatorname{im}A$ para cierto homomorfismo $A\colon R^n\rightarrow R^m$ definido por una matriz $A$ de tamaño $m\times n$. Este resultado es pues una consecuencia de la proposición anterior.
{{% /proof %}}


## Teoremas de estructura

Veamos que sobre un dominio de ideales principales todo módulo finitamente generado se descompone salvo isomorfismo como producto de módulos cíclicos.

{{% theorem name="Estructura de módulos finitamente generados sobre un DIP, 1ª forma" %}}
Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ es isomorfo a uno de la forma

$$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}$$

donde $d\_1,\dots,d\_n\in R$ no son cero ni unidades y satisfacen $d\_i|d\_{i+1}$, $1\leq i{<}n$. <!--- Además los enteros $k,r\geq 0$ son únicos y los $d_i$ son únicos salvo asociados. -->
{{% /theorem %}}


{{% proof %}}
Hemos visto en una [proposición](#fgfp) anterior que $M$ es finitamente presentado. Sea la matriz $A$ una presentación de $M\cong R^m/\operatorname{im}A$. En virtud de [otra](#simplify), su forma normal de [Smith](#smith)
$D=QAP^{-1}$
también presenta $M\cong R^m/\operatorname{im}D$. Es más, podemos eliminar las columnas de ceros. Más aún, algún $d\_i$ podría ser una unidad (los anteriores también tendrían que serlo, pues lo dividen). En este caso, podríamos eliminar la $i$-ésima fila y la $i$-ésima columna. De este modo acabamos con una matriz

$$\left( \begin{array}{ccc} d\_1&&\cr &\ddots&\cr &&d\_n\cr \hline &0& \end{array} \right)$$

donde los $d\_i$ no son nulos ni unidades, y además satisfacen $d\_i|d\_{i+1}$, $1\leq i{<}n$. El módulo presentado por esta matriz es el del enunciado, en virtud de una [proposición](#easy) anterior más.
{{% /proof %}}

La descomposición anterior de un $R$-módulo $M$ como producto de $R$-módulos cíclicos se puede agrupar en dos factores, la **parte libre** y la **parte de torsión**,

$$\underbrace{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}}\_{\text{parte de torsión}}\times \underbrace{R^{r}}\_{\text{parte libre}}.$$

{{% remark %}}
Este primer teorema de estructura demuestra que todo $R$-módulo finitamente generado sobre un DIP $R$ es isomorfo a un producto de módulos cíclicos de un tipo muy particular. Este producto es de hecho único en el siguiente sentido. Si

$$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}\cong\frac{R}{(e\_1)}\times \cdots \times\frac{R}{(e\_m)}\times R^{s},$$

donde los $d\_i$ y los $e\_j$ no son nulos ni unidades y satisfacen $d\_i\mid d\_{i+1}$ y $e\_j\mid e\_{j+1}$, entonces $r=s$, $n=m$ y cada $d\_i$ es asociado de $e\_i$. 
{{% /remark %}}

{{% watch %}}
A pesar de la unicidad de la forma del primer teorema de estructura, el isomorfismo no es único. Por ejemplo, de $\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}$ en sí mismo tenemos dos isomorfismos, la identidad y el intercambio de coordenadas $(a,b)\mapsto (b,a)$.
{{% /watch %}}

{{% remark %}}
Todo módulo cíclico $R/(d)$ sobre un DIP $R$ está en la forma del primer teorema de estructura, por tanto la unicidad antes mencionada demuestra que un $R$-módulo es cíclico si y solo si la descomposición dada por el teorema de estructura posee un único factor.
{{% /remark %}}

Dado un módulo $M$ finitamente generado sobre un DIP, vamos a ver que $T(M)$ es isomorfo a la parte de torsión de la descomposición del teorema de estructura y que $M/T(M)$ es isomorfo a la parte libre.

{{% proposition label="partsoffg" %}}
Si $M$ es un $R$-módulo sobre un dominio $R$ tal que

$$M\cong \frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}$$

con $d_i\neq 0$ para todo $i$, entonces 

$$
\begin{array}{rcl}
T(M)&\cong&\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)},\cr
M/T(M)&\cong& R^r.
\end{array}
$$

En particular, el $R$-módulo $M/T(M)$ es libre de rango $r$.
{{% /proposition %}}


{{% proof %}}
Hemos visto antes que la torsión se preserva por [isomorfismos](../generalities/#torsioniso) y además preserva [productos](../generalities/#torsionproduct), así que, por un lado,

$$
\begin{array}{rcl}
T(M)&\cong&T\left(\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}\right)\cr
&=&\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times \\{0\\}\cr
&\cong&\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}.
\end{array}
$$

Por otro lado,

$$
\begin{array}{rcl}
\frac{M}{T(M)}&\cong&
\frac{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}}{T\left(\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}\right)}\cr
&=& \frac{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r}}{\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times\\{0\\}}\cr
&\cong&R^r.
\end{array}
$$

{{% /proof %}}

Veamos que el rango de la parte libre de la descomposición del teorema de estructura solo depende del módulo $M$.

{{% corollary label="equalrank" %}}
Dado un dominio $R$ y dos $R$-módulos isomorfos $M\cong N$ tales que 

$$
\begin{array}{rcl}
M&\cong&\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}\times R^{r},
\cr
N&\cong &\frac{R}{(e\_1)}\times \cdots \times\frac{R}{(e\_m)}\times R^{s},
\end{array}
$$

y los $d_i$ y los $e_j$ son no nulos para todos los $i$ y $j$. Entonces $r=s$.
{{% /corollary %}}

{{% proof %}}
Como acabamos de ver, $M/T(M)$  es libre de rango $r$ y $N/T(N)$ es libre de rango $s$. También hemos [visto](../generalities/#torsionquotient) que $M/T(M)\cong N/T(N)$. Deducimos que $r=s$, ya que el rango de un módulo libre es invariante por isomorfismos, pues los isomorfismos preservan bases.
{{% /proof %}}


{{% theorem name="Teorema chino del resto" %}}
Si $R$ es un DIP y $\operatorname{mcd}(a,b)=1$ entonces tenemos un isomorfismo

$$\begin{array}{rcl}g\colon \frac{R}{(ab)}&\stackrel{\cong}\longrightarrow&\frac{R}{(a)}\times \frac{R}{(b)},\cr\bar r&\mapsto &(\bar r,\bar r).\end{array}$$

{{% /theorem %}}


{{% proof %}}
Consideramos el homomorfismo de $R$-módulos

$$f=\phi\_{\\{(\bar 1,\bar 1)\\}}\colon R\longrightarrow\frac{R}{(a)}\times \frac{R}{(b)}$$

definido por $f(1)=(\bar 1,\bar 1)$. 
Para un $r\in R$ cualquiera, como $f$ preserva el producto por escalares

$$f( r )=rf(1)=r(\bar 1,\bar 1)=(\bar r,\bar r).$$

Por el primer [teorema](../generalities/#isomodules) de isomorfía,

$$
\frac{R}{\ker f}\cong\\operatorname{im} f
$$

y este isomorfismo está definido como $\bar r\mapsto f( r )=(\bar r,\bar r)$. Por tanto bastará probar que $\ker f=(ab)$ y que $f$ es sobreyectivo.


Veamos primero que $\ker f=(ab)$.  En efecto $ab\in\ker f$ ya que $ab\equiv 0$ módulo $(a)$ y módulo $(b)$. Por lo tanto, $(ab)\subset \ker f$. Por otro lado, si $f( r )=(\bar r,\bar r)=(\bar 0,\bar 0)$, es decir si $r\equiv 0$  módulo $(a)$ y módulo $(b)$, entonces $a|r$ y $b|r$ luego $ab=\operatorname{mcm}(a,b)|r$, esto es $r\in (ab)$. 

Veamos ahora que $f$ es sobreyectivo, es decir, que dado cualquier $(\bar c,\bar d)\in \frac{R}{(a)}\times \frac{R}{(b)}$ existe $x\in R$ tal que $f(x)=(\bar{c},\bar{d})$. Esto equivale a resolver el sistema de ecuaciones

$$\left\\{\begin{array}{rcl}x&\equiv& c\mod (a),\cr x&\equiv& d\mod (b),\end{array}\right.$$

para $c,d\in R$ cualesquiera. Tomamos una identidad de Bézout $sa+tb=1$ y observamos que $x=sad+tbc$ resuelve la ecuación.
{{% /proof %}}


{{% theorem name="2ª forma del teorema de estructura" %}}
Dado un dominio de ideales principales $R$, todo $R$-módulo finitamente generado $M$ es isomorfo a uno de la forma

$$\frac{R}{(p\_1^{m\_1})}\times \cdots \times\frac{R}{(p\_n^{m\_n})}\times R^{r}$$

donde $p\_1,\dots,p\_n\in R$ son primos y $m\_i\geq 1$.
{{% /theorem %}}


{{% proof %}}
En virtud de la primera forma del teorema de estructura, basta ver que si $d\in R$ no es nulo ni una unidad, entonces $R/(d)$ es isomorfo a un producto de módulos cíclicos de la forma $R(p^m)$ con $p$ primo.

Todo DIP es un DFU, así que $d$ se puede descomponer, salvo asociados, como producto de potencias de primos no asociados, $p\_{1}^{m\_1}\cdots p\_{n}^{m\_n}$. Entonces, aplicando reiteradamente el teorema chino del resto, obtenemos que

$$\frac{R}{(d)}=\frac{R}{(p\_{1}^{m\_1}\cdots p\_{n}^{m\_n})}\cong \frac{R}{(p\_{1}^{m\_1})}\times\cdots\times \frac{R}{(p\_{n}^{m\_n})}.$$

El isomorfismo está definido simplemente como $\bar r\mapsto (\bar r,\dots,\bar r)$.  
{{% /proof %}}


Las dos formas del teorema de estructura de módulos finitamente generados sobre un DIP son de hecho equivalentes, se puede pasar de una a otra mediante el isomorfismo dado por el teorema chino del resto. Veamos ahora que ambas descomposiciones son únicas, en el segundo caso salvo orden de los factores.

{{% theorem %}}
La descomposición de un $R$-módulo finitamente generado $M$ dada en la 2ª forma del teorema de escructura es única, salvo orden de los factores.
{{% /theorem %}}

{{% proof %}}
Ya sabemos que el rango de la parte libre está unívocamente determinado, así que podemos restringirnos a $T(M)$ y, por tanto, suponer que el módulo es de torsión.

Dado un elemento $r\in R$, denotemos por $M[r]$ el núcleo de la multiplicación por $r$ en $M$, es decir, el submódulo $\\{a\in M | r\cdot a=0\\}\subseteq M$. Dado un elemento irreducible $p\in R$ y $m\geq 1$, es fácil ver que
$$p\cdot M[p^{m}]\subseteq M[p^{m-1}]\subseteq M[p^{m}].$$

En particular, el $R$-módulo cociente $M[p^{m}]/M[p^{m-1}]$ se anula al multiplicar por $p$, y por tanto podemos verlo como un módulo (es decir, un espacio vectorial) sobre el cuerpo $k=R/(p)$. Denotemos por $d(p,m)$ la dimensión de este espacio.

Tomemos ahora una descomposición de $M$ como producto de $R$-módulos cíclicos del segundo tipo,
$$M\cong M_1\times\cdots\times M_n,$$
con $M_i=\frac{R}{(p\_i^{m\_i})}$. Tenemos entonces que
$$
M[p^{m}]/M[p^{m-1}]\cong(M_1[p^{m}]/M_1[p^{m-1}])\times\cdots\times(M_n[p^{m}]/M_n[p^{m-1}])
$$
y, por tanto, $d(p,m)=\sum\_{i=1}^n \dim(M_i[p^{m}]/M_i[p^{m-1}])$. Veamos cuáles son estas dimensiones.

Consideramos primero el caso en el que $p_i\neq p$. Entonces, la multiplicación por $p^m$ en $M_i=\frac{R}{(p\_i^{m\_i})}$ es inyectiva: si $p^m\cdot\bar r=\bar 0$ para algún $r\in R$, entonces $p\_i^{m\_i}|p^mr$, y por tanto $p\_i^{m\_i}|r$ (ya que $p$ y $p_i$ son primos entre sí). Así que $M_i[p^m]=\\{0\\}$, y en este caso la dimensión es $0$.

Supongamos ahora que $p_i=p$ y $m_i<m$. En este caso, se tiene que $M_i[p^{m-1}]=M_i[p^m]=M_i$ (todo elemento de $M_i=\frac{R}{(p^{m\_i})}$ se anula al multiplicar por $p^{m-1}$), así que $M_n[p^{m}]/M_n[p^{m-1}]$ es trivial y de nuevo su dimensión es $0$.

Finalmente, consideramos el caso en el que $p_i=p$ y $m\_i\geq m$. Para todo $r\in R$, $p^m\cdot\overline{rp^{m\_i-m}}=\overline{rp^{m\_i}}=\bar 0$ en $M_i$, y por tanto $\overline{rp^{m\_i-m}}\in M_i[p^m]$. El homomorfismo $\phi:R\to M_i[p^m]$ dado por $\phi(r)=\overline{rp^{m\_i-m}}$ es sobreyectivo: si $\bar s\in M_i[p^m]$, entonces $p^m\cdot\bar s=\bar 0$ en $M_i$, es decir, $p^{m\_i}|p^ms$, y por tanto $p^{m\_i-m}|s$. Podemos entonces escribir $s=tp^{m\_i-m}$ con $t\in R$, de donde $\bar s=\phi(t)$. Componiendo con la proyección sobre el cociente, obtenemos un homomorfismo sobreyectivo $\psi:R\to M_i[p^m]/M_i[p^{m-1}]$.

Veamos cuál es su núcleo: $r\in\ker\psi$ si y solo si $\overline{rp^{m\_i-m}}\in M_i[p^{m-1}]$, es decir, si y solo si $p^{m-1}\cdot\overline{rp^{m\_i-m}}=\overline{rp^{m\_i-1}}=\bar 0$, si y solo si $p^{m\_i}|rp^{m\_i-1}$, si y solo si $p|r$. Por tanto, $\ker\psi=(p)$, y el teorema de isomorfía nos dice que $M_i[p^m]/M_i[p^{m-1}]\cong R/(p)=k$ como $R$-módulos (y como $k$-espacios vectoriales, ya que la operación es la misma). Así que, en este caso, la dimensión es $1$.

Concluimos entonces que $d(p,m)$ es igual al número de $i=1,\ldots,n$ tales que $p_i=p$ y $m\_i\geq m$. Equivalentemente, el número de factores iguales a $R/(p^{m})$ en la descomposición de $M$ es $d(p,m)-d(p,m+1)$ y, en particular, está unívocamente determinado.
{{% /proof %}}

{{% corollary %}}
La descomposición de un $R$-módulo finitamente generado $M$ dada en la 1ª forma del teorema de escructura es única.
{{% /corollary %}}

{{% proof %}}
De nuevo, podemos suponer que $M$ es de torsión. Supongamos que existen dos descomposiciones distintas
$$\frac{R}{(d\_1)}\times \cdots \times\frac{R}{(d\_n)}$$
y
$$\frac{R}{(e\_1)}\times \cdots \times\frac{R}{(e\_m)}$$
cumpliendo las condiciones del teorema de estructura. Descomponiendo los $d_i$ y los $e_j$ como producto de potencias de irreducibles, obtenemos dos descomposiciones en la 2ª forma, que deben ser la misma (salvo orden de los factores) por el teorema anterior.

Sea $k\geq 0$ tal que $(d\_{n-k})\neq (e\_{m-k})$. Existe al menos un elemento irreducible $p\in R$ que divide a $d\_{n-k}$ y $e\_{m-k}$ con distinto exponente (posiblemente cero). Supongamos que $p$ divide $d\_{n-k}$ con exponente $a$, y a $e\_{m-k}$ con exponente $b<a$. Como $e_j|e_{j+1}$, $p$ divide a $e_j$ con exponente $<a$ para todo $j=1,\ldots,m-k$. Es decir, el número de factores de la forma $R/(p^{m})$ con $m\geq a$ en la segunda descomposición es, como máximo, $k$. Pero, por otra parte, $d\_i$ es múltiplo de $p^a$ para todo $i=n-k,\ldots,n$, por lo que el número de factores de la forma $R/(p^{m})$ con $m\geq a$ en la primera descomposición es, como mínimo, $k+1$. Esto contradice el hecho de que las dos descomposiciones deben ser iguales salvo orden de los factores.
{{% /proof %}}

{{% definition %}}
Los elementos $d_1,\ldots,d_n$ que aparecen en la primera forma del teorema de estructura para un $R$-módulo finitamente generado $M$, que son únicos salvo producto por unidades, se llaman los **factores invariantes** de $M$. Los elementos $p\_1^{m\_1},\ldots,p\_n^{m_n}$ que aparecen en la segunda forma del teorema de estructura, que son únicos salvo orden y producto por unidades, se llaman los **divisores elementales** de $M$.
{{% /definition %}}

{{% example name="Las dos formas del teorema de estructura" %}}
El $\mathbb{Z}$-módulo

$$\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2^2)}\times \frac{\mathbb{Z}}{(3)}\times \frac{\mathbb{Z}}{(5)}\times\frac{\mathbb{Z}}{(5^2)}$$

está descompuesto según la segunda forma del teorema de estructura. Para descomponerlo según la primera, comenzamos agrupando los factores que en su denominador tiene las potencias de mayor grado de todos los primos que aparecen, usando el teorema chino del resto, 

$$
\frac{\mathbb{Z}}{(2^2)}\times \frac{\mathbb{Z}}{(3)}\times\frac{\mathbb{Z}}{(5^2)}\cong 
\frac{\mathbb{Z}}{(2^2\cdot 3\cdot 5^2)}=\frac{\mathbb{Z}}{(300)}.
$$

Seguidamente, agrupamos las potencias del segundo (si lo hubiere) mayor grado al que aparecen elevados los primos,

$$\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(5)}\cong \frac{\mathbb{Z}}{(2\cdot 5)}=\frac{\mathbb{Z}}{(10)}.$$

Observamos que aquí ya no aparece ninguna potencia de 3, ya que la única que había ha sido incluida en el grupo anterior. 
Así seguiríamos hasta agotar todos los factores. En este ejemplo solo quedaría uno más, 

$$\frac{\mathbb{Z}}{(2)}.$$

El resultado es 

$$\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(10)}\times \frac{\mathbb{Z}}{(300)}.$$

Un isomorfismo concreto entre este grupo abeliano y el del comienzo viene dado como composición de dos, primero

$$
\begin{array}{rcl}
\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(10)}\times \frac{\mathbb{Z}}{(300)}&\stackrel{\cong}\longrightarrow&
\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(5)}\times \frac{\mathbb{Z}}{(2^2)}\times \frac{\mathbb{Z}}{(3)}\times \frac{\mathbb{Z}}{(5^2)},\cr
(\bar a,\bar b, \bar c)&\mapsto&
(\bar a,\bar b,\bar b, \bar c, \bar c, \bar c),
\end{array}
$$

que es un isomorfismo por el teorema chino del resto, y luego

$$
\begin{array}{rcl}
\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(5)}\times \frac{\mathbb{Z}}{(2^2)}\times \frac{\mathbb{Z}}{(3)}\times \frac{\mathbb{Z}}{(5^2)}
&\\!\\!\\!\\!\stackrel{\cong}\rightarrow\\!\\!\\!\\!&
\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2^2)}\times \frac{\mathbb{Z}}{(3)}\times \frac{\mathbb{Z}}{(5)}\times\frac{\mathbb{Z}}{(5^2)},\cr
(\bar{a}\_1,\bar{a}\_2,\bar{a}\_3,\bar{a}\_4,\bar{a}\_5,\bar{a}\_6)&\\!\\!\\!\\!\mapsto\\!\\!\\!\\!&
(\bar{a}\_1,\bar{a}\_2,\bar{a}\_4,\bar{a}\_5,\bar{a}\_3,\bar{a}\_6),
\end{array}
$$

que es un isomorfismo por la conmutatividad del producto salvo isomorfismo.
{{% /example %}}



{{% example name="Grupos abelianos con el mismo número de elementos" %}}
Los grupos abelianos

$$\frac{\mathbb{Z}}{(4)}\times \frac{\mathbb{Z}}{(4)},\qquad\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(4)},$$

tienen $16$ elementos, pues $4\cdot 4=16=2\cdot 2\cdot 4$, luego existe una biyección entre ambos. Veamos que, a pesar de ello, no son isomorfos. Para verlo jugaremos con la noción de **orden** de un elemento de torsión $a\in A$ de un grupo abeliano $A$, que es el menor entero positivo $n\in\mathbb Z$ tal que $na=0$. El orden de $a$ divide a $n$ si y solo si $na=0$. En particular, para cada entero $n$, el subconjunto $T\_n(A)\subset A$ formado por los elementos cuyo orden divide a $n$ es un subgrupo, que se puede describir como 

$$T_n(A)=\\{a\in A\mid n\cdot a=0\\}.$$

Denotaremos $t\_n(A)$ al orden de $T_n(A)$. Además $T\_n(A\times B)=T\_n(A)\times T\_n(B)$, luego $t\_n(A\times B)=t\_n(A)t\_n(B)$. Es más, todo isomorfismo $A\cong B$ se restringe a $T\_n(A)\cong T\_n(B)$, por tanto en este caso $t\_n(A)=t\_n(B)$. Dado $m\neq 0$, el orden de $\bar a\in\mathbb Z/(m)$ divide a $n$ si y solo si $m\mid na$. Si denotamos $d=\operatorname{mcd}(n,m)$, esto equivale a decir que $\frac{m}{d}\mid a$, por tanto

$$T\_n\left(\frac{\mathbb{Z}}{(m)}\right)=\left(\overline{\frac{m}{d}}\right)=\left\\{0\cdot\overline{\frac{m}{d}},\dots,(d-1)\cdot \overline{\frac{m}{d}}\right\\},$$

pues $\overline{\frac{m}{d}}$ tiene orden $d$. Luego

$$t\_n\left(\frac{\mathbb{Z}}{(m)}\right)=\operatorname{mcd}(n,m).$$

Aplicando esto a los dos grupos del principio, vemos que el primero cumple

$$t\_2\left(\frac{\mathbb{Z}}{(4)}\times \frac{\mathbb{Z}}{(4)}\right)=2\cdot 2=4,$$

mientras que el segundo satisface

$$t\_2\left(\frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(2)}\times \frac{\mathbb{Z}}{(4)}\right)=2\cdot 2\cdot 2=8,$$

con lo cual no pueden ser isomorfos.
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

Si llamamos

$$\begin{array}{ccc}A=
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

$$x\_i=\frac{b\_i}{d\_i},\quad 1\leq i\leq k;\qquad x\_{k+1},\dots,x\_n\in\mathbb Z;$$

siendo estos últimos valores paramétricos cualesquiera. Observa que la solución es única si además $k=n$.

En general, $A$ tiene una forma normal de Smith $D$ que satisface $QAP^{-1}=D$, es decir $A=Q^{-1}DP$. Tenemos que

$$A\vec{x}=\vec{b}\Leftrightarrow DP\vec{x}=Q\vec{b}.$$

Llamando

$$\vec{y}=P\vec{x},$$

lo cual es un simple cambio de variables, podemos resolver esta ecuación en $\vec{y}$ como arriba, 

$$D\vec{y}=Q\vec{b}.$$

Las soluciones de la ecuación original se obtienen deshaciendo el cambio de variables

$$\vec{x}=P^{-1}\vec{y}.$$
$$\vec{x}=P^{-1}\vec{y}.$$

## Operadores lineales

Dado un cuerpo $k$ y un $k$-espacio vectorial $V$, un **operador lineal** en $V$ es un endomorfismo $f\colon V\rightarrow V$.


{{% proposition %}}
Un $k[ x ]$-módulo es lo mismo que un $k$-espacio vectorial equipado con un operador lineal.
{{% /proposition %}}


{{% proof %}}
Un $k[ x ]$-módulo $M$ es también un $k$-módulo, es decir, un $k$-espacio vectorial, restringiendo el producto por escalares a $k\subset k[ x ]$. La multiplicación por $x$ es un homomorfismo de $k[ x ]$-módulos 

$$\begin{array}{rcl}M&\stackrel{x\cdot}\longrightarrow& M,\cr a&\mapsto &x\cdot a,\end{array}$$

en particular también es un homomorfismo de $k$-módulos, es decir, es un operador lineal en el $k$-espacio vectorial $M$.

Recíprocamente, dado un $k$-espacio vectorial $V$ y un operador lineal $f\colon V\rightarrow V$, podemos definir una estructura de $k[ x ]$-módulo en $V$ del siguiente modo. Dado $v\in V$ y $p(x)=a\_nx^n+\cdots+a\_1x+a\_0\in k[ x ]$, definimos el producto por escalares como

$$p(x)\cdot v=a\_nf^n(v)+\cdots+a\_1f(v)+a\_0v.$$

Dejamos como ejercicio comprobar que este producto por escalares satisface las propiedades requeridas.
{{% /proof %}}


{{% remark %}}
Si $V=k^n$ y consideramos el operador lineal $A\colon k^n\rightarrow k^n$ definido por una matriz $A$ de tamaño $n\times n$ con entradas en $k$, entonces la estructura de $k[ x ]$-módulo en $k^n$ viene dada por $p(x)\cdot v=p(A)v$ para todo $p(x)\in k[ x ]$ y $v\in k^n$.
{{% /remark %}}

{{% proposition %}}
Dado un operador lineal $A\colon k^n\rightarrow k^n$, el $k[ x ]$-módulo asociado $k^n$ está presentado por la matriz $A-xI$.
{{% /proposition %}}

{{% proof %}}
Hemos de construir un isomorfismo entre el $k[ x ]$-módulo $k^n$ y el $k[ x ]$-módulo cociente

$$\frac{k[ x ]^n}{\operatorname{im} (A-xI)}.$$

Para ello, comenzamos considerando el homomorfismo de $k[ x ]$-módulos

$$\phi=\phi_{\\{e_1,\dots,e_n\\}}\colon k[ x ]^n\longrightarrow k^n,$$

que está definido por $\phi(e_i)=e_i$. Aquí estamos usando la notación $e_i$ tanto para los elementos de la base canónica del $k[ x ]$-módulo $k[ x ]^n$ como para los de la base canónica del $k$-espacio vectorial $k^n$. El homomorfismo $\phi$ es sobreyectivo porque su imagen contiene un conjunto de generadores de $k^n$.

Veamos que $\operatorname{im} (A-xI)\subset\ker \phi$. Como $\operatorname{im} (A-xI)$ está generado por las columnas de la matriz $B=A-xI$, basta ver que estas columnas están en el $\ker \phi$. La $j$-ésima columna es

$$b\_{*j}=(a\_{ij})\_{i=1}^n-xe\_j=\sum\_{i=1}^na\_{ij}e\_i-xe\_j.$$

Por tanto, 

$$\phi(b\_{*j})=\sum\_{i=1}^na\_{ij}e\_i-Ae\_j=0,$$

puesto que $\sum\_{i=1}^na\_{ij}e\_i=Ae\_j$ es la $j$-ésima columna de $A$. Esto demuestra que $\phi$ factoriza de manera única a través de la proyección natural, $\phi=g\circ p$,

$$k[ x ]^n\stackrel{p}\twoheadrightarrow \frac{k[ x ]^n}{\operatorname{im} (A-xI)}\stackrel{g}\longrightarrow k^n.$$

Como $\phi$ y $p$ son sobreyectivos, $g$ también lo será. 

Queremos probar que $g$ es un isomorfismo. Este homomorfismo sobreyectivo de $k[ x ]$-módulos también lo es de $k$-módulos, es decir, de $k$-espacios vectoriales. Si demostramos que la dimensión del cociente como $k$-espacio vectorial es $\leq n$, entonces $g$ será necesariamente biyectivo. Sabemos que  $S=\\{\bar{e}\_1,\dots, \bar{e}\_n\\}$ es un conjunto de generadores del cociente como $k[ x ]$-módulo. Es decir, todo elemento del cociente es una combinación lineal de $S$ con coeficientes polinómicos. Veamos que $S$ es también una base del cociente como $k$-espacio vectorial, es decir, que todo elemento es combinación lineal de $S$ con coeficientes constantes. Para ello basta ver que $x \bar{e}\_j$ es siempre una combinación lineal de $S$ con coeficientes constantes, ya que de aquí se deduciría por inducción que $x^m\bar{e}\_i$ también es una combinación lineal de $S$ con coeficientes constantes para todo $m\geq 1$. La $j$-ésima columna de $A-xI$ es $\sum\_{i=1}^na\_{ij}e\_i-xe\_j$, así que en efecto

$$x\bar{e}\_j=\sum\_{i=1}^na\_{ij}\bar{e}\_i.$$

{{% /proof %}}



{{% proposition %}}
Un $k[ x ]$-módulo $M$ finitamente generado es de torsión, $M=T(M)$, si y solo si tiene dimensión finita como $k$-espacio vectorial.
{{% /proposition %}}


{{% proof %}}
$\Rightarrow$ Si $M$ es de torsión entonces por el teorema de estructura de $k[ x ]$-módulos finitamente generados, $M$ es isomorfo a un producto de una cantidad finita de $k[ x ]$-módulos cíclicos $k[ x ]/(p(x))$ con $p(x)\in k[ x ]$ un polinomio no trivial. Como $k[ x ]/(p(x))$ tiene dimensión finita como $k$-espacio vectorial (su dimensión es el grado de $p(x)$), deducimos que $M$ también tiene dimensión finita como $k$ espacio vectorial (la suma de las dimensiones de los factores cíclicos del producto). 

$\Leftarrow$ Recíprocamente, si $M$ tiene dimensión finita como $k$ espacio vectorial, entonces no puede tener parte libre en su descomposición como producto de $k[ x ]$-módulos cíclicos ya que $k[ x ]$ no tiene dimensión finita como $k$-espacio vectorial.
{{% /proof %}}


Una **caja de Jordan** es una matriz cuadrada con una constante $\alpha \in k$, denominada **autovalor**, en todas las entradas diagonal principal, $1$ en todas las entradas de la diagonal que está justo por encima de la principal y $0$ en el resto, 

![Caja de Jordan](../../images/jordanblock.svg)

{{% theorem name="Forma normal de Jordan" %}}
Sea $k$ un cuerpo algebraicamente cerrado. Dado un $k$-espacio vectorial de dimensión finita $V$ equipado con un operador lineal $f\colon V\rightarrow V$ existe una base de $V$ respecto de la cual la matriz de $f$ es una matriz diagonal por cajas de Jordan. Esta matriz diagonal por cajas es única salvo permutación de las cajas y se denomina **forma normal de Jordan**.
{{% /theorem %}}


{{% proof %}}
Como $k$ es algebraicamente cerrado, los primos en $k[ x ]$ son los polinomios mónicos de grado $1$ y sus asociados. Sabemos que una base de

$$\frac{k[ x ]}{(x^m)}$$

como $k$-espacio vectorial es  $\\{\bar x^{m-1},\dots,\bar x,1\\}$. Haciendo un cambio de variables es fácil ver que una base de

$$\frac{k[ x ]}{((x-\alpha)^m)}$$

como $k$-espacio vectorial es  $\\{(\bar x-\alpha)^{m-1},\dots,\bar x-\alpha,1\\}$. Como 

$$\begin{array}{rcl}
x\cdot(\bar x-\alpha)^j&=&(x-\alpha+\alpha)\cdot(\bar x-\alpha)^j\cr
&=&(x-\alpha)\cdot(\bar x-\alpha)^j+\alpha\cdot(\bar x-\alpha)^j\cr
&=&(\bar x-\alpha)^{j+1}+\alpha\cdot(\bar x-\alpha)^j,
\end{array}$$

la matriz de la multiplicación por $x$,

$$\frac{k[ x ]}{((x-\alpha)^m)}\stackrel{x\cdot}\longrightarrow \frac{k[ x ]}{((x-\alpha)^m)}$$

respecto de la base anterior es la caja de Jordan de tamaño $m\times m$ y autovalor $\alpha$.

Usando la primera proposición, consideramos $V$ como un $k[ x ]$-módulo de torsión con $x\cdot a=f(a)$. En virtud del segundo teorema de estructura, $V$ se descompone como un producto finito de $k[ x ]$-módulos cíclicos, cocientes por potencias de primos,

$$V\cong\frac{k[ x ]}{((x-\alpha\_1)^{m\_1})}\times\cdots\times \frac{k[ x ]}{((x-\alpha\_n)^{m\_n})}.$$

Como $k$-espacio vectorial, el $k[ x ]$-módulo de la derecha tiene base 

$$\bigcup\_{i=1}^n\\{(0,\dots,(\bar x-\alpha_i)^j,\dots,0)\\}\_{j=m\_i-1}^0,$$

donde la coordenada no trivial $(\bar x-\alpha_i)^j$ es la $i$-ésima.
Respecto de esta base, la matriz del homomorfismo de multiplicación por $x$ es la matriz
diagonal por cajas de Jordan de tamaños $m\_i\times m\_i$ y autovalores $\alpha\_i$, $1\leq i\leq n$.

![Matriz de Jordan](../../images/jordanmatrix.svg)

Trasladando esta base a $V$ por el isomorfismo dado por el segundo teorema de estructura, obtenemos una base de $V$ respecto de la cual la matriz de $f$ es esta misma.

La unicidad de la forma normal de Jordan se corresponde con la de la segunda forma del teorema de estructura. Observa que, sin embargo, la base respecto de la cual la matriz de $f$ está en forma normal de Jordan no es única en general.
{{% /proof %}}


