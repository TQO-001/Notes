# React Notes

- A React component can only return one parent element.

```jsx
return <h1>Hello</h1><p>World</p>            // error
return <div><h1>Hello</h1><p>World</p></div> // okay 
```

- JavaScript expressions can be interpolated in JSX with `{}`

```jsx
return <div>{ new Date() }</div>
```

- A component can be a simple function or a class.

- React attributes are all camelCase - `onclick` becomes `onClick`.

- State should only be updated with `setState()`

- Class components should always call the base constructor with props.


## Setup

### Static HTML File

To get React working without any build processes for testing purposes, you can load React, React DOM, and Babel through external scripts.

```html
<!-- index.html -->

<html>
  <head>
    <meta charset="UTF-8">
  
    <title>Hello World</title>
  
    <script src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>
  </head>

  <body>
  
    <div id="root"></div>
    
    <script type="text/babel">
    class App extends React.Component {
        render() {
            return (
                <h1>Hello world!</h1>
            );
        }
    }

    ReactDOM.render(<App />, document.getElementById('root'));
    </script>
  </body>
</html>
```

### Create React App

[create-react-app](https://github.com/facebook/create-react-app) comes pre-installed with Webpack, Babel, ESLint, and other packages with no configuration required.

Make sure npm > 5.2 and Node > 6.0 are installed.

```bash
node -v 
nvm -v
```

Create `example` app.

```bash
npx create-react-app example
cd example
```

Start.

```bash
npm start
```

The default browser will open `localhost:3000`. 

We can create the same Hello World.

```jsx
// src/App.js

import React, { Component } from 'react';
import './App.css';

class App extends Component {
    render() {
        return (
            <h1>Hello, World!</h1>
        );
    }
}

export default App
```

```jsx
// src/index.js

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

## JSX

JSX is a JavaScript syntax extension. It resembles HTML in most ways, except `class` becomes `className`.

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

Represents:

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

## Components

A simple component is a function.

```jsx
const Button = props => {
    return <button type="submit">{props.label}</button>;
}

ReactDOM.render(<Button label="Submit" />, document.getElementById('root'));
```

Class synax component.

```jsx
class Button extends Component {
    render() {
        return <button>{this.props.label}</button>
    }
}

ReactDOM.render(<Button label="Submit" />, document.getElementById('root'));
````

## State

Increase a counter in the state, display the state in the DOM.

```jsx
class App extends Component {
    state = {
      clickCounter: 0,
    };
    
    handleClick = () => {
        this.setState((prevState) => {
            return { clickCounter: prevState.clickCounter + 1 };
        });
    };
    
    render() {
        return (
            <div>
                <button onClick={this.handleClick}>Click</button>
                <p>Clicked: {this.state.clickCounter}</p>
            </div>
        );
    }
}

export default App;
```

Modify an array and display the contents of the array.

```jsx
const list = [
    'one',
    'two',
    'three'
];

class App extends Component {
    state = {
      arr: [],
    };
    
    handleClick = item => {
        this.setState({
            arr: [...this.state.arr, item]
        });
    };
    
    render() {
        return (
            <div>
                {list.map(item => { 
                    return <button onClick={this.handleClick.bind(this, item)}>{item}</button>
                })}
               
                <p>Clicked: {this.state.arr}</p>
            </div>
        );
    }
}

export default App;
```

Note that we can return a function or an object.

```jsx
// object
handleClick = item => {
    this.setState({
        arr: [...this.state.arr, item]
    });
};
```

```jsx
// function
handleClick = item => {
    this.setState((prevState) => {
       return { arr: [...prevState.arr, item] } 
    });
};
```

## Constructor

Without constructor

```jsx
class App extends Component {
    state = {
      arr: [],
    };
}
```

With constructor

```jsx
// Class components should always call the base constructor with props.

class App extends Component {
    constructor(props) {
        super(props);
        
        this.state = {
            arr: [],
        };
    }
}
```

Sub class constructors cannot make use of `this` until `super()` is called.

```jsx
constructor(props) {
    super();
    
    console.log(this.props) // undefined
}
```

```jsx
constructor(props) {
    super(props);
    
    console.log(this.props) // defined
}
```

### Access props of the parent

```jsx
class Parent extends Component {
  render() {
    const { data } = this.props
    
    return <Child />
```

```jsx
const Child = props => {
  console.log(props.id)
}
```

```jsx
class Child extends Component {
  render() {
    console.log(this.props.id)
  }
}
```

### Crud

```jsx
class Parent extends Component {
  state = {
    users: []
  }
  
  add = user => {
    const { users } = this.state
    
    this.setState({ users: [...users, user] })
  }
  
  update = (id, updatedUser) => {
    const { users } = this.state

    this.setState({
      users: users.map(user => (user.id === id ? updatedUser : user)),
    })
  }
    
  delete = id => {
    const { users } = this.state

    this.setState({
      users: users.filter(user => user.id !== id),
    })
  }
}
```

```jsx
class Parent extends Component {
  state = {
    users: [],
    results: [],
  }
  
  search = event => {
  const { users } = this.state
  const { value } = event.target

  const results = users.filter(user => {
    const regex = new RegExp(value, 'gi')
    return user.name.match(regex)
  })

  this.setState({ results })
  
  render() {
    const { users, results } = this.state
    const data = results.length === 0 ? users : results
    
    return (
      <div>
        <Input onChange={this.search} />
        <Table data={data} />
      </div>
    )
  }
}
```
