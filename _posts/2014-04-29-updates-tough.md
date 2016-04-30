---
id: 7
title: Updates Are Tough
date: 2014-04-29T19:04:11+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=283
permalink: /updates-tough/
---
I find it interesting that the idea of developing a new feature and the actual development of that feature are often times on two totally different planes of difficulty. On the one hand, you think "Oh man. That would be so cool. Why didn't I do that? That's so frickin' EASY to DO."

And then you get to the other hand when you start developing, angry that your own idea lied to you about how easy or simple it was going to be&#8230; Why, idea? I thought we were going to be friends!?

Anyways, this past week I put out an update to my Extension Against Humanity Chrome extension, both UI and logic-wise. I actually received a small, but valuable amount of feedback from my friends about what could potentially be cool to add in future iterations; Everyone was on board with a way to copy and paste the card combinations that were generated so they could be more easily shared. So I set to work on creating a way to output the card combinations in a sentence before I could copy and paste them, and here's what I came up with!

Aside from a few hook-ins with the function names to make it work, I created a function called `makeSentence()`, as you can see it takes the text that's passed in to it and replaces underscores (if any) in the answer cards. If there are no underscores, it appends the white card(s) at the end of the black card. It was a little tricky with the substringing, but I got it done no problem!

```js
//	FUNCTION - makeSentence
//
//	This will take the current pairing of cards
//	and turn them into a functional sentence
//	for the user to have a better time parsing
//	the combination for themselves as well as
//	copy and pasting the combination to others
//
function makeSentence(blanks, fills){
// Sentence is used as a local copy that can now be modified.
var sentence = blanks;

// This is used purely to count the number of underscores we're dealing with.
var numBlanks = blanks.split("_").length - 1;

// If there exists more than one blank
if(numBlanks > 1){
// We're going to need to iterate over the matched white card text
$.each( fills.children(), function( index, value ){

  //Get the location of the underscore in this iteration
  var underscore = sentence.indexOf('_');

  // Reassign the output sentence to be a substring with added content.
  sentence = sentence.substring(0, underscore) + '[' + value.textContent.substring(0, value.textContent.length - 1) + ']' + sentence.substring(underscore+1);

});
}
else if (numBlanks == 1){ // If we only have one blank
$.each( fills.children(), function( index, value ){

  //Get the location of the underscore
  var underscore = sentence.indexOf('_');

  // Reassign the output sentence to be a substring with added content, replacing the underscore.
  sentence = sentence.substring(0, underscore) + '[' + value.textContent.substring(0, value.textContent.length - 1) + ']' + sentence.substring(underscore+1);

});
}
else{
$.each( fills.children(), function( index, value ){

  var underscore = sentence.indexOf('_');
  sentence = sentence + ' [' +value.textContent.substring(0, value.textContent.length - 1) + ']';
});
}

//Populate the output box with our newly formed sentence.
$('div.output').text(sentence);

}
```

As for the copying, I thought "Well, we could just find a way to add it to the clipboard." Honestly, there are few libraries in javascript that actually give you a way to functionally take control of the clipboard, and all of them involve a small, invisible flash file that is place atop the element you specify. It's kind of wonky, but it never really worked out for me.

I spent a while thinking of ways to make it work, at a few point I thought "Why can't javascript just access the clipboard? Why is that a big deal?" Well, it's a big deal because it's a privacy issue. If you allow javascript to access the clipboard without your consent, heavens knows what kind of information you put on there. It could be your SSN, your passwords, or some other sensitive data.  After I thought about it, maybe duping the computer into allowing me access to the clipboard wasn't a good idea, just to respect everyone's clipboard integrity.

So instead I went the way that Google does nowadays (at least with YouTube links), and I offered the generated text in a location easily accessible to the user.

I feel like it keeps a layer of complexity off of my extension now, since I'm not running another javascript library, and honestly, highlighting, copying, and pasting has been a workflow that almost everyone is used to in this day and age. I don't know what I'll update next to be sure, but I do know that I'm eyeballing JQuery and looking to turn that into raw javascript.

You can check out the changes by [downloading my extension](https://chrome.google.com/webstore/detail/extension-against-humanit/elijdemekphbocjmngdkfpmcgppdkmjf)! but if you already have it you've probably already seen them!
