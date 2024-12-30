---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Return from constructors

--- 
>[!info]
> Constructor functions don't have a `return` statement.
> The results from the `this` automatically becomes the output
>>[!question] But if there's a `return` statement inside a constructor function:
>> - if `return` is called with an __object__, then the __object is returned__ instead of `this`
>> 	- `return` with an object, __returns that object,__ ___in other cases `this` is returned.___
>> - if `return` is called with a ___primitive, it's IGNORED___.

>[!example] 
> Example: `return` overrides `this` by returning an object
> ```javascript
> function BigUser() {
> 	this.name = "John";
> 	
> 	return { name: "Godzilla" }; // <-- returns this object
> }
> 
> alert( new BigUser().name ); // Godzilla, got that object
> ```
> 
> Example with an __empty `return`__
> ```javascript
> function SmallUser() {
> 	
> 	this.name = "John";
> 	
> 	return; // <-- return this
> }
> 
> alert( new SmallUser().name ); // John
> ```


>[!tip] Omitting parentheses
>Parentheses can be omitted after `new`:
>```javascript
>let user = new User; // <-- no parentheses
>// same as
>let user = new User();
>```
>Omitting parentheses isn't considered a "good style", but the syntax is permitted by specification.

