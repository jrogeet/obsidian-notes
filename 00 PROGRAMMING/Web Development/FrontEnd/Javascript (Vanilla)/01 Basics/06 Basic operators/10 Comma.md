---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #operators
∗:[[01 Javascript|JavaScript]]  

---
# 10 Comma

--- 
Used to write shorter code

Allows to evaluate several expressions
- Dividing them with a comma `,`
- Each of them is evaluated but only the result of the last one is returned.

```javascript
let a = (1 + 2, 3 + 4);

alert( a ); // 7 (the result of 3 + 4)
```

The first expression `1 + 2` is evaluated and its __result is thrown away__.

Then, `3 + 4` is evaluated and ___returned as the result___.

>[!Caution] Comma has a very low precedence
>Lower than `=`, __parentheses__ are important
>Without parentheses `a = 1 + 2, 3 + 4`
>- Summing the numbers into `a = 3, 7`
>- then `=` assigns `a = 3` 
>- the __rest is IGNORED__

Example:
```javascript
// three operations in one line
for (a = 1, b = 3, c = a * b; a < 10; a++){
...
}
```


