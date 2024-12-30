---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Asynchronous Promises
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

> [!abstract] Promise
> The **`Promise`** object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.
> 
> A `Promise` is in one of these states:
> - _pending_: initial state, neither fulfilled nor rejected.
> - _fulfilled_: meaning that the operation was completed successfully.
> - _rejected_: meaning that the operation failed.

> [!info] `fetch()` & Asynchronous JavaScript Promises
> ```js
> fetch("https://jsonplaceholder.typicode.com/todos");
> 
> console.log("This will get executed right after the fetch above, even tho the data has not arrived.")
> ```
> - JavaScript will __NOT wait until the data is fetched__, `fetch()` will just execute as a function and move to the next line.

> [!info] `then()`
> will be called as soon as the _promise_ is fulfilled.
> ```js
>  fetch("https://jsonplaceholder.typicode.com/todos")
>  .then((res) => res.json())
>  .then((data) => console.log(data));
> ```
> - Inside `then()` we need to pass a __callback function__ (the code that __will be executed__ as soon as the __data has arrived__ )
> 	- `.then((res) => res.json())`: `.json()` __returns a promise too__, so we put another `.then()` with the result of that `.json()` which ___converts json to JavaScript Object___
