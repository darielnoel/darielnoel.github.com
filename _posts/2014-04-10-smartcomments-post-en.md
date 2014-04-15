---
layout: post
title: SmartComments, your project documentation always up to date.
description: "SmartComments, your project documentation always up to date"
category: articles
tags: [automatically comments, javascript]
comments: true
share: false
---
###Abstract

[SmartComments](http://smartcomments.github.io/) is a module for NodeJS that can be useful to automate documentation generation process, Using it you can save time and effort, allowing that your documentation can be always up to date with last source code updates.


###Introduction

According to studies carried out by a very prestigious agency, more than 40 per cent of developers prefer to document code than to write code. What?

My first reaction was think, May be possible that the world is changing so fast? Then, Why hadn't I noticed it until now? I asked to other team developers, and They told me that they were totally agreed.

For me always was very boring add the formal documentation to the source code made by me. Particularly those functions which when you read the name, you can know all about that. Also hated, update the documentation with every change in the source code. 

Why could not I enjoy that, when other developers could? I escaped from this dilemma when I heard my teammates laughing. OMG, It was just a sick joke...
 
---

###Body

Some tools like [YUIDocs](http://yui.github.io/yuidoc/), [JSDocs](http://usejsdoc.org/) and [others](http://www.lsauer.com/2013/05/javascript-documentation-generator.html) are used by many developers to generate his projects's documentation.

These tools need some input parameters, which should be written [explicitly](http://metajack.wordpress.com/2008/07/01/the-state-of-javascript-documentation-tools/) by the developers. For example:

{% highlight javascript %}
/**
 * Description
 * @method Function Name's
 * @param Param A
 * @param Param B
 * @return Return value
 */
{% endhighlight %} 

It's a tedious process, especially taking into account that when some change is made in a source code related with some of these parameters, We must update the related documentation. It becomes more significant, when we deal with well advanced projects, which have a poor documentation.

According to the [@evangoer](https://twitter.com/evangoer) in the conference ["Thinking of Documentation as Code"](http://www.youtube.com/watch?v=mEvvc80ZYU8), when documenting the source code, it is useful to think about three questions.

- What does the code do?
- How does it do it?
- Why does it do it?

[SmartComments](http://smartcomments.github.io/), is an open source tool
written in JavaScript. Which can run under [Node.js](http://nodejs.org/).
Using it you can automate the documentation generation process, resulting very beneficial in accelerating this process. [SmartComments](http://smartcomments.github.io/) can help us to generate things related to (What and How) questions.
On the figure below you can see the portions of the previous example that can be generated using [SmartComments](http://smartcomments.github.io/).  


{% highlight javascript %}
/**
 * Description
 * [@method Function_name] ---------- SmartComments
 * [@param Param_A] ----------------- SmartComments
 * [@param Param_B] ----------------- SmartComments
 * [@return Return_value] ----------- SmartComments
 */
{% endhighlight %}

Basically, we only should to put our function description, or any other detailed explanation if necessary.

Some [SmartComments](http://smartcomments.github.io/) features are:

 - Generate the necessary meta-information, to entire files, individually or inside some specific folder. 

 - [Sublime Text Plugin](http://smartcomments.github.io/#features), which give us access to the application from this editor. A useful feature of this plugin is to generate comments to a text selection.

 - Templates customization to add other tags dynamically to the comments. Like @event, @class, @attribute and others. Acording to the framework used by you, or your personal code style.

 - Online version demo that can be used for meta-information generation without installing the application.

A real use case raised by [Mr. Rich Kilgore](https://github.com/rick-kilgore) is 
this:

1.  I've set it up so that we put our minimal comments in the sources and commit them into source control that way.

2. Then, in our Gruntfile, to generate the docs I copy all the sources to a working dir, run smartcomments on them.

3. Finally run [YUIDocs](http://yui.github.io/yuidoc/) to generate the docs.

This happens every time we build and deploy our project. The main advantage of this aproach is that the API documentation is always up to date with the last changes in the source code.

It should be noted, however, that [SmartComments](http://smartcomments.github.io/)is just a tool. There are always some situations that need the human intervention. Particulary when we need to express the true meaning of the code.

---

###Conclusions

[SmartComments](http://smartcomments.github.io/) is useful to automate the documents generation process, Using it you can save time and effort, allowing that your documentation can be always up to date, with last source code updates. If do you want to collaborate with this open source project you can find out at [github](https://github.com/smartcomments/smartcomments).
