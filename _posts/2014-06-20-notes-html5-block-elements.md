---
id: 11
title: 'Notes: HTML5 Block Elements'
date: 2014-06-20T03:00:14+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=315
permalink: /notes-html5-block-elements/
---
This seems like slightly trivial to write about, but this is more for my own edification than anything else. HTML5 has been around for WHATEVER years and yet I still find myself in a place where I’m learning how to be properly semantic with it.

<!--more-->

For those of you that don’t know, HTML5 puts a strong emphasis on [semantic markup](http://html5doctor.com/lets-talk-about-semantics/). Semantic markup is a term used to describe how you code web pages, it’s meant to make your HTML code readable and infinitely more understandable. In the specification prior to HTML5, there weren’t any semantic block elements, and that’s why you’ll see a lot of websites constructed using an abundance of the element (which isn’t wrong, but it’s hard to know what’s going on just by glossing over the code). So In this post, I’m going to give myself (as well as you) a quick overview of some of the HTML5 elements I use the most, as well as when and where to use them!


## Section - `<section>`
The section element is probably the most confusing (for me) of the HTML5 block elements in terms of what it means. I always think it means "Oh, it’s a section of a page. Like a generic container" but that’s totally wrong. Points to me for trying, but a lot of points deducted for me taking the wrong route with it.

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-section-element):

    The section element represents a generic section of a document or application. A section, in this context, is a thematic grouping of content. Each section should be identified, typically by including a heading (h1-h6 element) as a child of the section element.

As mentioned above, sections are containers of thematically grouped content. The heading is a child of the section and gives the content its title.

## Article - `<article>`
The article element is still slightly confusing for me, but it’s not really that misguiding. It’s an article. When I think article, I think "a piece of content that is, in and of itself, a whole story." There aren’t a lot of contexts in which you would immediately jump to using the article tag, so that makes it a bit easier.

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-article-element):


      The article element represents a complete, or self-contained, composition in a document, page, application, or site and that is, in principle, independently distributable or reusable … This could be a forum post, a magazine or newspaper article, a blog entry, a user-submitted comment, an interactive widget or gadget, or any other independent item of content. Each article should be identified, typically by including a heading (h1-h6 element) as a child of the article element.

All you need to know is that an article is a piece of content that is complete outside of the context of the rest of the HTML document. It can be repurposed and removed and still make sense.

## Article - `<article>`
I’ve got to say I’m a huge fan of the `<nav>` element. You’d be hard pressed to find a great website that doesn’t have some sort of menu for website navigation. Nav just makes sense. It’s a navigation element.

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-nav-element):

      The nav element represents a section of a page that links to other pages or to parts within the page: a section with navigation links.

It’s common practice to wrap `<nav>` tags around an unordered list. But it’s a great tag because it lets you identify where the menu is in an HTML markup!

## Header - `<header>`
The header is a great element, because it allows you to wrap everything in the top part of your page into one nifty container. It also allows you to give other elements their own ‘head’ section if they need it (The header isn’t limited to just one tag per page).

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-header-element):


      The header element represents introductory content for its nearest ancestor sectioning content or sectioning root element. A header typically contains a group of introductory or navigational aids.


I deal a lot in WordPress, which pulls in a header.php file and inserts its content that way. This tag gives me a little bit more of that ‘modular’ feel when it comes to building my websites.

## Footer - `<footer>`
Much like the header, it’s a nice replacement for what would normally just be a div. Now you KNOW where the footer is. Fantastic!


According to the [specification](http://www.w3.org/TR/html5/sections.html#the-footer-element):

      The footer element represents a footer for its nearest ancestor sectioning content or sectioning root element. A footer typically contains information about its section such as who wrote it, links to related documents, copyright data, and the like.



You can also have multiple footers on the page since it can be applied semantically to be the footer of its parent element.

## Figure - `<figure>`
The figure is a tag that I haven’t worked into my HTML5 vocabulary effectively just yet, but I’m hoping that soon my markup will be more standards adhering going forward!

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-figure-element):

      The figure element represents some flow content, optionally with a caption, that is self-contained (like a complete sentence) and is typically referenced as a single unit from the main flow of the document.

It looks like anything in a figure is something that helps the flow of the document, but it could also be moved to its own dedicated space, and while it’s still referenced in the document, it doesn’t affect the way that the document flows.

## Aside - `<aside>`
As I understand it, the aside is a tag meant to work like a sidebar. A lot of websites make use of sidebar content, so this is a block element that holsters that content.

According to the [specification](http://www.w3.org/TR/html5/sections.html#the-aside-element):

      The aside element represents a section of a page that consists of content that is tangentially related to the content around the aside element, and which could be considered separate from that content. Such sections are often represented as sidebars in printed typography.<br /> The element can be used for typographical effects like pull quotes or sidebars, for advertising, for groups of nav elements, and for other content that is considered separate from the main content of the page.


It looks like I wasn’t that far off! Asides are generally used for sidebar content, but can have other purposes. it all depends on what you need your site to display for the user!


So that’s the post this time! I hope this quick overview gave you a good idea of when to use these block elements. I know I’ll probably be referencing my own notes here when I’m building pages. Semantics are important if you want your code to be maintainable and understandable down the road!
