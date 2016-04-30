---
id: 18
title: Namespacing Your Javascript
date: 2014-12-21T19:51:58+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=379
permalink: /namespacing-javascript/
---
I'm sorry you guys have to deal with me doting heavily on javascript these past few posts, but I've got to say that there's a lot to learn and I'm having fun just dealing with all of the unique challenges that coding in javascript gives me.

This post is going to be relatively short! but I know that I haven't written in a while so I thought I would talk really quick about javascript namespacing.

<!--more-->

In javascript, you have an object called 'window', and the window is basically your browser. it holds all the data about the website you're viewing at that moment in time. Now, when you code something up in js, unless you know what you're doing, you're probably going to end up with code that attaches itself to the window (also known as the 'global' namespace).

Will your code work? Absolutely.

But the idea behind namespacing is giving a central point through which all of your website or application's functionality can be funnelled. Since I coded this website when I was still a js novice, I'm sure I've placed a lot of variables and functions inside the global context.

So let's go ahead and take a look here, if the window variable is stored as a reference to the current browser window, and it's accessible in javascript by that variable, you bet we can add more properties to that object. In fact, if you ran a console.log on the window object, you'd probably be pretty surprised at the ridiculous amount of stuff just attached to this object. Let's make a namespace.

```js
window.codeAndComedy = {};
```

Boom. Namespaced. What I did there was define a property on the window object, and the value assigned to this new property is an empty object. Nested objects are great, aren't they? Let's say I wanted to define a function in this namespace that alerted users they reached my site (which, in honesty, is really obnoxious).

```js
window.codeAndComedy = {
   function youMadeIt() {
      alert("You made it!");
   }
}
```

Now you might think that I call this just by it's simple function signature:

`youMadeIt(); // This will do nothing`

The reason it will do nothing is because this function lives and dies in the namespace I've created

```js
window.codeAndComedy.youMadeIt(); // Alerts "You made it!"
```

Why is this cool? Why do you care? Well it's pretty simple, namespacing your code like this means you'll probably never run into horrifying conflicts with other libraries. You know how Prototypejs and JQuery both use the dollar sign as their alias? You can see why it's pretty important to specify a 'section' in which code can be accessed and run.

This also allows you to break up code into more manageable chunks. the beauty of the window object (and honestly any object in javascript) is that infinite object nesting is possible!

Maybe you don't want to type `window.codeAndComedy` to get to your stuff? That's a quick fix.

```js
var utilities = window.codeAndComedy; // alias it to another variable

utilities.youMadeIt(); // Call the function with a shorter signature.
```

All of the code that you place in this space is completely out of the global scope. Saving you headaches down the road when libraries are being used in full force. Namespacing, I've learned, is an important tool when you want to write a lot of code, and you also want to make sure that that code isn't going to conflict with itself or other libraries in that moment as well as going forward.

YOUR PARENTS GAVE YOU A NAME. GIVE YOUR CODE A NAME(space).
