<p >Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on Styling in ReactJS

> Purpose of the this hands-on training is to teach the students Styling in ReactJS.

## Outline

- Part 1 - Styling in ReactJS

- Part 2 - Inline CSS

- Part 3 - CSS Stylesheet

- Part 4 - CSS Modules

- Part 5 - SASS

- Part 6 - Styled Components

### Part 1 - What is Component?

---

- There is a famous saying, _"It is the box, that helps to sell the jewelry"_.
- Styling is the one of the most important part of the Front-End. In modern React, there are many ways to style a React application with CSS.

- We will learn the following two types for styling ReactJS:
  > Inline CSS  
  > CSS Stylesheet
  > CSS Modules
  > SASS
  > Styled Components

### Part 2 - Inline CSS

---

- Style attributes in ReactJS should be used **cameslCased** properties rather than CSS **kebab-case**. And to style an element with the inline style attribute, the value must be a JavaScript object. Another way you can create a variable that stores style properties and then pass it to the element.

Syntax :

```js
<div style={{nameOfProperty: "value"}}></div>
<h1 style={{nameOfProperty: number }}></h1>
```

> Example :

```js
export default class Button extends React.Component {
  render() {
    const anotherWay = {
      color: "wheat",
      backgroundColor: "limegreen",
      height: "70vh",
    };
    return (
      <div>
        <h1 style={{ color: "lightblue", fontSize: 32 }}>
          Styling an element is not hard!
        </h1>
        <div style={anotherWay}>Another way!</div>;
      </div>
    );
  }
}
```

- &#10071; Do not forget to use double braces (`{{}}`).

### Part 3 - CSS Stylesheet

---

- The most basic and most used way is write a plain CSS Stylesheet. And you can import it to ReactJS file:

Syntax :

```js
import "./style.css";
```

> Example :

```css
/* style.css */
.button {
  cursor: pointer;
  border: 1px solid #a5b1c2;
  background-color: #d1d8e0;
  padding: 8px;
  min-width: 64px;
  color: #4b6584;

  transition: all 0.8s ease-in;
}

.button:hover {
  background: #4b6584;
  color: #d1d8e0;
}
```

```js
// App.js
import React from "react";
import "./style.css";

export default function App({ items, onClick }) {
  return (
    <ul>
      <button className="button">Click Here!</button>
    </ul>
  );
}
```

### Part 4 - CSS Modules

---

- Also you use use CSS Modules for adding styles to your application. A CSS Module is a CSS file in which all class names and animation names are scoped locally- by default.

Syntax :

```js
import styles from "./style.module.css";
<div className={styles.property}>CSS Modules</div>;
```

> Example :

```css
/* style.module.css */
.outerDiv {
  border-color: #00b894;
  border: 10px solid #ff7675;
  border-radius: 10px;
  width: 50%;
  margin: 25%;
}
.innerDiv {
  padding: 15px;
  background-color: #636e72;
  color: wheat;
  text-align: center;
  font-size: 3rem;
}
```

```js
// App.js
import React from "react";
import styles from "./style.module.css";

const App = () => (
  <div className={styles.outerDiv}>
    <div className={styles.innerDiv}>CSS Modules</div>
  </div>
);

export default App;
```
