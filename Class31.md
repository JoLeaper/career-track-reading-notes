# Hooks
## Definition: A React hook allows for use of state and other features without writing a class.
## Used When: 
If you write a function component and realize you need to add some state to it, previously you had to convert it to a class. Now you can use a Hook inside the existing function component. We’re going to do that right now!

### A Hook
```js
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### A Non-Hook Equivalent
```js
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}
```

### The Hook
```js
  const [count, setCount] = useState(0);
```
Purpose: Calling useState declares state.   
Arguments: The only argument useState takes in is the <b>INITIAL STATE.<b>
Returns: A pair of values: the current state and a function that updates it.

## Displaying/Updating State (No Hooks)

```js
    this.state = {
      count: 0
    };

  <p>You clicked {this.state.count} times</p>

    <button onClick={() => setCount(count + 1)}>
    Click me
  </button>
```

## Displaying/Updating State (With Hooks)
```js
  const [count, setCount] = useState(0);

  <p>You clicked {count} times</p>

    <button onClick={() => this.setState({ count: this.state.count + 1 })}>
    Click me
  </button>
// if you need to declare multiple states, use multiple hooks!

  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
```

