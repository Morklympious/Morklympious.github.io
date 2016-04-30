---
id: 20
title: Separate Your Concerns, Prefix Your Nodes!
date: 2015-03-16T07:08:09+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=393
permalink: /separate-your-concerns-prefix-your-nodes/
---
<del></del>

This is going to be a quick post. Again, about javascript/jQuery (WHO COULD HAVE GUESSED?)

However, it's going to deal less with a certain function or facet of js and more with the separation of concerns.

<!--more-->

All code you write, especially as a front end web developer, should have a nice neat separation between form and function. Let's use a terrible analogy: imagine you're folding laundry. You wouldn't put your neatly folded shirts with your neatly folded towels. Or maybe you would? Hell, I don't know you for sure, but what I DO know is that it's probably best to keep shirts and towels separate for simplicity's sake. Think of the mess of pulling out a fresh shirt to realize OH NO IT'S JUST A TOWEL. Guess you're wearing a towel today. Look at your life. Look at your choices.

The same principle of separation applies here for your HTML/CSS/JS.

In the past few months I've been reading up on some good practices, and one I'm particularly fond of is using class 'hooks' specific to Javascript. Let's check out an example or two.

In this first one, I'll hook into Javascript the way I used to. Let's say I have this element:

```html
<div class="container contains-stuff items">
.
.
.
</div>
```

Now, my old habits would designate that I find some identifying feature about this div and hook into it with Javascript (using JQuery for brevity):

```js
$('.contains-stuff').on('click', ... );
```

This works. This works exactly as it should. So what's the problem? The problem is that we're hooking into a class that probably contains CSS properties. If that class changes for any semantic reason (it gets renamed to be more descriptive, perhaps) we lose our function, probably without knowing that we have.

Here's the way I've been doing things. Consider the same element with an added class:

```html
<div class="container contains-stuff items js-function">
.
.
.
</div>
```

I've added a class with a `js-` prefix. This is how I know that a DOM element is used for something functional. It's not used for styling at all, but at a glance of my HTML I can know exactly what has function attached to it. If I want to disable it, all I have to do is modify the class name.

In addition, it helps to name the class something less generic than `js-function`. Give it a name that describes its behavior! If it modifies an element, use `.js-modify-element` or if it changes the color of the text, use something like `.js-change-text`.

There's still some experimenting I'm doing with this, I've created a hybrid approach in adding a `.js` class and hooking into a css class through JQuery like so.

```html
<div class="container contains-stuff items js function">
.
.
.
</div>
```

In this way I'm still free to style the function class because the way that js will hook into it is:

```js
$('.js.function').on('click', ... );
```

Now, I'm not sure if this is optimal, but it feels clean to me. You don't have to do things this way, but it's definitely something to consider.

Happy coding!
