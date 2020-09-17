<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on Events in ReactJS

> Purpose of the this hands-on training is to teach the students Events.

## Outline

- Part 1 - What is Event?

- Part 2 - `constructor()` Method

- Part 3 - `render()` Method

- Part 4 - `componentDidMount()` method

- Part 5 - `componentDidUpdate()` Method

- Part 6 - `componentWillUnmount()` Method

### Part 1 - What is Event?

---

- An event is an action that could be triggered as a result of the user action like mouse click, loading of a web page, pressing a key, window resizes, and other interactions.

Syntax :

```js
// In HTML => lowercase and paranteses end of the function name
<button nameofevent="nameOfFunction()">Clarusway</button>
// In React => camelCase and NO paranteses end of the function name
<button nameOfEvent={nameOfFunction}>Clarusway</button>
```

> Example:

```js
// App.js
import React, { Component } from "react";

export default class App extends Component {
  function handleClick() {
      alert("Clicked Clarusway Button");
    }
  render() {

    return (
      <div>
        <button onClick={handleClick}>Clarusway</button>
      </div>
    );
  }
}
```

### Part 2 - Bind `this`

---

The `this` keyword represents the component that owns the method.

Syntax :

```js
<button nameOfEvent={this.nameOfFunction}>Click</button>
```

> Example:

```js
import React from "react";

export default class App extends React.Component {
  clarusway = () => {
    alert("Welcome to the place of the bests!");
  };
  render() {
    return <button onClick={this.clarusway}>Clarusway!</button>;
  }
}
```

### Part 3 - Passing Arguments to Event

---

- You will need to pass arguments to function in your React Projects. You can send two ways:

1. Anonymous arrow functions

Syntax:

```js
nameOfFunction = () => {
  {/* statement */}
}
...
<button nameOfEvent={() => this.nameOfFunction("value")}>Button</button>
```

> Example :

```js
import React from "react";
import "./App.css";

class App extends React.Component {
  clarusway = (a) => {
    alert(a + ": Welcome to the place of the bests!");
  };
  render() {
    return <button onClick={() => this.clarusway("Edward")}>Clarusway!</button>;
  }
}

export default App;
```

2. Bind event with `this`

---

- Keep in mind that firs argument has to be `this`

```js

```
