# Álgebra Básica

Esta web contiene las transparencias del profesor [Fernando Muro](http://personal.us.es/fmuro/) para la asignatura obligatoria [Álgebra Básica](http://www.us.es/estudios/grados/plan_171/asignatura_1710001) del [Grado en Matemáticas](http://www.us.es/estudios/grados/plan_171) de la [Universidad de Sevilla](http://www.us.es). Los contenidos son esencialmente los mismos que los de los apuntes disponibles en PDF en [este enlace](https://rodas5.us.es/items/1141d30f-73ed-4c7a-92f9-d5046dbdffe1/1/). Han sido elaborados por diversos profesores del [Departamento de Álgebra](http://www.algebra.us.es/).

{{< button href="./docs/latex.pdf" align="center" >}} Versión PDF {{< /button >}}<br>

{{% watch %}}
Esta web está **en construcción**. El contenido actual es incompleto, puede contener erratas y será modificado para su mejora sin previo aviso. Se recomienda recargar la web cada día que se consulte para evitar que el ordenador muestre copias antiguas almacenadas en la caché. La versión en PDF se genera automáticamente y puede contener errores derivados del proceso de conversion. 
{{% /watch %}}

## Cómo manejarse

Verás una barra de navegación lateral con desplegables. A ambos lados del contenido principal podrás encontrar flechas para ir tanto a la página siguiente como a la anterior. Estas flechas estarán abajo del todo si la ventana del navegador es pequeña.

![overview](./images/overview.png)

Una característica importante de la barra lateral es la casilla de búsquedas, que sirve para encontrar rápidamente una palabra o un texto dentro de la web. ¡Es sensible a los acentos!

![search](./images/search.png)

La barra superior de cada página te permitirá saber dónde estás y navegar a niveles anteriores rápidamente.

![topbar](./images/topbar.png)

Al colocarte sobre {{< icon name="fa-list-alt" size="large" >}} aparecerán enlaces a los diferentes epígrafes en los que se divide la página.

![sections](./images/sections.png)

El diseño es adaptable, debe funcionar igual de bien tanto en ordenadores como en dispositivos móviles (a veces mejor en formato apaisado). En pantallas pequeñas la barra lateral está en principio oculta pero puede mostrarse y volverse a ocultar pulsando el icono {{< icon name="menu-hamburger" size="large" >}} de la barra superior.

![responsive](./images/responsive.png)

Las pruebas de resultados aparecerán plegadas para no sobrecargar la página. Se despliegan pulsando sobre ellas.

{{% proof %}}
Aquí iría la demostración. El final se indica con un cuadrado a la derecha.
{{% /proof %}}

Hay algunas aplicaciones interactivas que se ejecutan al pulsar un botón. ¡Ojo! En ocasiones pueden tardar bastante tiempo en cargarse.

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

## Agradecimientos

Esta web se ha creado íntegramente con herramientas [libres y de código abierto](https://es.wikipedia.org/wiki/Software_libre_y_de_c%C3%B3digo_abierto), entre otras con el generador web [Hugo](https://gohugo.io/), la plantilla [docdock](http://docdock.netlify.com/), la librería para contenido matemático [MathJax](https://www.mathjax.org/), el programa de cálculo [SageMath](http://www.sagemath.org/) y su interfaz web [SageMathCell](https://sagecell.sagemath.org/). En la barra lateral encontrarás enlaces al código de esta web, que también es libre, y a instrucciones sobre cómo descargarlo y editarlo. La versión en PDF se genera usando la librería [shortcodes](https://pypi.org/project/shortcodes/) de [dmulholland](https://darrenmulholland.com/docs/shortcodes/).

