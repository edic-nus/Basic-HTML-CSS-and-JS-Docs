# Prepare our HTML

To be able to syle our HTML effectively, we need to give the HTML some identifying attribute, so that we can target them and style them correctly using our CSS. Our HTML body should looks like below:

```html
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

  <script type="text/javascript" src="index.js"></script>
</body>
```

Don't worry we will go over each section in more detailed in the next pages. We will just use this page as a reference of what our HTML should looks like at the end of this chapter.