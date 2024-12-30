---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 07 typeof operator

--- 
Returns the type of the operand.
- typeof is an __operator__, not a function

___typeof(x)___ is the same as __typeof x__

```javascript
typeof undefined // "undefined"
typeof 0 // "number"
typeof true // "boolean"
typeof "foo" // "string"
typeof Symbol("id") // "symbol"
```

```javascript
typeof Math // "object"
```
- ___Math___ is a built-in object that provides mathematical operations.

```javascript
typeof null // "object"
```
- ___null___ is NOT an object
- It's a special value
- __typeof__'s behavior is wrong

```javascript
typeof alert // "function"
```
- alert is a function
- Functions belong to the object type
