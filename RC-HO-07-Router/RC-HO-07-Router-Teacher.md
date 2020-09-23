<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-On React Router

> Purpose of the this hands-on training is to teach the students React Router.

## Outline

- Part 1 - What is Router?

- Part 2 - Install React Router

- Part 3 - Passing Arguments to Event

### Part 1 - What is React Router?

---

- React Router is the standard routing library for React.From the <a href="https://reactrouter.com/">React Router docs</a>:
  > Components are the heart of React's powerful, declarative programming model. React Router is a collection of navigational components that compose declaratively with your application.

### Part 2 - Install React Router

---

- Firstly you should have a react app or you can create a new one:

```js
npx create-react-app react-router-app
cd react-router-app
```

- And we can install React Router with `npm` or `yarn`. Since we are building a web app, we will use `react-router-dom` in this hands-on.

```
npm install react-router-dom
```

### Part 3 - Routing

---

- Routing is the process of keeping the browser URL in sync with what’s being rendered on the page. You can go any component with `<Route />` like this way.

Syntax :

```js
<Route path="/nameofcomponent" component={NameOfComponent} />
// for example
<Route path="/" component={HomePage} />
<Route path="/contact" component={Contact} />
```

```js
import React from "react";
import { BrowserRouter as Router, Switch, Route, Link } from "react-router-dom";

export default function App() {
  return (
    <Router>
      <div className="App">
        <nav>
          <ul>
            <li>
              <Link to="/">Home Page</Link>
            </li>
            <li>
              <Link to="/about">About Us</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>

        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/contact">
            <Contact />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}

function Home() {
  return <h2>Home</h2>;
}

function About() {
  return <h2>About Us</h2>;
}

function Contact() {
  return <h2>Contact</h2>;
}
```

- &#10071; In the contact url `/` matches both `/` and `/contact`. Therefore, both the routes are matched and rendered. How do we avoid that? You should pass the `exact= {true}` props to the router with `path='/'`:

```js
<Route exact={true} path="/" component={HomePage} />
```

- In React sense, you should use React Components for all page in another `js` file.

- <a href="https://codesandbox.io/s/react-router-app-01-otqhb?file=/src/App.js">React Router Example</a>

```
react-router-app
├── .gitignore
├── package.json
├── public
│ ├── favicon.ico
│ ├── index.html
│ └── manifest.json
├── README.md
├── src
│ ├── App.css
│ ├── App.js
│ ├── App.test.js
│ ├── index.css
│ ├── index.js
│ ├── logo.svg
│ └── registerServiceWorker.js
└── package.lock.json
```

**<p align="center">&#9786; Happy Coding &#9997;</p>**
