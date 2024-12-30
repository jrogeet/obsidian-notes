---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: Arrays
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---
 
 >[!tip] Duplicating & Adding to array
 >We can use the __spread `...array/object` operator__ to add an item
 >```js
 >const newBook = {
 >	id: 6,
 >	title: "Harry Potter and the Chamber of Secrets",
 >	author:  "J. K. Rowling",
 >};
 >
 >const booksAfterAdd = [...books, newBook];
 >```

> [!danger] Deleting an object/item from array
> We can use __`.filter()`__ method to ___Delete___ an item in the `array/object`
> ```js
> const booksAfterDelete = booksAfterAdd.filter((book) => book.id !== 3);
> ```
> - Delete the item that has the `id = 3`

> [!abstract] Update book object in the array
> We can use __`.map()`__ method to ___Update___ an item in the `array/object`
> ```js
> const booksAfterUpdate = booksAfterDelete.map((book) => book.id === 1 ? {...book, pages: 1210} : book);
> ```
