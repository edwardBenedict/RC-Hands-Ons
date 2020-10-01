<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on ReactJS Redux

> Purpose of the this hands-on training is to teach the students ReactJS Redux
> .

## Outline

- Part 1 - What is Redux?

- Part 2 - Class Component

- Part 3 - Function Component

- Part 4 - Rendering a ReactJS Component

- Part 5 - Component `constructor()`

- Part 6 - Transfer Data with `props` in Components

- Part 7 - Usage of Components

### Part 1 - What is Redux?

---

- Redux is an open-source JavaScript library for managing application state. We can use Redux with React, Angualar. Redux allows us React components read data from a Redux store, and dispatch actions to the store to update data. With Redux, we can pass data without prop-drilling.

### Part 2 - Install Redux

---

- To use React Redux with our React app, we should:

```js
// NPM
npm install react-redux redux
// or
// Yarn
yarn add react-redux redux
```

### Part 3 - `createStore`

---

- We can create `store` with `createStore` after `import { createStore } from "redux"`.
- Also we can pass initial state to `createStore`.

```js
// src/redux/store.js
import { createStore } from "redux";
import rootReducer from "../reducers.js";

const store = createStore(rootReducer);

export default store;
```

### Part 4 - Redux `reducer`

---

- `reducer` is just a function. First parameter of `reducer` is current state and second parameter is `action`. And `reducer` is most important part of Redux.

```js
// src/redux/reducers.js
const initialState = {
  movies: [],
};

function rootReducer(state = initialState, action) {
  return state;
}

export default rootReducer;
```

### Part 5 - `action`

---

- we define actions type in javascript object. It's look like,

```js
// src/redux/actions.js
{
  type: 'ADD_MOVIE',
  payload: { title: 'Inception', id: 1 }
}
```

- In javascript object there are two properties: `type` and `payload`.
