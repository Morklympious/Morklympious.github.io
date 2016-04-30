---
id: 24
title: 'Dependency Injection: What?'
date: 2015-09-02T20:52:35+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=419
permalink: /dependency-injection-what/
---
Dependency Injection. What is it? Why does it sound so cool?

Dependency injection is, in its simplest form, giving an object its instance variables. It means that when a given piece of code runs, it already has all the stuff it needs to do its job. Libraries like AngularJS use it, you can use the `require` call in Node.js to supply dependencies at runtime, there are a bunch of different technologies that allow you to inject dependencies.

But why, though? What makes it so good? Well, I'm glad you asked.

<!--more-->

Dependency injection is a technique that deals with inversion of control, where removal of dependencies gives greater options for your code. Provided the right interface, your code can choose which dependency to use, so long as the interface is kept the same.

In addition, dependency injection makes it possible to develop highly cohesive, lowly coupled code. If you had a library that was supplied to a chunk of code in your program, you could completely change that library you supply, so long as it has the same interface as the previous one. It will allow you to run your handwritten code in isolation, without having to look at the external library (as it would if you supplied the dependency inside your chunk of code.)

Let's look at a human example of dependency injection:

You're sick and dying in your bed, and you want something to drink. So, after a mosey and shuffle to the fridge, you grab some orange juice. but unfortunately you knock over the milk, you spill the iced tea. The water filter is off and it's all because you WENT ROGUE. YOU DID THIS. THIS IS ALL YOUR FAULT. NOW OUR FRIDGE WILL NEVER BE THE SAME.

This is a human example, WITHOUT dependency injection. Here, the object or method is looking to create the dependency (which is supplying a beverage) internally (or rather, on their own.)

To turn this horrible fridge fiasco into a successful scenario, let's utilize dependency injection.

You're sick and dying in your bed, and you want something to drink. So, you call to your parents and say 'I would like a drink from the fridge, please.' And now, your parents, ostensibly ANOTHER piece of code, will supply you with your dependency when you need it. Which is immediately. Get well soon.

In that scenario, you're the code that requires something. And your parents are the code that handle beverage acquisition. By calling to them, you've introduced the injection of the dependency on your parents. The drink is the dependency.

And you know what? you don't CARE how they get the drink from the fridge into your hands, you just care that the drink magically makes it from the fridge to you. Your parents could run a marathon all over town, gallon of Sunny Delight in hand, and THEN give it to you. YOU. DON'T. CARE. This frees you up to think about optimizing your channel surfing technique, or the easiest way to blow your nose while eating breakfast, who knows? The point is you're not trying to do something that you (a chunk of code) are not originally meant for (in this extremely limiting scenario)

I know, I've probably made this more complicated than I need to. But you can already see that, as a sick person, the need for something to drink is satisfied, and you never had to muck around in the fridge. Meaning the code that is YOU is kept clean and understandable (or snotty and bedridden.)

Other examples include:

'I want a million dollars by monday. I don't care HOW you get it. Just have it on my desk.' Dependency: A million dollars

'The only thing that keeps me going anymore is the coffee that work provides us.' Dependency: Coffee

The code example of this can be seen in a typical module pattern. Let's say I have two modules, one that has an object containing references to DOM nodes, and the other that attaches event behavior to those nodes.

```js
window.nodes = window.nodes || (function() {
  return {
    lists: document.getElementsByTagName('ul')
  }
}())

window.behavior = window.behavior || (function (nodes) {
 /* This contains logic that deals with the nodes. I can access the nodes since I passed them as a parameter. This is basic dependency injection. */

 // nodes.lists is an accessible property here now.
}(window.nodes))
```

Dependency injection is useful for a number of reasons, chief of which is that it makes your code easier to build, extend, test, and maintain. Starting early with it means you'll have an application that can scale beyond your wildest dreams... WHAT A TIME TO BE ALIVE.

Happy Coding!
