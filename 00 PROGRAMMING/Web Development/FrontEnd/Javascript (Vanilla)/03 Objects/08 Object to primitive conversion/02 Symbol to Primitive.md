---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Symbol.toPrimitive

--- 
`Symbol.toPrimitive` is a built-in symbol.
Should be used to __name the conversion method__
```javascript
obj[Symbol.toPrimitive] =  function(hint) {
	// here goes the code to convert this object to a primitive
	// it must return a primitive value
	// hint = one of "string", "number", "default"
};
```

if method `Symbol.toPrimitive` exists, __it's used for ALL HINTS__, and no more methods are needed.

For instance, `user` object implements it:
```javascript
let user = {
	name: "John",
	money: 1000,
	
	[Symbol.toPrimitive](hint) {
		alert(`hint: ${hint}`);
		return hint == "string" ? `{name: "${this.name}"}` : this.money;
	}
};

// conversions demo:
alert(user); // hint: string -> {name: "John"}
alert(+user); // hint: number -> 1000
alert(user + 500); // hint: default -> 1500
```

