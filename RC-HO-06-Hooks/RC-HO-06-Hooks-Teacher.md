<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On React Hooks

> Purpose of the this hands-on training is to teach the students React Hooks.

## Outline

- Part 1 - What is Hook?

- Part 2 - Bind `this`

- Part 3 - Passing Arguments to Event

### Part 1 - What is Hook?

---

- "Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes. (We don’t recommend rewriting your existing components overnight but you can start using Hooks in the new ones if you’d like.)" saying <a href="https://reactjs.org/docs/hooks-overview.html">React Official Docs</a>.
- In the past, functional components were nice to use, since they were less verbose, but they were quite limited.

- Using the React Hooks, you should import them from React:

```js
import React, { useState, useEffect, useContext, ... } from "react";
```

- React Hooks do not contain any breaking changes. You can keep use `class` components or `function` with hooks.
-

### Part 2 - State Hook (`useState`)

---

- Before React Hooks, we should write `this.setState()` in `class component`.

```js
import React, { Component } from "react";

export default class Button extends Component {
  constructor() {
    super();
    this.state = { output: "Click for BEST!" };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(() => {
      return { output: "Clarusway" };
    });
  }

  render() {
    const { output } = this.state;
    return <button onClick={this.handleClick}>{output}</button>;
  }
}
```

- With React Hook, we can update state without `setState()` and `class component`.

- Firstly, we should import most used hook, `useState`:

```js
import React, { useState } from "react";
```

- And we should define two variables. You can give a name whatever you want, but best practice is `name` and `setName` variable name.

```js
const [output, setOutput] = useState("Best");
```

- The `best` argument passed to `useState` is the initial state.

- So with hooks, we can write previous example like this way.

```js
import React, { useState } from "react";

export default function Button() {
  const [output, setOutput] = useState("Click for BEST!");

  return <button onClick={() => setOutput("Clarusway!")}>{output}</button>;
}
```

### Part 3 - Effect Hook (`useEffect`)

- Effect Hooks can be used for fetching data.

```js
import React, { useState, useEffect } from "react";

export default function DataLoader() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []); // <= This array prevent infinite loop

  return (
    <div>
      {data.map((el) => (
        <p key={el.id}>
          {el.id}. {el.name}
        </p>
      ))}
    </div>
  );
}
```

- We can use `setData` instead of calling `this.setState`.
- In the array(`[]`) at the end of the `useEffect`, we can write dependecies.When the dependencies are changed, the `useEffect` will run again. Otherwise the array is empty, the effect runs only once.

- We dont have an argument in array, but if we have an argument like `[customerId]`, it will run the certain value(`customerId`) has changed between the component re-renders.

### Part - Context Hook (`useContext`)

---

- With the `useContext`, you dont need to **prop-drilling** anymore. Instead of passing local data around and through several layers of components, it takes a step back to create global state, which is extremely useful for data that needs to be shared across components (data such as themes, authentication, etc.)

```js
// src/ThemeContext.js
import React from "react";

const ThemeContext = React.createContext(null);

export default ThemeContext;
```

> Example

1.<a href="https://codesandbox.io/s/without-usecontext-0f8ek">
Without useContext</a>

2.<a href="https://codesandbox.io/s/usecontextpractice-lo5c6">
With useContext</a>
**<p align="center">&#9786; Happy Coding &#9997;</p>**
