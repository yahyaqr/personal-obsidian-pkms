---
created: Tuesday, December 13th 2022 - 07.34
updated: Tuesday, December 13th 2022 - 07.34
---
Lesson Review

Awesome work, we can now build “stateful” function components using the `useState` React Hook!

Let’s review what we learned and practiced in this lesson:

-   With React, we feed static and dynamic data models to JSX to render a view to the screen
    
-   Use Hooks to “hook into” internal component state for managing dynamic data in function components
    
-   We employ the State Hook by using the code below:
    
    -   `currentState` to reference the current value of state
        
    -   `stateSetter` to reference a function used to update the value of this state
        
    -   the `initialState` argument to initialize the value of state for the component’s first render
-
```JSX
const [currentState, stateSetter] = useState( initialState );
```

-   Call state setters in event handlers
    
-   Define simple event handlers inline with our JSX event listeners and define complex event handlers outside of our JSX
    
-   Use a state setter callback function when our next value depends on our previous value
    
-   Use arrays and objects to organize and manage related data that tends to change together
    
-   Use the spread syntax on collections of dynamic data to copy the previous state into the next state like so: `setArrayState((prev) => [ ...prev ])` and `setObjectState((prev) => ({ ...prev }))`
    
-   Split state into multiple, simpler variables instead of throwing it all into one state object

---

```JSX
// index.js

import React from "react";
import ReactDOM from "react-dom";
// import App from "./Container/AppClass";
import App from "./Container/AppFunction";

ReactDOM.render(
  <App />,
  document.getElementById("app")
);
```

```JSX
// AppClass.js

import React, { Component } from "react";
import NewTask from "../Presentational/NewTask";
import TasksList from "../Presentational/TasksList";

export default class AppClass extends Component {
  constructor(props) {
    super(props);
    this.state = {
      newTask: {},
      allTasks: []
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
    this.handleDelete = this.handleDelete.bind(this);
  }

  handleChange({ target }){
    const { name, value } = target;
    this.setState((prevState) => ({
      ...prevState,
      newTask: {
        ...prevState.newTask,
        [name]: value,
        id: Date.now()
      }
    }));
  }

  handleSubmit(event){
    event.preventDefault();
    if (!this.state.newTask.title) return;
    this.setState((prevState) => ({
      allTasks: [prevState.newTask, ...prevState.allTasks],
      newTask: {}
    }));
  }

  handleDelete(taskIdToRemove){
    this.setState((prevState) => ({
      ...prevState,
      allTasks: prevState.allTasks.filter((task) => task.id !== taskIdToRemove)
    }));
  }

  render() {
    return (
      <main>
        <h1>Tasks</h1>
        <NewTask
          newTask={this.state.newTask}
          handleChange={this.handleChange}
          handleSubmit={this.handleSubmit}
        />
        <TasksList
          allTasks={this.state.allTasks}
          handleDelete={this.handleDelete}
        />
      </main>
    );
  }
}
```

```JSX
// AppFunction.js

import React, { useState } from "react";
import NewTask from "../Presentational/NewTask";
import TasksList from "../Presentational/TasksList";

export default function AppFunction() {
  const [newTask, setNewTask] = useState({});
  const handleChange = ({target}) => {
    const {name, value} = target;
    setNewTask((prev) => ({...prev, id: Date.now(), [name]: value}));
  };

  const [allTasks, setAllTasks] = useState([]);
  const handleSubmit = (event) => {
    event.preventDefault();
    if (!newTask.title) return;
    setAllTasks((prev) => [newTask, ...prev]);
    setNewTask({});
  };
  const handleDelete = (taskIdToRemove) => {
    setAllTasks((prev) => prev.filter((task) => task.id !== taskIdToRemove));
  };
  
  return (
    <main>
      <h1>Tasks</h1>
      <NewTask
        newTask={newTask}
        handleChange={handleChange}
        handleSubmit={handleSubmit}
      />
      <TasksList
        allTasks={allTasks}
        handleDelete={handleDelete}
      />
    </main>
  );
}
```