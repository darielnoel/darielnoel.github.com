---
layout: post
title: SmartComments, genera comentarios automáticamente al código javascript.
description: "SmartComments, genera comentarios automáticamente al código javascript."
category: articles
tags: [comentarios automáticos, javascript]
comments: true
share: true
---

###Introducción

Según estudios realizados por una prestigiosa agencia más del 90% de los programadores prefieren documentar el codigo fuente a escribirlo. ¿Qué?

Mi primera reacción fue pensar, ¿Es posible que el mundo halla cambiado tan rápido sin que me halla dado cuenta? Le pregunté a otros programadores del equipo si creían que el misterioso titular fuera cierto, y muy serios asintieron. En mi mente el recuerdo vigente de lo tedioso que resultaba para mi, comentar el código fuente que había escrito, sobre todo aquellas funciones que con solo leer el nombre ya se sabía lo que hacían. Además de tener que actualizar la documentacion cada vez que se realizaba algún cambio.

Pero, ¿Por qué yo no lo disfrutaba y otras personas si? En medio de ese dilema estaba cuando alguien estalló en carcajadas y fue entonces que noté las caras sonrientes de mis compañeros de equipo... Uff, menos mal que era una broma.

###Desarrollo

Muchos utilizamos herramientas como [YUIDocs](http://yui.github.io/yuidoc/), o [JSDocs](http://usejsdoc.org/), entre [otras](http://www.lsauer.com/2013/05/javascript-documentation-generator.html) para generar la documentación de nuestros proyectos. éstas necesitan una serie se parámetros de entrada que deben ser escritos de manera [explícita](http://metajack.wordpress.com/2008/07/01/the-state-of-javascript-documentation-tools/), por los programadores como por ejemplo:

{% highlight javascript %}
/**
 * Descripción
 * @method Nombre de la función
 * @param Parámetro A
 * @param Parámetro B
 * @return Valor que retorna
 */
{% endhighlight %}

Para muchos éste proceso puede resultar algo tedioso, sobre todo si tenemos en cuenta que cuando ocurre un cambio en alguno de estos parámetros, como el nombre de la función por ejemplo, tenemos que actualizar la documentación correspondiente. 

También muchas veces hay partes de la documentación que pueden ser redundantes e innecesarias, es obvio que la funcion getNombre() devuelve el atributo nombre de la clase que la implemente, por solo tomar un ejemplo.

Éstos fenómenos toman proporciones significativas cuando nos tenemos que hacer cargo de proyectos bastante avanzados y que tienen una escasa documentación.


Según [@evangoer](https://twitter.com/evangoer) en la conferencia ["Thinking of Documentation as Code"](http://www.youtube.com/watch?v=mEvvc80ZYU8), en la mayoría de los casos al documentar el código fuente es muy útil el hacerse 3 preguntas:

- ¿Qué es lo que hace el código? 
- ¿Cómo es que lo hace? 
- ¿Porque lo hace?

[SmartComments](http://smartcomments.github.io/), es una herramienta de código abierto escrita en [Node.js](http://nodejs.org/) que puede automatizar y acelerar así considerablemente el proceso de generación de documentación. sobre todo respondiendo las preguntas (¿Qué? y ¿Cómo?). En la siguiente imagen se muestran las partes del ejemplo anterior que pueden ser generadas por [SmartComments](http://smartcomments.github.io/). 

{% highlight javascript %}
/**
 * Descripción
 * [@method Nombre_de_la_función] ------- SmartComments
 * [@param Parámetro_A] ----------------- SmartComments
 * [@param Parámetro_B] ----------------- SmartComments
 * [@return Valor_que_retorna] ---------- SmartComments
 */
{% endhighlight %}

Básicamente solo tendríamos que poner la descripción de nuestra función. O alguna otra explicación más detallada. 


Algunas de las funcionalidades de [SmartComments](http://smartcomments.github.io/) son:

 - Generar la metainformación necesaria para la generación de documentación a ficheros completos, de manera individual, o que se encuentren dentro de una jerarquía de directorios determinada. 

 - [Plugin](http://smartcomments.github.io/#features) para (sublime text), que da acceso a las funciones de la aplicación a través de este editor y que además permite generar comentarios a una selección de texto, lo cual es una funcionalidad bastante útil.
 
 - Personalización mediante plantillas para la generación de documentación a eventos, clases, atributos, entre otros. Y en dependencia del estilo de códificación de nuestra empresa o framework.

 - Versión online a modo de demostración que puede ser utilizada para la generación de metainformación si no se desea instalar la aplicación.

Un caso de uso interesante planteado por [Mr. Rich Kilgore](https://github.com/rick-kilgore) es la utilización de [SmartComments](http://smartcomments.github.io/) es el siguente: 

1. Se comentan se forma explícita solamente las funciones que son relevantes y se realizan los commit al control de versiones de esa manera.

2. Usando una tarea de [Grunt](http://gruntjs.com/) Se copia todo el código fuente a una carpeta temporal, y se ejecuta [SmartComments](http://smartcomments.github.io/) para generar la metainformación de las funciones que tienen menos relevancia.

3. Luego se ejecuta [YUIDocs](http://yui.github.io/yuidoc/), para generar la documentación API.

Esto ocurre de forma automatizada cada vez que se construye y se despliega el proyecto. La ventaja de esta filosofía de trabajo es que siempre la documentación API está actualizada con los últimos cambios del código fuente. 


Hay que señalar que [SmartComments](http://smartcomments.github.io/) es solo una herramienta, y como herramienta al fin solo puede hacer (por ahora) una parte del proceso. Siempre existen casos complejos que necesitan de la intervención humana. Sobre todo a la hora de querer expresar la verdadera semántica de determinado código.



###Conclusiones

[SmartComments](http://smartcomments.github.io/) puede ser muy útil a la hora de automatizar el proceso de generación de documentación, ahorrándonos horas de esfuerzo, y permitiendo que nuestra documentación siempre esté actualizada con los últimos cambios en el código fuente. Si quieres colaborar con este proyecto open source, puedes hacerlo mediante [github](https://github.com/smartcomments/smartcomments).  
