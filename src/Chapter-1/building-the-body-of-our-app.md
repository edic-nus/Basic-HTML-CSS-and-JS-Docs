# Building the body of our app

```html
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

  <script type="text/javascript" src="index.js"></script>
</body>
```

I know it is a bit intimidating, but let try to break it into individual section, just like in [1.2](./defining-a-basic-template.md).

## Add Item

```html
<h3>Add Item</h3>
<div>
  <input type="text" />
  <button>Add</button>
</div>
```

Here, we see a few new elements.

The `<h3>` element represents the heading for their sections. We have from `h1` to `h6` with `h1` the largest and `h6` is smallest. It is important to notice that the heading element has some predefined CSS style applied to them by default, which is what makes them differentiatable from other elements.

The `<div>` element respresents a grouping or a division. It does not do much other than acting as a container for other elements to help in grouping and oragnising all of its child elements.

The `<input>` element represents a typed data field, usually to allow the user to edit the data. It acts as what it names suggest, a field for user to input data into. Here, it has an attribute of `type` with a value of `text` to tell the browser to render this as a box that you can input text into. There are many types to an input and you can explore about all of them [here](https://html.spec.whatwg.org/multipage/input.html#the-input-element).

The `<button>` element represents a button (wow surprised!) labeled by its contents.

## Incomplete tasks

```html
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
```

So for our incomplete task we would probably want to render something that looks like a list of some kind. And fortunately, HTML have just the right elements for that:

The `<ul>` element represents an unordered list (there is also an ordered list version, try to guess what the element name might be). An unordered list will rendered all the list items with a bullet point in front.

The `<li>` element represent every children inside of it as a list item.

Here we also see a new `type` to the input which is a `checkbox`. We also see a new attributes call `value` which just attached a value to the input, but becareful as this goes by case by case basis, not every input types would be able to process the `value` attribute.


## Completed tasks

```html
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
```

The completed task is exactly the same as the incomplete tasks section except for one small detail. We would want the `input` element with `type` of value checkbox to also have the attribute `checked`.

And **TADAH**! Congratulation you have now successfuly build your To Do List app structure in HTML. It is that simple, and technically you could ship this to the web now.

But it does feel a bit lack luster isn't it ...

That is where our next chapter come into the picture.
