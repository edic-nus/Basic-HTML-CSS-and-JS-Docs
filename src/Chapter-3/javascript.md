# Chapter 3: Javascript

Welcome to the last section of this introductory workshop, you have done well to get to here. Now that our To Do List app has got a facelifted, we can start thinking about maybe add the actual functionality to the app. 

As you can see, so far our HTML is not very interactive, so let start using Javascript - the last piece to modern web technology - to manipulate the DOM and add the `add`, `edit` and `delete` functionality to our To Do List app.

As per the usual routine, here the code we should have at the end of this chapter.

```js
//  Add item section
var addItemInput = document.getElementById("add-item-input");
var addItemButton = document.getElementById("add-item-button");

var incompleteTasksList = document.getElementById("incomplete-tasks");
var completedTasksHolder = document.getElementById("completed-tasks");

addItemButton.addEventListener("click", function addTask() {
  if (addItemInput.value !== "") {
    var listItem = createNewTask(addItemInput.value)
    incompleteTasksList.appendChild(listItem);
  }
  addItemInput.value = ""
})

// Todo section
function createNewTask(addValue) {
  var listItem = document.createElement("li");
  listItem.className = "view-mode"

  var checkBox = document.createElement("input");
  checkBox.type = "checkbox";
  checkBox.onchange = checkBoxHandler

  var h4 = document.createElement("h4");
  h4.innerText = addValue;

  var input = document.createElement("input");
  input.id = "edit-input";
  input.type = "text";
  input.value = addValue;

  var editButton = document.createElement("button");
  editButton.innerText = "Edit";
  editButton.onclick = editButtonHandler

  var deleteButton = document.createElement("button");
  deleteButton.innerText = "Delete"
  deleteButton.onclick = deleteButtonHandler

  listItem.appendChild(checkBox);
  listItem.appendChild(h4);
  listItem.appendChild(input);
  listItem.appendChild(editButton);
  listItem.appendChild(deleteButton);

  return listItem
}

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

function deleteButtonHandler() {
  let li = this.parentNode
  li.remove()
}

function checkBoxHandler() {
  if (this.checked == true) {
    completedTasksHolder.appendChild(this.parentNode)
  } else {
    incompleteTasksList.appendChild(this.parentNode)
  }
}

var checkBoxes = document.querySelectorAll("input[type=checkbox]");
var editButtons = document.querySelectorAll(".edit");
var deleteButtons = document.querySelectorAll(".delete");

checkBoxes.forEach(box => box.onchange = checkBoxHandler)
editButtons.forEach(button => button.onclick = editButtonHandler)
deleteButtons.forEach(button => button.onclick = deleteButtonHandler)
```

One of the thing I wanted to note is that, although Javascript is a very important and crucial part of the modern web dev experience (if not the most important one), we will not be covering indepth about all the intricacy of how javascript works, and all of its quirk and inner working. However, if you are interested in a deeper dive into the world of Javascript, please let us know and if there is enough demand, we can set up a new workshop on just Javascript.

Ok, now let's get to the cool part.