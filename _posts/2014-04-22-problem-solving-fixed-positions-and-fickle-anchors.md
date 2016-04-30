---
id: 6
title: Fixed Positions and Fickle Anchors
date: 2014-04-22T03:00:20+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=227
permalink: /problem-solving-fixed-positions-and-fickle-anchors/
---

Since I’ve been working for [Pixelkin](http://pixelkin.org) as a web developer, you can bet that I’m typically bombarded with "Can we…" and "is it possible to…" on a frequent basis. Since Pixelkin runs on a custom theme developed by ThemeNectar, it’s important that I watch where I’m stepping and try my best not to completely kill what makes the theme so magical.

<!--more-->

A while ago I was approached with a problem, The main menu for Pixelkin is placed with fixed CSS, which makes it persistently stay in the browser viewport regardless of user interaction. The issue is that no one seemed to anticipate the use of anchors to jump to other parts in the page.

Pixelkin also has a library of gaming terms that relies on anchors to jump to differing sections of the alphabetical terms

So as you would expect, clicking on an anchor would effectively scroll it to the top of the document. Behind the fixed menu. Where no one could see it. Now I don’t have to tell you that it’s a pain in the ass for users to click an anchor tag, have the page move and then scroll slightly up. The developer in me says "Oh whatever, it’s fine, they’ll figure it out" and the UX designer in me screams violently.

I implemented a jQuery script I call Anchorfix, which is applied to an anchor tag that absolutely must be shown under the primary menu. Using the height property, it finds the height of the menus and adds them together (even accounting for the WP admin bar if it’s there) and then uses that as a base offset for placing the anchor.

After the offset is established, adding a few more pixels for nice padding gives us a desired result!
