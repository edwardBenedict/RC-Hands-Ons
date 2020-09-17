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

1. `render()` Method
1. `componentDidMount()` Method
1. `componentDidUpdate()` Method
1. `componentWillUnmount()` Method

- Main concept of <a href="https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/" target="_blank">React Component lifecycle</a>.

- says

### Part 2 - `render()` Method

---

- You can see `render()` method every class component.

Syntax :

```js
class RenderComponent extends Component {
  render() {
    return <div>{/* Statement */}</div>;
  }
}
```