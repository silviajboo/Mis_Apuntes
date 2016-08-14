#Google Analytics

##Guía de isntalación y uso

# ÍNDICE

1. Instalación
2. Qué pesatañas mirar, cómo hacer el seguimiento general
3. Qué pesatañas mirar, cómo hacer el seguimiento de los objetivos
4. Bibliografía

###Instalación

_Instalar Google Analytics_

1. Registrarse en Google Analytics
2. Rellenar los campos que pide con la información del sitio web
3. Ir a la pestaña de administrador, en la cabecera
4. Ir a información de seguimiento (icono .js) y clic en código de seguimiento
5. Copiar el sript debajo de "Seguimiento del sitio web" y pegar en las páginas html en las que queremos
que haga el seguimiento. Hay que pegarlo antes del cierre del body.
6. Una vez hemos subido los cambios al host podemos comprobar si funciona yendo a Informes > tiempo real. 
Aquí podemos ver en tiempo real cuando usuarios hay ahora mismo en el sitio. No olvides recargar la página.

* Google Analytics tarda un tiempo en recopilar datos, por lo que no contará con una gráfica que puedas estudiar
al instante. Lo recomendable es esperar unas semanas o unos meses para hacer el primer estudio.

_Instalar Objetivos_

1. Ir a administrador > todos los datos del sitio web > objetivos.
2. + Nuevo objetivo.
3. En configuración del objetivo elegir **Personalizado**.
4. Poner nombre al objetivo (Ideal usar nombre de la acción, como formulario enviado, etc.).
5. Elegir tipo de objetivo:
	* Destino: Carga de una ubicación específica. Página web o pantalla de aplicación del tipo ¡Gracias por registrarse!
	* Duración: Sesiones que duran un tiempo determinado o más.
	* Páginas/pantallas por sesión: El usuario ve un número concreto de páginas o de pantallas.
	* Evento: Activación de una acción definida como evento. Por ejemplo, una recomendación social, reproducción de vídeo o clic en anuncio.
6. Establecer la información del objetivo:
	* Destino: Igual a (y url de la página a partir del primer /, https://www.dominio.com se suprime). Empieza por (todas las páginas que empiecen por
	alguna palabra clave). Y Expresión regular (Todas las páginas que tengan una expresión que se repita, por ejemplo todas las páginas de portfolio
	contienen la la expresión **port-** + el nombre del proyecto. O por ejemplo tadas aquellas que lleven un símbolo, como $ % &, etc.).
	* Duración: Establecer el tiempo mínimo que debe pasar el usuario para que se cumpla el objetivo.
	* Páginas/pantallas por sesión: Establecer el número de páginas mínimas que debe ver el usuario para que se complete este objetivo.
	* Evento: Poner tres etiquetas en el html de la página en, por ejemplo, un botón. Éstos serán categoría, acción y etiqueta.
	En el **html** hay que poner este script: ``ga('send', 'event', 'category', 'action', 'label');``. Los dos primeros campos 'send' y 'event' se dejan igual.
	A los otros tres les podemos asignar un valor, por ejemplo, puede quedar así: ``ga('send', 'event', 'contacto', 'enviar', 'formulario');``
	Para un clic de un enlace, después de por ejemplo ``class="nommbre-de-la-clase"`` habría que poner ``onClick="ga('send', 'event', 'category', 'action', 'label');"``. También se puede hacer con 
	un hover ``onmouseover="ga('send', 'event', 'category', 'action', 'label');"``
7. Establecer un valor: Cada vez que un usuario completa un objetivo, este importe se registra y se suma al resto para incluirse en los informes como valor del objetivo.
8. Enbudo de conversión: Son los pasos que realizan nuestros usuarios para llegar al objetivo. Esto es ideal cuando se sigue un procedimiento de pasos, como
una compra o un registro y así saber dónde existe el abandono. **Obligatorio significa si que para que se cumpla el objetivo es obligatorio que el usuario pase
por cada una de las páginas que has detellado.**
9. Para saber cómo ver los reportes y así poder comprobar que los objetivos funcionan ver sección **"Qué pestañas mirar, cómo hacer el seguimiento de los objetivos"**
de este documento.

##Qué pesatañas mirar, cómo hacer el seguimiento general

1. Audiencia > General: En el inicio de la pestaña de informes lo primero que nos sale es un gráfico llamado visión general.
Nos pone _Sesiones_, que son las visitas. Si subimos arriba del todo de la página, parte derecha se puede elegir
desde cuando hasta cuado quieres ver la métrica.

1.1. Cuadros:
* Sesiones: Número de visitas. La cifra que te da no es cuantas personas han visitado tu web, sino cuantas
visitas ha tenido tu web. Es decir, si tus sesiones son 4, puede que una misma persona haya entrado 4 veces.
Si un usuario entra 4 veces, para que cada visita sea contabilizada debe pasar entre cada una al menos 30min.
* Usuarios: Número de visitas por personas diferentes. Una visita equivale a un usuario. Cruzando los datos
que te da las **sesiones y los usuarios** puedes saber si éstos acceden más de una vez a tu sitio.
* Páginas/Sesión:La media de páginas que ven tus **sesiones**.
* Nº de páginas vistas: Es el resultado de multiplicar **sesiones x páginas/sesión**. Esto quiere decir, por ejemplo,
si un usuario entra en tu home, visita tu galería y tu página de contacto, eso contaría como **Tres páginas
vistas**

_Estos tres datos son muy importantes si tu sitio se mantiene con publicidad, porque las visitas de ésta
se pueden contar como número de impresiones que tiene un anuncio en tu página. Dependiendo siempre de dónde
situes la publicidad._

* Duración media de la sesión: la media de tiempo que pasa un usuario en tu sitio. Un minuto de media, por ejemplo,
está muy bien porque el usuario está interesado el ver algo.
* Porcentaje de rebote: es el porcentaje de *Usuarios* que llegan a tu página, la miran dos segundos, y se van sin
haber visto alguna otra página de tu sitio. *¡Pero ojo!* No debe ser malo necesariamente. A lo mejor tu usuario 
llegó a lo que buscaba rápidamente. Que las métricas sean buenas o malas depende del objetivo de tu sitio web.
* Porcentaje de nuevas sesiones: Porcentaje de nuevos usuarios que entran por primera vez en tu sitio.

_Recuerda que los datos que estás viendo hacen referencia al periondo que has seleccionado en la parte superior derecha
la página._

* Los datos demográficos hacen referencia a las **Sesiones**. 
* Idiomas: registra el lenguaje que tiene configurado en su navegador la sesión. 
* País, ciudad: Luegar de procedencia de las sesiones. Los que te pone "not set" es porque sus navegafores no permiten que localices dónde está la sesión. 
Puedes clicar en el enlace _ver todo el informe_ y sale un mapa para poder ver gráficamente los datos demográficos.
* Sistema: Tiene que ver con el equipo al que accede a tu sitio.
* Navegador: Si es Chorme, Firefox, etc. _Esto es importante para prestar especial atención a cómo se ve tu sitio en los navegadores
con más porcentaje, que son lo que usan tus usuarios._
* Sistema operativo: Windows, iOS, Android, etc.
* Proveedores de servicio: Quienes dan internet a tus sesiones.
* Móvil: Hace referencia a quienes entran con teléfonos móviles.

1.3. Audiencia > Datos demográficos

**Para ver estos datos, la primera vez que accedas a esta pestaña, tendrás que habilitar estas opciones**

Aquí puedes ver la edad y sexo de tus usuarios.

1.4. Audiencia > Intereses

Si les gusta el cine, la televisión, etc.

2.1. Adquisión > Visión general

De dónde viene el tráfico.

* Tráfico orgánico: Sesiones que entran a través de Google. Estas sesiones han buscado el sitio web en cuestión o ha puesto
palabras claves para que el sitio apareciese en los resultados de búsqueda.
* Directo: Hace referencia a las sesiones que han entrado tecleando en la barra del navegador la url complea de la web o
porque lo tenían guardado en favoritos.
* Referencia: Son las sesiones que acceden al sitio por haber hecho clic en un enlace. Por ejemplo un email, link en facebook,
Twitter u otra red social.

_Recuerda que los datos que estás viendo hacen referencia al periondo que has seleccionado en la parte superior derecha
la página._

2.2. Adquisión > Todo el tráfico

Detalle de dónde viene el tráfico.

* Referencias: Aquí se pueden ver las urls que están generando tráfico al sitio.

3.1. Comportamiento > Visión general

* Todas las páginas: Ver cuales son las páginas que ven las sesiones. Esta es la más interesante porque tenemos una visión general 
del comportamiento de los usuarios en el sitio.
* Desglose de contenidos: Cuáles son las más visitas. Puedes categorizarlas, por si son búsquedas, etc.

##Qué pesatañas mirar, cómo hacer el seguimiento de los objetivos

1. Eventos: Éstos se pueden ver en la pestaña de informes > tiempo real > eventos.
2. Demás objetivos: ir a informes > conversiones > objetivos > visión general.
	* En el menú desplegable, situado en la parte superior izquierda, podemos ver los objetivos que se han cumplido.
	* En visión general se pueden hacer las comparaciones y los porcentajes de objetivos cumplidos, etc.
	* Los porcentajes de abandono tienen que ver con los **Enbudos de conversión**.
	* Ubicación de consecuencia de objetivos: muestra dónde se han cumplido los objetivos.
	* Fuente/medio: De donde han venido las visitas que han cumplido los objetivos.
	* URLs objetivos: Podemos ver con más detalle la procedencia de quienes cumplen los objetivos y además ver el impacto monetario si
	hemos establecido un valor a la hora de crear el objetivo.

#Bibliografía

* [Instalar Google Analytics](https://www.youtube.com/watch?v=0EQ9TcVqmTw)
* [Tutorial: Qué mirar en Google Analytics](https://www.youtube.com/watch?v=PCxoic2cvVI)
* [Cómo poner los eventos en html](https://www.youtube.com/watch?v=1Qg88Dk5gak)
* [Cómo crear los objetivos en Google Analytics](https://www.youtube.com/watch?v=ptEcdWn-EfU)
* [Definición del los distintos tipos de objetivos](https://support.google.com/analytics/answer/1012040?hl=es#goal_types)
* [Interpretar los informes de los objetivos](https://www.youtube.com/watch?v=nFuo5nRpLnQ)