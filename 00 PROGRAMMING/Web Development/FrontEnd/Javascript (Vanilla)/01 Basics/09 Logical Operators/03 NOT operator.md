---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #logical 
∗:[[01 Javascript|JavaScript]] 

---
# 03 NOT operator

--- 
One exclamation point `!`
```javascript
result = !value;
```
>[!important] Precedence
>NOT `!` is the __HIGHEST__ of all logical operators
>- so it always executes first, before `&&` or `||`


>[!important] Accepts a single argument and does the following:
>1. _Converts_ the operand to boolean type: `true/false`
>2. Returns the__ inverse__ value.
>```javascript
>alert( !true ); // false
>alert( !0 ); // true
>```

>[!INFO] double NOT `!!`
>Sometimes used for converting a value to boolean type:
>- Value-to-Boolean conversion:
>```javascript
>alert( !!"non-empty string" ); //true (line 1)
>alert( !!null ); // false (line 2)
>```
>Line 1: Converts value to boolean and returns the inverse
>Line 2:  Inverses it again
>
>More verbose way to do the same thing:
>```javascript
>alert( Boolean("non-empty string") ); // true
>alert( Boolean(null) ); // false
>```

---
### More example:

```javascript
//first variant:
if (!(age >= 14 && age <= 90))

//second variant:
if (age < 14 || age > 90)
```
- `if` condition that checks `age` is NOT between `14` and `90` inclusively.
	- First variant using NOT `!`
	- Second variant without it.

