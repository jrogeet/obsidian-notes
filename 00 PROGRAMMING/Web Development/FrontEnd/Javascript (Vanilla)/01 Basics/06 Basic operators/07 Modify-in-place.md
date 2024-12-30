---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #operators 
∗:[[01 Javascript|JavaScript]] 

---
# 07 Modify-in-place

--- 
```javascript
let n = 2;

n = n + 5;
n += 5; // n = 7 (same as n = n + 5)

n = n * 2;
n *= 2; // n = 14 (same as n = n * 2)

alert( n ); // 14
```

```javascript
let n = 2;

n *= 3 + 5; // right part evaluated first, same as n *= 8

alert( n ); // 16
```