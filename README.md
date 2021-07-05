# **React**

![](https://i.imgur.com/NYCkGlj.png)

---
# Learning Outcomes:
- What is React?
- Where we can use React?
- How React Work?
- Why to Use React?
- Who Use React?
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

# Why to Use React?
1. Easy to Learn and Use
2. Creating Dynamic Web Applications Becomes Easier
3. Reusable Components
4. Performance Enhancement
5. The Benefit of Having JavaScript Library

</br>

# Who Use React?

![](https://i.imgur.com/vRbudib.png)

</br>

# How does React flow?
![](https://i.imgur.com/dp4VVIv.png)

---

# **React Component**
In this section you will be known with react component and its types.

###  What is React Component?
**Components** are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function.

It also accepts arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.

> **React Component** should name with a capital letter.

> All **React components** must act like pure functions with respect to their props.

> A **React component** can be anything in your web application like a Button, Text, Label, or Grid.

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

### Composing Components
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
# React Props
**Props** are **arguments** passed into React components it's passed to components via HTML attributes. React Props are like function arguments in JavaScript and **attributes in HTML**.

</br>

 To send props into a component, use the same syntax as HTML attributes:


 **Example:**

Add a **"brand"** attribute to the Car element:

```javascript
const myelement = <Car brand="Ford" />;
```

The component receives the argument as a **props object**:


```javascript
// Use the brand attribute in the component:

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}
```
Props are also how you pass data from **one component** to **another**, as parameters.

```javascript
// Send the "brand" property from the Garage component to the Car component:

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}

class Garage extends React.Component {
  render() {
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```

If you have a **variable** to send, and not a string as in the example above, you just put the **variable** name inside curly brackets:

```javascript
// Create a variable named "carname" and send it to the Car component:
class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h2>;
  }
}

class Garage extends React.Component {
  render() {
    const carname = "Ford";
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand={carname} />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```

Or if it was an **object**:

```javascript
// Create an object named "carinfo" and send it to the Car component:

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand.model}!</h2>;
  }
}

class Garage extends React.Component {
  render() {
    const carinfo = {name: "Ford", model: "Mustang"};
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand={carinfo} />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```
</br>

###  Props wiht function component
```javascript
function Car({brand}) {
  render() {
    return <h2>I am a {brand}!</h2>;
  }
}

function Garage {
  render() {
    const carname = "Ford";
    return (
      <div>
      <h1>Who lives in my garage?</h1>
      <Car brand={carname} />
      </div>
    );
  }
}

ReactDOM.render(<Garage />, document.getElementById('root'));
```
---
</br>

# React State


### What is a State?

The State of a component is an object that holds some information that may change over the lifetime of the component.

</br>

### Difference of Props and State.

 1. Props are immutable,once set the props cannot be changed, while State is an observable object that is to be used to hold data that may change over time and to control the behavior after each change.

 2. States can only be used in Class Components while Props don’t have this limitation in v 14 and less.

 3. While Props are set by the parent component, State is generally updated by event handlers.

</br>

**Example:**

```javascript
// The state object can contain as many properties as you like:
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  render() {
    return (
      <div>
        <h1>My Car</h1>
      </div>
    );
  }
}
```
**Using the state Object** 
Refer to the state object anywhere in the component by using the:
```javascript
this.state.propertyname
```
Refer to the state object in the **render()** method:

```javascript
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color}
          {this.state.model}
          from {this.state.year}.
        </p>
      </div>
    );
  }
}
```
Changing the state **Object**

 To change a value in the state object, use the **this.setState()** method. When a value in the **state** object changes, the component will re-render, meaning that the output will change according to the new value(s).

```javascript
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  changeColor = () => {
    this.setState({color: "blue"});
  }
  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color}
          {this.state.model}
          from {this.state.year}.
        </p>
        <button
          type="button"
          onClick={this.changeColor}
        >Change color</button>
      </div>
    );
  }
}

```
---
# Mentors Team 
- [Hanan](https://github.com/Hanan795/)
- [Saja](https://github.com/SajaLahaleeh)
- [Noujod](https://github.com/Jood80)
