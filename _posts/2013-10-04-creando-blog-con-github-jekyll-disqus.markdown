---
layout: post
title:  "Creando mi blog con Github Pages, Jekyll y Disqus!"
date:   2013-10-04 23:55:36
categories: github jekyll disqus
---

Durante mucho tiempo he querido escribir algunos artículos referentes a mi experiencia como desarrollador y siempre habían cosas que me lo impedían, exacto la pereza es la principal causa pero no es la única. Cuando buscamos donde publicar nuestros artículos encontramos un sin numero de posibilidades (wordpress, blogger, tumblr, y otros)

## Entonces? Que me detiene?

Principalmente el control, o la falta de control. Claro que puedes crear un blog en cualquiera de esas plataformas, pero en realidad puedes hacer que luzca exactamente como tu quieres? puedes asignarle tu propio nombre de dominio? La respuesta es un rotundo NO. Tu blog termina siendo uno mas del montón entre tantos otros, a menos que cuentes con un presupuesto para poder pagar los costes de personalización.

## Mi Solución

Como buen desarrollador pienso en que un blog no es muy complicado, unos dos o tres modelos apenas (artículos, comentarios, tags), quizás en Rails, Sinatra, Django, Flask; pero vienen otra vez los costos (hosting, base de datos, etc) aunque quizás pueda subirlo a Heroku.

Luego recordé que he encontrado muchas paginas personales e incluso blogs con url como usuario.github.com o usuario.github.io, algunas con el mismo look de github, otras totalmente distintas. Así que me puse a investigar y adivinen! cualquiera con una cuenta en [Github][github] puede hacerlo! Y como se puede crear blog usando Github con [Github Pages][github-pages] y [Jekyll][jekyll-gh].

## Jekyll

Jekyll me gusta porque es bastante sencillo de usar y básicamente tú haces todo el sitio desde cero. Tienes características útiles como sistema de templates, urls y plugins. Y al final todo el sitio es exportado a archivos estáticos, lo cuál creo es la característica más importante ya que te permite servir esos archivos básicamente desde cualquier servidor, como github gratuitamente. Puedes leer la [documentacion de Jekyll][jekyll] para mas información

## Disqus

De esta joya ya había escuchado bastante, ademas muchos sitios importantes manejan sus comentarios usando [Disqus][disqus], por que lo hacen? Bien por que lo único que hay que hacer es crear una cuenta para tu site, agregar un código HTML a tu blog y listo! [Disqus][disqus] se encarga de todo, puedes aceptar comentarios anónimos, exigir que la persona se registre con su información de Twitter, Facebook o Google; moderación de comentarios y mas. Todo esto gratuitamente y sin programar nada.

## El resultado

El resultado lo estas viendo, no se si escriba mas a menudo pero por lo menos lo haré con mas gusto y a mi propio estilo.

[disqus]: http://disqus.com
[github]: https://github.com
[github-pages]: http://pages.github.com/
[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]: http://jekyllrb.com
