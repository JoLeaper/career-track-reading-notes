# React Props and State
## setState
- State Examples: Whether or not a user is logged in (boolean), username to display based on active account (string)
- If a React component has state, the UI is rendered base on state.
- setState() is the only legitimate way to update state after declaring initial state.
```js
import React, { Component } from 'react'

class Search extends Component {
  constructor(props) {
    super(props)

    state = {
      searchTerm: ''
    }
  }
}

setState({searchTerm: event.target.value})

// ALTERNATIVELY

    handleChange = (e) => {
        const newState = {}
        newState[e.target.name] = e.target.value;
        this.setState(newState);
    }

        render() {
        return (
            <div>
                <form onSubmit={this.handleSubmit}>
                    <input onChange={this.handleChange} name='task'></input>
                    <input onChange={this.handleChange} name='priority_level' type='number'></input>
                    <button>Add Task</button>
                </form>
            </div>
        )
    }
```
