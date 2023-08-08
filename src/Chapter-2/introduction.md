# Introduction to CSS

## What is CSS?

Cascading Style Sheets or CSS is a style sheet language used for describing the presentation of a document written in a markup language such as HTML. CSS like HTML also have "versions". Nowsaday, people usually refer to the version of CSS that is widely used as CSS3. However, this is, as we have seen previously, just another buzzword.

For CSS, the proper term to refer to a version of CSS is called level. The last official level of CSS is actually 2.1. Afterward, the functionalities of CSS are splitted into what we called module and they are developed independently at different level. So there is actually no such thing as CSS3. It is just a bunch of different module at different level depending on the progress made by the CSS Working Group team. Here is the link to the [spec sheet](https://www.w3.org/Style/CSS/specs.en.html) if you wish to know more, and here is the link to a quick [reference sheet](https://www.w3schools.com/cssref/index.php) for when you are developing.

In any case, the main purpose of CSS is to allow for a level of seperation betwneen content and presentation. Anecdotally, it is similar to how the process of decoration of a building is seperated from the process of building it. CSS is only used as a way to modify how HTML elements are presented, but not how they work.

Although, in the current modern web landscape, presentation and functionality is often one and the same thing. We will see some example of this later, on how the presentation can indicate a lot more to the user about the functionality of an element, than the element itself.

## Terminology

In CSS, there are only a few terminoligies. Two most important one are:

**Selector:**

```css
#id {}
.class {}
#id:hover {}
```

These are selectors, which as the name suggested, used to select the specific HTML element that we want to sytle.

**Properties:**

```css
{
  margin: 0;
  padding: 0;
}
```

Inside the brackets, we have properties `margin` and `padding` with values of `0`.

## Basic syntax

CSS is a an art of experimentation, so there is really no way to learn it other than by practicing and experimenting. Here is just some very basic CSS sytax for you to start with:

To describe a properties, we specify the name of the properties follow by a colon and the value of that properties:
```css
properties: value
```

To target an HTML element in general, we just use the name of the element as a selector:

```css
div {
  /* properties inside here*/
}
```

To target html element with an id, we use a `#` and then the name of the id folowed by curly bracket
```css
#name {
  /* properties inside here*/
}
```

To target html element with a class, we use a `.` in place of `#`:

```css
.name {
  /* properties inside here*/
}
```

To target some certain state of a HTML element (we also call this pseudo-class) , we do:

```css
input:hover {
  /* properties inside here*/
}
```

To target a pseudo-element (we won't be covering this in this workshop) of a CSS element, we do:

```css
div::after {
  /* properties inside here*/
}
```

To comment we use `/*` and close off with `*/`:
```css
/* This is a comment */
```

And that is all the syntax that you need to know for now for CSS.

## TOP to BOTTOM styling

If there is one thing you should remember about CSS, so that you can avoid a lot of pain in the future is this one:

> Style is applied from TOP to BOTTOM

To put it simply:

```css
body {
  margin: 10px;
  padding: 10px;
  color: red;
  margin: 20px
}
```
What would the final value of `margin` be?

```css
body {
  margin: 10px;
  padding: 10px;
  color: red;
}

body {
  padding: 0px;
}

body {
  color: green;
}
```

What would be the final value of `margin`, `padding` and `color` be?

You can declare the same selectors and properties multiple time through out your CSS, but only the last declaration will take effect.