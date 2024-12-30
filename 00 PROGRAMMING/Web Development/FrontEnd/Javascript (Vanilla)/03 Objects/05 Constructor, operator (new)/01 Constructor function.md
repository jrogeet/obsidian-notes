---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Constructor Function

--- 
>[!tip] Purpose:
>To implement __reusable object creation code.__
>
>A function for creating new objects

>[!tip] Note:
> - __Any Function__ (except `arrow` functions, as it don't have `this`) ___can be used as a constructor___. 
>It can be run with `new`.
> - The "__Capital letter first__" is a common agreement, to make it clear that a function is to be run with `new` 

>[!info] Constructor Function
> Technically regular function
> - Named with __capital letter first__.
> 	- Not required
> 	- It's just a symbol that tells the `function` is a constructor function.
> - Should be executed only with `"new"` operator.
> 
> EXAMPLE:
>```javascript
>function User(name) {
>	this.name = name;
>	this.isAdmin  = false;
>}
>
>let user = new User("Jack");
>
>alert(user.name); // Jack
>alert(user.isAdmin); // false.
>```
>___When a `function` is executed with `new`___:
>- A __new empty object__ is created and assigned to `this`.
>- __The function body executes__. Usually it modifies `this`, adds new properties to it.
>- The __value of `this` is returned.__
>
>>[!tip]- In other words, `new User (...)` does something like:
>>```javascript
>>function User(name) {
>>	// this = {}; (implicity)
>>	
>>	// add properties to this
>>	this.name = name;
>>	this.isAdmin = false;
>>	
>>	// return this; (implicitly)
>>}
>>```
>
>`let user = new User("Jack")` gives the same result as:
>```javascript
>let user = {
>	name: "Jack",
>	isAdmin: false
>};
>```
>__Creating other users is easier and shorter this way__, `new User("Ann"), new User("Alice")` and so on.
>Which is the main purpose of constructors -__Implement reusable object creation code.__
>
>>[!tip] new function() {...}
>>
>>```javascript
>>// create a function and immediately call it with new
>>let user = new function() {
>>	this.name = "John";
>>	this.isAdmin = false;
>>	
>>	// ... other code for user creation
>>	// maybe complex logic and statements
>>	// local variables etc
>>};
>>```
>>This constructor __can't be called again__, it's now saved anywhere and just got ___created and called___ right away.



