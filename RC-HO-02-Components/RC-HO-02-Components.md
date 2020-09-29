<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on ReactJS Components

> Purpose of the this hands-on training is to teach the students ReactJS Components.

## Outline

- Part 1 - What is Component?

- Part 2 - Class Component

- Part 3 - Function Component

- Part 4 - Rendering a ReactJS Component

- Part 5 - Component `constructor()`

- Part 6 - Transfer Data with `props` in Components

- Part 7 - Usage of Components

### Part 1 - What is Component?

---

- <a href="https://reactjs.org/docs/components-and-props.html" target="_blank">ReactJS official document</a> says about components "Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. This page provides an introduction to the idea of components".

![image](https://drive.google.com/uc?export=view&id=1v4Sk5ELQs9KDIgizxv9oQM4sYbUw7mbT)
**<p align="center">React Component</p>**

- A ReactJS component can be one of the following two types:
  > Class Component  
  > Functional Components (Stateless Components)

### Part 2 - Class Component

---

- When you defining a component in ReactJS, the name of component must start with an capital letter.

- You should `import React, { Component } from "react";`. This statement creates an inheritance to `React.Component`, and gives your component acces to `React.Component`s functions.

Syntax-1:

```js
import React, { Component } from "react";
class Navbar extends Component {
  render() {
    return <h1>Hi, I am Navbar!</h1>;
  }
}
export default Navbar; // Don’t forget to use export default!
```

Syntax-2:

```js
import React from "react";
export default class Sidebar extends React.Component {
  // Also you can import like this way
  render() {
    return <h2>Hi, I am Sidebar!</h2>;
  }
}
```

### Part 3 - Function Component

---

- `function` Components also returns HTML like `Class Components` but `Class Components` have some additional features.
- The first letter name of `function` Component must be capital letter like `Class Component`.

Syntax:

```js
import React from "react";
function Button() {
  return <div>This is a function component!</div>;
}
export default Button; // Don’t forget to use export default!
```

### Part 4 - Rendering a ReactJS Component

---

- The `ReactDOM.render()` method is used to call the `reactjs`component, it render JSX expressions to the DOM. It expects a component instance as first parameter, and a HTML element to which the DOM of the element object will be mounted.

Syntax:

```js
function NameOfComponent() {
  // Statement
}

const element = <NameOfComponent />;
ReactDOM.render(element, document.getElementById("root"));
```

### Part 5 - Component `constructor()`

---

- The `constructor()` is a method used to initialize an object's state in a class. It automatically called during the creation of an object in a class.

Syntax :

```js
class App extends Component {
  Constructor(props) {
    super(props);
  }
  // ...
}
```

- ⛔ You cannot call `setState()` method directly in the `constructor()`. You will learn more about `setState` later in this course.

### Part 6 - Transfer Data with `props` in Components

---

- You can use `props` to pass data or arguments into React Components.

Syntax :

```js
<NameOfComponent nameOfProp="value" />;
// And you can use value in another component.
<div>.... {this.props.nameOfProp}</div>;
```

```js
class Course extends React.Component {
  render() {
    return <h2>I want to go to {this.props.brand}!</h2>;
  }
}

class Person extends React.Component {
  render() {
    return (
      <div>
        <h1>Which course do you want to go?</h1>
        <Course brand="Clarusway" />
      </div>
    );
  }
}
```

---

### Part 7 - Usage of Components

---

- You can use components or component in another component whenever and how many times you want.

Syntax :

```js
class NameOfInnerComponent extends React.Component {
  render() {
    return {
      /* Statement */
    };
  }
}
class NameOfOuterComponent extends React.Component {
  render() {
    return (
      <div>
        {/* Statement */}
        <NameOfInnerComponent />
      </div>
    );
  }
}
```

- If component is in another js file, you should:

```js
import NameOfInnerComponent from "./NameOfInnerComponent";
```

**<p align="center">&#9786; Happy Coding &#9997;</p>**
