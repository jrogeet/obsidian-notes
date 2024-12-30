---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 02 BigInt

--- 
Number type cannot represent integer values larger than (2^53 - 1) or ___9007199254740991___ or less than -(2^53 - 1) for negatives

a ___BigInt___ value is created by appending __n__ to the end of an integer:
```javascript
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```