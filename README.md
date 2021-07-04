# **React**

![](https://i.imgur.com/NYCkGlj.png)

---
# Learning Outcomes:
- What is React
- Where we can use React?
- How React Work?
- Why to Use React?
- React Component
- React Props
- React State


---


#  What is React?
**React** is a free and open-source front-end JavaScript library for building user interfaces or UI components. It is maintained by **Facebook** and a community of individual developers and companies. It lets developers compose complex UIs from small and isolated pieces of code called “components”.

</br>

# Where we can use React?
1. Web Application using **React.js**.
2. Mobile Application using **React Native**. 

</br>

# How React Work?
![](https://i.imgur.com/dp4VVIv.png)

</br>

# Why to Use React?
1. Easy to Learn and USe
2. Creating Dynamic Web Applications Becomes Easier
3. Reusable Components
4. Performance Enhancement
5. The Benefit of Having JavaScript Library



---

# **React Component**
In this section you will be known with react component and its types.

###  What is React Component?
**Components** are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function.

It also accepts arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

> React Component should name with a capital letter.

> All React components must act like pure functions with respect to their props.

### React Component Types:
**1. Function Component:**
They called it as function component because it is literally JavaScript functions.

**Example:**
```javascript
function Welcome(props) {
  return <h1>Hello World!</h1>;
}
```

**2. Class Component:**
Using ES6 classes, you create a react class component.

**Example:**
```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## 3. Composing Components
React components can refer to other components in their output.

**Lets explain that with an example.**

By return to previous Example:

```javascript
function Welcome(props) {
  return <h1>Hello World!</h1>;
}
```

Here we have a Welcome component, which we can use in another component.

lets use it in an App:

```javascript
function App() {
  return (
    <div>
      <Welcome />
      <h1> I'm Here </h1> 
    </div>
  );
}
```

You can render **App** like that:

```javascript
ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

