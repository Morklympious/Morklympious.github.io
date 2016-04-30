---
id: 12
title: Enhancement and Degradation
date: 2014-07-02T05:10:52+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=328
permalink: /enhancement-degradation/
---
If you ever find yourself in a situation where you're in an interview and the first thing your interviewer asks you is:

_what are your thoughts on progressive enhancement and graceful degradation?_

Then what are you doing? Why would they jump straight to THAT question? Why couldn't they say hello or ask you if you needed a bio break? Yeesh.

<!--more-->

This week or whatever's topic is about, you guessed it, progressive enhancement and graceful degradation. These are terms I often run into, not necessarily in my day-to-day, but I've had more than enough interviews where the question is asked. Let's actually talk about this now.

Both the enhancement and degradation are two sides of the same coin. While they didn't necessarily originate at the same time, they represent some of the same procedures, but on different ends of a project.

## Graceful Degradation

[Graceful degradation](http://webdesign.about.com/od/webdesignglossary/g/graceful-degradation.htm) (as I understand it) was a movement back in the ol' days of the internet. You know, back when people were like "I'm gonna get on NETSCAPE and check my E-MAIL because that's literally the most exciting thing about the internet!" Graceful degradation involved developing with the latest and greatest browsers in mind, and after all the bells and whistles were thrown on, web developers had to think to themselves Oh great. now we gotta make sure it doesn't look like complete hell when people aren't using the latest and greatest browsers.

Graceful degradation made browser features the most important priority. Develop for those browsers first, and then make sure it's passable on older browsers.

## Progressive Enhancement

[Progressive enhancement](http://www.smashingmagazine.com/2009/04/22/progressive-enhancement-what-it-is-and-how-to-use-it/) has buzzword written all over it. Well. So does graceful degradation, but I digress. Progressive enhancement was actually born out of graceful degradation and is considered to be its developmental successor.  This methodology takes the same idea (develop for one main priority, and then move forward with secondary priorities) and focuses on the content itself as opposed to the software on which it is viewed.

This is actually really awesome, because the content is priority one. Since content is at the top, developers have to strive for consistency across a lowest common denominator (typically that denominator is IE 8/9 since more other browsers today are becoming very standards compliant.) Developers who use this methodology develop content and it becomes more exciting because they then get to implement sick, sweet, and cutting edge new features for the users that have browsers supporting those hip, cool new features.

Progressive enhancement focuses entirely on the content, and builds its structure around that, utilizing a strong [separation of concerns](http://en.wikipedia.org/wiki/Separation_of_concerns) design approach.

Now you can actually see a lot of examples of progressive enhancement in the most popular projects that people release nowadays! For example, you almost never see a case when someone doesn't use a [CSS reset](http://necolas.github.io/normalize.css/) or someone who doesn't [shiv HTML5 elements into their older versions of Internet Explorer](https://code.google.com/p/html5shiv/). Libraries like [Modernizr](http://modernizr.com/) allow for feature detection so you can really pinpoint your supported features and not have to worry about things breaking or exploding violently because you didn't think of some edge case that really doesn't MATTER BUT IT TOTALLY MATTERS TO THE PEOPLE USING YOUR-- I'm getting off track.

Anyways, If you're going to design a site, you should probably use progressive enhancement. [Separate your files](http://www.onlinetools.org/articles/unobtrusivejavascript/cssjsseparation.html), even up the playing field, and get to it!
