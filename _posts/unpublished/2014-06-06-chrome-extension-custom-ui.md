---
layout: post
title: Interfaz de Usuario Personalizada para una extensión de Google Chrome.
description: "Interfaz de Usuario Personalizada para una extensión de Google Chrome"
category: articles
tags: [google chrome, extensión, interfaz de usuario]
comments: true
share: true
---

##Why use iframes, then?

Well, iframes are the only way (currently) to isolate a chunk of Javascript, CSS and HTML without being influenced by the current web page style and behavior.

Also, I was stubborn enough to think there was probably a way to communicate between all the layers in a graceful manner. Even though I could not find an answer on Google or StackOverflow.

##The problem

Yo quiero una interfaz de usuario personalizada, no solo el popup que nos dan los muchachos de chrome, iframes are the only way (currently) to isolate a chunk of Javascript, CSS and HTML without being influenced by the current web page style and behavior.

In fact, the problem resided with the use of iframes. I had to send lots of data through JSON objects from the Background layer to any of the iframes and vice versa. Manipulating an iframe is not possible from the Content Script injected in the page, because of the cross-domain restriction.

For example, the page URL currently viewed is

http://www.example.com

and the injected iframe URLs are

chrome-extensions://uniqueidmadeoutoflotsandlotsofletters

Communication between both is impossible because cross-domain communication is a big NO-NO.


##What’s the solution?




<figure>
	<a href="http://anijs.github.io/examples/scrollreveal/"><img src="/images/2014-05-31-scrollreveal-anijs-demo/scrollreveal.png"></a>
</figure>

En el ejemplo se puede encontrar buena [documentación](http://anijs.github.io/examples/scrollreveal/), y el [código fuente](http://anijs.github.io/examples/scrollreveal/).

##Ventajas

- Menos de 10kb.
- No es necesario usar JQuery ni otras bibliotecas de terceros.
- Sintaxis declarativa.
- Funciona correctamente en Iphone, Ipad y Android.

Si tienes algún ejemplo o estás usando AniJS en tu sitio o aplicación y quieres incluirlo en la página oficial de AniJS por favor [contáctame](https://twitter.com/dariel_noel), me daría gran placer ayudarte a compartir tu trabajo con la comunidad.
