# React Toggle Visibility 

- Initially, the text should be hidden 
- When the button is clicked, the text should become visible if it was hidden, and hidden if it was visible 
- Use the `useState` hook to manage the visibility state.

# Solution 

`ToggleVisibility.js`

```jsx
import React, {useState} from 'react';

function ToggleVisibility() {
    const [hidden, setHidden] = useState(false);

    function toggleHidden() {
        setHidden(!hidden);
    }

    return (
        <div>
            <button onClick={toggleHidden}>Show/hide text</button>
            {hidden && <p> Toggle me!</p>}
        </div>
    )
}

export default ToggleVisibility;
```

# Key Concepts 

**Conditional Rendering:** React allows you to conditionally render elements based on a certain condition. In this exercise, we'll use conditional rendering to display or hide the text element based on the visibility state. 

**Event handling:** React supports various event handlers, such as `onClick`, which allows you to execute a function when an element is clicked. In this exercise, we'll use the `onClick` event handler to toggle the visibility state when the button is clicked. 

# Solution Walkthrough

**Initialize state variable** `isVisible` **with** `false`.

We create a state variable `isVisible` using the `useState` hook and set its initial value to `false`, indicating that the text should be initially hidden. 

```jsx
const [isVisible, setIsVisible] = useState(false);
```

**Create the `handleToggleVisibility` function:**

We create a new function called `handleToggleVisibility` that toggles the `isVisible` state variable by setting it to its opposite value (`!isVisible`)

```jsx
function handleToggleVisibility() {
    setIsVisible(!isVisible);
}
```

**Attach the `handleToggleVisibility` function to the button's `onClick` event handler:**

We connect the `handleToggleVisibility` function to the `onClick` event handler of the button. This ensures that the function is called every time the button is clicked, toggling the visibility of the text element. 

```jsx
<button onClick={toggleHidden}>Show/hide text</button>
```

**Conditionally render the text element based on the `isVisible` state:**

We use conditional rendering to display the text element only if the `isVisible` state is `true`

```jsx
{isVisible && <p>Toggle me!</p>}
```
