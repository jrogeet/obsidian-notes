---
Programming Language: JavaScript
Framework/Library: ReactJS
Type: fundamentals
Topic: JSX
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Working with Components, Props, and JSX
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - ReactJS
  - javascript
  - jsx
---
> [!abstract] General JSX Rules
> - Works similar to HTML, BUT we can enter "JavaScript mode" by using `{ }` for (text or attributes)
> - We can place __JavaScript expressions__ inside `{ }`
> 	- Examples: 
> 		- reference variables,
> 		- create arrays,
> 		- objects,
> 		- `[].map()`,
> 		- ternary operator
> - ***Statements are not allowed*** (`if/else`, `for`, `switch`)
> - _JSX_ produces a __JavaScript expression__
> 	- ![[Pasted image 20241230001323.png]]
> 	1. We can place __other pieces of__ _JSX_ inside `{ }`
> 	2. We can write _JSX_ __anywhere__ inside a component (in `if/else`, assign to variables, pass it into functions)
> - A piece of *JSX* can only have __one root element__. If you need more, use `<React.Fragment>` (or the short `<>`)

![[Pasted image 20241230001953.png]]

