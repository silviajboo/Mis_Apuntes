#Wordpress

##Guía del backend y Child Theme (Modificar el template)

A la hora de usar un CMS hay que tener en cuenta los requisitos técnicos.
Hay que tener en cuenta qué permite el hosting. La mayoría ofrece soporte para wordpress (instalación), pero algunos como ``GOST``no lo permite porque requiere Node.js en el server instalado.
Para los templates cuánta personalización, si no vamos a tocar código. Cada CMS es un mundo, cada uno es distinto del otro.

#### Distinción entre Wordpress.org y Wordpress.com
El primero es el proyecto (el zip que te descargas) y el segundo te ofrece un hosting personalizado.

# Descargando e instalando WORDPRESS

Hay 2 métodos. 
* Como mencioné antes, existen proveedores de hosting que ofrecen la instalación de Wordpress en un click.
* La otra forma en yendo a wordpress.org y descargar la última versión en .zip.

1. Descargar zip de la web de Wordpress
2. En la raiz de la carpeta de mi hosting (generalmente denominada /public), copiamos el contenido de la carpeta de wordpress en la raiz.
	* Introducimos la dirección de nuestro hosting con el sufijo ``/wp-admin`` (www.tudominio.com/wp-admin) y el servidor nos muestrará el index.php.
	* Seleccionamos el idioma
	* Luego nos pide información: nombre de la base de datos, usuario, etc.
	* Ejecutamos
	* Nos pedirá más información para la base de datos (tienes que crear la base de datos en tu cPanel del host server, generalmente la opción es "mySql")
	* La opción de disuadir robots es para que google no nos encuentre
3. Nos lleva a la página de login de Wordpress (dominio/wp-admin)
	*Introducimos la clave y usuario y ya estamos en el backend. Ya podemos crear entradas, páginas y seleccionar un tema visual.
* Escritorio: novedades, actualizar, etc.
* Entradas: Crear posts
* Apariencia: temas (Elegir o añadir nuevo)
* Apariencia: Crear menús custom

##Child Theme (Modificar el template)

Antes de nada, para mejorar nuestro flujo de trabajo crearemos un servidor local, para no estar subiendo todo el tiempo nuestras modificaciones.

###Crear servidor local (localhost)

Antes de instalar el servidor local en nuestro ordenador tienes que tener en cuenta tres datos que te aparecerán a lo largo de la instalación:

* La carpeta por defecto donde se ha instalado el WampServer (c:\wamp\).
* El servidor SMTP (localhost).
* El nombre de usuario (root).

_Si quieres usar wamp para el servidor local mira este enlace [Cómo instalar Wamp](http://www.gianoliveira.com/como-instalar-un-servidor-local.html)_

1. Para poder instalar Wordpress en tu servidor local tienes que crear una base de datos, es muy fácil.
	* Para acceder al servidor local desde el navegador solamente tendrás que teclear http://localhost/
	* Entramos en el enlace phpMyAdmin, el usuario es **root** y sin contraseña.
	* Vamos a la pestaña “Bases de Datos” y veremos el campo “Crear base de datos”. Escribimos el nombre de la nueva base de datos que queremos crear, wordpress por ejemplo, asignamos el Cotejamiento “utf8_spanish_ci” y clic en el botón “Crear”.
	
2. Instalar wordpress en el servidor local
	* Copia y pega el contenido de la carpeta Wordpress que descargaste desde www.wordpress.org y pégalo en la carpeta C:\wamp\www\.
	* Escribe http://localhost/wordpress/ en el navegador.
	* Configura los datos que te pide (nombre de usuario es **root**, contraseña **si has establecido alguna** y servirdor **localohost**).
	* Una vez introducidos todos los datos que te pide wordpress accederás al login (localhost/wordpress/wp-admin).
	* Si tecleas en el navegador http://localhost/wordpress/ verás el frontend de la web, tal y como la verán tus usuarios.

##Trabajando con el Child Theme

_Consiste en crear un tema hijo, que modifica los estilos del tema padre.
Consiste en cargar una hoja de estilos propia justo después de la hoja de estilos del tema padre. 
Sobreescribimos y añadimos nuevas reglas sin tocar el tema original_

##Cómo crear el Child Theme

1. Crea una carpeta en tu carpeta de temas con el nombre del tema padre seguido de "-hijo" (o "-child" en inglés). La carpeta de temas está en ``wp-content/themes``.`
2. En la carpeta del tema hijo, crea un archivo que se llame style.css. Este es el único archivo requerido para hacer un tema hijo. La hoja de estilos debe empezar con las siguientes líneas:
````
/*
 Theme Name:   Twenty Fourteen Child
 Theme URI:    http://example.com/twenty-fourteen-child/
 Description:  Twenty Fourteen Child Theme
 Author:       John Doe
 Author URI:   http://example.com
 Template:     twentyfourteen
 Version:      1.0.0
 Tags:         light, dark, two-columns, right-sidebar, responsive-layout, accessibility-ready
 Text Domain:  twenty-fourteen-child
*/
@import url("../twentyfourteen/style.css");

/* =Aquí empieza la personalización de tu tema
-------------------------------------------------------------- */
```` 

3. Cambiar: Las líneas que sólo requieren cambios son el **nombre del Theme, la Plantilla. También el @import debe llamar a **wp_enqueue_style ()** para poner en cola el style
del parent y sobreescribir los estilos.
4. Crear un archivo functions.php en la carpeta raíz de su Child el Theme. Justo al comienzo, en la primera línea, se debe añadir una etiqueta de apertura de PHP. Todo otro código estará después de esta etiqueta de apertura de PHP.
````
<?php //Etiqueta PHP de inicio

	Contenido

?> //Etiqueta PHP de cierre
````

##Trabajando con jetpack

1. Módulo JetPack CSS personalizado.

Nota: si optas por Slim JetPack, no es necesario que realices la activación en el paso 2, y en el paso 3, deberás acudir a Ajustes > Slim JetPack. El resto todo es igual.
Listo, ya tenemos activado nuestro editor donde pegar o escribir las reglas CSS que modificarán nuestro diseño o tema. Lo fantástico de este método, es que JetPack va a incluir los estilos CSS que definamos en este editor justo detrás en la carga de los que el tema trae por defecto (style.css), 
por lo que podemos sobreescribirlos sin problemas, sin miedo a perder los cambios en futuras actualizaciones.

Si no lo utilizas aún, consiste en descargar el plugin [Jetpack](https://codex.wordpress.org/) para modificar el código del template en el backend de wordpress.
Si no tienes cuenta en WordPress.com también puedes usar el plugin gratuito [Slim JetPack](http://www.silocreativo.com/2014/04/como-modificar-anadir-css-tema-wordpress/) y activar el módulo de CSS personalizado.

## Usando el plugin Simple Custom CSS

Igual de fácil que usar el módulo de Jetpack. Después de instalar Simple Custom CSS y activar el plugin, simplemente tienen que navegar hasta Apariencia > Custom CSS y añadir tus lineas de CSS personalizado.

##Editar directamente el style.css de tu Tema

Pasamos a la zona gris de la edición de CSS en WordPress. Editar directamente el CSS de tu tema (style.css) no es la solución más limpia. Tanto si es un tema premium como un tema gratuito, vas a perder dichos cambios cuando el tema se actualice.
Si aún así estás convencido de que este es tu método, veamos como podemos realizarlo directamente a través del panel de Administración de WordPress. Los pasos son:
1. Ir a Apariencia > Editor
2. Buscar el archivo style.css (comprobar que está seleccionado el tema actual)
3. Editar con sumo cuidado.

# Bibliografía

* [Wordpress Codex](https://codex.wordpress.org/) Para consultar documentación de uso, como mdn.
* [Wordpress SEO](https://wordpress.org/plugins/all-in-one-seo-pack/) Para consultar documentación de uso, como mdn.
* [Servidor local, como crear, como exportar al hosting](http://www.gianoliveira.com/como-instalar-un-servidor-local.html)
* [Formas de modificar el styles.css de una plantilla](http://www.silocreativo.com/2014/04/como-modificar-anadir-css-tema-wordpress/)
* [Cómo crear un Child Theme](https://codex.wordpress.org/es:Temas_hijos)