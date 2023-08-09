# Create Task Functions

Ok, now let's build the real meat of this app, the `createNewTask()` function.

```js
function createNewTask(addValue) {
  var listItem = document.createElement("li");
  listItem.className = "view-mode"

  var checkBox = document.createElement("input");
  checkBox.type = "checkbox";

  var h4 = document.createElement("h4");
  h4.innerText = addValue;

  var input = document.createElement("input");
  input.id = "edit-input";
  input.type = "text";
  input.value = addValue;

  var editButton = document.createElement("button");
  editButton.innerText = "Edit";

  var deleteButton = document.createElement("button");
  deleteButton.innerText = "Delete"

  listItem.appendChild(checkBox);
  listItem.appendChild(h4);
  listItem.appendChild(input);
  listItem.appendChild(editButton);
  listItem.appendChild(deleteButton);

  return listItem
}
```

It is a lot, but we will be covering this through a live coding section in the workshop. This function will allow us to create a new task and return it as a value. Next we just simply have to plug in to our click event listener.

```js
addItemButton.addEventListener("click", function addTask() {
  if (addItemInput.value !== "") {
    var listItem = createNewTask(addItemInput.value)
    incompleteTasksList.appendChild(listItem);
  }
  addItemInput.value = ""
})
```

And Tadah! Now, we could add new task to the `incompelte-tasks` section. However, all the buttons and checkbox of the added task does not really do anything. Let's fix that.

## Checkbox Handler
```js
function checkBoxHandler() {
  if (this.checked == true) {
    completedTasksHolder.appendChild(this.parentNode)
  } else {
    incompleteTasksList.appendChild(this.parentNode)
  }
}
```

This function is quite simple in nature. However, it does introduce you with a new keyword `this`. `this` keyword is very important and crucial to the understanding of JS. However, to go indepht, it will probably need a whole workshop by itself, so in this workshop we just have to understand that `this` refer to the element that this function is attached to. Let added it to our `createNewTask()` function:

```js
// ...
var checkBox = document.createElement("input");
checkBox.type = "checkbox";

checkBox.onchange = checkBoxHandler
//...
```

Now, when we change the state of the checkbox, we can see that the task will move to its correct section.

## Edit Button Handler
```js
function editButtonHandler() {
  if (this.parentNode.className == "edit-mode") {
    this.parentNode.className = "view-mode"
    let h4 = this.parentNode.children[1]
    let input = this.parentNode.children[2]
    h4.innerText = input.value
  }
  else
    this.parentNode.className = "edit-mode"
}
```

This function purpose is to allow us to change an element from `view-mode` to `edit-mode` or vice-versa. 

If we are in the `edit-mode`, it will read the value inside the `input` field, and give that value to the `h4` element.

Let's add this to our `createNewTask()`

```js
//...
var editButton = document.createElement("button");
editButton.innerText = "Edit";

editButton.onclick = editButtonHandler
//...
```

## Delete Button Handler
```js
function deleteButtonHandler() {
  let li = this.parentNode
  li.remove()
}
```

This function only main purpose is to remove the element from the HTML. This is a real and actual removal, you can check your HTML in the dev tool to see that the element has been completely removed.

And to add our final helper function to the `createNewTask()` function

```js
//...
var deleteButton = document.createElement("button");
deleteButton.innerText = "Delete"

deleteButton.onclick = deleteButtonHandler
//...
```