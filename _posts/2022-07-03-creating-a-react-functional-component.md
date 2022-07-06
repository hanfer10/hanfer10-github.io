---
layout: post
title: Creating a React Functional Component.
summary: A quick guide on implementing React functional components.
categories: jekyll update
---

React utilizes a syntax extension called JSX to allow HTML and JavaScript to be written in the same file. This is useful as it allows us to execute any JavaScript code directly inside the HTML. This is done by utlizing curly braces {} to hold this code. In addition to this you can return HTML in JavaScript logic making React a very versatile tool.

A component is a code block which is reusable and seperates the UI into chunks. You may have a component that represents an entire page or a page can be made up of several components. This makes writing the code simpler and also more maintanable because these components are independent pieces and in good practice they represent one part of the page.

a React functional component is more or less a JavaScript/ES6 function that returns JSX. This is a basic example of a valid functional component:
```javascript
const Hello = (props) => {
  return <h1>Hello, {props.name}<h1>;
}
```
To then use this component we want to export it to make it available elsewhere:
```javascript
const Hello = (props) => {
  return <h1>Hello, {props.name}<h1>;
}

export default Hello;
```

Now this component is available for importing wherever needed and you have a React functional component.
