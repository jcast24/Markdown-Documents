# React Character Counter

Create a simple Character Counter component that allows users to type in text and displays the number of characters in real-time. 

- Create a text area element for users to type in text
- Display the characters count below the textarea in real-time
- Use the `useState` hook to manage the text state 

# Solution 

```jsx
import React, { useState } from 'react';

function CharacterCounter() {
  const [text, setText] = useState('');

  function handleTextareaChange(event) {
    setText(event.target.value);
  }

  return (
    <div>
      <textarea value={text} onChange={handleTextareaChange} />
      <p>Character count: {text.length}</p>
    </div>
  );
}

export default CharacterCounter;
```

# Solution Walkthrough 

React uses synthetic events to handle user interactions, such as changes to input fields. In this component, we need to respond to changes in the textarea's value. We create a function called `handleTextAreaChange` that accepts an event object as its parameters. This event object contains information about the change, including the new value of the textarea. The function updates the `text` state variable with the updated value. 

```jsx
function handleTextareaChange(event) {
  setText(event.target.value);
}
```

We use the `handleTextareaChange` function as an event handler, attaching it to the `onChange` event of the textarea. **Remember:** this pattern of explicitly setting the value of an input field and providing an event handler to update the state is known as a **controlled component** in React:

```jsx
<textarea value={text} onChange={handleTextareaChange} />
```

# Real-time updates and React's Re-rendering 

One of React's core features is its ability to efficiently re-render components when their state or props change. By connecting the `text` state to the textarea's value and the displayed character count, React will automatically re-render the component whenever `text` is updated. This ensures that the character count displayed below the textarea always reflects the current length of the text:

```jsx
<p>Character count: {text.length}</p>
```
