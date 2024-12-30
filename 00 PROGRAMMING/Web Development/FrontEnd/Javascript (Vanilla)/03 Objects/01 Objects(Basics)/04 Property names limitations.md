---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Property names limitations

--- 
Property names has __NO LIMITATIONS__. 
- They can be any strings or symbols
	- Other types are _automatically converted to strings_.

```javascript
// these properties are all right
let obj = {
	for: 1,
	let: 2,
	return: 3
};

alert( obj.for + obj.let + obj.return ); // 6
```

```javascript
let obj = {
	0: "test" // same as "0": "test"
};

// both alerts access the same property (the number 0 is converted to string "0")
alert( obj["0"] ); // test
alert( obj[0] ); // test (same property)
```