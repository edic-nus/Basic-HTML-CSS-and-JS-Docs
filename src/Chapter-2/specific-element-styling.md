# Specific element styling

Now let focus more on how to target specific element or group of elements on our HTML to style them. Remember the important rule of CSS: **TOP to BOTTOM**.

```css
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

Let dissect some special syntax here a bit more.

## Selectors of same style

```css
.view-mode,.edit-mode {
  display: flex;
  align-items: center;
}
```

The comma `,` indicates that both the class `.view-mode` and `.edit-mode` should use the style defined as follow. You can use this for any kind of selector that you want to give the same styling to, so you do not have to write the same style over and over again. One of the core principles of programming which is **DRY (Don't Repeat Yourself)**.

## Selectors specificity
```css
.view-mode #edit-input {
  display: none;
}

.edit-mode h4 {
  display: none;
}

#completed-tasks h4{
  text-decoration: line-through;
}
```

Here, we get to see how the CSS specificity rule works. In the first declaration, it will first target every element with the class `.view-mode` and then target all the element with the `id` of `edit-input` which in our case would be:

```html
<input id="edit-input" type="text" value="Maybe see financial advisor">

<input id="edit-input" type="text" value="Pay Bills">
```

You can see that the element

```html
<input id="edit-input" type="text" value="Pay Bills Again"> 
```

is not included, because its parent element which is `li` is not of class `view-mode` it is of class `edit-mode`

Here we want to make the input field to not be displayed when we are not in the edit mode (or the `edit-mode` in term of class) so we use `display: none`. However, it is worth mentioning that `display: none` **DOES NOT DELTETE THE ELEMENT**, it only make the elements go invisible. A rule of thumb as mentioned before is that **CSS only modified the presentation**, not the actual structure of the HTML.

Similarly, we do not want to see the `h4` element when in the edit mode, because that would be unecessary. So we can make it not go invisible with:

```css
.edit-mode h4 {
  display: none;
}
```

And finally, we want every `h4` in the Complete tasks section to be crossed out. To do that we just have to simply do the following:

```css
#completed-tasks h4{
  text-decoration: line-through;
}
```

And with that, Congratulation, you have finished styling your HTML!!!

Doesn't it look much nicer now? 
*(Ok maybe not the best looking To Do List out there, but definitely way better than from our starting point)*