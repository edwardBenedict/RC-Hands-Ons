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

### PArt 2 - Bind `this`

---
