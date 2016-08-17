# WORDPRESS Guía

## Para templates

Tenemos un archivo html con el diseño maestro.
``{% include topheader.html %}``

Lo que queremos hacer con un CMS es aplicar el template al contenido.
````
PRESTASHOP
JECKILL
WORDPRESS
Server aconsejado por Mike: Gandi.net
Para crear un nombre de dominio: Domainr.com
Para tener un servidor local: desktop server (el logo es una S sobre fondo azul)
````

## A la hora de usar un CMS hay que tener en cuenta los requisitos técnicos.
Hay que tener en cuenta qué permite el hosting. La mayoría ofrece soporte para wordpress, pero algunos como ``GOST``no lo permite porque requiere Node.js en el server instalado.
También cuánta personalización. Cada CMS es un mundo, cada uno es distinto del otro.

## Wordpress.org y .com
El primero es el proyecto (el zip que te descargas) y el segundo te ofrece un hosting personalizado.

# DESCARGANDO WORDPRESS

1. Descargar zip de la web de Wordpress
2. Para instalar un tema nuevo creamos una carpeta en wp-content > Themes (Dentro hay un screenshot.png para hacer un preview de la web)
3. En la raiz de la carpeta de mi hosting, copiamos la carpeta de wp en la raiz.
a. Lo primero que busca al cargar la web, el servidor nos muestra el index.php.
b. Seleccionamos el idioma
c. Luego nos pide información: nombre de la base de datos, usuario, etc.
d. Ejecutamos
e. Nos pedirá más información para la base de datos
f. La opción de disuadir robots es para que google no nos encuentre
g. Nos lleva a la página de login de Wordpress (dominio/wp.admin)
h. Accedemos al panel de control
* Escritorio: novedades, actualizar, etc.
* Entradas: Crear posts
* Apariencia: temas (Elegir o añadir nuevo)
* Apariencia: Crear menús custom

## Editando el código

* Lo que está entre ``<?php>`` llama al archivo php correspondiente.
_Podemos añadir un ``if`` para generar condicionales a la hora de llamar al template php._
Podemos añadir también una parte de un template: ``get_template_part()_``

1. En la carpeta del template, tenemos: 
* **Header.php:** donde podemos modificar el html del heade. Aquí podemos cambiar la url de la home, entre otras cosas.
* **Index.php:** modificamos la página de home. Aquí nos llama el header del php para que se muestre. 

2. CSS
_Solo hay un archivo css, y no está en la carpeta de css._

* Siempre se puede crear una nueva hoja y lincarla con el tag de stylesheet.
* Dentro de nuestro styles.css suele haber una documentación útil para emplearlo.

3. Posicionamiento
* Hay plugings para esto. Igualmente el HTML ha de estar bien estructurado y el contido debe aportar valor.

4. Javascript y Jq
Se puede meter una hoja de js.


# Bibliografía

* [Wordpress Codex](https://codex.wordpress.org/) Para consultar documentación de uso, como mdn.
* [Wordpress SEO](https://wordpress.org/plugins/all-in-one-seo-pack/) Para consultar documentación de uso, como mdn.
