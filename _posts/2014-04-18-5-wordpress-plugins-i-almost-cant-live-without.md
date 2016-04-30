---
id: 4
title: '5 WordPress Plugins I Almost Can&#8217;t Live Without'
date: 2014-04-18T03:00:18+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=223
permalink: /5-wordpress-plugins-i-almost-cant-live-without/
---

Yeah, I know I’m not doing you any favors by adding yet another top five post to the ever growing number of ‘Top X WordPress Plugins’ articles, but just as any other developer wants to share their knowledge about what’s useful to them, I feel like I could best articulate that to you in a nice section-by-section piece!

Plugins are an important part of the WordPress ecosystem, they’re more than just plug and play modules, they represent communities, a deeper understanding, and most important of all, the continued use of a blogging platform that grows in power and function by the day.

<!--more-->

So, without further ado, I present the five plugins I almost can’t live without.

# WP-Optimize

WP-Optimize is a plugin that I’ve only recently discovered, but I’m already in love with it.

This plugin is a database optimizer, at its core it scans your WordPress Database, looks through your tables and tells you what could be optimized. Even better, it’s a one-click solution. You have a moderate level of control over what gets cleared and what stays.

In my usage, I managed to reduce the size of a WordPress database from about 36 megabytes to 26 megabytes (It could have been more, but the team I worked with decided to keep up to 10 weeks of post revisions)

WP-Optimize looks through your posts and checks to see if there are extra revisions that could be removed. Additionally, it takes a look at Comments, Pingbacks, Transient settings, and a couple of other things. WP-Optimize lets you know how much space you could reduce your database by, and (importantly enough) it lets you know which optimization options could cause wayward behavior (which aren’t typically the biggest space savers when optimized anyway)

There’s a good chance you can speed up the load time of your site if you’ve got a smaller database to query, because huge databases can take longer to sift through. WP-Optimize has you covered in keeping your database as small and optimal as possible.

# EWWW image Optimizer

I discovered EWWW a while back when I was looking at ways to optimize website load times. I definitely spent more time doing it than I thought I would. EWWW and I became firm friends after my first set of image optimizations.

EWWW Image Optimizer is a plugin that allows optimization all of the images in the WordPress database, once again shrinking its size. A great passive benefit of having EWWW installed is the fact that upon uploading any image file, it’s automatically crunched and optimized to take up the least amount of space while retaining quality.

If you want to keep the same image quality across your entire website but you’re looking to boost site load speed or reduce the return time of a query on the database, this might be a plugin you want to check out!

# W3 Total Cache

I’m pretty sure it would’ve been impossible for me to not list a caching plugin on this top five, the benefits versus the overhead on W3TC is so skewed in favor of better site performance it’s ridiculous

W3 Total cache is probably the most popular caching plugin on WordPress. I’ve used it on a website I’ve worked on before, and page load times improved from a dismal 8 seconds to less than 3.

This plugin essentially takes ‘snapshots’ of the pages and files associated with your site. Since most of the content doesn’t actually change from request to request, the cache is able to serve up content that’s ready to go and in the pipeline as opposed to serving up a new copy of the stylesheet, the scripts, whathaveyou. The caching of static resources (resources that don’t typically change that often) usually results in a faster load time.

When fully configured in a way that synergizes well with your webhosting plan, you can expect your WordPress site load time to drop drastically.

# Duplicator

Duplicator, to me, is like the first friend I ever met in elementary school, really cool, really exciting, and I just wanted to spend all my time with them. I ran into duplicator when I was working on The Next. I was curious about a way to clone a WordPress environment from a live website to a local test server.

Needless to say, I stumbled on Duplicator and I never looked back. This is a plugin that feels like it was crafted by the gods themselves. Duplicator takes a complete website snapshot of your WordPress environment. When I say complete, I mean complete. All of your plugins, images, settings, and configurations are there.

After running Duplicator, the plugin stores a package that includes a .zip file and an installer.php file. If you want to duplicate the site into a local server, all you need to do is create a database, create a user for that database, place the .zip and installer file in a folder located inside www/htdocs and navigate to the installer file. After filling out the fields in the installer file, Duplicator goes to work and creates a replica of your website locally.

This plugin is probably one of the most useful plugins for moving entire WordPress installations. It doesn’t yet have Multisite support, but in most cases, you’ll probably only be moving one installation.

# Pods

Developing with PODS is really where I started my WordPress development streak. It’s powerful, and it gives a whole new level of extensibility to your WordPress.

PODS is more than just a plugin. When you install PODS, you enable your WordPress to do some incredibly powerful things. PODS allows you to add custom post types, page types, taxonomies, categories, etc. Or if you don’t want to create new ones PODS allows you to extend the functionality of the existing post, page, etc types.

Even better than that, the custom fields you can add support a million different formats from using the WordPress WYSIWYG (What you see is what you get) editor to a file upload form where you can upload different files if that’s what your solution calls for.

To cite an example from this website (Code and Comedy), My resume page makes use of a custom post type called ‘languages’, and each of those little squares with the icon, name, and proficiency level that you see is being pulled from an individual post. In addition to the post title (for admin purposes) the individual post has three custom fields:

Language name &#8211; The name of the language (C++, Java, HTML, etc.) &#8211; accepts input in a plain text field

Proficiency level &#8211; The proficiency (with 4 being greatest) of the knowledge of the technology &#8211; accepts input in the form of a drop down select list. You can select Beginner, intermediate, proficient, or advanced which correspond to 1, 2, 3, 4 respectively.

Language Logo &#8211; An image or logo (64&#215;64 is what I decided on) of the language &#8211; Accepts input in the form of an image upload.

All of that took me less than ten minutes to set up in PODS, and now its a functionality I can control and change at will. I was able to make a new post type and give it three specialized custom fields in under ten minutes. Isn’t that impressive!?

PODS will also allow complex relationships between almost anything that WordPress supports.

Not only that, but it plays nice with the WordPress core. This means you’re able to use WordPress calls to get custom fields added by PODS. Oh, and did I mention that PODS comes with its own suite of functions? You’re able to navigate through PODS that you set up with a coupld of functions, and all of the docs are easily accessible.

Each of these five plugins serves a unique purpose that has made my development and design experience far easier than I thought it would originally be. If you’re looking to power pack your installation and give it a lot more capability, each of these plugins, whether it’s for the sake of speed or extensibility, will drastically improve your experience in working with WordPress.

In the end, it’s not up to me, but each of these plugins is definitely worth a look at! Go check ‘em out!

Happy coding, everyone!
