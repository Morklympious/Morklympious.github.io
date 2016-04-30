---
id: 13
title: Polyfills, polyfills, polyfills!
date: 2014-07-10T02:47:59+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=337
permalink: /polyfills-polyfills-polyfills/
---
Polyfill. It's a fun word to say.

Then again, almost any word that has the prefix 'poly-' is pretty fun to say. Polyrhythm, polyurethane, polygraph. All fun, all the time.

As it applies to web development, a polyfill is a tool that is used to enable a legacy browser to support something a more recent browser would support as if it was native. The idea behind calling it a polyfill is obvious, it's a tool that fills all the gaps presented by older browsers, making them behave in a more modern fashion.

<!--more-->

Honestly, 'polyfill' is a word that's been showing up on my radar a lot, and I actually couldn't be happier about it, because it offers solutions to problems that web developers always run into: making everything work with older browsers, it evens up the playing field so much in some cases that progressive enhancement and graceful degradation don't really factor in!

There are so many polyfills, too. People recreate these features using javascript, since the support for JS is a lot more widespread than the support for CSS3.

If you want IE7/IE8 to support the opacity CSS property?
[There's a polyfill for that.](https://github.com/bladeSk/internet-explorer-opacity-polyfill)

You want your site to resize dynamically when CSS3 media queries aren't supported?
[BAM. POLYFILL.](https://github.com/scottjehl/Respond)

Would you like to support something if the feature exists?
[There's a tool that lets you enable your features conditionally!](http://modernizr.com/)

(although Modernizr might be less of a polyfill and more of an indicator of what features your environment isn't supporting)

Honestly, Modernizr keeps a [pretty sizable list of different polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills)that achieve the job of supporting HTML5 features when they aren't supported natively.

Be sure to check it out!

Happy coding!
