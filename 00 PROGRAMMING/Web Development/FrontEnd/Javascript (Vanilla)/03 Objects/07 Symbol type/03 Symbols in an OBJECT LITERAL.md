---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #Symbol
∗:[[01 Javascript|JavaScript]] 

---
# Symbol in Object Literal

--- 
>[!info]- Object Literal
>a straightforward and concise way to define objects in JavaScript.
> ```javascript
> let person = {
> 	name: 'John',
> 	age: 30,
> 	city: 'New York'
> };
> ```

__Square brackets__ are needed when using a `Symbol` in an object literal.

```javascript
let id = Symbol("id");

let user = {
	name: "John",
	[id]: 123
};
```

Because we need the __value__ from variable `id` as the key,
NOT the string `"id"`.


