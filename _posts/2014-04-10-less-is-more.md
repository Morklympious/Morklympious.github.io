---
id: 1
title: LESS is More
date: 2014-04-10T03:00:40+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=207
permalink: /less-is-more/
---

<p dir="ltr">
  I’m one of those bums that really likes to do things the way that they’ve been done before. That’s not to say that I’m not open to change, but I feel like at any given point along the route of a project, I’m likely to take a path that I’ve stomped over a few times. While I was creating my portfolio website I was looking for a solution that utilized some really strong, really robust boilerplate technologies. The kind of stuff that would scale and the technology that would allow me to build a site in a smart way.

  I had no idea that LESS was going to be a part of that solution.
</p>

<!--more-->

For those of you that don't know, [LESS](http://lesscss.org/) is a Javascript compiled CSS pre-processor (Think PHP but for styling) that allows you to do things that would make vanilla CSS weep. I found myself quickly learning the basics in less than two hours, and now that I’ve a taste for the technology, I’ve got to say it’s going to be hard to code anything in plain ol’ CSS ever again.

Here are a few reasons why LESS is my new favorite:

## Nested Styles

It’s funny, because if you ever look at the way I used to do CSS stylesheets, it was with a nesting operator (div > span). For some reason I just got really accustomed to that, and eventually I broke that habit, but with LESS, all of that gets taken care of with nesting like you would in a more standard coding language.

ex. Lets say I have this markup

```html
<section id="section-area">
   <div>
      <span>I’m a span!</span>
   </div>
</section>
```

Now if I’m nesting with CSS selectors, to target the span I’d probably have to write:

```css
#section-area > div > span{
   color: red;
}
```

If I want to style the span in this markup, my LESS would look something like

```less
#section-area {
   div{
      span{
         color:red;
      }
   }
}
```

And the best part about it is that at any nested point along the way I can add a style, no problem!

Did I also mention that all CSS3 makes for valid LESS? If you want to style things the old fashioned way then that’s totally fine! Both of the above examples will achieve the same thing in LESS.

## Variables

This is probably one of the features I’m most in love with, and it’s because it makes changing something like your color scheme a snap. it also makes selecting a series of fonts and fallbacks as simple as declaring them all in one @fonts variable.

Currently, I’m dealing with a @sans-serif variable that stores the fonts of this site

```less
@sans-serif: "Roboto", "Helvetica Neue", Helvetica, Arial, sans-serif;
```

Note that I’m able to achieve all of these fall backs and then when I want to place all of those fonts I just have to use font-family: `@sans-serif`

It’s a snap!

## Function Calls

Functions in LESS can be defined a lot like CSS class selectors, which is really awesome. There are plenty of examples when using a style like border-radius. The problem is that every major browser does things a little differently, and you usually want to target the specific browsers if you can, that way you know things will end up rendering the way you want them to.

Let’s take a look at border-radius:

```less
.some-class{
   -webkit-border-radius: @radius;
   -moz-border-radius: @radius;
   border-radius: @radius;
}
```

You can see we have the webkit border-radius declared first, then the firefox border-radius, and then the default standard CSS border-radius. Now personally, I’m not a fan of having to remember that series of fallbacks. In fact, I don’t think I could remember those three lines of code unless I dealt with them every hour of my life. Enter LESS mixin functions!

We can declare this class like so, and it becomes akin to a function signature.

```less
.border-radius(@radius: 4px) {
  -webkit-border-radius: @radius;
  -moz-border-radius: @radius;
  border-radius: @radius;
}
```
There’s a default value for the parameter, and it utilizes the variables we set. we can pass any px value into .border-radius() that we want to. it just depends on what curve or corner we’re going for.

And so, if we want to make use of this function in our `.some-class` selector:

```less
.some-class{
  .border-radius(2px);
}
```

And the rest will take care of itself. Once again LESS will output a smaller, yet syntactically equivalent style as opposed to CSS. It’s unbelievable!


There are also a multitude of functions that will make things easier, LESS supports two color based functions that I absolutely make use of: `Lighten(@basecolor, percentage)` and `Darken(@basecolor, percentage)`. These functions allow you to make small, subtle variations on your color scheme. Which can be incredibly useful because I often find myself at a loss for what colors should be used.


LESS offers basic math functions, too! Like `floor()`, `ceil()` `percentage()`, and `round()`. What’s great here is that you’re not required to use any of the things LESS provides, but it’s here as a strong development toolkit that you’d be foolish not to make use of!

## Support for Mobile first design (320andup) & Modular sheets

This is another thing I love, LESS can be structured with media queries to import other stylesheets, I’m using a version of [Malarkey&#8217;s 320andup](https://github.com/malarkey/320andup/) which is used for mobile-first design, but the media queries and the import statements (which, now that I think about it, could be implemented in vanilla CSS) make stylesheet development completely modular. The Modular design is also complemented by the semantic naming of my stylesheets, I have base.less (The global sheet) 480up.less, 768up.less, 1030up.less, and 1240up.less. All of these styles make my development more streamlined and easier to troubleshoot.

More than that, your users are going to thank the internet gods that your site loads much, much faster on a mobile phone. The idea is to keep your base.less file small so that phones or smaller resolution devices don’t have to struggle in order to load all of the bells and whistles they won’t even get to see! That’s some smart thinkin’ right there.

## In conclusion

At the end of the day, it’s really your choice if you want to stick to vanilla CSS or jump ship and join me. Maybe you’ve already moved from CSS to SASS (another CSS pre-processor) but I’ve got to say that I’ve taken some time to learn LESS and I can’t imagine working on CSS without it now. It’s almost too powerful. I’m a fan of anything that’ll speed up the development and make things a lot easier on the end user. Remember everyone, LESS is more!
