# React Counter Example

App.js

```JSX
import React from "react";
import Counter from "./Counter"

function App() {
    return (
        <div> 
            <Counter />
        </div>
    )
}
```

Counter.js

```JSX
import React, {useState} from 'react';

function Counter() {
    const [count, setCount] = useState(0);

    function incrementCount() {
        setCount(count + 1)
    }
    return (
        <div>
        <button onClick={incrementCount}>Increment</button>
        <p>Count: {count}</p>
        </div>
  );
}

export default Counter;
```

# Solution Walkthrough

**Event Handling**: React supports event handling like, `onClick`, which allows you to execute a function when an element is clicked. In the example above, we used `onClick` to increment the counter when the button is clicked. 

# Step by Step 

## Initialize the state variable 

We first initialized the state variable `count` using the `useState` hook and set its initial value to 0. 

```JSX
const [count, setCount] = useState(0);
```

## Create the handle function 

We create a new function called `incrementCount` that increments the count variable by 1. 

```jsx
function incrementCount() {
    setCount(count + 1)
}
```

## Attach the handle 

We can connect the `incrementHandle` function to the `onClick` event handler of the button. This ensures that the function is called every time the button is clicked. 

## Display the current count: 

We can use the `count` state variable to display the current count in a paragraph element. 

```jsx
<p> Count: {count}</p>
```