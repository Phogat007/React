### Namaste React Course by Akshay Saini  

# Chapter 05 - Let’s Get Hooked!  

### Q: What is the difference between `Named export`, `Default export`, and `* as export`?  
**A:** In JavaScript, modules enable us to organize code by exporting values, functions, or objects from one module and importing them into another. The three common methods for exporting are: `named exports`, `default exports`, and `wildcard/namespace exports`. Here’s a breakdown:  

1. **Named Exports**  
   - Used to export multiple items from a module, each with its own specific name.  
   - The `export` keyword is followed by the item being exported.  

   **Example:**  
   ```js
   // mathUtils.js
   export const add = (a, b) => a + b;  
   export const subtract = (a, b) => a - b;  
   ```  

   To import these items, specify their names in curly braces:  
   ```js
   import { add, subtract } from './mathUtils';  
   ```  

2. **Default Exports**  
   - Allows exporting a single item as the default from a module.  
   - Use the `export default` syntax to define the default export.  

   **Example:**  
   ```js
   // main.js
   const greeting = "Hello, world!";  
   export default greeting;  
   ```  

   Default exports can be imported without curly braces, and the name can be customized during import:  
   ```js
   import myGreeting from './main';  
   ```  

3. **Wildcard or Namespace Exports (`* as`)**  
   - Combines all named exports from a module into a single object.  
   - Useful for grouping exports under a common namespace.  

   **Example:**  
   ```js
   // utilities.js
   export const funcA = () => { /* ... */ };  
   export const funcB = () => { /* ... */ };  
   ```  

   To import all named exports as a single object:  
   ```js
   import * as utils from './utilities';  
   utils.funcA();  
   utils.funcB();  
   ```  

**Summary:**  
`Named exports` allow multiple items to be exported by name, `default exports` focus on a single main item, and `wildcard exports` bundle all named exports into one object for easier access. The method you choose depends on your project’s requirements and coding style.  

---

### Q: Why is a `config.js` file important?  
**A:** A `config.js` file centralizes application settings, making them easy to update and manage. It often contains key-value pairs or constants used across the application, such as API endpoints, timeout durations, or environment-specific variables.  

**Example:**  
```js
export const API_URL = 'https://api.example.com';  
export const TIMEOUT = 5000;  
```  

**Benefits:**  
1. **Consistency:** Ensures a single source of truth for configuration values.  
2. **Maintainability:** Simplifies updates, especially for environment-specific configurations like development, staging, and production.  
3. **Readability:** Keeps code cleaner by separating settings from the main application logic.  

Centralized configuration files are especially useful in large projects, ensuring that changes are localized and easier to track.

### Namaste React Course by Akshay Saini  

# Chapter 05 - Let’s Get Hooked!  

### Q: What are React Hooks?  
**A:** `React Hooks` are a feature introduced in React 16.8 that allows functional components to manage state and handle side effects. Hooks eliminate the need for class components, making code more concise and easier to understand while enabling the use of component state and lifecycle features in functional components.  

Here are some commonly used React Hooks:  

1. **`useState`**  
   - Manages state in functional components.  
   - Provides a state variable and a function to update it.  

   **Example:**  
   ```js
   import React, { useState } from 'react';  

   function Counter() {  
     const [count, setCount] = useState(0);  

     return (  
       <div>  
         <p>Count: {count}</p>  
         <button onClick={() => setCount(count + 1)}>Increment</button>  
       </div>  
     );  
   }
   ```  

2. **`useEffect`**  
   - Handles side effects like data fetching, subscriptions, or DOM manipulation.  
   - Replaces lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.  

   **Example:**  
   ```js
   import React, { useEffect, useState } from 'react';  

   function DataFetching() {  
     const [data, setData] = useState([]);  

     useEffect(() => {  
       fetch('https://api.example.com/data')  
         .then(response => response.json())  
         .then(data => setData(data));  
     }, []);  

     return (  
       <ul>  
         {data.map(item => (  
           <li key={item.id}>{item.name}</li>  
         ))}  
       </ul>  
     );  
   }
   ```  

3. **`useContext`**  
   - Simplifies accessing values from a React Context.  
   - Helps avoid prop drilling in deeply nested components.  

   **Example:**  
   ```js
   import React, { useContext } from 'react';  
   import MyContext from './MyContext';  

   function MyComponent() {  
     const value = useContext(MyContext);  

     return <div>Context Value: {value}</div>;  
   }
   ```  

4. **`useReducer`**  
   - Manages more complex state logic compared to `useState`.  
   - Useful for state transitions, such as those in forms or dynamic UIs.  

   **Example:**  
   ```js
   import React, { useReducer } from 'react';  

   const initialState = { count: 0 };  

   function reducer(state, action) {  
     switch (action.type) {  
       case 'increment':  
         return { count: state.count + 1 };  
       case 'decrement':  
         return { count: state.count - 1 };  
       default:  
         return state;  
     }  
   }  

   function Counter() {  
     const [state, dispatch] = useReducer(reducer, initialState);  

     return (  
       <div>  
         <p>Count: {state.count}</p>  
         <button onClick={() => dispatch({ type: 'increment' })}>Increment</button>  
         <button onClick={() => dispatch({ type: 'decrement' })}>Decrement</button>  
       </div>  
     );  
   }
   ```  

5. **`useRef`**  
   - Provides a way to persist values across renders without causing re-renders.  
   - Commonly used for accessing DOM elements or storing mutable values.  

   **Example:**  
   ```js
   import React, { useRef, useEffect } from 'react';  

   function MyComponent() {  
     const inputRef = useRef(null);  

     useEffect(() => {  
       inputRef.current.focus();  
     }, []);  

     return <input ref={inputRef} />;  
   }
   ```  

**Why React Hooks?**  
Hooks simplify state management, promote reusability of logic, and encourage cleaner, declarative code structures in functional components.  

---

### Q: Why do we use the `useState` Hook?  
**A:** The `useState` Hook allows functional components to maintain and update their own local state. It’s fundamental for creating interactive and dynamic components in React.  

**Key Advantages of `useState`:**  

1. **Local State Management:**  
   - Isolates state to the component, keeping it independent and reusable.  

2. **Reactive Updates:**  
   - Automatically triggers re-renders when the state changes, updating the UI efficiently.  

3. **Simplifies Functional Components:**  
   - Enables functional components to manage state without converting them into class components.  

4. **Declarative Programming:**  
   - Allows developers to focus on *what* the UI should look like based on state, while React handles the *how*.  

5. **Ease of Use:**  
   - Simple API with predictable behavior.  

**Example:**  
```js
import React, { useState } from 'react';  

function Counter() {  
  const [count, setCount] = useState(0);  

  const increment = () => setCount(count + 1);  

  return (  
    <div>  
      <p>Count: {count}</p>  
      <button onClick={increment}>Increment</button>  
    </div>  
  );  
}
```  

In this example, `useState` creates a `count` state variable and a `setCount` function to update it. Clicking the button increments the count and triggers a re-render, updating the UI.  

**Conclusion:**  
The `useState` Hook empowers functional components with state capabilities, enabling developers to create modern, interactive React applications.


