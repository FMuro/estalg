# Cómo generar y editar estos apuntes en tu ordenador

1. Instala [Hugo](https://gohugo.io/getting-started/installing/) y [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

2. Abre una terminal  y ejecuta los siguientes comandos
```
$ git clone --recurse-submodules https://gitlab.com/edarfoc/estalg.git
$ cd estalg
$ hugo server
```

3. Si pinchas [aquí](http://localhost:1313/estalg/) probablemente te aparecerá la vista previa en el navegador. Si no te aparece, mira los mensajes que genera el último comando. Debe aparecer una línea como la siguiente, que contiene la dirección web local correcta:
```
Web Server is available at http://localhost:1313/estalg/ (bind address 127.0.0.1)
```

Los ficheros de contenido se encuentran en el subdirectorio `contents`. Los puedes abrir y modificar con tu editor de texto favorito. La vista previa se regenerará automáticamiente cada vez que guardes los cambios.

La organización de `contents` en subdirectorios y ficheros se corresponde con la distribución jerárquica del contenido de la web, reflejada en la barra lateral. Esto también explica el encabezamiento de los ficheros de contenido, que aparece rodeado con `+++`.