<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On React Context

> Purpose of the this hands-on training is to teach the students React Context.

## Outline

- Part 1 - What is React Context?

- Part 2 - Install React Router

- Part 3 - Create an `App.js` Component

- Part 4 - Let's Create Three Component

- Part 5 - The Router `<BrowserRouter>`

- Part 6 - Add The Components and Routes In The `App.js` File

### Part 1 - What is React Context?

---

- React Context allows us to pass data through the component tree without having to pass props down manually at every level. From the <a href="https://reactrouter.com/">React docs</a>:

  > In a typical React application, data is passed top-down (parent to child) via props, but this can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.

- We should import `useContext`:

```js
import React, { useContext } from "react";
```

### Part 2 - `createContext`

---

- You can import `createContext` or you can use dot notation(`React.createContext`)

```js
import React, { createContext } from "react";
const ExampleContext = createContext(defaultValue);
// or
import React from "react";
const ExampleContext2 = React.createContext(defaultValue);
```

### Part 3 - `Context.Provider`

---

- After `createContext`, `Context.Provider` allows us to pass props to consuming components.

Syntax:

```js
<ExampleContext.Provider value={/* value or values(in array) */}
```

### Part 4 - `Context.Consumer`

---

- `Context.Consumer` allows us to use the value at any component, whichever component subscribes to it.

Syntax :

```js
<ExampleContext.Consumer>{value}</ExampleContext.Consumer>
```

- Click for [Context Example](https://codesandbox.io/s/react-context-app-t9wf5?file=/src/App.js){:target="_blank" rel="noopener"}.

**<p align="center">&#9786; Happy Coding &#9997;</p>**
