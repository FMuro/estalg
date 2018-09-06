# Cómo generar y editar estos apuntes en tu ordenador

1. Instala [Hugo](https://gohugo.io/getting-started/installing/).

2. [Descarga](https://gitlab.com/edarfoc/estalg/-/archive/master/estalg-master.zip) los archivos de los apuntes y descomprimelos en el directorio que desees.

3. [Descarga](https://gitlab.com/edarfoc/hugo-theme-lecturenotes/-/archive/master/hugo-theme-lecturenotes-master.zip) la plantilla para generar los apuntes y descomprime su contenido en el subdirectorio `themes/hugo-theme-lecturenotes/`.

4. Abre una terminal en el directorio principal y ejecuta `hugo server`. 

5. Si pinchas [aquí](http://localhost:1313/estalg/) probablemente te aparecerá la vista previa en el navegador. Si no te aparece, mira los mensajes que genera el comando anterior. Debe aparecer una línea como la siguiente, que contiene la dirección web local correcta:
```
Web Server is available at http://localhost:1313/estalg/ (bind address 127.0.0.1)
```

6. Los ficheros de contenido se encuentran en el subdirectorio `contents`. Los puedes abrir y modificar con tu editor de texto favorito. La vista previa se regenerará automáticamiente cada vez que guardes los cambios. 

La organización de `contents` en subdirectorios y ficheros se corresponde con la distribución jerárquica del contenido de la web, reflejada en la barra lateral. Esto también explica el encabezamiento de los ficheros de texto, que aparece rodeado con `+++`. Esto es mejor aprenderlo por el método de ensayo-error.