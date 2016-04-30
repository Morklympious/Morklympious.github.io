---
id: 8
title: 'Notes: JQuery and Javascript Equivalents'
date: 2014-05-10T20:22:59+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=291
permalink: /notes-jquery-javascript-equivalents/
---

So I've been getting a lot more into working with a hybridized javascript and JQuery coding syntax. Which is problematic because it means that I'm not quite there in terms of being independent of JQuery entirely, but I decided to post a (hopefully growing reference) that may help both you and I in working on developing native javascript skills.

<!--more-->

In a lot of cases, using vanilla javascript can speed up the execution time of your scripts by an unbelievable amount. JQuery makes things a lot easier to manage, and by all means, it's powerful. However, for simple things (a lot of what I like to do, actually) javascript in its raw form probably suits the situation best. A lot of what I'm finding out about these equivalents comes from attempting to convert my Extension Against Humanity driver script into native javascript.

Anyways, onto my notes!

## Selection
Selection refers to selection elements in the HTML by ID, class, or tag name.

__jQuery__
```javascript
$('#id');
$('.class');
$('h1');
```
__javascript__
```js
document.getElementById('id');
document.getElementsByClassName('class');
document.getElementsByTagName('tag');
document.querySelector('#id'/'.class'/'tag'); // This is as close to a JQuery selector as you really get. It's also a very heavy call.
```

Simple hide/show Manipulation
I say 'simple' because any robust or involved animations for elements might generally want to use a very mature library like JQuery or Scriptaculous.

__jQuery__
```js
$('element/id/class').show() // Show accepts parameters, but this is a very basic usage
$('element/id/class').hide() // Hide also accepts parameters, but again, basic usage
```
__javascript__
```js
document.getElementById('id').css('display','block')
document.getElementById('id').css('display','none')
```

Alternatives for the CSS like ('visibility', 'hidden') and ('visibility','visible') work as well if you'd like to just hide the element but retain the space it took up.

Properties of HTML elements
This is a simple list so far, because I've only interacted with the text inside an HTML element through javascript.

JQuery
```js
$(element/id/class).text // Will select the text inside this HTML node.
```

__javascript__
```js
document.getElementById('id').textContent
document.getElementById('id').innerText // Old IE way of doing things.
```

Innertext is given as well because it's an old way that internet explorer used to handle grabbing the contained text of an HTML element.

Hopefully this list will grow so that I can reference it in the future, but I wanted to make sure I wrote these down in order to solidify them in my head.

__Note from 2016 Brad:__ A site that does a similar thing actually exists! It's called [You Might Not Need jQuery](http://youmightnotneedjquery.com)

Thanks for reading!
