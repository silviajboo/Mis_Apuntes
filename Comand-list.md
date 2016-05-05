# 0.ÍNDICE

1. Github
2. Vim
3. Gulp
4. SASS
5. Javascript


# 1.Github

## 1.1.Configuración de la terminal

* Nombre: `git config -–global user.name “nombre”`
* Email: `git config global user.email example@example.com`
* Comprobar: `git config --list`
* Añadir origen: `git remote add origin https://github.com/example.git`

## 1.2.Procedimiento

* Crear .git: `git init`
1. Comprobar qué se se ha añadido: `git status`
2. Añadir lo que me interesa: `git add nombredelarchivo ó Añadir todo git add .`
3. Bajarme lo que está en el repo: `git pull`
4. Creo un comentario descriptivo: `git commit -m “mensaje-descriptivo”`
5. Subir al repo: `git push origin nombre-de-la-rama`

## 1.3.Ramas

* Saber en qué rama estamos: `git branch`
* Crear nueva rama: `git branch nombre-de-la-rama`
* Cambiar de rama: `git checkout nombre-de-la-otra-rama`
* Crear y cambiar de rama simultáneamente: `git checkout -b nombre-de-la-rama`
* Cambiar el nombre de la rama: `git branch -m nombre-antiguo nombre-nuevo`
* Eliminar rama local: `git branch -d nombre-de-la-rama`
* Eliminar rama remota: `git push origin --delete nombre_rama`
* Forzar eliminar rama: `git branch -D nombre-de-la-rama`
* Listado de todas las cosas que podemos hacer: `git branch -h`

#### 1.3.1.Merge

_Cuando no hay cambios es master_

1. Ir a master: `git checkout master`
2. Mergear la rama: `git merge nombre-de-la-rama`

_Cuando si hay cambios en master pero no hay conflicto_

1. Ir a master: `git checkout master`
2. Mergear la rama: `git merge nombre-de-la-rama
3. Hacemos un commit: `git commit -m “mensaje-descriptivo”` _Nos pide hacer un commit debido a que junta los cambios de ambas ramas en un nuevo commit_

_Qué hacer cuando hay conflicto simple_

1. Comprobar qué conflictos hay: `git status`
2. Pasamos a nuestro editor y vemos esta estructura nuestro código dividido por símbolos de mayor y menos que, y unas barras.
3. Eliminamos esto que nos ha generado, salvo lo que nos queramos quedar.
4. Añadimos: `git add nombre-del-archivo`
5. Comiteamos: `git commit -m "mensaje-descriptivo"`
6. Con vim resolvemos el conflicto: `:wq (sintaxis de vim)`

##1.4.Alias

_Para hacer atajos cuando usamos combinaciones de comandos_

* Crearlo: `Git config --global alias.nombredelalias 'comandos de git'`
* Ver todos nuestros alias: `git config --global --get-regexp`
* Eliminar un alias: `git config --global --unset alias.nombredelalias`

##1.5 Github pages

###1.5.1 Usar las plantillas de github

_En la página de Github, usando sus plantillas con markdown_

1. Ir al repo en cuestión, en master
2. Ir a settings y bajar hasta la sección `GitHub Pages`
3. Botón: Launch automatic page generator
4. Introducir el texto con Markdown
5. Elegir plantilla y seguir pasos

###1.5.2 Subir mi proyecto web

_Subir archivos a gh-pages_

1. Crear rama con nombre: `gh-pages`
2. Push: con el index en la raiz y demás carpetas
3. Para visitar la página: `http://nombre-de-usuario.github.io/nombre-del-repo`

##1.6.Comandos de la consola

* Ir a un directorio: `cd y nombre del directorio`
* Paso atrás: `cd ..`
* Ver items de directorio actual: `ls -l`
* Crear nuevo directorio `mkdir nombre`
* Crear un archivo: `touch nombredelarchivo.extensión`
* Con las flechas arriba y abajo vemos el historial de las teclas que hemos ido usando
* Abrir programa o directorio: `open .`

##1.7.Deshaciendo cosas

* Para deshacer el git add: `git reset HEAD <archivo>...`
* Eliminar archivo en local y remoto: `git rm miarchivo.php` y comitear
* Eliminar una carpeta en local y remoto: `git rm -r micarpeta`
* Eliminar rama local: `git branch -d nombre-de-la-rama`
* Eliminar rama remota: `git push origin --delete nombre_rama`
* Forzar eliminar rama: `git branch -D nombre-de-la-rama`


# 2.Vim
_vim para entrar en el html_

* Habilitar los comandos `:`
* Habilitar la edición del código: `cntrl + I`
* Salir: `:q`
* Forzar la salida: `:!q`
* Guardar: `:w`
* Guardar y salir `:wq`

# 3.Gulp

## 3.1.Organización

* Carpeta de trabajo: `src`
* Carpeta de publicación: `dist`
* Dentro de `src`: `img`, `scss`, `css` y `js`
* Dentro de `dist`: `img`, `scss`, `css` y `js`
* Instalaremos: `node_modules`
* Tasks: `gulpfile.js`
* Info del proyecto: `package.json`

## 3.2.Instalación

_Por primera vez_

1. Creamos package.json: `npm init`
2. Para que nuestra terminal reconozca los comandos de gulp: `npm install --global gulp-cli`
3. Instalamos node_modules: `npm i gulp --save-dev`
4. Creamos y configuramos nuestro gulpfile.js añadiendo las funciones que necesitemos
5. Instalamos cada función con su código correspondiente

_En base al package.json_

1. Creamos las carpetas
2. Situamos el gulpfile.js y package.json en la raiz de nuestro proyecto
3. Instalamos node_modules: `npm i gulp --save-dev`
4. Instalar lo referenciado en .json: `npm i`

# 4.SASS

## 4.1.Imports

1. Generamos el archivo central: main.scss _Donde irán los imports_
2. Creamos los partial: `_nombre.scss`
3. En el main.scss pondremos los imports: `@import: 'nombredelpartial';`
4. Ejecutamos el watch: `sass --watch scss/nombredelarchivo.scss:css/nombredelarchivo.css`
5. Podemos comprimir el código resultante: `--style compressed`

## 4.2.Variables

1. Generamos un partial para las variables
2. Creamos aquí las variables: `$color: #333333;`
3. Aplicamos nuestra variable: `$color`

## 4.3.Mixings

1. Creamos un partial para los mixings
2. Los ponemos así: `@mixin nombre {border: 1px;}`
3. Para aplicarlo usamos: `@include nombre`

_Podemos variar el mixing puntualmente_ `@include nombre (#666)`

# 5.Javascript

## 5.1.Smooth scrolling

1. Insertar antes de `</body>` del html: 
`<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>`
2. Poner debajo el link de la hoja js: `<script src="js/nombre.js"></script>`
3. En la hoja js poner:

```$(document).ready(function(){
	$('a[href^="#"]').on('click',function (e) {
	    e.preventDefault();
	    var target = this.hash;
	    var $target = $(target);
	    $('html, body').stop().animate({
	        'scrollTop': $target.offset().top
	    }, 900, 'swing', function () {
	        window.location.hash = target;
	    });
	});
});
```

## 5.2.Acordeón

1. Poner esto en la hoja js:

```
$('.toggle').click(function() {
    if ($(this).siblings().is(':visible')) {
        $(this).siblings().slideUp();
        $(this).siblings().find('.inner:visible').slideUp();
    } else {
        $(this).parent().parent().find('inner:visible').slideUp();
        $(this).siblings().slideToggle();
    };
});
```

2. Necesitamos lincar el jquery.js de mike (ya pondré el enlace) antes del `</body>` y del link de nuestro .js
3. Esto debe ir en nuestro style.css:

```
ul .inner {
  overflow: hidden;
  display: none;
}
ul .inner.show {
  display: block;
}
ul li a.toggle {
  width: 100%;
  display: block;
  transition: background .3s ease;
```

## 5.3.Botón "ver más"

1. Creamos 3 clases: la primera para estilar el botón, la segunda para añadir el texto al botón y la tercera para hacer el cambio.

```
.port-btn-seemore {
    margin: 0px 0px 80px;
    padding: 10px 40px;
}

.port-btn-seemore:before {
    content: "Ver más";
}

.port-btn-seeless:before {
    content: "Ver menos";
    background-color: greenyellow;
}
```
2. Añadimos un id al botón `id="seemore"` en el HTML
3. En la hoja js añadimos este código

```
$(document).on("ready", main);

function main(){
    $("#seemore").on("click", cambiarTexto);
}

function cambiarTexto(){
    $(this).toggleClass("port-btn-seeless");
}

```

## 5.4.Animaciones al hacer click

1. Hay que hacer dos clases: una con los estilos y otra con la animación
2. También hacemos dos id: uno con un nombre y al otro le añadimos un 2. Esto lo hacemos para poder aplicar la animación a más de un elemento.
3. Colocamos en el html, tanto la clase con los estilos, como el id1 en unos y el id2 en otros.
4. Definimos en el estilo de la animación cómo queremos que sea.
5. Las animaciones están en la carpeta de `01 Resourses`, en el archivo `animate.css`


```
$(document).on("ready", first);

function first(){
    $("#id1, #id2").on("click", second);
}

function second(){
    $(this).toggleClass("animationclass");
}
```

# Bibliografía

* [Makigas](https://www.youtube.com/user/MakiGAS93)
* [gh-pages](https://www.youtube.com/watch?v=I-d9_l7myXw)
* [Eliminar ramas](http://vensign.com/como-borrar-una-rama-local-y-remota-en-git/)
* [Animaciones en CSS3](http://www.csslab.cl/2011/06/21/animaciones-css3-avanzadas/)
* [Usando animate.css combinado con jq](http://www.csslab.cl/2011/06/21/animaciones-css3-avanzadas/)
* [GitHub animate.css combinado con jq](https://github.com/daneden/animate.css)
* [Cambiar estilos con toggle](https://www.youtube.com/watch?v=HTHJbbRVdSU)