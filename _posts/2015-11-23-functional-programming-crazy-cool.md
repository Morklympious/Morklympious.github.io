---
id: 26
title: Functional programming, neat!
date: 2015-11-23T18:48:42+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=433
permalink: /functional-programming-crazy-cool/
---
So I decided to source my local library in helping me improve my skills as a developer.

"Functional javascript, That sounds cool." I said to myself.

Little did I know what I was getting into. As it turns out, functional programming is something that's been around for a while ever since [Scheme](https://en.wikipedia.org/wiki/Scheme_(programming_language)) and  [LISP](https://en.wikipedia.org/wiki/Lisp_(programming_language)) were like "Hey. We exist." I suppose I wasn't entirely prepared for it, because the book itself rocked (and continues to rock) my belief in my abilities as a programmer. Not that that's bad, but I've mostly known imperative styles of programming.

<!--more-->

If you're curious, functional programming is a few things:

1. It deals heavily in abstractions, that is, the idea of 'abstracting' a simple task, and eventually using them to build more complex abstractions.

2. It doesn't worry about program state; Every function, when passed a value will perform as if it were doing the calculation for the first time

3. [Higher order functions](http://www.sitepoint.com/higher-order-functions-javascript/) are huge in functional programming! taking in one or more functions as a parameter and returning a new function to use based on those inputs? HUUUUUGE.

3. In my own words, functional programming is strongly about taking data in, and acting on that data until you get what you want.

Functional programming is actually pretty cool! The idea that you can take a microcosm of behavior and abstract it out into a single function is kind of awesome. In fact, if you really want to see it in action, go check out lodash or underscore. Both of which support a functional style and do it freakishly well! If you're anything like me and just read "go check out..." and softly scoffed to yourself, good job, you and I are going to get along after all.

Here's an example.

```js
function isString(string) {
  return typeof string === "string"
}
```

Now we have a function that tells us if something is a string.

```js
isString('Hey') // true;
isString(42) // false;
```

In fact, maybe we want to be able to check on an arbitrary type? In which case let's make a generic function:

```js
isOfType(type, value) {
  return typeof value === type;
}
```

```js
isOfType('string', 'Hey') // True
```

There's actually still an issue here" what if we're passed something that isn't a string? Well, Functional javascript taught me this:

```js
function isOfType(type, value) {
  if(!isString(type)) return;
  return typeof value === type;
}
```

And look at that. I've used a function defined previously to aid me in checking for the proper parameters. You can see that by building a simple `isString()` function, I've abstracted the logic of checking to see if something is a string with an if/else block. With enough abstractions, I can begin to build more robust and complex functions.

I'm not saying that this revolutionary, but it's a little bit of what I've learned, but I'll have to get back to you when I finally start grasping the rest of that entire book.

Happy Coding!
