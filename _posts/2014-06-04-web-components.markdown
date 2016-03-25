---
layout: post
title: "Web Components"
date: 2014-06-04 16:30:00 -0500
comments: true
categories:
---

Probably by now, you have heard of Web Components. Web Components are comprised
of four different specifications (
[Custom Elements](http://www.polymer-project.org/platform/custom-elements.html),
[Templates](http://www.polymer-project.org/docs/polymer/template.html),
[Shadow DOM](http://www.polymer-project.org/platform/shadow-dom.html) and
[HTML imports](http://www.polymer-project.org/platform/html-imports.html)). It's
a neat placed package of web technologies.

The goal of Web Components, is to organize and standardize best practices for web
technologies. We all have seen or experienced how polluted a project can get when we
start adding dependencies to it.

A Web Component is meant to keep things organized, to not conflict with the existing
DOM and reduce the amount spent learning the code or API.

Some ideas of where Web Components would work:

* Photo Carousel - `<photo-carousel src="['pic1.jpg', 'pic2.jpg']"></photo-carousel>`
* Twitter Profile Card - `<twitter-profile-card user="omar12" tweets="5"></twitter-profile-card>`
* Stripe Payment Form - `<stripe-payment id="12345"></stripe-payment>`
* Disqus Comments - `<disqus-comments short_name="awesomeblog"></disqus-comments>`
* Video Player - `<my-video-player src="/path-to-video/videofile.mp4"></my-video-player>`

SaaS companies can provide inhouse Web Components to their customers and have it
running in no time.

In "Old HTML" terms, a Web Component is a JavaScript plugin on an iframe. We know
that even has its limitations and it feels wrong in some way. But please, don't
think of them like that.

### How to work with Web Components using Polymer

1.Download Polymer

We will download Polymer using Bower. If you haven't heard of Bower, it's basically
a package manager for project dependencies. Find out more about Bower [here](http://bower.io/).

```bash
bower init
bower install --save Polymer/platform
bower install --save Polymer/polymer
```

Read more about the installation [here](http://www.polymer-project.org/docs/start/getting-the-code.html).

2.We add the following in the `<head>` of where you will include your Web Component.

{% highlight html %}
<head>
  <!-- 1. Import the Web Components Polyfill -->
  <script src="bower_components/platform/platform.js"></script>

  <!-- 2. Import the Custom Elements-->
  <link rel="import" href="web-components/my-cool-element.html">
</head>
{% endhighlight %}

The 2 things to notice, is that we need to include the Polymer Polyfill.

3.Build your Polymer element.

Create an html file in the **web-component** folder.

{% highlight html %}
<!-- Import Polymer -->
<link rel="import" href="../bower_components/polymer/polymer.html">

<!-- Define your custom element -->
<polymer-element name="my-cool-element" noscript>
    <template>
        <h3>My Cool Element</h3>
    </template>

</polymer-element>
{% endhighlight %}

You can include Custom Elements on other Custom Elements (cue Xhibit meme).

{% highlight html %}
<!-- Import Polymer -->
<link rel="import" href="../bower_components/polymer/polymer.html">
<link rel="import" href="my-cool-element.html">

<!-- Define your custom element -->
<polymer-element name="my-cool-element" noscript>
    <template>
        <h1>Super Cool Element!</h1>
        <my-cool-element></my-cool-element>
    </template>

</polymer-element>
{% endhighlight %}

Of course, the above is not a practical example, but something to manipulate or
read data.

Right now, Web Components are [partially supported](http://jonrimmer.github.io/are-we-componentized-yet/)
on Chrome/Opera (Blink) and Firefox. No support on Safari or IE.

Keep an eye on it, Google and Mozilla are spending good amounts of
energy behind Web Components, we can only hope more adoption of the technologies.

### More Reading and Resources
* <http://webcomponents.org/>
* <http://webcomponents.org/articles/web-components-best-practices/>
* <http://www.polymer-project.org/>
* <http://component.kitchen/>
