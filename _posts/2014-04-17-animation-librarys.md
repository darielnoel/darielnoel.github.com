---
layout: post
title: Animaciones.JS
description: "Características principales bibliotecas animación."
category: articles
tags: [animaciones, bibliotecas, javascript]
comments: true
share: false
---

He aquí lo que puede convertirse en mi próxima aventura, pero no pienso dar detalles hasta el final, solo pequeñas piezas que se irán juntando, creo que puede ser divertido.

La primera pieza será un compendio de las principales bibliotecas de animación que se usan en el FrontEnd, las caracterizaré de acuerdo a una serie de parámetros que a continuación listo:

- Aceptación en la comunidad.
- Dependencia de bibliotecas externas.
- Cantidad de ficheros a incluir.
- Tecnología predominante.(CSS, SVG, Canvas, Javascript)
- Filosofía de trabajo.
- Animaciones por defecto.
- Los 3 ingredientes mágicos. (queso, costilla, curri).

###[animate.css](http://jster.net/library/animate-css)

- Aceptación en la comunidad.  
	**Start:** 11,752  
	**Fork:**  2516  

- Dependencia de bibliotecas externas.
	No.

- Cantidad de ficheros a incluir.
	1 (animate.css)

- Tecnología predominante.
	CSS

- Filosofía de trabajo.  
	animate.css Se basa en la inclusión de clases CSS que representan animaciones predeterminadas.
{% highlight javascript %}
$(document).ready(function(){
	$('.go').click(function(){

		//Se le agrega la clase de las animaciones que se desean
		$('.animatecss').addClass('animated bounceOutLeft').one(

			//Cuando se quiera que una animacion termine solo se le quitan las clases correspondientes
			'webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend', function(){
				$(this).removeClass('animated bounceOutLeft');
		    });

	});
});
{% endhighlight %} 

- Animaciones por defecto.
	Gran cantidad de animaciones por defecto, de hecho esto es lo que hace grande a esta biblioteca.

- Los 3 ingredientes mágicos. (queso, costilla, curri).  
	Queso: Si  
	Costilla: Si  
	Curri: No  

###[tween.js](http://jster.net/library/tween-js)

- Aceptación en la comunidad.  
	**Start:** 1690  
	**Fork:**  266  

- Dependencia de bibliotecas externas.
	No

- Cantidad de ficheros a incluir.
	1 (tween.js)

- Tecnología predominante.
	JavaScript

- Filosofía de trabajo.
	tween.js Se basa en calcular los valores intermedios entre un valor inicial y un objetivo.
	Estos valores son expuestos a través del callback **onUpdate**.
	{% highlight javascript %}
    init();
    animate();
    function init() {
		//Elemento que se quiere animar
        var output = document.createElement( 'div' );
        output.style.cssText = 'position: absolute; left: 50px; top: 300px; font-size: 100px';
        document.body.appendChild( output );
		
		//Definiendo el objeto TWEEN
        var tween = new TWEEN.Tween( { x: 50, y: 0 } )
            .to( { x: 400 }, 2000 )

            //Función para calcular el intervalo
            .easing( TWEEN.Easing.Elastic.InOut )

            //callback para la actualización de los valores
            .onUpdate( function () {

                output.innerHTML = 'x == ' + Math.round( this.x );
                output.style.left = this.x + 'px';

            } )
            .start();

    }

    function animate() {
        requestAnimationFrame( animate ); // js/RequestAnimationFrame.js needs to be included too.
        TWEEN.update();

    }
	{% endhighlight %} 

- Animaciones por defecto.
	No cuenta con animaciones por defecto, ya que en mi opinión no la calificaría como una biblioteca de animación.

- Los 3 ingredientes mágicos. (queso, costilla, curri).  
	Queso: No  
	Costilla: Si  
	Curri: No

###[animo.js](http://jster.net/library/animo-js)

- Aceptación en la comunidad.  
	**Start:** 1622  
	**Fork:**  231  

- Dependencia de bibliotecas externas.
	Si, jquery-2.0.0.min.js o superior.

- Cantidad de ficheros a incluir.
	3
	{% highlight html %}
		<link href="animate+animo.css" rel="stylesheet" type="text/css">
		<script src="http://code.jquery.com/jquery-2.0.3.min.js" type="text/javascript"></script>
		<script src="animo.js" type="text/javascript"></script>
	{% endhighlight %} 

- Tecnología predominante.
	CSS, JavaScript

- Filosofía de trabajo.
	animo.js Se basa en la combinación de la biblioteca animate.css con el poder de javascript, para una fácil manipulación de las animaciones.
	{% highlight javascript %}
	$(element).animo({
		// [string]/[array] class name(s) of the css animation,
		animation: "name", // or ["name1", "name2", "name3"]
		// [float] time (in seconds) for the animation to last during 1 iteration
		duration: 0.8,
		// [int] number of times the animation shall repeat itself
		iterate: 1,
		// [string] how the animation should progress over the duration of each cycle
		timing: "linear",
		// [boolean] whether or not to "cleanse" the element after the animation has completed
		keep: false
	} [,function]);
	{% endhighlight %} 

- Animaciones por defecto.
	Gran cantidad de animaciones por defecto.

- Los 3 ingredientes mágicos. (queso, costilla, curri).  
	Queso: Si  
	Costilla: Si  
	Curri: No  

###[Textillate.js](http://jster.net/library/textillate)

- Aceptación en la comunidad.  
	**Start:** 1459  
	**Fork:**  288  

- Dependencia de bibliotecas externas.
	Si.  
		- jQuery  
		- animate.css, by Daniel Eden  
		- lettering.js, by Dave Rupert  

- Cantidad de ficheros a incluir.
	3
{% highlight html %}
<link href="assets/animate.css" rel="stylesheet">
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.0/jquery.min.js"></script>
<script src="jquery.textillate.js"></script>
{% endhighlight %} 

- Tecnología predominante.
	CSS, JavaScript, HTML Data Api

- Filosofía de trabajo.
	animo.js Se basa en la combinación de la biblioteca animate.css con el poder de javascript, además de la HTML Data API, lo cual le da un toque declarativo.
	{% highlight html %}
	<h1 class="tlt" data-in-effect="rollIn">Title</h1>
	{% endhighlight %}

	{% highlight javascript %}
	$('.tlt').textillate({ in: { effect: 'rollIn' } });
	{% endhighlight %} 

- Animaciones por defecto.
	Gran cantidad de animaciones por defecto.

- Los 3 ingredientes mágicos. (queso, costilla, curri).  
	Queso: Si  
	Costilla: Si  
	Curri: Si  

###[Anima](http://jster.net/library/anima)

- Aceptación en la comunidad.  
	**Start:** 1076  
	**Fork:**  85  

- Dependencia de bibliotecas externas.
	No 

- Cantidad de ficheros a incluir.
	1
{% highlight html %}
<script src="https://rawgithub.com/lvivski/anima/master/anima.min.js"></script>
{% endhighlight %} 

- Tecnología predominante.
	JavaScript, CSS

- Filosofía de trabajo.
	Anima Se basa en la creación de animaciones mediante Javascript, permitiendo tener un mayor control acerca de las mismas.
	{% highlight javascript %}
	//Inicializacion
	var world = anima.world();
	
	//Elemento que se va a animar
	var item = world.add(document.querySelector("div"));

	//Configuración de la animación y comenzar la animación
	item.animate({
	  translate: [x, y, z],
	  opacity: .5,
	  duration: 500,
	  ease: 'ease-in-out-quad',
	  delay: 100
	})
	{% endhighlight %} 

- Animaciones por defecto.
	Gran cantidad de animaciones por defecto.

- Los 3 ingredientes mágicos. (queso, costilla, curri).  
	Queso: Si  
	Costilla: Si  
	Curri: No  

¿No crees que les falte un poco de **curri** a estas bibliotecas?
