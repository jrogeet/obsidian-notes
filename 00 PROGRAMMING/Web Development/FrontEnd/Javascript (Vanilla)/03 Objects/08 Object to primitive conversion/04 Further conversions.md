---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Design

---
> [!info]
> Many `operators` and `functions` perform type conversions
> Example:
> 	Multiplication `*` __converts operands to numbers__
> 
> If we pass an `object` as an ___argument___, 
> there are two stages of calculations:
> 1. `Object` is __converted to primitive__ 
> 2. If necessary, the __resulting primitive__ is also ___converted___.
> 
> ```javascript
> let obj = {
> 	// toString handles all conversions in the absence of other methods
> 	toString() {
> 		return "2";
> 	}
> };
> 
> alert(obj * 2); // 4, object converted to primitive "2", then multiplication made it a number
> ```
> 1. The _multiplication_ `obj * 2` first __converts the object to primitive__ (string `"2"`)
> 2. Then `"2" * 2` becomes `2 * 2` (the string is converted to number).

Binary plus will __concatenate strings__ in the same situation
```javascript
let obj = {
	toString() {
		return "2";
	}
};

alert(obj + 2); // 22 ("2" + 2), conversion to primitive returned a string => concatenation
```




