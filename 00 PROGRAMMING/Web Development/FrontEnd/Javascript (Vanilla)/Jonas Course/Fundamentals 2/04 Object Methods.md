---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object 
∗:[[01 Javascript|JavaScript]] 

---
# 04 Object Methods

--- 
```javascript
const jonas = {
	firstName = 'Jonas',
	lastName = 'Schmedtmann',
	birthYear = 1991,
	job: 'teacher',
	friends: ['Michael', 'Peter', 'Steven'],
	hasDriversLcense: true,

}
```

>[!tip] Function inside Object
>Object can also store a `function` as a value
>```javascript
>const jonas = {
>	...
>	
>	calcAge: function(birthYear) {
>		return 2037 - birthYear;
>	}
>};
>
>// access using dot and square brackets
>console.log(jonas.calcAge(1991));
>console.log(jonas['calcAge'](1991))
>```

## this Keyword
>[!abstract] Access an information inside the object.
>```javascript
>let user = {
>	name : "John",
>	age: 30,
>	
>	sayHi() {
>		// "this" is the "current object"
>	}
>};
>
>user.sayHi(); // John
>```

>[!caution] It's also possible without using `this`, by referencing it via the outer variable:
>```javascript
>let user = {
>	name: "John",
>	age: 30,
>	
>	sayHi() {
>		alert(user.name); // "user" instead of "this"
>	}
>};
>```
>Cons: when we changed the object name, it will result to an error or will refer to wrong object.

>[!tip] Creating and storing in a variable with `this`
>```javascript
>calcAge: function() {
>	this.age = 2037 - this.birthYear;
>	return this.age
>}
>```

---
### More examples:
```javascript
const jonas = {
    firstName: 'Jonas',
    lastName: 'Schmedtmann',
    birthYear: 1991,
    job: 'teacher',
    friends: ['Michael', 'Peter', 'Steven'],
    hasDriversLicense: true,

	calcAge: function() {
		this.age = 2037 - this.birthYear;
		return this.age
	},
	
    getSummary: function() {
        return  `${this.firstName} is a ${this.calcAge()} years old ${this.job}, and he has ${this.hasDriversLicense ? 'a' : 'no'} driver's license.`

    }
};

console.log(jonas.getSummary())
```

