---
id: 10
title: 'Chatbox Sorcery: A Nifty Trick'
date: 2014-06-05T21:03:24+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=305
permalink: /chatbox-sorcery-nifty-trick/
---
A while ago I was asked a tricky HTML and CSS question that left me stumped even though I know I had seen the [answer a thousand times on various websites.](http://css-tricks.com/snippets/css/css-triangle/)"

_How do you make a chat style box using a single div?_

<!--more-->

```html
<div class=”chat”></div>
```

That is, a ‘chat style box’ being a box with a triangle on it to denote that someone is talking, much like something you’d see in an iPhone text message conversation or something of that nature. The question left me stumped, and it wasn’t even that big of a deal that I couldn’t get it, some of these CSS-based tricks just come with time, but here’s the skinny:

CSS will allow you to use a thing called [pseudo elements.](http://www.w3schools.com/css/css_pseudo_elements.asp) These are elements that ‘exist’ before and after any element you can target with a CSS selector. Which means if you wanna do some crazy stuff, then you GO AHEAD AND DO SOME CRAZY STUFF. One of the crazy things is the chatbox. The pseudo elements you can use to achieve this effect are `:before` and `:after`. You only need one of them to achieve the triangle.

Essentially the way that it works is you use the pseudo element to style a box that has borders on three sides. What you want to do is give every side except for the pointer side a thick border. Something like `10px solid`  will do. Now, you’ll want to give each side perpendicular to the pointer side a transparent color, making `10px solid transparent` will achieve this. As for the side opposite of your desired pointer, you need to establish the color, and it’ll give you a triangle of the color you specify.

The triangle won’t show up unless you actually specify the pseudo element to have content. Otherwise it just doesn’t show up.

`content: '';`  is the way to achieve this, it’ll insert nothing and give the element its background and border properties.

All in all, it’s a really neat trick, and it’s incredibly useful if you’re trying to achieve website performance because you’ve just saved the DOM a tag that it would otherwise have to load. Good for you! Good for me! GOOD FOR EVERYONE.

I’ve attached a JSFiddle so you can better see what’s going on here!

Happy coding!

[More Pseudo-element stuff](http://css-tricks.com/pseudo-element-roundup/)
