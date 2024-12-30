---
Programming Language: JavaScript
Framework/Library: N/A
Type: fundamentals
Topic: RestSpread Operator
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Review of Essential JavaScript for React
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - jsbasics
  - javascript
  - JS-Fundamentals
---
# RestSpread Operator

--- 

>[!tip]  __Rest__ Operator (ARRAY)
>```javascript
>const [primaryGenre, secondaryGenre, ...otherGenres] = genres;
>```
> - `...otherGenres` __stores all the other remaining `properties/indexes`__
> - Can only be put in the __end__ of the ___Destructured Object/Array___

> [!tip] __Spread__ Operator (ARRAY)
> Create a new array __and a new element__ with all the existing element.
> 
> ```javascript
> // WRONG WAY
> const newGenres = [genres, "epic fantasy"]; // [["science fiction", "humor", "speculative fiction"], "epic fantasy"]
> ```
> - Doing this will create an array with 2 elements:
> 	- 1st: A whole array (`genres`)
> 	- 2nd: the __string__
> 
> ```javascript
> const newGenres = [...genres, "epic fantasy"]; // new element "epic fantasy" added in the end
> const newGenres = ["epic fantasy", ...genres]; // added at the start
> ```
> - If we do this, it's as if we typed all the elements inside `genres` array 1 by 1

> [!abstract] __Spread__ operator (OBJECT)
> Create a new object with a new property.
> ```javascript
> const updatedBook = {...book, moviePublicationDate: "2001-12-19"};
> ```
> - `book` is the __object__
> - `moviePublicationDate: "2001-12-19"` is the new property.
> 
>> [!tip] Update a property
>> Updated existing property
>> ```javascript
>> const updatedBook = {...book, moviePublicationDate: "2001-12-19", pages: 1210};
>> ```
>>  - `pages:1210`  is in the last so it __overrides__ the `pages` inside `...book`
>> 	 - if we put the `pages:1210` __FIRST__ and `...book` last or at the right of `pages` then the __original__ will override the new update.




