---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions
∗:[[01 Javascript|JavaScript]] 

---
# 01 Function expressions

--- 
No matter how the function is created, a function is a __value__.
>[!info]- Function is a value representing an "action"
>- Regular values like strings or numbers represent the ___data___
>- A function can be perceived as an ___action___
>- We can pass it between variables and run when we want

>[!caution]- Declaration vs Expression difference?
> - Function Declaration can be called, _before_ defining the function.
> ```javascript
> const age1 = calcAge1(1991);
> 
> function calcAge1(birthYear) {
> 	return 2037 - birthYeah;
> }
> ```
>  - Function Expression can't, it will result to an ___Error___
>```javascript
>// this will result to an ERROR:
>console.log(age1, age2);
>
>const calcAge2 = function(birthYear) {
>	return 2037 - birthYear;
>}
>
>// console.log(age1, age2);
>```


>[!tip] Function Expression
> Function is a special kind of value
>```javascript
>let sayHi = function() {
>	alert( "Hello" );
>};
>```

>[!abstract] Function in JavaScript
>not like the functions in other programming language, where mentioning the function name causes its execution.
>JavaScript treats function a value
>```javascript
>function sayHi() {
>	alert( "Hello" );
>}
>
>alert( sayHi ); //shows the function code
>```

>[!tip] Copy a function to another variable
>```javascript
>function sayHi() { // (1) create
>	alert( "Hello" );
>}
>
>let func = sayHi; // (2) copy
>
>func(); // Hello  //(3) run the copy (it works)!
>sayHi(); // Hello // this still works too (why wouldn't it)
>```
>- the Function Declaration `(1)` creates the function and put into the variable named `sayHi`
>- Line `(2)` copies it into the variable `func`
>	- Note: There's no parentheses `()` after `sayHi`, if there is `func = sayHi()`would store `sayHi()`_result_ into `func`. __NOT the function__ `sayHi` itself.
> - Now the function can be called as both `sayHi()` and `func()`
> ```javascript
> let sayHi = function() { // (1) create
> 	alert( "Hello" );
> };
> 
> let func = sayHi;
> // ...
> ```

>[!question] Why is there a `semicolon` at the end?
> ```javascript
> function sayHi() {
> 	// ...
> }
> 
> let sayHi = function() {
> 	// ...
> };
> ```
> >[!DONE] Answer
> > - a Function Expression is created as `function(...) {...}` inside the assignment statement: `let sayHi = ...;`.
> > - The semicolon `;` is recommended at the end, it's not a part of the function syntax
> > - It's there for a simpler assignment
> > 	- like `let sayHi = 5;`

---

![[01 Function declaration#Function Inside a Code Block]]

>[!DONE] We are able to do this with Function Expression:
>```javascript
>let age = prompt("What is your age?", 18);
>
>let welcome;
>
>if (age < 18) {
>	welcome = function {
>		alert("Hello!");
>	};
>} else {
>	welcome = function() {
>		alert("Greetings!");
>	};
>}
>
>welcome(); // ok now
>```
>>[!tip] Simplify further using Ternary/Question mark operator `?`:
>>```javascript
>>let age = prompt("What is your age?", 18);
>>
>>let welcome = (age < 18)?
>>	function() { alert("Hello!"); } :
>>	function () { alert("Greetings!"); };
>>	
>>	welcome(); // ok now
>>```
