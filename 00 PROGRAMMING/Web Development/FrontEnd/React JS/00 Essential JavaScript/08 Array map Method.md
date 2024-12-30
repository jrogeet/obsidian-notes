---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Array map Method
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

> [!abstract] Array Map method
> - __Loops__ over an `array`
> - Returns a new `array` with the _same length_
> - with __some operation applied__

```javascript
const x = [1, 2, 3, 4, 5].map((el) => el * 2);
console.log(x); // [ 2, 4, 6, 8, 10 ]
```

```js
const title = books.map((book) => book.title);
```
- returns an `array` of all the titles of the `books`


#### Not using an `arrow function`:
###### with `return`
```js
const title = books.map((book) => {
	return {
		title: book.title,
		author: book.author,
	};
});
```

###### No `return`
```js
const title = books.map((book) => ({
	title: book.title,
	author: book.author,
	reviewsCount: getTotalReviewCount(book),
}))
```

