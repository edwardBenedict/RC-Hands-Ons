<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On React Router

> Purpose of the this hands-on training is to teach the students React Router.

## Outline

- Part 1 - What is Router?

- Part 2 - Install React Router

- Part 3 - Create an `App.js` Component

- Part 4 - Let's Create Three Component

- Part 5 - The Router `<BrowserRouter>`

- Part 6 - Add The Components and Routes In The `App.js` File

### Part 1 - What is React Router?

---

- React Router is the standard routing library for React. From the <a href="https://reactrouter.com/">React Router docs</a>:
  > Components are the heart of React's powerful, declarative programming model. React Router is a collection of navigational components that compose declaratively with your application.

### Part 2 - Install React Router

---

- Firstly you should have a react app or you can create a new one:

```js
npx create-react-app react-router-app
// or
yarn create react-app react-router-app
```

- And we can install React Router with `npm` or `yarn`. Since we are building a web app, we will use `react-router-dom` in this hands-on.

```js
npm install react-router-dom
// or
yarn add react-router-dom
```

### Part 3 - Create an `App.js` Component

---

In `src` directory, create `App.js` component file.

```js
// App.js

import React, { Component } from "react";

export default class App extends Component {
  render() {
    return (
      <div>
        <h2>Welcome to React Router Hands-On</h2>
      </div>
    );
  }
}
```

And, in the index.js;

```js
// index.js

import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("app"));
```

### Part 4 - Let's Create Three Component

---

- Create `Home.js` in the `src/components/` directory.

```js
// Home.js

import React, { Component } from "react";

export default class Home extends Component {
  render() {
    return (
      <div>
        <h2>This is Home Page </h2>
      </div>
    );
  }
}
```

- Create second components as `AboutUs.js` in the `src/components/` directory.

```js
// AboutUs.js

import React, { Component } from "react";

export default class AboutUs extends Component {
  render() {
    return (
      <div>
        <h2>This is About Us Page</h2>
      </div>
    );
  }
}
```

- Lastly, create third one as `ContactUs.js` in the `src/components/` directory.

```js
// ContactUs.js

import React, { Component } from "react";

export default class ContactUs extends Component {
  render() {
    return (
      <div>
        <h2>This is Contact Us Page.</h2>
      </div>
    );
  }
}
```

### Part 5 - The Router `<BrowserRouter>`

---

A `<Router>` that uses the **HTML5** history API (`pushState`, `replaceState` and the `popstate` event) to keep your UI in sync with the URL. We will use alias for `<BrowserRouter>` as `<Router>`.

```js
// App.js

import React, { Component } from "react";
import { BrowserRouter as Router } from "react-router-dom";

export default class App extends Component {
  render() {
    return (
      <Router>
        <div>
          <h2>Welcome to React Router Hands-On</h2>
        </div>
      </Router>
    );
  }
}
```

### Part 6 - Add The Components and Routes In The `App.js` File

---

```js
// App.js

import React, { Component } from "react";
import { BrowserRouter as Router, Switch, Route, Link } from "react-router-dom";
import Home from "./components/Home";
import AboutUs from "./components/AboutUs";
import ContactUs from "./components/ContactUs";
import "./styles.css";

class App extends Component {
  render() {
    return (
      <Router>
        <div className="App">
          <h2>Welcome to React Router Hands-On</h2>
          <nav className="navbar navbar-expand-lg navbar-light bg-light">
            <ul className="navbar-nav mr-auto">
              <li>
                <Link to={"/"} className="nav-link">
                  Home
                </Link>
              </li>
              <li>
                <Link to={"/contactus"} className="nav-link">
                  Contact Us
                </Link>
              </li>
              <li>
                <Link to={"/aboutus"} className="nav-link">
                  About Us
                </Link>
              </li>
            </ul>
          </nav>
          <hr />
          <Switch>
            <Route exact path="/" component={Home} />
            <Route path="/contactus" component={ContactUs} />
            <Route path="/aboutus" component={AboutUs} />
          </Switch>
        </div>
      </Router>
    );
  }
}

export default App;
```

- &#10071; In the contactus url `/` matches both `/` and `/contactus`. Therefore, both the routes are matched and rendered. How do we avoid that? You should pass the `exact= {true}` props to the router with `path='/'`:

```js
<Route exact={true} path="/" component={HomePage} />
```

- Click here to see <a href="https://codesandbox.io/s/react-router-app-88izz?file=/src/App.js">React Router Example</a>.

```
react-router-app
├── public
│     └── index.html
├── src
│    ├── components
│    │       ├── Home.js
│    │       ├── ContactUs.js
│    │       └── AboutUs.js
│    ├── App.js
│    ├── index.js
│    └── styles.css
└── package.json
```

**<p align="center">&#9786; Happy Coding &#9997;</p>**
