# jQuery - DOM Manipulation

## Installation
jQuery is a client side library, which means we need to include it in our HTML. To do this, we include the CDN (content delivery network) in a script tag, which we can copy/paste. One source: [Google Hosted Libraries](https://developers.google.com/speed/libraries/) 

## DOM manipulation with jQuery

To select an element in the DOM, we use the global jQuery function:

```js
// This is the basic syntax for jQuery selections
$(' ')

// To select a particular element by tag, you do
$('div') // selects all div elements

// To select by ID, you use the same syntax as CSS selectors
$('#someID') // Would select the element with ID="someID"

// To select all elements of a particular class, use CSS syntax again
$('.someClass') // Selects all elements of the class "someClass"

// And you can use more complicated CSS selectors as well
$('p.anotherClass') // Selects all <p> tags that also have the class "anotherClass" (<p class="anotherClass">)
```

If you use variable assignment when doing a selection, a "jQuery" object is returned

```js
var paragraphs = $('p'); // Returns a jQuery object containing all <p> tags on your web page.
```

Here is a demonstration of all the different types of jQuery selectors: https://www.w3schools.com/Jquery/trysel.asp

#### Selecting a DOM element and changing it's content

In this HTML:

```html
<div id="myDiv">Hello world!</div>
```
We can select and change html elements like so:

```js
// vanilla JavaScript
document.getElementById('myDiv').innerHTML = "Goodbye world!";

//jQuery
var myDiv = $('#myDiv')
myDiv.html("Goodbye world!");
```

#### Adding and removing DOM elements

If we want to add a new DIV that provides an opinion, our vanilla JavaScript would have to be:

```js
var newDiv = document.createElement("div");
newDiv.innerHTML = "Indigo should not be included in ROYGBIV";
document.querySelector("body").appendChild(newDiv);
```

And in jQuery, it looks like this:

```js
var newDiv = $("<div></div>").text("Indigo should not be included in ROYGBIV");
$("body").append(newDiv);
```

Say we've had a change of heart and want to rescind our previous statement. In vanilla JS:

```js
document.querySelector("body").removeChild(document.querySelector(".bright-div"));
```

And in jQuery:

```js
$(".bright-div").remove();
```
