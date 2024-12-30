---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Property value shorthand

--- 
```javascript
function makeUser(name, age) {
	return {
		name: name,
		age: age,
		// ...other properties
	};
}

let user = makeUser("John", 30);
alert(user.name); // John
```

>[!tip] Special property shorthand
>Instead of `name:name` we can just write `name` like this:
>```javascript
>function makeUser(name, age) {
>	return {
>		name,   // same as name: name
>		age,   // same as age: age
>		// ...
>	};
>}
>```
>Using both _normal_ and __shorthand__ properties in the same object:
>```javascript
>let user = {
>	name,   // same as name:name
>	age: 30
>};
>```

