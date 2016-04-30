---
id: 16
title: Efficiency in Event Handling
date: 2014-09-27T20:42:29+00:00
author: Bradley
layout: post
guid: http://bradleystafford.com/?p=355
permalink: /efficiency-event-handling/
---
I've been dancing around that good 'ol jQuery fire for a while now, and I've got to say that I've been learning a lot. The combination of books I've read and the application of the framework itself has taught me a lot about what I can do with jQuery. In this sense, it leads me to more effectively code up website behavior.

So I'd like to talk about click handlers!

<!--more-->

Click handlers are great. Almost every website you visit has some custom implemented click behavior for reason of submitting a form, performing a calculation, or even changing all the text on the page to blue (who knows?)

With that in mind, JQuery offers up the `.on()` method, which is really the method it uses for all of its event handling needs since something like jQuery 1.7. JQuery also offers `.click()`, a handler that's just used as a shorthand for `.on('click')`. Now here's where things get interesting. Both of them effectively do the same thing; they both allow behavior to be attached to specific user actions.

However, `.on()` allows you to delegate your events.

Consider this code:

```html
<div class="parent-element">
  <ul>
    <li></li>
    .
    .
    .
    <li></li>
  </ul>
</div>
```

Let's say for the sake of this scenario, we have 7000 list items. That's huge. a HUGE amount of list items, let's also say that we want a behavior that turns the text content of the list item red when we click that item.

We can achieve that like this with `.click()`:

```js
    $('li').click(function(e){
      $(this).css('color', 'red');
    });
```

All well and good, right? Let's think for a second, though. We're attaching an event handler to every single list item. That's 7,000 handlers. If we're working with some high load website or application, we're going to want to shrink that number as best we can.

So let's do the same thing with `.on()`:

```js
    $('.parent-element').on('click', 'li', function(e){
      var self = $(e.target);
      self.css('color', 'red');
    });
```

Here we attach the handler to the parent div, and make use of the second parameter in `.on()`. The second parameter allows us to further specify something to look for that will trigger these events. This is a single handler that now will listen for each list item in the 7000 list items, but through the power of event bubbling, we only need one handler.

More on that 'event bubbling' thing. Event bubbling is something that occurs on an event that's recognized by the browser. If you click any list item in that code, a 'click' event fires on that list item. Even bubbling will cause the click event on that list item to 'bubble up' to its parent element, wherein a click event is fired (on the parent). This process will continue until the document itself is reached, so any elements that have a handler attached to them that match the event will fire.

This is what makes `.on()` so powerful. Instead of listening to every element, we let the DOM do what it does naturally, and have a single handler deal with the event when it comes up.

The `e.target` wrapped in a jQuery object refers to the element that was clicked. in some instances, it can also refer to `$(this)`, but I err on the safe side and use a 'self' variable to store the targeted element.

So remember. Next time you need to add a bunch of handlers to elements, think about delegating your events instead of directly attaching them to the DOM Elements themselves.
