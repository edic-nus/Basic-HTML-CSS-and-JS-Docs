# Chapter 1: HTML

The way I want to try to do this is to start with the goal in mind. So by the end of this chapter, we should have something that looks somewhat like this:

```html
<html>

<head>
  <title>Todo App</title>
  <link href='https://fonts.googleapis.com/css?family=Lato:300,400,700' rel='stylesheet' type='text/css'>
  <link rel="stylesheet" href="index.css" type="text/css" media="screen" charset="utf-8">
</head>


<body>
  <div>
    <h3>Add Item</h3>
    <div>
      <input type="text" />
      <button>Add</button>
    </div>

    <h3>Todo</h3>
    <ul>
      <li>
        <input type="checkbox">
        <h4>Maybe see financial advisor</h4>
        <input type="text" value="Maybe see financial advisor">
        <button>Edit</button>
        <button>Delete</button>
      </li>

      <li>
        <input type="checkbox">
        <h4>Pay Bills Again</h4>
        <input type="text" value="Pay Bills Again">
        <button>Edit</button>
        <button>Delete</button>
      </li>
    </ul>

    <h3>Completed</h3>
    <ul>
      <li>
        <input type="checkbox" checked>
        <h4>Pay Bills</h4>
        <input type="text" value="Pay Bills">
        <button>Edit</button>
        <button>Delete</button>
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

This not the final version yet, but more like what we should have at the end of this chapter.
If you compare this with the codebase on Github, you will see that a lot is missing, and that is because all the id and class has been stripped from the HTML. But no worry, we will put them back soon.