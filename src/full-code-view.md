# Full code view

## HTML
`index.html`:
```html
<html>

<head>
  <title>Todo App</title>
  <link href='https://fonts.googleapis.com/css?family=Lato:300,400,700' rel='stylesheet' type='text/css'>
  <link rel="stylesheet" href="index.css" type="text/css" media="screen" charset="utf-8">
</head>


<body>
  <div class="container">
    <h3>Add Item</h3>
    <div class="add-item-wrapper">
      <input id="add-item-input" type="text" />
      <button id="add-item-button">Add</button>
    </div>

    <h3>Todo</h3>
    <ul id="incomplete-tasks">
      <li class="view-mode">
        <input type="checkbox">
        <h4>Maybe see financial advisor</h4>
        <input id="edit-input" type="text" value="Maybe see financial advisor">
        <button class="edit">Edit</button>
        <button class="delete">Delete</button>
      </li>

      <li class="edit-mode">
        <input type="checkbox">
        <h4>Pay Bills Again</h4>
        <input id="edit-input" type="text" value="Pay Bills Again">
        <button class="edit">Edit</button>
        <button class="delete">Delete</button>
      </li>
    </ul>

    <h3>Completed</h3>
    <ul id="completed-tasks">
      <li class="view-mode">
        <input type="checkbox" checked>
        <h4>Pay Bills</h4>
        <input id="edit-input" type="text" value="Pay Bills">
        <button class="edit">Edit</button>
        <button class="delete">Delete</button>
      </li>
    </ul>
  </div>

  <script>
    console.log("Hi this is an example of JS code in HTML")
  </script>

  <script type="text/javascript" src="index.js"></script>
</body>

</html>
```

`index.css`:

```css
body {
  background: "mistyrose";
  color: #333;
  font-family: Lato, sans-serif;
  margin: 0;
  padding: 0;
}

.container {
  display: block;
  width: 60%;
  margin: 100px auto 0;
}

h3 {
  color: #333;
  font-weight: 700;
  font-size: 15px;
  border-bottom: 2px solid #333;
  padding: 30px 0 10px;
  margin: 0;
  text-transform: uppercase;
  display: block
}

button {
  background: mistyrose;
  border-radius: 1rem;
  padding: 0 1rem;
  margin-left: 1rem;
  height: 2rem;
  cursor: pointer;
}

input {
  margin-right: 1rem;
  font-size: 18px;
  line-height: 18px;
  height: 2rem;
  padding: 10px;
  border: 1px solid #ddd;
  background: #fff;
  border-radius: 6px;
  font-family: Lato, sans-serif;
  color: #888;
}

input:focus-visible,
input:hover {
  outline: transparent;
  border: 1px solid pink;
}

ul {
  margin: 0;
  padding: 0;
}

/* Add item */
.add-item-wrapper {
  display: flex;
  align-items: center;
  margin-top: 1rem;
}

/* Edit item */
.view-mode,.edit-mode {
  display: flex;
  align-items: center;
}

.view-mode #edit-input {
  display: none;
}

.edit-mode h4 {
  display: none;
}

/* Complete item */
#completed-tasks h4{
  text-decoration: line-through;
}
```

`index.js`:

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