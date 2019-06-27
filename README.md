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


##### An example

```html

<button>Click Me</button>

```

```js

//find the button
const btn = document.querySelector('button')

// add event listener, and callback function
btn.addEventListener('click', () => {
  console.log("click works")
})
```


#### Can we find out what we clicked on?

- We can use the `event` object which is automatically passed to our callback function for us.

- `event.currentTarget` - is the object that the event listener is attached to.

- `event.target` - is the elemenet we clicked on which is inside the element the event listener is attached to.

```html
<ul>
  <li>Taco</li>
  <li>Burrito</li>
  <li>Sopa</li>
  <li>Tostada</li>
</ul>
```

javascript
```js

const ul = document.querySelector('ul');

ul.addEventListener('click', (e) => {
  // e is short for event which is the object that automatically gets passed to the callback function
  console.log(e.currentTarget); // will always be the ul 
  console.log(e.target); // is the element we are clicking on, could be any of the li's or ul's
});
```

-  This is called *Event Delegation*

- *Event delegation* is a technique for listening to events where you delegate a parent element as the listener for all of the events that happen inside it.

- By doing it this way we don't have to set an event listener to every single element!

#### Lets add some DOM UI to our Pokemon app together!

Clone this repo [Pokemon vanilla]()












