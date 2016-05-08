---
id: 30
title: The Migration
date: 2016-02-26T23:58:15+00:00
author: Bradley
layout: post
permalink: /the-migration/
---

So it's been a minute, I'll give you that. You're probably wondering where I went. You're likely hoping it was somewhere awesome.

It wasn't.

I've actually spent time really thinking about the technology debt of my blog. It's not huge, actually. In fact, The old incarnation of my blog is pretty much self sufficient thanks to the wonders of Wordpress. I'm incredibly thankful for the ease at which I'm able to get a site up and running. I'm NOT thankful that it takes me 50 menus and an image upload to post an article.

<!--more-->

At the same time, I realize that since starting this blog I've had my hand in all sorts of projects that varied in scope or technology. As I dove deeper into the world of Node.js and different javascript libraries and frameworks, it dawned on my that Wordpress was becoming a dreaded solution to my problem.

_what was my problem?_

I just wanted to be able to write out a ding-dang text file, throw it on my server somewhere, and then have some serious demon magic take care of the site part. You can argue that that's what Wordpress did for me, but the real issue is that Wordpress does so much _more_ than that.

I don't need that amount of demon magic.

## Enter Github pages

A while ago I found out that github supported pages, a feature that allows you to breathe a website to life via a specific branch of your project in github (that, or your entire account). This was an amazing discovery, because it meant I'd be able to integrate my knowledge of git with my blog writing process.

Github supports Jekyll, a technology that's often used to build static websites. What's a static website? Well, a static website can be thought of as a 'finished product'.

Imagine my blog is a fine meal. How is the meal made? ingredients and hard work. probably some MSG. Static site generation means taking those ingredients and making that meal. The REAL beauty is in publishing new articles, I'm able to write in Markdown, I'm able to publish by pushing to the git repository. When my Github repo receives a push, it runs the build step again to re-generate my site from a bunch of static files.

It's like I have a team of chefs that will literally bake me a cake, and then when I say "but wait, add strawberries" they straight up bake a new cake. It's nuts.

What a waste of food. Anyways, here's why this is awesome:

1. I no longer have to deal with WISYWIG (what you see is what you get) editors.
2. I can easily inject code snippets (This was a nightmare in Wordpress).
3. Adding/removing/editing articles is easy with git, since they're just files that I've authored.
4. Jekyll static site generation means that all of my design and structure of the site live and die as raw files in the repo, I don't have to worry about what they look like coming out of the process as long as I follow the conventions.

That's just CONVENIENT.

If you're trying to start a blog and you want it to be easily accessible I suggest learning rudimentary git (you'll need to learn 4 commands, probably) and creating a Github account so you can reap the benefits of:

- A free user site
- Static site generation, and
- A buttery smooth editing experience

I'm not really looking back on this migration and thinking I made a bad choice. I made a choice that makes sense for me, and honestly, it feels light, clean, and awesome.

This is part of a multi-step migration of moving my blog into its own site, and letting my original domain [http://bradleystafford.com](http://bradleystafford.com) become a hub for all the channels where I make/do things. It's cleaner, better, and less of a headache for people to actually FIND what they're LOOKING FOR.

Happy coding!
