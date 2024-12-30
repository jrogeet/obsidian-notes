---
Programming Language: JavaScript
Framework/Library: ReactJS
Type: fundamentals
Topic: Components
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Working with Components, Props, and JSX
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - ReactJS
  - javascript
  - components
---
```js
function Footer() {
  const hour = new Date().getHours();
  const openHour = 12;
  const closeHour = 22;
  const isOpen = hour >= openHour && hour <= closeHour;
  console.log(isOpen);

  //   if (hour >= openHour && hour <= closeHour) alert("We're currently open!");
  //   else alert("Sorry we're closed");

  return (
    <footer>{new Date().toLocaleTimeString()}. We're currently open!</footer>
  );

  //   return React.createElement("footer", null, "We're currently open!");
}
```