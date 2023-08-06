# Defining a basic template

In this section we will start with defining a very basic HTML template, and quickly go over what each of the section means.

First, create a new folder and name it `Todolist` (or anything you would like to honestly). Next use your Text Editor (for this workshop, VSCode is the officially supported one) and open up the folder.

Inside you Text Editor, find your workspace vertical, right click your mouse and create a new file. Name the file `index.html`. Open the file and type in the following:

```html
<html>

  <head>
    <title>Todo App</title>
    <link href='https://fonts.googleapis.com/css?family=Lato:300,400,700' rel='stylesheet' type='text/css'>
    <link rel="stylesheet" href="index.css" type="text/css" media="screen" charset="utf-8">
  </head>

  <body>
    This is a basic HTML template
    <script type="text/javascript" src="index.js"></script>
  </body>

</html>
```

You can also copy the code above by clicking the copy icon on the top right side of the code block, but I would recommend typing it out just to get the feel of it.

## \<head> section

```html
<head>
  <title>Todo App</title>
  <link href='https://fonts.googleapis.com/css?family=Lato:300,400,700' rel='stylesheet' type='text/css'>
  <link rel="stylesheet" href="index.css" type="text/css" media="screen" charset="utf-8">
</head>
```

The `<head>` element represents a collection of metadata for the Document.

The `<title>` element represents the documents's title or name. This is also the title that you would see on your tab bar when you hover over it. There can only be one `<title>` tag per document.

The `<link>` element allow authors to link their documents to other resources. For the purpose of the workshop, we do not need to know what exactly the attributes of the two `<link>` tags above do. Our concern is what in what functionality do the links provide.

```html
<link href='https://fonts.googleapis.com/css?family=Lato:300,400,700' rel='stylesheet' type='text/css'>
```

This link fetch a particular font called Lato from Google Font and download it along side with our document to be render with our website on the client side.

```html
<link rel="stylesheet" href="index.css" type="text/css" media="screen" charset="utf-8">
```

This link fetch our CSS file which we will write later on. It will then apply to the HTML for us to configure all the styling. 

## \<body> section

```html
<body>
  This is a basic HTML template
  <script type="text/javascript" src="index.js"></script>
</body>
```

The `<body>` element represents the contents of the document. There is only one of it in the document. This is where all the user content will be constructed and displayed.

The `<script>` element allows authors to include dynamic script and data blocks in their documents. So this is where our document call for our `index.js` file which we will be creating in chapter 3 to manipulate our document. You can also put the `<script>` into the `<head>` section, but it can create some issue regarding the rendering order of the HTML element, so usually for most people, they put it as the last thing in their `<body>` element.

Now that we have our basic template, let's start building the main frame for our To Do List app.