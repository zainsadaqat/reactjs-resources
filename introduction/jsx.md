# JSX in ReactJS

JSX (JavaScript XML) is a syntax extension for JavaScript used in React to describe what the UI should look like. It allows you to write HTML-like code directly inside JavaScript, making it easier to build and visualize the structure of your components.

## Why Use JSX

1. Readable and Declarative: It lets you write HTML and JavaScript together, making the code more intuitive and easier to read.
2. Integration with JavaScript: You can embed JavaScript expressions directly within JSX using {}.
3. Transpilation to JavaScript: JSX gets compiled into regular JavaScript (React.createElement) by tools like Babel, ensuring compatibility with browsers.

## Example of JSX

Here’s how JSX works in a React component

```jsx
import React from "react";

function Greeting() {
  const name = "John";
  return <h1>Hello, {name}!</h1>; // Embedding a JavaScript expression
}

export default Greeting;
```

What Happens Behind the Scenes?

The above JSX code:

```jsx
<h1>Hello, {name}!</h1>
```

is transpiled into:

```jsx
React.createElement("h1", null, `Hello, ${name}!`);
```

## Key Points About JSX

### 1. One Parent Element: JSX requires a single parent element to wrap all child elements

### Correct

```jsx
return (
  <div>
    <h1>Title</h1>
    <p>Paragraph</p>
  </div>
);
```

### Incorrect

```jsx
return (
  <h1>Title</h1>
  <p>Paragraph</p>
);
```

### 2. JavaScript Expressions: You can use {} to embed variables, functions, or any valid JavaScript expressions

```jsx
const num = 5;
return <p>The number is {num * 2}</p>;
```

### 3. CSS Classes: Use className instead of class to define classes in JSX

```jsx
return <div className="container">Content</div>;
```

### 4. Self-Closing Tags: Tags without children must be self-closed

```jsx
return <img src="image.jpg" alt="example" />;
```

### Real-World Analogy

Think of JSX as a recipe card:

- The JSX is the recipe, showing the ingredients (HTML structure) and instructions (JavaScript logic).
- React uses this recipe to cook up (render) the final dish (UI).
