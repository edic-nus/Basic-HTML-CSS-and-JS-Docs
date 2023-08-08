# Chapter 2: CSS

Ok, it is great that we have managed to create our HTML template, but we can't really bare to look at it like this. It has not taste, or some my said no "class" at all (pun intended).

So now let try to add some spice to our To Do List app.

*Disclaimer: I am a terrible designer, I only try to make it looks nicer than the barebone version. Please try to one up me in the future and submit your design to the Github repository for demonstration purpose.*

And as usual, here is the full code view.

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

It might looks like a lot... because it is a lot. As part of my experience, I usually find CSS file to be the longest and hardest to read, so it is usually my last priority, and prefer to use CSS-in-JS (a more common format for modern web dev using library or framework such as Angular, React, Vue, ...) isntead. But in any case, we will try to give our HTML a make over as best as we can.