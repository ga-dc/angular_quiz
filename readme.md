# Quiz Week 10

## Instructions

1. Fork this repo.
- Clone your fork.
- Fill in your answers by writing the appropriate area, or placing an 'x' in the square brackets for multiple-choice questions.
- Add/Commit/Push your changes to Github.
- Open a pull request.

## Question 1

You're given a blank file called `blogpost.module.js`. Update the file so that it instantiates a new Angular module called `BlogPost` that takes `ui.router` as a dependency. Use Angular code style conventions.

**Your answer:**
```js
"use strict";

(function(){
  angular
  .module("BlogPost", [
    "ui.router"
  ]);
}());
```

## Question 2

Given a custom directive whose `link` function contains the line:

```js
scope.status = "Click";
```

Which *one* of the following buttons would *not* be displayed?

```html
[ ] A: <button data-ng-if="status">Click</button>
[ ] B: <button data-ng-show="status">Click</button>
[x] C: <button data-ng-hide="status">Click</button>
[ ] D: <button>{{status}}</button>
```

## Question 3

One button below has an `ng-click` attribute; the other has `data-ng-click` instead. How does this affect them?

```html
<button ng-click="create()">Click</button>
<button data-ng-click="create()">Click</button>
```

**Your answer:**

> It doesn't affect them. It only affects whether the HTML will validate: the second will, the first will not.

## Question 4

Which of the following is the most correct? **Explain your answer.**

**Your answer:**

> **A** is the most correct. The `ng-app` directive should be attached to an element that contains all other Angular directives.

### A:
```html
<html data-ng-app="myapp">
  <head>
    <title>My app</title>
  </head>
  <body>
    <h1><a data-ui-sref="index">My App</a></h1>
    <div></div>
  </body>
</html>
```

### B:
```html
<html> 
  <head data-ng-app="myapp">
    <title>My app</title>
  </head>
  <body>
    <h1><a data-ui-sref="index">My App</a></h1>
    <div></div>
  </body>
</html>
```

### C:
```html
<html> 
  <head>
    <title>My app</title>
  </head>
  <body>
    <h1><a data-ui-sref="index">My App</a></h1>
    <div data-ng-app="myapp"></div>
  </body>
</html>
```

## Question 5

> A change to the view updates the model without a page refresh. A change to the model updates the view without a page refres.

Which one of the following concepts does this best illustrate?

```
[ ] A: Modularity
[ ] B: MVC
[x] C: Two-way data-binding
[ ] D: Separation of concerns
```

## Question 6

What is an IIFE, and why do we use them?

**Your answer:**

> An Immediately-Invoked Function Expression is a function that calls itself as soon as it's defined, and then isn't called again. It's useful because of closure: variables defined inside it won't exist outside it, and so can't clutter the global scope.

## Question 7

What is the `ui-sref` directive, and how is it used?

**Your answer:**

> The `s` in `sref` stands for "state". An Angular state is a URL with an attached template and controller. `ui-sref` is used to dynamically generate links to different states.

## Question 8

Which line in the following code snippet will throw an error? **Explain your answer.**

**Your answer:**

> Line 3 will throw an error. `use strict` prevents you from using any variables without declaring them first with `var`. `i` hasn't been declared.

```js
/*1*/ "use strict";
/*2*/ var max = 100;
/*3*/ for(i = 1; i < max; i++){
/*4*/   if(i % 15 == 0) console.log("FizzBuzz");
/*5*/   else if(i % 3 == 0) console.log("Fizz");
/*6*/   else if(i % 5 == 0) console.log("Buzz");
/*7*/   else console.log(i);
/*8*/ }
```

## Question 9

You have defined a custom directive called called `my-directive`. You can include a custom directive in a template in four different ways. Demonstrate **two** of these four.

**Your answer:**
```html
<my-directive></my-directive>

<div data-my-directive></div>

<div class="my-directive"></div>

<!-- directive:my-directive -->
```

## Question 10

Of the three following options, which is the most "correct" way of organizing the files that make up an Angular app? Why is this option considered "better" than the other two?

**Your answer:**

> **B** is correct. Angular is made up of templates and components that are very closely-linked. In this layout, related components are listed right next to each other in alphabetical order.

> **A** and **C** would require a lot of jumping from folder to folder because they don't reflect the intertwinedness of HTML and JS in Angular. **C** does not reflect the "one view, one controller" paradigm.

### A:
```
/js
  app.js
  controllers/
    artist_index.js
    artist_show.js
  directives/
    artist_form.js
    song_form.js
  views/
    artist_index.html
    artist_show.html
    artist_form.html
    song_form.html
```

### B:
```
/js
  app.js
  artists/
    index.controller.js
    index.html
    show.controller.js
    show.html
    form.directive.js
    form.html
  songs/
    form.html
    form.directive.html
```

### C:
```
/js
  app.js
  controllers/
    artists_controller.js
  directives/
    songs_directive.js
/html
  artists/
    index.html
    show.html
    form.html
  songs/
    form.html
```

