---
layout: post
title: "Working with Flex"
date: 2014-06-01 20:40:22 -0500
categories:
excerpt: Flexbox (or flex layout) is a CSS box model optimized for user interface design.
---

Flexbox (or flex layout) is a CSS box model optimized for user interface design.
The child elements of a flex container have greater "flexibility" on how it is
laid out on an HTML page. This means that it provides a simpler and more powerful
tool for distributing space and aligning content for complex (or simple) layouts
in web apps or web pages.

Using Flexbox can get your Responsive website layout working as intended.

Below is the barebones to get Flexbox going. The example is keeping the "Mobile First"
approach.

[**View Demo**](http://codepen.io/Omar12/full/itDzI/)

### The following is a barebones example of the HTML:
{% highlight html %}
<div class="flex--products">
  <div class="product">Product 1</div>
  <div class="product">Product 2</div>
  <div class="product">Product 3</div>
  <div class="product">Product 4</div>
</div>
{% endhighlight %}

First we define `display: flex` to the parent element that we want to hold the
elements that will flex.
{% highlight css %}
.flex--products {
  display: flex;
  flex-direction: row;
}
{% endhighlight %}

`flex-direction: row` will place each child element on its own row.

For wider viewports, we will switch the elements to be in its each column.

{% highlight scss %}
@media screen and (max-width: 46rem) {
  .flex--products {
    flex-direction: column;
  }
}
{% endhighlight %}

For the child elements, we define a `flex: auto`. `flex: auto` will automatically
adjust the widths of the adjacent elements.

{% highlight scss %}
.product {
  flex: auto;
  padding: 1rem;
  margin: .1rem;
  background: $product-color;
}
{% endhighlight %}

Full SCSS:

{% highlight scss %}
$midnight-blue: #2c3e50;
$belize-blue: #2980b9;
$white: #fff;

$bg-color: $midnight-blue;
$product-color: $belize-blue;

body {
  background: $bg-color;
  color: $white;
  padding: .5rem;
}

.flex--products {
  display: flex;
  flex-direction: row;
}

.product {
  flex: auto;
  padding: 1rem;
  margin: .1rem;
  background: $product-color;
}

@media screen and (max-width: 46rem) {
  .flex--products {
    flex-direction: column;
  }
}
{% endhighlight %}

### Below you will find more Flexbox resources:

**Reading**

* [CSS Tricks: A Guide To Flexbox](http://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [Smashing Magazine: Centering Elements with Flexbox](http://coding.smashingmagazine.com/2013/05/22/centering-elements-with-flexbox/)

**Code**

* [The Ultimate Flexbox Cheat Sheet](http://www.sketchingwithcss.com/samplechapter/cheatsheet.html)
* [Phillip Walton: Solved by Flexbox](http://philipwalton.github.io/solved-by-flexbox/)

**Sandboxes**

* [flexexplorer](http://bennettfeely.com/flexplorer/)
* [Flexy Boxes](http://the-echoplex.net/flexyboxes/)

**Technical**

* [W3C Flexible Box Layout Module](http://www.w3.org/TR/css3-flexbox/)
* [Flexbox layout isn't slow](http://updates.html5rocks.com/2013/10/Flexbox-layout-isn-t-slow)
* [Can I Use.com](http://caniuse.com/flexbox)
