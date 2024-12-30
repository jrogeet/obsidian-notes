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
## Rendering Root in React 18
```js
import React from "react";
import ReactDOM from "react-dom/client";
```
- This is where we import __React__ from the ___node_modules___
	- There's another way using `script` tag, but in React application we don't do that:
	- ![[Pasted image 20241228140405.png]]

```js
function App() {
  return <h1>Hello React!</h1>;
}
```
- The function name doesn't need to be named `App`, it's just a common name convention
- A _'status' component_ (like `App()`) have to __start with an UPPERCASE__

```js
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```
- here, we render the `App` component into the `root` id element from _index.html_ in "public" folder using ___ReactDOM___'s `createRoot` function

## Strict Mode
Renders _components_ ___twice___ to __find certain bugs__
```js
...
root.render(
	<React.StrictMode>
		<App />
	</React.StrictMode>
);
```
