---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Array sort Method
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

#### Sorting in Ascending & Descending order:

```js
const arr = [3, 7, 1, 9, 6];

// ASCENDING:
const sorted = arr.sort((a, b) => a - b); // output: [1, 3, 6, 7, 9]

// DESCENDING:
const sorted = arr.sort((a, b) => b - a); // output: [9, 7, 6, 3, 1]
```

###### Warning:
> This modifies the original array:
```js
const arr = [3, 7, 1, 9, 6]; // becomes: [1, 3, 6, 7, 9]
const sorted = arr.sort((a, b) => a - b); // output: [1, 3, 6, 7, 9]
```
- If the `a - b` or the callback function returns a _negative_, it will be __sorted in ascending way (small first)__

> Adding `.slice()` creates a copy of that array to ___preserve the original data___
```js
const arr = [3, 7, 1, 9, 6]; // still the same: [1, 3, 6, 7, 9]
const sorted = arr.slice().sort((a, b) => a - b); // output: [1, 3, 6, 7, 9]
```

> [!example] Book Pages Sorting
> ```js
> const sortedByPages = books.slice().sort((a, b) => a.pages - b.pages);
> ```
