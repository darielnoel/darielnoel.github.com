---
layout: post
title: Buscando un CDN para mi nueva Biblioteca JavaScript.
description: "Buscando un CDN para mi nueva Biblioteca JavaScript"
category: articles
tags: [cdn, biblioteca, javascript, css]
comments: true
share: true
---

Una red de entrega de contenidos (CDN, content delivery network en inglés) es una red superpuesta de computadoras que contienen copias de datos, colocados en varios puntos de una red con el fin de maximizar el ancho de banda para el acceso a los datos de clientes por la red. Un cliente accede a una copia de la información cerca del cliente, en contraposición a todos los clientes que acceden al mismo servidor central, a fin de evitar embudos cerca de ese servidor.[[1]](http://greco.dit.upm.es/~encarna/docs/satelec05.pdf)

A continuación se caracterizan algunos de acuerdo a:

- Requisitos
- Facilidad de uso


- [cdnjs](http://cdnjs.com/) 

	CDNJS es un proyecto creado en 2011 cuyos encargados principales son Ryan Kirkman y Thomas Davis, soportado con la infraestructura de Cloudflare, una empresa que ofrece servicios CDN gratuitos y de pago.[[2]](http://www.univunix.com/tutoriales/cambia-las-librerias-locales-por-las-de-cdnjs) 

	- Requisitos:
		Las bibliotecas deben tener notable popularidad: 100 estrellas o watchers en GitHub es un buen ejemplo, pero siempre y cuando su popularidad sea razonable se añadirán a la Red.[Ver](https://github.com/cdnjs/cdnjs#cdnjs-script-repository)...
	
	- Facilidad de Uso:
		Totalmente integrado con el flujo de trabajo de github. [Ver más](https://github.com/cdnjs/cdnjs#adding-a-new-or-updating-an-existing-library).

- [jsdelivr](http://www.jsdelivr.com/) 

	jsDelivr es un servicio gratuito de “Content Delivery Network” donde los desarrolladores de JavaScript pueden alojar sus archivos, y los usuarios pueden acelerar sus sitios web mediante la descarga de todos sus plugins con JavaScript. Un servicio similar es cdnjs.com, el cual ofrece alojamiento para bibliotecas JavaScript. 

	jsDelivr, por su parte, ofrece alojamiento para elementos JavaScript y jQuery, su infraestructura cuenta con 13 ubicaciones que permitirán acelerar la carga de tu sitio web.[[3]](http://mvkoen.com/cdn-gratuito-de-jsdelivr-para-wordpress/) 

	- Requisitos:
		Si es la primera vez que el proyecto es creado, se debe enviar solamente el archivo minificado.[Ver más](https://github.com/jsdelivr/jsdelivr#how-to-submit-or-update-projects)
	
	- Facilidad de Uso:
		Totalmente integrado con el flujo de trabajo de github. [Ver más](https://github.com/jsdelivr/jsdelivr#how-to-submit-or-update-projects).

- [Cached Commons](http://cachedcommons.org/) 

	Utiliza Github Pages como un CDN!

	NO LONGER SUPPORTED.

Recursos útiles:  

- [CDNperf](http://www.cdnperf.com/)
	Comparación performance de diversos CDN.


