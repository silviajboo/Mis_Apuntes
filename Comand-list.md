# 0.ÍNDICE

1. Github
2. Vim
3. Gulp


# 1.Github

## 1.1.Configuración de la terminal

* Nombre: `git config –global user.name “nombre”`
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
* Eliminar rama: `git branch -d nombre-de-la-rama`
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

_En la página de Github_

1. Ir al repo en cuestión, en master
2. Ir a settings y bajar hasta la sección `GitHub Pages`
3. Botón: Launch automatic page generator
4. Introducir el texto con Markdown
5. Elegir plantilla y seguir pasos

###1.5.2 Subir mi proyecto web

1. Crear rama con nombre: `gh-pages`
2. Subir: con el index en la raiz y demás carpetas
3. Visitar página: http://nombre-de-usuario.github.io/nombre-del-repo

##1.6.Comandos de la consola

* Ir a un directorio: `cd y nombre del directorio`
* Paso atrás: `cd ..`
* Ver items de directorio actual: `ls l`
* Crear nuevo directorio `mkdir`
* Crear un archivo: `touch nombredelarchivo.extensión`
* Con las flechas arriba y abajo vemos el historial de las teclas que hemos ido usando
* Abrir programa o directorio: `open .`


# 2.Vim
_vim para entrar en el html_

* Habilitar los comandos `:`
* Habilitar la edición del código: `cntrl + I`
* Salir: `:q`
* Guardar: `:w`
* Guardar y salir `:wq`

# 3.Gulp

## 3.1.Organización

* Carpeta de trabajo: `src`
* Dentro de `src`: `img`, `scss`, `css` y `js`
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

1. Insertar antes de `</body>` del html: `<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>`
2. Poner debajo el link de la hoja js
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


# Bibliografía

* [Makigas](https://www.youtube.com/user/MakiGAS93)
* [gh-pages](https://www.youtube.com/watch?v=I-d9_l7myXw)