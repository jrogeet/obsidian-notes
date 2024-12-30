---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 01 Number

--- 
Represents both __integer__ and __floating point__ numbers.

Besides regular numbers,
there are so-called "___special numeric values___":
`Infinity`, `-Infinity` and `NaN`.

- `Infinity` 
	- division by zero:
```javascript
alert( 1 / 0 ); // Infinity
```
- or reference it directly:
```javascript
alert(Infinity); // Infinity
```

- `NaN`
	- Computational error
	- Incorrect or undefined math operation
```javascript
alert("not a number" / 2); // NaN, such division is erroneous
```
- If there's __NaN__ in math expression, it will also be the result.
	- EXCEPT: __NaN ** 0__ is ___1___.
