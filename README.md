# Js-Dom-Events

![GA logo!!!](https://camo.githubusercontent.com/6ce15b81c1f06d716d753a61f5db22375fa684da/68747470733a2f2f67612d646173682e73332e616d617a6f6e6177732e636f6d2f70726f64756374696f6e2f6173736574732f6c6f676f2d39663838616536633963333837313639306533333238306663663535376633332e706e67)

---
## Learning Objectives
<br>

<p>Students will be able to:</p>

- Describe what a DOM event is
- Be able to write a DOM Event
- Understand a callback

---

#### What is a DOM EVENT

- A DOM event is some user interaction on a page that our document is listening for.  For example, we could be listening for a click, a double click, or when someone presses a certain key.  When one of these events are heard, we can then call a function to initiate some reaction to the event that will perform some operation on the page. 


#### Basic Syntax

``` someElement.addEventListener(event name, callback)```

- if the event is "click", the callback is the code that should run when user "clicks" "someElement"
-  the function that runs when an event is clicked is called an 

*event Handler* - event lister connects event to handler, event handler is what actually happens when user does the event

*note: events are strings*

#### Callback

callback - a callback function is a function to be executed after another has finished.

- So in our case after someone has triggered the event listener function the callback will then be called to perform whatever logic we want to happen when a user clicks on an event.

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

#### Lets play around 

- What we will do here is do a simple example of adding something from one list "a menu" to another list "an order"

- First Let's add some more html

```html
<section id="menu">
  <h4>Menu</h4>
  <h6>Click the Item to add to menu</h6>
  <ul>
    <li>Taco</li>
    <li>Burrito</li>
    <li>Sopa</li>
    <li>Tostada</li>
  </ul>
</section>


<section id='order'>
  <h4>Order</h4>

</section>
```

- and Lets add some css, if you haven't used flexbox before check out this [article](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

```css
body {
  display: flex;
  justify-content: center;
}

#menu, #order {
  padding: 2em;
}

#menu {
  margin-right: 3%;
}
```











