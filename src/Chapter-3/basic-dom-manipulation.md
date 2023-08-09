# Basic DOM manipulation

In this part, we will start writing some code to manipulate our Document.

First of all, I want to introduce you to your two best companions for your learning and debugging journey:

```js
console.log("Hi, I am your best debugging companion number 1")
```
The first is your `console.log()` function which just log stuff onto the browser console for you to see.

The second one is your browser dev tools which I will show you how to use some of its functionality in the live workshop.

## Selecting element

One of the intersting things about JS is that a lot of capability of JS does not come from JS itself but come from the browser. Most browser will provided what we call a DOM API for JS interact with as eluded to in the HTML chapter. 

To call this DOM API in JS, we just have to simply use key word `document`:

```js
console.log(document)
```

You will be given back the structure of your html file within the browser console.

To get an element with a particular id, we do:

```js
var item = document.getElementById("id")
```

So now let fetch 4 items of concern to us:

```js
var addItemInput = document.getElementById("add-item-input");
var addItemButton = document.getElementById("add-item-button");

var incompleteTasksList = document.getElementById("incomplete-tasks");
var completedTasksHolder = document.getElementById("completed-tasks");
```

These 4 lines will grab the following 4 element from our HTML:

```html
<input id="add-item-input" type="text" />

<button id="add-item-button">Add</button>

<ul id="incomplete-tasks">
  <!-- ... -->
</ul>

<ul id="completed-tasks">
  <!-- ... -->
</ul>
```

Ignoring the two `ul` elements for now. We know that the purpose of our input and button here is to add new tasks to our list. So what we would probably want to do is to take whatever text that is in the input field and creates a new task and add it to the `incomplete-tasks` section when the button is pressed. So how would we do that?

Most actionable element in HTML would have this built in helper function called `addEventListener` that allow us to listen to certain event that is happening to the element it is attached to. In our case, let's put an event listener on the `addItemButtom`.

```js
addItemButton.addEventListener("click", function addTask() {
  console.log("I was clicked");
})
```
Here, we are trying to listen to an event on `addItemButton` and this event named is `click`. So, whenever the button is clicked on, the function `addTask() {}` will be triggered. This will in turn log the

> I was clicked

to the browser console.

## Event Listener

Next, let try to specify a bit more behaviour to our click event listener. Let's try to mimic the behaviour as if an actual item is being added to the `incomplete-tasks` section. We wouldn't want the input to be cleared after we click the add button, so that users can type in the next task immediately. 

```js
addItemButton.addEventListener("click", function addTask() {
  console.log(addItemInput.value)
  addItemInput.value = ""
})
```

Here, we will console.log the value inside the input and then set that field to an empty string `""` on every click. Ok, but we still have a slight problem, we wouldn't want to add an empty task right? So let's put some condition on when we would want to log our value.

```js
addItemButton.addEventListener("click", function addTask() {
  if (addItemInput.value !== "") {
    console.log(addItemInput.value)
  }
  addItemInput.value = ""
})
```

And Voilà! We now have ourselves a function that will log out a value of the text inside the input field and clear it off when we click the add button.