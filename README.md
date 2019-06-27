# Js-Dom-Events

#### What is a DOM EVENT

- A DOM event is some user interaction on a page that our document is listening for.  For example, we could be listening for a click, a double click, or when someone presses a certain key.  When one of these events are heard, we can then call a function to initiate some reaction to the event that will perform some operation on the page. 


#### Basic Syntax

``` someElement.addEventListener(event name, callback)```

- if the event is "click", the callback is the code that should run when user "clicks" "someElement"
-  the function that runs when an event is clicked is called an 

*event Handler* - event lister connects event to handler, event handler is what actually happens when user does the event

*note: events are strings*

##### How do I know what the events are? 

- Hopefully you guess the docs - [mdn Web Events](https://developer.mozilla.org/en-US/docs/Web/Events)


