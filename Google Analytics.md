#Google Analytics

##Gu�a de isntalaci�n y uso

# �NDICE

1. Instalaci�n
2. Qu� pesata�as mirar, c�mo hacer el seguimiento general
3. Qu� pesata�as mirar, c�mo hacer el seguimiento de los objetivos
4. Bibliograf�a

###Instalaci�n

_Instalar Google Analytics_

1. Registrarse en Google Analytics
2. Rellenar los campos que pide con la informaci�n del sitio web
3. Ir a la pesta�a de administrador, en la cabecera
4. Ir a informaci�n de seguimiento (icono .js) y clic en c�digo de seguimiento
5. Copiar el sript debajo de "Seguimiento del sitio web" y pegar en las p�ginas html en las que queremos
que haga el seguimiento. Hay que pegarlo antes del cierre del body.
6. Una vez hemos subido los cambios al host podemos comprobar si funciona yendo a Informes > tiempo real. 
Aqu� podemos ver en tiempo real cuando usuarios hay ahora mismo en el sitio. No olvides recargar la p�gina.

* Google Analytics tarda un tiempo en recopilar datos, por lo que no contar� con una gr�fica que puedas estudiar
al instante. Lo recomendable es esperar unas semanas o unos meses para hacer el primer estudio.

_Instalar Objetivos_

1. Ir a administrador > todos los datos del sitio web > objetivos.
2. + Nuevo objetivo.
3. En configuraci�n del objetivo elegir **Personalizado**.
4. Poner nombre al objetivo (Ideal usar nombre de la acci�n, como formulario enviado, etc.).
5. Elegir tipo de objetivo:
	* Destino: Carga de una ubicaci�n espec�fica. P�gina web o pantalla de aplicaci�n del tipo �Gracias por registrarse!
	* Duraci�n: Sesiones que duran un tiempo determinado o m�s.
	* P�ginas/pantallas por sesi�n: El usuario ve un n�mero concreto de p�ginas o de pantallas.
	* Evento: Activaci�n de una acci�n definida como evento. Por ejemplo, una recomendaci�n social, reproducci�n de v�deo o clic en anuncio.
6. Establecer la informaci�n del objetivo:
	* Destino: Igual a (y url de la p�gina a partir del primer /, https://www.dominio.com se suprime). Empieza por (todas las p�ginas que empiecen por
	alguna palabra clave). Y Expresi�n regular (Todas las p�ginas que tengan una expresi�n que se repita, por ejemplo todas las p�ginas de portfolio
	contienen la la expresi�n **port-** + el nombre del proyecto. O por ejemplo tadas aquellas que lleven un s�mbolo, como $ % &, etc.).
	* Duraci�n: Establecer el tiempo m�nimo que debe pasar el usuario para que se cumpla el objetivo.
	* P�ginas/pantallas por sesi�n: Establecer el n�mero de p�ginas m�nimas que debe ver el usuario para que se complete este objetivo.
	* Evento: Poner tres etiquetas en el html de la p�gina en, por ejemplo, un bot�n. �stos ser�n categor�a, acci�n y etiqueta.
	En el **html** hay que poner este script: ``ga('send', 'event', 'category', 'action', 'label');``. Los dos primeros campos 'send' y 'event' se dejan igual.
	A los otros tres les podemos asignar un valor, por ejemplo, puede quedar as�: ``ga('send', 'event', 'contacto', 'enviar', 'formulario');``
	Para un clic de un enlace, despu�s de por ejemplo ``class="nommbre-de-la-clase"`` habr�a que poner ``onClick="ga('send', 'event', 'category', 'action', 'label');"``. Tambi�n se puede hacer con 
	un hover ``onmouseover="ga('send', 'event', 'category', 'action', 'label');"``
7. Establecer un valor: Cada vez que un usuario completa un objetivo, este importe se registra y se suma al resto para incluirse en los informes como valor del objetivo.
8. Enbudo de conversi�n: Son los pasos que realizan nuestros usuarios para llegar al objetivo. Esto es ideal cuando se sigue un procedimiento de pasos, como
una compra o un registro y as� saber d�nde existe el abandono. **Obligatorio significa si que para que se cumpla el objetivo es obligatorio que el usuario pase
por cada una de las p�ginas que has detellado.**
9. Para saber c�mo ver los reportes y as� poder comprobar que los objetivos funcionan ver secci�n **"Qu� pesta�as mirar, c�mo hacer el seguimiento de los objetivos"**
de este documento.

##Qu� pesata�as mirar, c�mo hacer el seguimiento general

1. Audiencia > General: En el inicio de la pesta�a de informes lo primero que nos sale es un gr�fico llamado visi�n general.
Nos pone _Sesiones_, que son las visitas. Si subimos arriba del todo de la p�gina, parte derecha se puede elegir
desde cuando hasta cuado quieres ver la m�trica.

1.1. Cuadros:
* Sesiones: N�mero de visitas. La cifra que te da no es cuantas personas han visitado tu web, sino cuantas
visitas ha tenido tu web. Es decir, si tus sesiones son 4, puede que una misma persona haya entrado 4 veces.
Si un usuario entra 4 veces, para que cada visita sea contabilizada debe pasar entre cada una al menos 30min.
* Usuarios: N�mero de visitas por personas diferentes. Una visita equivale a un usuario. Cruzando los datos
que te da las **sesiones y los usuarios** puedes saber si �stos acceden m�s de una vez a tu sitio.
* P�ginas/Sesi�n:La media de p�ginas que ven tus **sesiones**.
* N� de p�ginas vistas: Es el resultado de multiplicar **sesiones x p�ginas/sesi�n**. Esto quiere decir, por ejemplo,
si un usuario entra en tu home, visita tu galer�a y tu p�gina de contacto, eso contar�a como **Tres p�ginas
vistas**

_Estos tres datos son muy importantes si tu sitio se mantiene con publicidad, porque las visitas de �sta
se pueden contar como n�mero de impresiones que tiene un anuncio en tu p�gina. Dependiendo siempre de d�nde
situes la publicidad._

* Duraci�n media de la sesi�n: la media de tiempo que pasa un usuario en tu sitio. Un minuto de media, por ejemplo,
est� muy bien porque el usuario est� interesado el ver algo.
* Porcentaje de rebote: es el porcentaje de *Usuarios* que llegan a tu p�gina, la miran dos segundos, y se van sin
haber visto alguna otra p�gina de tu sitio. *�Pero ojo!* No debe ser malo necesariamente. A lo mejor tu usuario 
lleg� a lo que buscaba r�pidamente. Que las m�tricas sean buenas o malas depende del objetivo de tu sitio web.
* Porcentaje de nuevas sesiones: Porcentaje de nuevos usuarios que entran por primera vez en tu sitio.

_Recuerda que los datos que est�s viendo hacen referencia al periondo que has seleccionado en la parte superior derecha
la p�gina._

* Los datos demogr�ficos hacen referencia a las **Sesiones**. 
* Idiomas: registra el lenguaje que tiene configurado en su navegador la sesi�n. 
* Pa�s, ciudad: Luegar de procedencia de las sesiones. Los que te pone "not set" es porque sus navegafores no permiten que localices d�nde est� la sesi�n. 
Puedes clicar en el enlace _ver todo el informe_ y sale un mapa para poder ver gr�ficamente los datos demogr�ficos.
* Sistema: Tiene que ver con el equipo al que accede a tu sitio.
* Navegador: Si es Chorme, Firefox, etc. _Esto es importante para prestar especial atenci�n a c�mo se ve tu sitio en los navegadores
con m�s porcentaje, que son lo que usan tus usuarios._
* Sistema operativo: Windows, iOS, Android, etc.
* Proveedores de servicio: Quienes dan internet a tus sesiones.
* M�vil: Hace referencia a quienes entran con tel�fonos m�viles.

1.3. Audiencia > Datos demogr�ficos

**Para ver estos datos, la primera vez que accedas a esta pesta�a, tendr�s que habilitar estas opciones**

Aqu� puedes ver la edad y sexo de tus usuarios.

1.4. Audiencia > Intereses

Si les gusta el cine, la televisi�n, etc.

2.1. Adquisi�n > Visi�n general

De d�nde viene el tr�fico.

* Tr�fico org�nico: Sesiones que entran a trav�s de Google. Estas sesiones han buscado el sitio web en cuesti�n o ha puesto
palabras claves para que el sitio apareciese en los resultados de b�squeda.
* Directo: Hace referencia a las sesiones que han entrado tecleando en la barra del navegador la url complea de la web o
porque lo ten�an guardado en favoritos.
* Referencia: Son las sesiones que acceden al sitio por haber hecho clic en un enlace. Por ejemplo un email, link en facebook,
Twitter u otra red social.

_Recuerda que los datos que est�s viendo hacen referencia al periondo que has seleccionado en la parte superior derecha
la p�gina._

2.2. Adquisi�n > Todo el tr�fico

Detalle de d�nde viene el tr�fico.

* Referencias: Aqu� se pueden ver las urls que est�n generando tr�fico al sitio.

3.1. Comportamiento > Visi�n general

* Todas las p�ginas: Ver cuales son las p�ginas que ven las sesiones. Esta es la m�s interesante porque tenemos una visi�n general 
del comportamiento de los usuarios en el sitio.
* Desglose de contenidos: Cu�les son las m�s visitas. Puedes categorizarlas, por si son b�squedas, etc.

##Qu� pesata�as mirar, c�mo hacer el seguimiento de los objetivos

1. Eventos: �stos se pueden ver en la pesta�a de informes > tiempo real > eventos.
2. Dem�s objetivos: ir a informes > conversiones > objetivos > visi�n general.
	* En el men� desplegable, situado en la parte superior izquierda, podemos ver los objetivos que se han cumplido.
	* En visi�n general se pueden hacer las comparaciones y los porcentajes de objetivos cumplidos, etc.
	* Los porcentajes de abandono tienen que ver con los **Enbudos de conversi�n**.
	* Ubicaci�n de consecuencia de objetivos: muestra d�nde se han cumplido los objetivos.
	* Fuente/medio: De donde han venido las visitas que han cumplido los objetivos.
	* URLs objetivos: Podemos ver con m�s detalle la procedencia de quienes cumplen los objetivos y adem�s ver el impacto monetario si
	hemos establecido un valor a la hora de crear el objetivo.

#Bibliograf�a

* [Instalar Google Analytics](https://www.youtube.com/watch?v=0EQ9TcVqmTw)
* [Tutorial: Qu� mirar en Google Analytics](https://www.youtube.com/watch?v=PCxoic2cvVI)
* [C�mo poner los eventos en html](https://www.youtube.com/watch?v=1Qg88Dk5gak)
* [C�mo crear los objetivos en Google Analytics](https://www.youtube.com/watch?v=ptEcdWn-EfU)
* [Definici�n del los distintos tipos de objetivos](https://support.google.com/analytics/answer/1012040?hl=es#goal_types)
* [Interpretar los informes de los objetivos](https://www.youtube.com/watch?v=nFuo5nRpLnQ)