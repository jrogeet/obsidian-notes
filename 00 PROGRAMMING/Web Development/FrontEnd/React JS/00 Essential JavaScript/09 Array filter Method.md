---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Array filter Method
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

Adds a value in an `array` ONLY if the ___condition___ returns __true__
```js
const longBooks = books.filter((book) => book.pages > 500);
```
- Adds each `book` that has more than ___500 pages___

#### Chaining `.filter()`
```js
const longBooksWithMovie = books.filter((book) => book.pages > 500).filter((book) => book.hasMovieAdaptation);

// with proper format:
const longBooksWithMovie = books
	.filter((book) => book.pages > 500)
	.filter((book) => book.hasMovieAdaptation);
```

##### Combination of `.filter()` and `.map()`
```js
const adventureBooks = books.filter((books) => books.genres.includes("adventure")).map((book) => book.title);
```
- Filters `books` that has the genre `adventure`
	- and only store the `book.title` in `adventureBooks` array variable.