<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On React Hooks

> Purpose of the this hands-on training is to teach the students React Hooks.

## Outline

- Part 1 - What is Hooks?

- Part 2 - Install React Router

- Part 3 - Create an `App.js` Component

- Part 4 - Let's Create Three Component

- Part 5 - The Router `<BrowserRouter>`

- Part 6 - Add The Components and Routes In The `App.js` File

### Part 1 - What is React Hooks?

---

- With React Hooks in-built functions, React developers use state and lifecycle methods inside functional components.

- There are 10 built-in hooks, that was come with React 16.8 but commonly used hooks are:

- `useState()`
- `useEffect()`
- `useContext()`
- `useReducer()`

### Part 2 - Import Hooks

---

- We should import React Hooks for using them.

```js
import { useState, useContext, useEffect, useReducer } from "react";
```

- You can import anyone you need.

### Part 3 - `useState` Hooks

---

- Before `useState` Hook, you can mutate internal state with `this.setState`.

```js
import React, { Component } from "react";

export default class Button extends Component {
  constructor() {
    super();
    this.state = { text: "Click Button" };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(() => {
      return { text: "Been clicked!" };
    });
  }

  render() {
    const { text } = this.state;
    return <button onClick={this.handleClick}>{text}</button>;
  }
}
```

- With React Hooks, you can do this operation without an ES6 class.

- Firstly, you should import `useState`:

```js
import React, { useState } from "react";
```

- After that;

```js
const [text, setText] = useState("Click Button");
```

- The names(`text`,`setText`) above can be anything you want, it doesn't matter for React. Commonly used like this way `name`, `setName`.

- In this example, `"Click Button"` is initial state.

```js
import React, { useState } from "react";

export default function Button() {
  const [text, setText] = useState("Click Button");

  return <button onClick={() => setText("Been clicked!")}>{text}</button>;
}
```

- You can mutate `text` using `setText`.

**<p align="center">&#9786; Happy Coding &#9997;</p>**
