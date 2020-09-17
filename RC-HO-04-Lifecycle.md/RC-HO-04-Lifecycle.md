<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on Component Lifecycle in ReactJS

> Purpose of the this hands-on training is to teach the students Component Lifecycle.

## Outline

- Part 1 - What is Lifecycle?

- Part 2 - Class Component

- Part 3 - Function Component

- Part 4 - Rendering a ReactJS Component

- Part 5 - Component `constructor()`

- Part 6 - Transfer Data with `props` in Components

- Part 7 - Usage of Components

### Part 1 - What is Component?

---

- You can think of lifecycle methods as the series of events that happen from the birth of a component to its death. Like every living being, components go through a cycle of birth, growth, and death.

> Mount -> Birth  
> Update -> Growth  
> Unmount -> Death

- We will learn most used React Lifecycle Methods:

1. `constructor()` Method
1. `render()` Method
1. `componentDidMount()` Method
1. `componentDidUpdate()` Method
1. `componentWillUnmount()` Method

- Main concept of <a href="https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/" target="_blank">React Component lifecycle</a>.

### Part 2 - `constructor()` Method

---

- `constructor()` method is the phase in which the component is going to start its journey. The `constructor()` in a React component is called before the component is mounted. If you want to implement the constructor for a React component, you need to call `super(props)` method before any other statement.

Syntax :

```js
Constructor(props){
     super(props);
}
```

> Example:

```js
// App.js
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      course: "Clarusway",
    };
    console.log("Constructor Method run here!");
  }

  render() {
    return (
      <div className="App">
        <h2>React Constructor Example</h2>
      </div>
    );
  }
}
export default App;
```

- &#10071; See the sequence of lifecycle components, please open the browser console.

### Part 3 - `render()` Method

---

- You will use `render()` method every class component. When the component file is called it calls the `render()` method by default because that component needs to display the HTML markup or we can say JSX syntax.

Syntax :

```js
class RenderComponent extends Component {
  render() {
    return <div>{/* Statement */}</div>;
  }
}
```

> Example

```js
// App.js
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      course: "Clarusway",
    };
    console.log("Constructor Method run here!");
  }

  render() {
    console.log("Render Method run here!");
    return (
      <div className="App">
        <h2>React Constructor Example</h2>
      </div>
    );
  }
}
export default App;
```

- When you run this code blocks, you will in the browser console:

```
Constructor Method run here!
Render Method run here!
```

### Part 4 `componentDidMount()` method

---

- As understood from the name, after all the elements of the page is rendered correctly, this method is called.

- This method is also used for integration with other JavaScript frameworks and any functions with delayed execution such as `setTimeout` or `setInterval`. You can use it to update the state so we can trigger the other lifecycle methods.

Syntax :

```js
componentDidMount() {
    {/* Statement */}
      }
```

> Example :

```js
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "Ed Benedict",
    };
    console.log("Constructor Method run here!");
  }

  getName() {
    setTimeout(() => {
      console.log("Data fetched.");
      this.setState({
        name: "Walter White",
      });
    }, 1000);
  }

  componentDidMount() {
    console.log("componentDidMount Method run here!");
    this.getName();
  }

  render() {
    console.log("Render Method run here!");
    return <div>{this.state.name}</div>;
  }
}

export default App;
```

- When you run this code blocks, you will in the browser console:

```
Constructor Method run here!
Render Method run here!
componentDidMount Method run here!
Data fetched.
Render Method run here!
```

- The `render()` method will run every time after `componentDidMount()` method.

### Part 5 - `componentDidUpdate()` Method

---

- `componentDidUpdate()` is called as soon as the updating happens. The `componentDidUpdate()` is usually used when update the DOM in response to prop or state changes.

- You can call `setState()` in this lidecycle but if you do not use `componentDidUpdate()` correctly, it can lead to an infinite loop.

Syntax :

```js
componentDidUpdate(prevProps, prevState) {
  {/* Statement */}
}
```

> Example :

```js
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "Ed Benedict",
    };
    console.log("Constructor Method run here!");
  }

  getName() {
    setTimeout(() => {
      console.log("Data fetched");
      this.setState({
        name: "Walter White",
      });
    }, 1000);
  }

  componentDidMount() {
    console.log("componentDidMount Method run here!");
    this.getName();
  }
  componentDidUpdate(prevProps, prevState) {
    console.log("componentDidUpdate Method run here!");
  }

  render() {
    console.log("Render Method run here!");
    return <div>{this.state.name}</div>;
  }
}

export default App;
/* Expected output in the browser console:
constructor Method run here!
render Method run here!
componentDidMount Method run here!
Data fetched.
render Method run here!
componentDidUpdate Method run here!
*/
```

### Part 6 - `componentWillUnmount()` Method

---

- `componentWillUnmount()` method is called just before the component is unmounted and destroyed. If there are any cleanup actions that you would need to do, this would be the right way.
- &#10071; You can not use `componentWillUnmount()` for changing the component state.
- You should not call setState() in componentWillUnmount() because the component will never be re-rendered. Once a component instance is unmounted, it will never be mounted again.

Syntax :

```js
componentWillUnmount() {
 {/* Statement */}
}
``

> Example:

```

```js
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "Ed Benedict",
    };
    console.log("Constructor Method run here!");
  }
  componentWillMount() {
    console.log("componentWillMount Method run here!");
  }

  getName() {
    setTimeout(() => {
      console.log("Data fetched");
      this.setState({
        name: "Walter White",
      });
    }, 1000);
  }

  componentDidMount() {
    console.log("componentDidMount Method run here!");
    this.getName();
  }
  componentDidUpdate(prevProps, prevState) {
    console.log("componentDidUpdate Method run here!");
  }

  render() {
    console.log("Render Method run here!");
    return <div>{this.state.name}</div>;
  }
}

export default App;

/* /* Expected output in the browser console:
constructor Method run here!
componentWillMount Method run here!
render Method run here!
componentDidMount Method run here!
Data fetched.
render Method run here!
componentDidUpdate Method run here!
*/
```
