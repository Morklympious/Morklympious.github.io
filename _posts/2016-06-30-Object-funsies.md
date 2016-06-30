---
id: 32
title: Object Funsies
date: 2016-06-30
author: Bradley Stafford
layout: post
permalink: /object-funsies/
---

Objects are a fun data structure in javascript. Well, I guess if your definition of "fun" is creating a dictionary and then accessing that dictionary every time you need to know something.

Fun, right?

You bet your ass it's fun.

There was a time when I thought that objects were just these simple data structures that held two things: a key and a value.

```js
var object = {
  key: 'value'
};
```

It was great! I knew that if I needed a hash map, a dictionary, or a structure that I'd be using to look stuff up, I'd use an object. They were so simple! So brilliant!

<!--more-->

They're still brilliant, but over time I found out that they could get as complex as you wanted them. The object primitive, `{}`, is what most javascripters use when they need an object. There's also `Object.create`

## Some `Object.create` magic

```js
var object = {
  key: 'value'
};

var obj = Object.create(null);
```

The difference between these two is that the former has a prototype, which is `Object`. The latter, however, has __no__ prototype. `Object.create` accepts a parameter that can either be an object, or `null`, and it uses that object to define the created object's prototype (instead of the default `Object` prototype). If it's `null`, the object is literally created with no prototype, meaning it's a truly naked POJO (plain ol' javascript object).

Object creation became more interesting to me at that point. Amazing that an object could be created completely clean and free of prototypes.

It gets even better. Objects can have a prototype that's completely configurable.

### Configurable properties with `Object.create`

```js
var object = {
  key: 'value'
};

var obj = Object.create({
  key: {
    value: 'value',
    writable: true,
    enumerable: false,
    configurable: true
  }
});
```
Yeah. That's right. we're gettin' REAL object heavy right now, but let's take a look at the flexibility this affords us by deconstructing that `Object.create` call up there.

```js
var obj = Object.create({
  key: {
    value: 'value', // The value for this key
    writable: true, // Determines whether or not we can modify the value
    enumerable: false, // Determines whether or not this shows up in for loops
    configurable: true // Can we change (configure) these 'meta' properties?
  }
});
```
So it turns out that with _any_ property defined on an object this way, we can define whether or not it can change, whether or not it can be looped over, __as well as__ whether or not we can actually change these meta-level properties at a later time!

Objects are pretty nuts. There's another interesting conferred by using `Object.create`, it's custom getting and setting.

### Custom getting and setting with `Object.create`

```js
var obj = Object.create({
  key: {
    value: 'value', // The value for this key
    get: function() {
      console.log('THERE CAN BE ONLY ONE HIGHLANDER.');
      return this.value;
    },
    set: function(val) {
      console.log('NEW VALUE OH BOY');
      this.value = val;
    }
  }
});
```

Okay... this is. This is ridiculous. But you see where I'm going with this, right? You could take an object property and define custom getters and setters on it that could potentially produce all kinds of side effects.

For example, based on my definition up there, literally __any time__ I access `obj.value`, that is, __any time I read `obj.value`__, the `get` function runs, and I get 'THERE CAN BE ONLY ONE HIGHLANDER' output to my console.

Every time.

Conversely, if I assign a new value to my key via `obj.key = 5`, I'll get "NEW VALUE OH BOY" thrown into my console because it'll run the `set` function.

This is amazing. It's also incredibly ill-advised without a proper use-case. But the point is _can you believe this is a thing?_

__I sure can. Because javascript is just WEIRD.__

## Custom serialization

Custom serialization is another thing you can do! if you need a serialized object and you don't like what `JSON.stringify(object)` gives you, you can just tell the object itself what it needs to do when it should be serialized.

```js
var object = {
  key: 'value',
  toJSON: function() {
    return "Literally nothing related to this object. Serialized";
  }
}
```
Essentially what this object is doing is specifying a `toJSON()` property. Normally, when serializing an object, you end up with a string verson of the object as specified by `JSON.stringify()`. By defining it at the object level, the serialization process via `JSON.stringify()` will use that method on the object instead of the default method of serialization. While not _strictly_ prototypal, it mimics behavior similar to the prototype chain. I covered this in the last article about how prototypal inheritance and delegation up the prototype chain works.

([Go read it.](prototypes))
([Also read about the custom `.toJSON()` property](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#toJSON()_behavior))

Anyways, Now we have an object that will run (and serialize the return value of) a custom hook if we call it with `JSON.stringify()`! 

```js
var object = {
  key: 'value',
  toJSON: function() {
    return "Literally nothing related to this object. Serialized";
  }
}

JSON.stringify(object) === '"Literally nothing related to this object. Serialized"' // true

```

Again, This works because `toJSON()`exists on `object`. Since we've defined it here, it actually takes this function and uses it to output a serialized return value from `toJSON()`

## Your brain is a little fried

This isn't the only time javascript is gonna blow your mind. it's ridiculous how flexible this language is, man. I recommend you head over to [JSBin](http://jsbin.com) or some other editor and try these things out! And if none of them work, please tell me so I can actually fix my examples (if they're not-so-hot)

Happy coding!
