---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Optional Chaining
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---

```js
function getTotalReviewCount(book) {
	const goodreads = book.reviews.goodreads.reviewsCount;
	const librarything = book.reviews.librarything.reviewsCount;
	return goodreads + librarything;
}

console.log(getTotalReviewCount(book)); // 812
```

but, what if the `book` doesn't have a review in `librarything` ?
It will result into an ___`Cannot read properties of undefined (reading 'reviewsCount')`___ error.

---

### Optional Chaining
[[01 non-existing property Problem| Optional Chaining (Non-existing Property Problem)]]

```js
function getTotalReviewCount(book) {
	const goodreads = book.reviews.goodreads.reviewsCount;
	const librarything = book.reviews.librarything?.reviewsCount ?? 0;
	return goodreads + librarything;
}

console.log(getTotalReviewCount(book)); // 812
```
- `book.reviews.librarything?.reviewsCount` 
	- tells JavaScript to continue reading ___properties___ __only if what comes before it exists__
		- in this case, if `book.reviews.librarything` exists, it will continue reading the next property:`reviewsCount`