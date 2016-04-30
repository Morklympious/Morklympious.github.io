---
id: 2
title: 'Extension Against Humanity: A Fever Dream'
date: 2014-04-12T03:00:42+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=198
permalink: /extension-against-humanity-a-fever-dream/
---

If you ever get inside my head, you’ll immediately discover that I’ll go on large thinking sprees about things I can make. You’ll also notice that the thinking sprees usually involve topics that are interesting in some way or topics that I enjoy. Extension Against Humanity was a running idea I had at the end of a thinking spree on a Friday night. I wanted to make a generator of Cards Against Humanity Cards and turn it into an extension.

"Wait, hasn’t someone already made a Cards Against Humanity extension?"" I’d ask myself.

The answer, fortunately enough, was a resounding "Nope."

<!--more-->

For those of you that don’t know, Cards Against Humanity is essentially a NSFW version of Apples to Apples. The game is played in rounds, with one player reading a black ‘question’ card and the remaining players handing them a white ‘answer’ card as a completion of that question. It’s a fun game, and it gets a lot of laughs every time I play it.

So I set to work on creating a sweet, silly Chrome extension that would give me a random generation of those cards I so ardently admire. Creating a chrome extension wasn’t as hard as I thought it would be. I used to think that developing extensions required a tome of knowledge only obtainable in some far off land. Much to my surprise, [that tome exists on the internet](https://developer.chrome.com/extensions/getstarted).

I didn’t actually start with a base set of files from Google’s tutorial, I wanted to see if there was a boilerplate technology first. Something that would allow me to hit the ground running and start developing the core part of my extension without spending countless hours experiencing headaches with setup. I discovered [Extensionizr](http://extensionizr.com/), which is a boilerplate extension generator. It has a lot of useful tools for setting up the file structure based around what you want it to do. I’d have to say that since this is my first time, it easily saved me a few hours. On top of that, I began solidifying my usage of both Git and Github, since I wanted to make sure I could make the extension public and version control my project at the same time.

After downloading the skeleton of my extension, it was time to start putting meat on the bones. Much to my surprise, building an extension was just like building a small, self-contained website. There was HTML, CSS, and Javascript. It was still making use of my web development skills in a cool and unique way, just on a much smaller scale than I’m used to. Something that I really enjoyed was the discovery of other projects that involved Cards Against Humanity on github. I found a user who had a text file compilation of most of the cards, including some fan made expansions. Once I saw that they also included a JSON (Javascript Object Notation) file, I knew that I would be able to use JS to pull the card information from that file.

I built my extension logic first; I didn’t care what it looked like if it couldn’t generate random pairs of cards. The script queries the included JSON file that has the cards, and then splits them into two decks. From there it uses some global variables to determine how many answers the black card can accept as well as how many white cards are currently a part of the pairing being displayed. Eventually there came a breakthrough point where I was generating random pairs of cards, new black cards for the current white cards, and vice versa.

After that it was smooth sailing, outside of a few anomalous errors with determining what the next black card was going to be, it worked really well, I was free to code up a nice looking UI for it that was reminiscent of the Cards Against Humanity brand.

After all was said and done for code and my Chrome extension looked gorgeous, I had to generate a whole lot of images and variations on how I was going to present this extension, because the Chrome extension library allows you to set images of specific dimensions that will help them advertise your creation more effectively. That ate up a few hours to say the least. Even though I spent more time in Photoshop than I probably wanted to, the final product is something I’m happy I took the time to make those assets for.

All in all, this was a fun weekend project, and I have more plans for it in the future that may include a wealth of features I’m really excited about (such as Twitter-sharing your combination or copying it to the clipboard). I know I’ll be working more with Github and Git in the future, this is a project that has really opened my eyes to the power of version control and repositories.

You can get my extension [here](https://chrome.google.com/webstore/detail/chrome-against-humanity/elijdemekphbocjmngdkfpmcgppdkmjf) (EDIT: The Gods of Google have taken down my extension for some branding reasons (It was originally called Chrome against humanity &#8212; oops.) It should hopefully be back up soon! )

View the [Github Repository for Extension Against Humanity](https://github.com/Morklympious/Chromeagainsthumanity)

P.S. If you’ve got an idea for Extension Against Humanity, let me know! We could work on this together!
