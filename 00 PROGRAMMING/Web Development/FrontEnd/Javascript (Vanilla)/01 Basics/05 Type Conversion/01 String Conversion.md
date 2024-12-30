---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 01 String Conversion

--- 
Happens when we need the string form of a value.

To convert value to a string:
`String(value)`
```javascript
let value = true;
alert(typeof value); // boolean

value = String(value); // now value is a string "true"

```
A `false` becomes ___"false"___,
`null` becomes ___"null"___, etc.
