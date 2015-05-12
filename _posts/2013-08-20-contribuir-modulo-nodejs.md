---
layout: post
title: ¿Como contribuir con el desarrollo de un módulo de Node.js usando github?
description: "Como contribuir con el desarrollo de un módulo de Node.js usando github."
category: articles
tags: [node.js, módulo, git, github, linux, npm]
comments: true
share: true
---

Se asume que se tienen conocimientos básicos de [git](http://es.wikipedia.org/wiki/Git), [github](https://github.com/), [Node.js](http://nodejs.org/), [Sistemas basados en UNIX](http://es.wikipedia.org/wiki/Unix.)


Tomaremos como ejemplo el módulo [YUIDocs](http://yui.github.io/yuidoc/) el cuál nos permite la generación de documentación automática. Este módulo puede ser instalado mediante el comando:

{% highlight bash %}
npm install -g yuidocjs
{% endhighlight %}

De esta estamos instalando [YUIDocs](http://yui.github.io/yuidoc/) de manera global en nuestra PC. 

{% highlight bash %}
/usr/local/lib/node_modules 
{% endhighlight %}


En **node_modules** podemos ver todos los módulos de **Node.js** que han sido instalados hasta el momento, y ahora también [YUIDocs](http://yui.github.io/yuidoc/) (yuidoc).

También se habrá creado un link simbólico que apunta al fichero definido por el módulo como su ejecutable:

{% highlight bash %}
/usr/local/bin
{% endhighlight %}


Si se quiere saber qué fichero es el que se ha definido como ejecutable de un módulo abrimos el fichero **package.json** que se encuentra en la raíz del módulo y buscamos la sentencia: 


{% highlight json %}
“bin”:  {“yuidoc ” :  ”./lib/cli.js”} 
{% endhighlight %}

en este caso, la misma le indica a npm que debe crear un link simbólico cuyo nombre es “yuidoc ” y que el mismo va a apuntar al fichero ”./lib/cli.js” .


Buscamos en github el repositorio de desarrollo del módulo, y le hacemos fork.

<figure>
	<a href="/images/2013-08-20-contribuir-modulo-nodejs/yuidocs-fork.png"><img src="/images/2013-08-20-contribuir-modulo-nodejs/yuidocs-fork.png"></a>
</figure>

Clonamos nuestro fork en nuestra carpeta local,

{% highlight bash %}
git clone git@github.com:yui/yuidoc.git
{% endhighlight %}


Agregamos un remote del repositorio original para estar sincronizados con las actualizaciones que se le hagan al módulo por parte de sus desarrolladores.

{% highlight bash %}
git remote add upstream git://github.com/darielnoel/yuidoc.git
{% endhighlight %}


Sincronizamos el módulo con la última versión.

{% highlight bash %}
git pull upstream master
{% endhighlight %}


El anterior proceso se encuentra muy bien explicado en el [sitio oficial de YUI3](http://yuilibrary.com/yui/docs/tutorials/contribute/).

Bueno hasta aquí ya tenemos el módulo, en nuestra PC, sincronizado con los últimos cambios hechos al mismo por sus desarrolladores, y pudiéramos empezar a modificarlo. Una práctica recomendable es crear una nueva rama para cada nueva funcionalidad, y trabajar en ella por ejemplo:

{% highlight bash %}
git checkout -b funcionalidadX upstream/master
{% endhighlight %}

Esto nos da la posibilidad de que si llegamos a un punto en el que queremos ir a la versión original simplemente nos cambiamos a la rama master y listo.

{% highlight bash %}
git checkout master
{% endhighlight %}

**¿Cómo probar que nuestros cambios funcionan realmente como esperamos?**

Suponiendo que estemos en la raíz de la carpeta que contiene el módulo que descargamos para que se instalen localmente las dependencias del módulo hacemos:

{% highlight bash %}
npm install .
{% endhighlight %}

Luego creamos un link simbólico del fichero descrito en package.json como el bin, en nuestro ejemplo **lib/cli.js**.

{% highlight bash %}
ln -s /rutaAlModuloQueClonaste/bin/cli.js usr/local/bin/yuidoc
{% endhighlight %} 

De esta manera ejecutará el módulo nuestro y no el módulo que se ha instalado globalmente
cuando hagamos:

{% highlight bash %}
yuidoc --help
{% endhighlight %}
