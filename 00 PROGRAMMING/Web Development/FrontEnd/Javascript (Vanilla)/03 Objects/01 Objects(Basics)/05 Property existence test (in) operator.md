---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Property existence test, “in” operator

--- 
Difference of JavaScript to other languages,
is that any __Property__ of an Object is possible to access.
- There will be __NO ERROR__ if property doesn't exist

```javascript
let user = {}

alert( user.noSuchProperty === undefined ); // true means "no such property"
```


>[!info] Special operator `"in"` for that.
>```javascript
>"key" in object
>```
>For instance:
>```javascript
>let user = { name: "John", age: 30};
>
>alert( "age" in user ); // true, user.age exists
>alert( "blabla" in user ); // false, user.blabla doesn't exist
>```
>
>`undefined` vs `in`
>```javascript
>let obj = {
>	test: undefined
>};
>
>alert( obj. test ); // it's undefined, so - no such property?
>
>alert( "test" in obj ); // true, the property does exist!
>```

##  `for..in` loop

Go through over all keys of an object
```javascript
for (key in object) {
	// executes the body for each key among object properties
}
```

```javascript
let user = {
	name: "John",
	age: 30,
	isAdmin: true
};

for (let key in user) {
	// keys
	alert( key ); // name, age, isAdmin
	// values for the keys
	alert( user[key] ); // John, 30, true
}
```
We could user another variable name instead of just `key`
	For instance: `"for (let prop in obj)"`


## Ordered like an object
The phone codes(keys) go in the ascending sorted order, because they are _integers_. `1, 41, 44, 49`
```javascript
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}
```

>[!info] Integer properties
>A string that can be converted to-and-from an integer without a change.
>`49` is an integer
>`+49` and `1.2` are not:
>```javascript
>// Number(...) explicitly converts to a number
>// Math.trunc is a built-in function that removes the decimal part
>alert( String(Math.trunc(Number("49"))) ); // "49", same, integer property 
>alert( String(Math.trunc(Number("+49"))) ); // "49", not same "+49" ⇒ not integer property
>alert( String(Math.trunc(Number("1.2"))) ); // // "1", not same "1.2" ⇒ not integer property
>```

If the keys are __NON-INTEGER__, they are listed in the __creation order__
```javascript
let user = {
	name: "John",
	surname: "Smith"
};
user.age = 25; // add one more
// non-integer properties are listed in the creation order
for (let prop in user) {
	alert( prop ); // name, surname, age
}
```