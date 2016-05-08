---
id: 22
title: Keeping Your JS Selectors Cached
date: 2015-06-02T22:57:57+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=407
permalink: /keeping-your-js-selectors-cached-ft-a-goblin/
---
I'm always looking for the next optimization or construct I can use to improve my javascript code. Here you are thinking "Well, I mean. With all these posts about javascript, DUH."

I GET IT, ALRIGHT. WE KNOW. WE ALL KNOW I'M *ALL* ABOUT THE JS.

I just learn really interesting stuff in javascript!

<!--more-->

Anyways, let's get to the meat and bones here: webpage performance doesn't incur a huge hit as a result of javascript, typically. That's not to say you shouldn't take every measure to optimize performance, I'm just pointing out that a lot of performance issues will only start showing themselves if you've got to run a high traffic, high content site like Amazon, Google, etc.

It goes without saying that you should probably develop from the ground up with this in mind. Is your website going to explode into fame? Probably not.

But when that DOES HAPPEN (because it WILL because you're a ROCKSTAR and I believe in you) you're going to be glad that you did.

So let's talk about caching selectors.

Let's say we have an HTML element with an ID of 'thing' and we want to pass it in as a parameter to our method `doStuffWith();`

The first example is without caching it, the second involves caching.

```js
// Without caching
doStuffWith(document.getElementById('thing'));
```

```js
// With caching
var thing = document.getElementById('thing');
doStuffWith(thing);
```

Which would you prefer?

The answer should probably be the cached version. Here's why: BECAUSE IT'S SUPER SWEET.

Okay, here's the real reason: if you have a reference to that element saved, then subsequent calls to that elements reference are improved. The javascript goblin that figures out what's going on with your code is like "Okay, 'thing' is a reference to the DOM element with an ID of 'thing'. I don't have to look this up because I already did once."

Here we only have to use the variable instead of the nonsense of finding it again. Not only does it improve performance, but it's going to be easier to type, and make our code less prone to typos which could ultimately bring about the destruction of your website, and your sanity.

As you slam your head to the keyboard, you wish you cached that variable.

For you level 99 code moguls, I get it. You're not impressed. I know you're not. In fact, why are you even HERE? You should be off writing all these javascript libraries that I nerd out about! For the less experienced, here's where I thought things would get pretty novel.

Let's make a namespace on the window in javascript.

```js
window.codeAndComedy = {};
```

Okay. Done. Next, let's add another object that we can keep our references in. Something that implies a collection of stored variables. Let's say box. Wait. No. let's use crate. Crates are way cooler.

```js
window.codeAndComedy.crate = {};
```

Now let's define a method in the codeAndComedy context that will store references in the crate. We'll call the method 'goblin' because this article has already trekked into the absurd and I want to keep the ball rolling.

```js
window.codeAndComedy.goblin = function() {}
```

Okay. We want our DOM goblin to do some cool things:

1) the DOM goblin should use JQuery to look up a DOM node only if it can't find a reference to that node in the crate.

2) If the DOM node isn't in the crate, its gotta put it in the crate!

Here we go!

```js
    window.codeAndComedy.goblin = function(thing) {
    	//Let's alias a few things to make it easy.
    	var crate = window.codeAndComedy.crate;

    	// We're looking for the thing!
    	// If the thing is in the crate

    	if( crate[thing] )
    		return crate[thing]; // return the thing, we have a reference!

    	else // We didn't find it in the crate
    	crate[thing] = $(thing); // So we'll add it to the crate!

    	return crate[thing];

    }
```

And done. This is a nice function because it means we're caching every single selector that we use with CSS selector names.

Even in the event that we only use a selector once, it's not bad to have a reference to it somewhere.

In the likely event that we need to reference a DOM element multiple times, we know that it's in the crate. and If we can't find it in the crate, we'll put a jQuery object that selects that thing into the crate.

__Note from 2016 Brad: This will definitely not work if what you're trying to query changes in quantity__

It's not a groundbreaking construct, but this is something that's actually really interesting to me because I never thought about having a single object through which all of my references were found. It's a nice, central location that actually cleans my code of a million var statements if I need to look up several elements with jQuery. Even better, I get to use all those jQuery methods on the thing my goblin returns!

While it may not have its place everywhere, I think that there can be a fairly decent performance boost, especially if you're dealing with ludicrous amounts of selectors.

Happy Coding!
