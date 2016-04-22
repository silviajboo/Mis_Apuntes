#ÍNDICE

1. Github
2. Vim


# 1.Github

## 1.1.Configuración de la terminal

* Nombre: `git config –global user.name “nombre”`
* Email: `git config global user.email example@example.com`
* Comprobar: `git config list`
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

##1.5.Comandos de la consola

* Ir a un directorio: `cd y nombre del directorio`
* Paso atrás: `cd ..`
* Ver items de directorio actual: `ls l`
* Crear nuevo directorio `mkdir`
* Crear un archivo: `touch nombredelarchivo.extensión`
* Con las flechas arriba y abajo vemos el historial de las teclas que hemos ido usando
* Abrir programa o directorio: `open .`

# 2.Vim
_vim para entrar en el html_

* : es para habilitar los comandos
* cntrl + I es para editar el texto
* :q para salir
* :w para guardar


# Bibliografía

* [Makigas](https://www.youtube.com/user/MakiGAS93)