<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On Events in ReactJS

> Purpose of the this hands-on training is to teach the students Events.

## Outline

- Part 1 - What is Event?

- Part 2 - Bind `this`

- Part 3 - Passing Arguments to Event

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
<button nameOfEvent={() => this.nameOfFunction("argument")}>Button</button>
```

> Example :

```js
import React from "react";

class App extends React.Component {
  clarusway = (name) => {
    alert(name + ": Welcome to the place of the bests!");
  };
  render() {
    return <button onClick={() => this.clarusway("Edward")}>Clarusway!</button>;
  }
}

export default App;
```

2. Bind event with `this`

---

- Keep in mind that first argument has to be `this`

Syntax :

```js
<button nameOfEvent={this.nameOfFunction.bind(this, "argument")}>Click</button>
```

> Example :

```js
import React from "react";

class App extends React.Component {
  clarusway = (name) => {
    alert(name + ": Welcome to the place of the bests!");
  };
  render() {
    return (
      <button onClick={this.clarusway.bind(this, "Walter")}>Clarusway!</button>
    );
  }
}

export default App;
```

- &#10071; If you send arguments without using the `bind` method, `(this.clarusway(this, "Walter")` instead of `this.clarusway.bind(this, "Walter"))`, the shoot function will be executed when the page is loaded instead of waiting for the button to be clicked.

---

- &#9889; We used `<button>` tag in this hands-on, but you can use others which you want.
