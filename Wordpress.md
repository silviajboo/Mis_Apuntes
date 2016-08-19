#Wordpress

##Gu�a del backend y Child Theme (Modificar el template)

A la hora de usar un CMS hay que tener en cuenta los requisitos t�cnicos.
Hay que tener en cuenta qu� permite el hosting. La mayor�a ofrece soporte para wordpress (instalaci�n), pero algunos como ``GOST``no lo permite porque requiere Node.js en el server instalado.
Para los templates cu�nta personalizaci�n, si no vamos a tocar c�digo. Cada CMS es un mundo, cada uno es distinto del otro.

#### Distinci�n entre Wordpress.org y Wordpress.com
El primero es el proyecto (el zip que te descargas) y el segundo te ofrece un hosting personalizado.

# Descargando e instalando WORDPRESS

Hay 2 m�todos. 
* Como mencion� antes, existen proveedores de hosting que ofrecen la instalaci�n de Wordpress en un click.
* La otra forma en yendo a wordpress.org y descargar la �ltima versi�n en .zip.

1. Descargar zip de la web de Wordpress
2. En la raiz de la carpeta de mi hosting (generalmente denominada /public), copiamos el contenido de la carpeta de wordpress en la raiz.
	* Introducimos la direcci�n de nuestro hosting con el sufijo ``/wp-admin`` (www.tudominio.com/wp-admin) y el servidor nos muestrar� el index.php.
	* Seleccionamos el idioma
	* Luego nos pide informaci�n: nombre de la base de datos, usuario, etc.
	* Ejecutamos
	* Nos pedir� m�s informaci�n para la base de datos (tienes que crear la base de datos en tu cPanel del host server, generalmente la opci�n es "mySql")
	* La opci�n de disuadir robots es para que google no nos encuentre
3. Nos lleva a la p�gina de login de Wordpress (dominio/wp-admin)
	*Introducimos la clave y usuario y ya estamos en el backend. Ya podemos crear entradas, p�ginas y seleccionar un tema visual.
* Escritorio: novedades, actualizar, etc.
* Entradas: Crear posts
* Apariencia: temas (Elegir o a�adir nuevo)
* Apariencia: Crear men�s custom

##Child Theme (Modificar el template)

Antes de nada, para mejorar nuestro flujo de trabajo crearemos un servidor local, para no estar subiendo todo el tiempo nuestras modificaciones.

###Crear servidor local (localhost)

Antes de instalar el servidor local en nuestro ordenador tienes que tener en cuenta tres datos que te aparecer�n a lo largo de la instalaci�n:

* La carpeta por defecto donde se ha instalado el WampServer (c:\wamp\).
* El servidor SMTP (localhost).
* El nombre de usuario (root).

_Si quieres usar wamp para el servidor local mira este enlace [C�mo instalar Wamp](http://www.gianoliveira.com/como-instalar-un-servidor-local.html)_

1. Para poder instalar Wordpress en tu servidor local tienes que crear una base de datos, es muy f�cil.
	* Para acceder al servidor local desde el navegador solamente tendr�s que teclear http://localhost/
	* Entramos en el enlace phpMyAdmin, el usuario es **root** y sin contrase�a.
	* Vamos a la pesta�a �Bases de Datos� y veremos el campo �Crear base de datos�. Escribimos el nombre de la nueva base de datos que queremos crear, wordpress por ejemplo, asignamos el Cotejamiento �utf8_spanish_ci� y clic en el bot�n �Crear�.
	
2. Instalar wordpress en el servidor local
	* Copia y pega el contenido de la carpeta Wordpress que descargaste desde www.wordpress.org y p�galo en la carpeta C:\wamp\www\.
	* Escribe http://localhost/wordpress/ en el navegador.
	* Configura los datos que te pide (nombre de usuario es **root**, contrase�a **si has establecido alguna** y servirdor **localohost**).
	* Una vez introducidos todos los datos que te pide wordpress acceder�s al login (localhost/wordpress/wp-admin).
	* Si tecleas en el navegador http://localhost/wordpress/ ver�s el frontend de la web, tal y como la ver�n tus usuarios.

##Trabajando con el Child Theme

_Consiste en crear un tema hijo, que modifica los estilos del tema padre.
Consiste en cargar una hoja de estilos propia justo despu�s de la hoja de estilos del tema padre. 
Sobreescribimos y a�adimos nuevas reglas sin tocar el tema original_

##C�mo crear el Child Theme

1. Crea una carpeta en tu carpeta de temas con el nombre del tema padre seguido de "-hijo" (o "-child" en ingl�s). La carpeta de temas est� en ``wp-content/themes``.`
2. En la carpeta del tema hijo, crea un archivo que se llame style.css. Este es el �nico archivo requerido para hacer un tema hijo. La hoja de estilos debe empezar con las siguientes l�neas:
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

/* =Aqu� empieza la personalizaci�n de tu tema
-------------------------------------------------------------- */
```` 

3. Cambiar: Las l�neas que s�lo requieren cambios son el **nombre del Theme, la Plantilla. Tambi�n el @import debe llamar a **wp_enqueue_style ()** para poner en cola el style
del parent y sobreescribir los estilos.
4. Crear un archivo functions.php en la carpeta ra�z de su Child el Theme. Justo al comienzo, en la primera l�nea, se debe a�adir una etiqueta de apertura de PHP. Todo otro c�digo estar� despu�s de esta etiqueta de apertura de PHP.
````
<?php //Etiqueta PHP de inicio

	Contenido

?> //Etiqueta PHP de cierre
````

##Trabajando con jetpack

1. M�dulo JetPack CSS personalizado.

Nota: si optas por Slim JetPack, no es necesario que realices la activaci�n en el paso 2, y en el paso 3, deber�s acudir a Ajustes > Slim JetPack. El resto todo es igual.
Listo, ya tenemos activado nuestro editor donde pegar o escribir las reglas CSS que modificar�n nuestro dise�o o tema. Lo fant�stico de este m�todo, es que JetPack va a incluir los estilos CSS que definamos en este editor justo detr�s en la carga de los que el tema trae por defecto (style.css), 
por lo que podemos sobreescribirlos sin problemas, sin miedo a perder los cambios en futuras actualizaciones.

Si no lo utilizas a�n, consiste en descargar el plugin [Jetpack](https://codex.wordpress.org/) para modificar el c�digo del template en el backend de wordpress.
Si no tienes cuenta en WordPress.com tambi�n puedes usar el plugin gratuito [Slim JetPack](http://www.silocreativo.com/2014/04/como-modificar-anadir-css-tema-wordpress/) y activar el m�dulo de CSS personalizado.

## Usando el plugin Simple Custom CSS

Igual de f�cil que usar el m�dulo de Jetpack. Despu�s de instalar Simple Custom CSS y activar el plugin, simplemente tienen que navegar hasta Apariencia > Custom CSS y a�adir tus lineas de CSS personalizado.

##Editar directamente el style.css de tu Tema

Pasamos a la zona gris de la edici�n de CSS en WordPress. Editar directamente el CSS de tu tema (style.css) no es la soluci�n m�s limpia. Tanto si es un tema premium como un tema gratuito, vas a perder dichos cambios cuando el tema se actualice.
Si a�n as� est�s convencido de que este es tu m�todo, veamos como podemos realizarlo directamente a trav�s del panel de Administraci�n de WordPress. Los pasos son:
1. Ir a Apariencia > Editor
2. Buscar el archivo style.css (comprobar que est� seleccionado el tema actual)
3. Editar con sumo cuidado.

# Bibliograf�a

* [Wordpress Codex](https://codex.wordpress.org/) Para consultar documentaci�n de uso, como mdn.
* [Wordpress SEO](https://wordpress.org/plugins/all-in-one-seo-pack/) Para consultar documentaci�n de uso, como mdn.
* [Servidor local, como crear, como exportar al hosting](http://www.gianoliveira.com/como-instalar-un-servidor-local.html)
* [Formas de modificar el styles.css de una plantilla](http://www.silocreativo.com/2014/04/como-modificar-anadir-css-tema-wordpress/)
* [C�mo crear un Child Theme](https://codex.wordpress.org/es:Temas_hijos)