---
id: 34
title: Coding for Comedy
date: 2016-12-01
author: Bradley Stafford
layout: post
permalink: /coding-for-comedy/
---

If you couldn't tell, I'm a man of jokes. A lot of jokes. In fact, suffice it to say that I'd probably sacrifice a lot of time and effort to make even the smallest joke. Does this make me a loser?

Yes. Yes it does. That's probably why I'm writing this.

Writing Javascript for jokes is probably one of the most useful things I (or you) could do with your time. You're using your knowledge to construct something that you ostensibly could show to other people and have a laugh about while demonstrating some skills. Unless you're constructing a project that just outputs the word "BANANA" and all of its anagrams... I don't think there are a lot of those.

I want to take some time to actually throw down some of my ideas of Javascript libraries that would be really fun to make. Am I a visionary? Well. Let's just call me the Kanye West of Javascript.

<!--more-->

## Idea: Famous Jasons

The headline is all I really need to make the joke. I think it'd be funny to make JSON files for every famous Jason that we have. Think about how comical it'd be to have this arbitrary file containing data about some famous Jason!

- JSON Derulo
- JSON Sudekis
- JSON Segal
- JSON Statham

I would essentially have a mass file of Jasons and all their data.
Is this an undertaking I would consider? Absolutely.

What did I tell you? I'd break my back for the joke. It's not even that GOOD. Hell, I'd break YOUR back for the joke. No back is safe. Call me Bane, because I'm about to break a lot of backs. 

# Idea: Useless Javascript

I always thought it'd be a great idea to make a functional Javascript library that performs a bunch of functions that do trivial or almost worthless computations. Why? Well, sure, there's no actual utility (or maybe some trivial amount of utility that you couldn't get elsewhere with Lodash, jQuery, etc.) but more importantly it shows that I can BUILD THINGS. FUNNY THINGS.

consider this:
```js
// There is almost no purpose to this.
function former(former, latter) {
  return former;
}

// OH GREAT YEAH CAN'T HAVE FORMER WITHOUT LATTER
function latter(former, latter) {
  return latter;
}

/*
  Good. A function that eliminates one of it's parameters
  when called. This is TRULY SURVIVOR. 
*/
function survivor() {

  return function() {
    var args = Array.prototype.slice.call(arguments);
    var random = Math.floor(Math.random() * args.length);
    args[random] = null;
  }

}
```

What am I even doing?

Very clearly I am MAKING THE GREATEST, MOST COMMITTED JOKE IN THE HISTORY OF CODE.

That's hyperbole. That's a writing tactic used to make you laugh (please laugh). The library wouldn't be useful, but good lord would it be stupid. Sometimes we all need to detach from our high-level code design and enjoy a few dumb things. Useless.js could be one of those dumb things.

# Idea: Self Deleting DOM
Remember a while back when that one dude released a language that essentially ran a self delete whenever the code you wrote caused an error? Yeah. That was called Vigilant. It's the most devout code I've ever had the pleasure to read about. Why not have something like that?

Except instead of deleting when something goes wrong, just deleting on something like load. So it's less "You messed up" based and more "lol c u l8r dude."

I'd like to call it MartyrDOM. Maybe I'll leave a fancy message where I deleted the element. Something like a flag with my face on it that says "WE HAVE LOST A NODE, BUT GAINED A MARTYR." Or maybe we just make that message configurable and then have the code choose a random node to sacrifice in the name of holy code. 

```js
MartyrDOM(document.body) // This is a really bad idea. 
```

Yeah okay that has no real use, but it's a pun. The pun is literally enough for me to want to code it. 

## Mellow out!

Javascript doesn't have to always be serious business. I think it's initial run as the laughing stock of programming is very endearing and some of the stuff the language lets you do is probably best learned on a project where you're intentionally being goofy. 

I think it's just IMPORTANT to have a sense of humor about code. With something like that in mind, it lets you have lighthearted fun when you're tackling a real problem. It also helps make debugging bearable (if you're like me and use "yeeeeee" as your very-excited console log statements). Maybe you're not at all like me, perhaps you just code because it's your job, or because it's intrinsically fun for you.

Give comedy a try!

CODE FOR COMEDY. 
BECAUSE CODE IS POETRY. 
POETRY IS ART. 
ART IS COMEDY. 
COMEDY IS POETRY. 
ART. 
POETRY. 
COMEDY. 
COMEDY. 
COMEDY. 
COMEDY. 
COMEDY.

Happy coding!
