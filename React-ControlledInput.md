# React Controlled Input Field 

Create an input field component that allows a user to type in text and display the test in real-life time. 

- Every time the user types something in the input field, the test should update in the text element. 
- You should use the `useState` hook to keep track of the text state. 

# Solution

`Inputfield.js`

```jsx
import React, {useState} from 'react';

function inputField() {
    const [text, setText] = useState("");

    function handleInputChange(event) {
        event.preventDefault();
        setText(event.target.value);
    }

    return (
        <div> 
            <input type="text" value={text} onChange={handleInputChange}/>
            <p>Input text: {text}</p>
        </div>
    )
}

export default inputField;
```

# Key Concepts

**Controlled components** is a component where the state of the input field is directly controlled by React. The value of the input field is set by a state variable, and any change in the value triggers an event handler to update the state. 

# Solution Walkthrough 

## Initialize state variable `text` with an empty string 

```jsx
const [text, setText] = useState('');
```

## Change the handleInputChange function

We create a new function called handleInputChange that takes the `event` object as a parameter. This function is responsible for updating the `text` state variable witht the current value of the input field. 

```jsx
function handleInputChange(event) {
    setText(event.target.value);
}
```
## Set up the controlled input field component and Attach the `handleInputChange` function to the input field's `onChange` event handler

In the JSX component, we set the `value` attribute of the input field to the current text state. This makes the input field a controlled component, as its value is directly controlled by React. 

We connect the `handleInputChange` function to the `onChange` event handler of the input field. This ensure that the function is called every time the input field's value changes. 

```jsx
<input type="text" value={text} onChange={handleInputChange} />
```

## Display in real time
```jsx
<p> Input text: {text} </p>
```
