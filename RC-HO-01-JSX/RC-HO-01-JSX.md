<p>Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on ReactJS JSX

> Purpose of the this hands-on training is to teach the students ReactJS JSX.

## Outline

- Part 1 - What is JSX?

- Part 2 - ReactJS without JSX vs with JSX

- Part 3 - Expressions In JSX

- Part 4 - Using HTML blocks in JSX

- Part 5 - Comments in JSX

### Part 1 - What is JSX?

---

- React utilizes features of modern JavaScript for many of its patterns. Its biggest departure from JavaScript comes with the use of <a href="https://reactjs.org/docs/introducing-jsx.html" target="_blank">JSX</a> syntax. JSX extends JavaScript's syntax so that HTML-like code can live alongside it. For example:

Syntax :

```js
let motto = <h1>Way to Reinvent Yoursel!</h1>;
```

### Part 2 - ReactJS without JSX vs with JSX

---

- React doesn’t require using **JSX**, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.

Syntax without JSX:

```js
const myelement = React.createElement(
  "h1",
  { className: "top" },
  "I do not use JSX!"
);

ReactDOM.render(myelement, document.getElementById("root"));
```

Syntax with JSX:

```js
const myelement = <h1 className="top">I Love JSX!</h1>;

ReactDOM.render(myelement, document.getElementById("root"));
```

- JSX allows us to write HTML directly within the JavaScript code.

- And if you need to use nested elements, coding without JS will be so complicated.

### Part 3 - Expressions In JSX

---

- JSX will only accept expressions between curly braces(`{}`). The curly braces tell our transpiler to process what is between the curly braces as normal JavaScript.

Syntax :

```js
let nameOfVariable = "value";
<div>Population: {nameOfVariable} </div>;
// or
let imgPath = "....";
let element = <img src={imgPath} alt="image" />;
```

> Example:

```js
import React from "react";

const shape = "Rectangle";
const specifications = {
  length: 8,
  width: 29,
  getArea: function () {
    return this.length * this.width;
  },
};
const getResult = (specifications) =>
  `length: ${specifications.length}(cm) * 
   width : ${specifications.width}(cm) => 
   area : ${specifications.getArea()}(cm2)`;

export default function Vehicles() {
  return (
    <div>
      <p>{shape}</p>
      <p>{getResult(specifications)}</p>
    </div>
  );
}
// Expected Output :
// Rectangle
// length: 8(cm) * width : 29(cm) => area : 232(cm2)
```

- ⛔ If we do not `import React from "react";` it will give this error:  
  `'React' must be in scope when using JSX react/react-in-jsx-scope`.

### Part 4 - Using HTML blocks in JSX

---

- You can write HTML elements with inside parentheses:

```js
const best = (
  <ul>
    <li>Tesla</li>
    <li>Clarusway</li>
    <li>IBM</li>
  </ul>
);
```

- The HTML code must be wrapped in **ONE** top level element.(Mostly `<div>...</div>`tag.)
- JSX follows XML rules, and therefore HTML elements must be properly closed.(`<img src="..." />`)

### Part 5 - Comments in JSX

---

- JSX allows us to use comments that begin with `/*` and ends with `*/` and wrapping them in curly braces `{}` just like in the case of JSX expressions.

Syntax:

```js
<div>
  <h1 className="hello">Welcome to Calrusway</h1>
  {/* This is a comment in JSX */}
</div>
```

**<p align="center">&#9786; Happy Coding &#9997;</p>**
