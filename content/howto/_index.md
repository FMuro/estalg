+++
title = "Cómo editar"
hidden = true
+++

Estos apuntes están alojados en [GitLab](https://gitlab.com/), una plataforma de colaboración en línea abierta e intuitiva.

En el menú de la izquierda de cada página aparece un enlace <i class="fa fa-edit"></i> **Edita esta página** para editar su código en GitLab (tras darte de alta e ingresar en la plataforma). Aquí te explico lo que hay que saber para harcelo.

Tras incorporar los cambios a GitLab, y siempre que no haya errores, la versión actualizada de la página estará disponible [en esta dirección](https://edarfoc.gitlab.io/estalg) al cabo de unos minutos.

## Markdown básico

El título de esta sección se ha escrito con el código `## Markdown básico`. Las **negrillas** se escriben `**negrillas**` y las *cursivas* `*cursivas*`.

* Hacer listas...
	1. ... es muy...
	2. ... fácil.
* El código de esta lista es el siguiente:

```
* Hacer listas...
	1. ... es muy...
	2. ... fácil.
* El código de esta lista es el siguiente:
```

## Notación matemática

Hugo entiende $\LaTeX$. Prueba de ello es que acabo de escribir <code>$\LaTeX$</code>. Lo entiende casi todo, pero son necesarias algunas modificaciones: 

* **Subíndices**: El símbolo `_` se sustituye por `\_`, por tanto $\sum\_{n\geq 0}a\_n$ se escribe `$\sum\_{n\geq 0}a\_n$`.

* **Corchetes**: El conjunto $\\{0,1,2\\}$ se escribe `$\\{0,1,2\\}$`, con doble barra inclinada `\\`.

* **Entornos tabulares**: en vez de usar `\\` para saltos de línea hay que usar `\cr`, así $\left(\begin{smallmatrix} 1 & 0 \cr 0 & 1 \end{smallmatrix}\right)$ es `$\left(\begin{smallmatrix} 1 & 0 \cr 0 & 1 \end{smallmatrix}\right)$`.


## Entornos

Los entornos habituales se escriben de manera algo diferente. Por ejemplo, una definición y su código fuente:

{{% definition %}}
Esto es una **definición**.
{{% /definition %}}


```
{{%/* definition */%}}
Esto es una **definición**.
{{%/* /definition */%}}
```

Están definidos los entornos **definition**, **proposition**, **corollary**, **lemma**, **theorem**, **example**, **proof**, **remark**, **exercise** y **watch**. Los tres últimos no tienen barra de título, por ejemplo:

{{% remark %}}
Esto es una **observación**.
{{% /remark %}}

```
{{%/* remark */%}}
Esto es una **observación**.
{{%/* /remark */%}}
```

Los teoremas pueden tener **nombre**.

{{% theorem name="Nombre" %}}
Esto es un teorema con nombre. 
{{% /theorem %}}

```
{{%/* theorem name="Nombre" */%}}
Esto es un teorema con nombre. 
{{%/* /theorem */%}}
```

Los ejemplos *deben* tener nombre porque es lo único que aparecerá en la barra del título. 

{{% example name="Nombre del ejemplo" %}}
Esto es un ejemplo.
{{% /example %}}


```
{{%/* example name="Nombre del ejemplo" */%}}
Esto es un ejemplo.
{{%/* /example */%}}
```

Las pruebas tienen un aspecto especial. Aparecen plegadas para no sobrecargar el contenido y se despliegan pulsando sobre ellas.

{{% proof %}}
Esto es una prueba. Aparecen plegadas por defecto. 
{{% /proof %}}

```
{{%/* proof */%}}
Esto es una prueba. Aparecen plegadas por defecto. 
{{%/* /proof */%}}
```

Todos los entornos anteriores (excepto las pruebas) admiten **etiquetas** para hacer referencias.

{{% definition label="mi_def" %}}
Esto es una definición etiquetada como *mi_def*. 
{{% /definition %}}

```
{{%/* definition label="mi_def" */%}}
Esto es una definición etiquetada como *mi_def*. 
{{%/* /definition */%}}
```

## Markdown avanzado

Es sencillo crear enlaces y referencias a entornos etiquetados o secciones:

* Aprende markdown en [Wikipedia](https://en.wikipedia.org/wiki/Markdown). Este enlace se escribe `[Wikipedia](https://en.wikipedia.org/wiki/Markdown)`.

* Pulsa [aquí](#notación-matemática) para ir a la sección titulada *Notación matemática*. En este caso el código es `[aquí](#notación-matemática)`.

* Pulsa [aquí](#mi_def) para ir a la definición etiquetada *mi_def*. Aquí el código es `[aquí](#mi_def)`.


Los dos últimos ejemplos enlazan a contenidos de esta misma página. Para hacer una referencia a algún entorno de otra página hay que indicar la ruta. Se puede enlazar al [criterio de Eisenstein](../rings/factorization/#eisenstein) desde aquí escribiendo `[criterio de Eisenstein](../rings/factorization/#eisenstein)` ya que es un teorema etiquetado *eisenstein* que está dentro del bloque de Factorización del tema de Anillos.

También es fácil insertar imágenes alojadas dentro del proyecto:

![esto es una imagen](../images/gaussian_primes.png)

```
![esto es una imagen](../images/gaussian_primes.png)
```

## Sage

Es posible incluso insertar código en Sage para que se ejecute al pulsar un botón. Esto permite incluir aplicaciones interactivas.

<div class="sage">
 <script type="text/x-sage">
@interact
def _(n=slider(3,100, step_size=1, default = 5, label="n=")):
   lattice1 = []
   lattice2 = [[1,1], [1,-1], [-1,1], [-1,-1]]
   lattice3 = []
   for x in [-n .. n]:
       for y in [-n .. n]:
           if is_prime(x^2+y^2) and (x^2+y^2).mod(4) == 1:
               lattice1 = lattice1 + [[x,y]]
   for z in list(primes(3,n+1)):
       lattice3 = lattice3 + [[z,0], [-z,0]]
   lattice1_plot = point(lattice1, rgbcolor='green', size=400/n)
   lattice2_plot = point(lattice2, rgbcolor='red', size=800/n)
   lattice3_plot = point(lattice3, rgbcolor='blue', size=800/n)
   return show(lattice1_plot+lattice2_plot+lattice3_plot, aspect_ratio=1)
 </script>
</div>

```
<div class="sage">
 <script type="text/x-sage">
@interact
def _(n=slider(3,100, step_size=1, default = 5, label="n=")):
     lattice1 = []
     lattice2 = [[1,1], [1,-1], [-1,1], [-1,-1]]
     lattice3 = []
     for x in [-n .. n]:
         for y in [-n .. n]:
             if is_prime(x^2+y^2) and (x^2+y^2).mod(4) == 1:
                 lattice1 = lattice1 + [[x,y]]
     for z in list(primes(3,n+1)):
         lattice3 = lattice3 + [[z,0], [-z,0]]
     lattice1_plot = point(lattice1, rgbcolor='green', size=400/n)
     lattice2_plot = point(lattice2, rgbcolor='red', size=800/n)
     lattice3_plot = point(lattice3, rgbcolor='blue', size=800/n)
     return show(lattice1_plot+lattice2_plot+lattice3_plot, aspect_ratio=1)
 </script>
</div>
```

## Edita en tu ordenador

Si vas a editar los apuntes de un modo más que ocasional, es probable que te resulte más cómodo procesar los cambios en tu ordenador y luego subirlos a GitLab. Te explico cómo.

1. Instala [Hugo](https://gohugo.io/getting-started/installing/) y [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

2. Abre una terminal  y ejecuta los siguientes comandos:
```
$ git clone --recurse-submodules https://gitlab.com/edarfoc/estalg.git
$ cd estalg
$ hugo server
```

3. Si pinchas [aquí](http://localhost:1313/estalg/) probablemente te aparecerá la vista previa en el navegador. Si no te aparece, mira los mensajes que genera el último comando. Debe aparecer una línea como la siguiente, que contiene la dirección web local correcta:
```
Web Server is available at http://localhost:1313/estalg/ (bind address 127.0.0.1)
```

Los ficheros de contenido se encuentran en el subdirectorio `contents`. Los puedes abrir y modificar con tu editor de texto favorito. Recuerda recargar la vista previa en el navegador cuando guardes los cambios.

La organización de `contents` en subdirectorios y ficheros se corresponde con la distribución jerárquica del contenido de la web, reflejada en la barra lateral. Esto también explica el encabezamiento de los ficheros de contenido, que aparece rodeado con `+++`.

Para subir los cambios realizados al repositorio de GitLab hacer falta [aprender algo de Git](https://rogerdudler.github.io/git-guide/index.html).
