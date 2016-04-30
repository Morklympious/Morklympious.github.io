---
id: 27
title: You Are Not so Smart
date: 2015-12-30T17:22:12+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=441
permalink: /you-are-not-so-smart/
---
You are not so smart. I mean that in the nicest way possible.

When I say that, I really mean that if you think you know everything in a particular field, you're wrong. Even if you DID know everything in a particular field, you know who would lose sleep trying to prove it wrong through a minor technicality? This guy. There's always something to learn. That something is always present in the front-end space.

<!--more-->

There's something cool that I ran into the other day when I was at an interview, and when I say something cool, I mean something that made me yell "what!?" a lot. I was asked about how some specific javascript code executed:

```js
var someFunction = function() {
  var idx = 0;
  var obj = {};
  obj.idx = idx;
  this.idx = obj.idx

  if(this.idx !== 'undefined')
    this.idx = 2;

  return idx;
};


var a = someFunction();
var b = new someFunction();
```

To give you some context, I was on an interview rampage. You could probably receive about two dollars in nickels from the state of Oregon or Hawaii with the amount of crushing I did throughout the whole process. My confidence in my abilities was fairly elevated at this point. I was consumed by my own power.

So consumed I had to tell my 150 Twitter followers about my successes through the usage of crude, awful puns.

And, despite my success, for the life of me I couldn't figure this out.

For the unitiated, there's a huge difference between functions that use the new keyword and functions that don't. The biggest difference is that functions created through the use of the new keyword are actually objects created by javascript and allocated for your use. Functions declared with the new keyword have their 'this' context already bound to that object, and they also have a defined prototype. You don't get those things without using the 'new' keyword! Instead 'this' will point to the global object, and a prototype on a non 'new' instance is just... well, a default function prototype.

It was challenging! I loved it. I think that any time your knowledge is challenged in a setting like an interview is an opportunity to grow. It's one of the greatest things about interviews (even if I don't FULLY agree with the technical interview process).

I learned a lot just from a single coding exercise. I am not so smart. You are not so smart. That's okay, because one thing we're both always doing is LEARNING.

Happy coding!
