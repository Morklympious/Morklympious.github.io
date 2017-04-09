---
id: 35
title: Unified Programming
date: 2016-12-01
author: Bradley Stafford
layout: post
permalink: /unified-programming/
---

It's been about three months since my last post, and I'm starting to feel incredibly bad about it, so here I am slapping some words onto a text file hoping that it'll eventually make its way out to you.

I want to take a minute to talk about adapting to your work environment. I recently moved from the AmazonUI team to the Prime Now UI team at Amazon, and much like any other job switch, it came with new coworkers, a new codebase, and a new way of doing things. The benefit being that the codebase was near non-existent just months prior to my arrival, so everything being built was slowly being developed from the ground up. As I began to work on features, I noticed something pretty horrifying:

I hated the code.

I didn't like the camel case, I was groaning at the pedantic use of ES6, the lack of consistent structure, some functions were named to be 8 words long.

I began fighting.

<!--more-->

I fought the hell out of the convention that was already there. I won some battles, and some battles were much like the trials of Sisyphus: progress without payoff. I knew in my head that a lot of the problem had to do with the way I believed code should be structured, and I was very eager to defend that structure. However, the more time I've had to think about it, and the more times I've had to justify what I wanted to do: I was hard pressed to find a reason other than "it looks good".

This is where we get into the meat of the lesson: adapt. As a member of a team, it's important that you find a middle ground for "what makes sense" in your code vs. "what you want".

Here are a few examples of my team-incompatible opinions that I had to let go of:

- Functions that are named a single, lowercase word.
- Using objects to hold constants.
- Using `var` in all cases.
- Making equals line up with eachother for pretty variable declarations

These aren't terrible things to lose because what you gain is team cohesion. It was a pretty swift lesson learning to code less like my solo-self and code more like a member of the team I'm currently on. This way, the team has an expected coding style, and not only that, you also build trust with your team.

Is it unwise to go right back to your rogue ways after demonstrating to the team you can code in a style similar to the current codebase?

Well, if the code is __good__, then yes it's unwise.
Otherwise you need to go full Jack Bauer in 24 on that code. I learned a small lesson, even though I kind of knew I would have to be unified in coding convention.  

As for my opinions being tucked away, you can _bet_ that I'm going to still code the way that I want to in my projects, know why? because I'm _brilliant_. I am a _vision_, the code I write should be _displayed in the goddamn louvre_. Okay, fine, it's not _that_ great, but I encourage you to do the same! It keeps all of us happy in that we get to write the code that we like on our own time, and we get to write the code that makes sense when there are 17 people contributing across a multitude of code bundles.

Speaking of happy, happy coding! I'll try not to be so late with my next blog post :)
