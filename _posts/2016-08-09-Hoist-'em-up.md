---
id: 33
title: Hoist 'em up
date: 2016-08-09
author: Bradley Stafford
layout: post
permalink: /hoist-em-up/
---

Let's have a quick chat about hoisting in javascript.

When I say hoisting, I'm talkin' about pullin' yourself up by your bootstraps and DOING SOMETHING WITH YOUR LIFE. Focus on your craft! JUST FOCUS ON YOUR CRAFT!
And then when you're done doing that, let's have a quick chat about hoisting in javascript

So, this is an interesting question in that when I was interviewing last year for various web developer positions, I was asked this question a few times despite getting pretty far in my career without hearing about it.

Now, it was fortunate that by reading a few archaic books on web development in my spare time, I managed to pick up the concept of function hoisting. Let's have a look.

<!--more-->

## Functions and Hoisting

```js
// Ways to define functions

function dopeness() {
  return 5;
}

var dopest = function() {

}
```

These are two of many ways that you could define a function in javascript. the first definition is called a function definition. The second is called a function expression.

__Function declarations in javascript are hoisted__  

This means when you define a function this way, you can safely assume that regardless of where it's placed in your file, it's available at the top of the current scope.

```js
dopeness(); // => 5

function dopeness() {
  return 5;
}
```
This code works _because_ hoisting occurs. Before any of this runs, you can imagine javascript taking the entirety of `dopeness` and placing it at the top of the file (well above the point where we call it.)

What about function expressions though?

Well, function expressions are slightly different, and they're handled differently too. Let's try doing the same thing we did with declarations:

```js
dopest(); // => ReferenceError, dopest is not defined.

var dopest = function() {
  return 5;
}
```

Notice that calling the function before it's written causes an error. The difference is that this is a function _expression_, meaning it's dynamically interpreted at runtime.

Yeah, that's right, _declaring_ a function (e.g. `function fn() {}`) allows javascript engines to index those functions so they're able to be used anywhere in the scope they're defined in (regardless of where they're defined in that scope). Conversely, _expressing_ a function (e.g. `var fn = function() {}`) means that it only becomes available after the `var` is evaluated to be a function.

__function expressions (e.g. functions defined with `var`) are not hoisted__

## Variable hoisting

There is another kind of hoisting, and it's variable hoisting. I know you might be thinking "Well, variables can't be hoisted because function expressions, which are declared using `var`, aren't hoisted."

And you're right, function expressions __aren't__ hoisted, but we're talking about the variable you use to define that function, not the function itself.

When you define a variable somewhere in your program flow, it's actually hoisted to the top. Meaning it's __declared__, but not __defined__. This is another static analysis thing that javascript takes care of: it runs through each scope and builds a table of variables that are declared in the scope so they can be referenced anywhere in that scope.

Let's say you define a function like so:

```js
function variables() {

  return [a, b, c];

  var a = 1;
  var b = 2;
  var c = 3;

}

variables(); // => [undefined, undefined, undefined]
```

You would probably think we'd error out because we're referencing variables that we haven't defined yet, but instead we're getting a return statement of three undefined array members.

__This is because variables `a`, `b`, and `c` were hoisted.__

Let's take that code and see what the function looks like with hoisted variables.

```js
function variables() {
   // This is what hoisting does. it declares (but does not assign) the
  // variables you've defined in your scope.
  var a, b, c;

  return [a, b, c];

  var a = 1;
  var b = 2;
  var c = 3;

}

variables(); // => [undefined, undefined, undefined]
```

You see that each variable defined in the `variables` function is defined at the top. It's actually kind of nutty that javascript does that automatically, but it's also one more thing to be aware of when you see a variable being assigned without being defined.

## Conclusion

In general, I like to define my variables where I choose to define them with `var`, I'm not the biggest fan of letting other developers interpret that I'm using variable hoisting, so I prefer to reference variables after I explicitly define and/or assign them.
Make the best call for your projects! Pull up those suspenders! HOIST.

Happy coding!
