---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Array reduce Method
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

> [!abstract] reduce method
> Reduces/Boil down the entire array into _1 value_
> - _first value_: Callback function 
> - _second value_: Starter value


```js
const pagesAllBooks = books.reduce((accumulator, book) => accumulator + book.pages, 0)
```
- `0` is the starting value of the ___`accumulator`___
	- then in the callback function, it's getting added. 
- Conceptually, I think it looks like the iterations in a for loop