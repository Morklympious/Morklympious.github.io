---
id: 31
title: Prototypes
date: 2016-06-05
author: Bradley Stafford
layout: post
permalink: /prototypes/
---

I could have sworn that I've written about prototypes before this... I'm sure I've included enough information in articles where the prototype WASN'T the focus of my writing to justify feeling that way. You aren't here to tell me whether or not I've actually done that. You're here to READ.

So READ.

Anyways, today we're going to talk about prototypes and how crazy cool they are.

<!--more-->

## The prototype

The prototype. A _crucial_ building block of any javascript code. You're probably wondering what it is, what it does, and why it sounds so _awesome_.

Well, in javascript, the prototype is a construct that allows inheritance and reusability. Every major type in javascript has a prototype. For example, `Object`'s prototype contains methods that are useful or common to operations used to create or interface with objects.

If you come from an Object Oriented background, you can think of the prototype as a 'base class' that instances inherit from.

It's probably easier to just stop reading the garbage being expelled from my brain and look at some of the CODE. Let's say we have a simple object:

```js
var obj = {one: 1, two: 2};
```

Great job! We did it. We made an object. Pat on the back for you. Pat on the back for me. We're legit now. Now check this out:

```js
var obj = {one: 1, two: 2};

obj.toString(); // "{one: 1, two: 2}"
```

We used `Object`'s `toString()` method to return the string version of that object. Where did this method come from? The `prototype`, my friend!

Prototypes are cool because they're a central point of methods across data types. The object up there was able to use `toString()` because it's an object, and every single object 'inherits' the functionality of the `Object` prototype.

I put 'inherits' in quotes because an instance of an object doesn't copy the `toString()` method, it actually delegates up to the prototype. I'll talk more about that later, though.

If you add something to the prototype of a given data type, it becomes available to every object that is an instance of that type. For example:

```js
Object.prototype.toBradley = function() {
  return "Bradley";
}

var object = {};

object.toBradley(); // "Bradley"
```

You'll notice thatI was able to use the `toBradley()` function immediately with no other fuss or configuration.

The important part here is __Any function or property added to a prototype becomes immediately accessible to all objects of that type__.

## Why Does this Work?

Good question! Why _does_ this work? Is this some wizardry? Some warlockery? Let's find out!

So, there's this concept in javascript called the 'prototype chain', and it's a large part of the way that javascript executes methods. Let's look at another object example to get an idea:

```js
var obj = {
  value: 777,
  get: function() {
    return this.value;
  }
  set: function(value) {
    this.value = value
  }
}

obj.value // => 777
obj.get() // => 777
obj.set(888);
obj.get() // => 888
```

Here we have a basic object with a few properties and methods. `value`, which is just a value that it holds, as well as `get` and `set`, which are functions responsible for changing or retrieving that value. What happens when you call something that isn't on your object? Let's lay out our current prototype chain:

```
obj (you are here) -- has this prototype --> Object.prototype
```

Remember when we defined that _super good-looking  and also jaw-droppingly impressive_ `.toBradley()` method on the `Object` prototype? Let's trace what happens if we call `obj.toBradley()`

The instant `obj.toBradley()` is called, javascript looks inside of `obj` to see if there's a method called `toBradley()`. As you can see, we didn't define `toBradley()` here. So javascript __then__ looks at the next thing in the prototype chain, which happens to be the `Object` prototype itself!

So now we're here:

```
obj -- has this prototype --> Object.prototype (you are here)
```

Since we defined `toBradley()` on the prototype earlier, javascript sees that its defined and _actually_ takes that function and uses it in the context of our current object (`obj`). As I said earlier, prototypes give types a baseline of functionality. Through the magic of delegating up the prototype chain, if something isn't found at the current level, javascript will look for your property or function at every 'level' until it runs out of those 'levels'.

## Overriding!

You see what happens when we don't have the thing we're trying to access available on the object we're calling it on, javascript either:

- a) goes one level up the prototype chain until it finds it, or
- b) runs out of objects in the prototype chain, at which point you get an error that it doesn't exist.

We can use this delegation system to override behaviors! Let's revise our object example.


```js
var obj = {
  value: 777,
  get: function() {
    return this.value;
  }
  set: function(value) {
    this.value = value
  },
  toBradley: function() {
    return "Bradley Sucks"
  }
}


obj.value // => 777
obj.get() // => 777
obj.set(888);
obj.get() // => 888
obj.toBradley() // => "Bradley Sucks"
```

We've added a `toBradley()` method to this object, which actually is used first! Again, the reason for this is that javascript finds __exactly what its looking for at the current 'level'__, so it doesn't need to travel up the prototype chain, allowing you to 'override' the prototype for this specific method.

## All in all

The prototype is incredibly powerful. It can make your life easier, it can also set everything you know and love on fire until all of your code turns into a messy spaghetti inferno. What's important in this case is knowing what's happening behind the scenes when you're messin' with the prototype

This is really just scratching the surface, a custom class can have a prototype chain that's any number of objects long, it can get incredibly sophisticated, but I hope this gave you a super rudimentary look at what's actually happening out there!

Happy coding!
