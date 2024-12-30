---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #operators
∗:[[01 Javascript|JavaScript]] 

---
# 04 Numeric conversion, unary +

--- 
Unary plus / plus operator `+`
- When applied to a single value, i doesn't do anything
- BUT, if the operand is _not a number_, the unary plus __converts it into a number__
- It does the same thing as `Number(...)` but shorter
```javascript
// No effect on numbers
let x = 1;
alert ( +x ); // 1

let y = -2; 
alert ( +y ); // -2

//COnverts non-numbers
alert( +true ); //1
alert( +"" ); // 0
```

The binary plus would add them as strings:
```javascript
let apples = "2";
let oranges = "3";

alert( apples + oranges ); // "23", the binary plus concatenates strings
```

We need to convert and then sum them:
```javascript
let apples = "2";
let oranges = "3";

//both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5

//the Longer Variant:
// alert( Number(apples) + Number(oranges) ); // 5
```

---
### More Examples:

```javascript
let a = prompt("First number?", 1);
let b = prompt("Second number?", 2);

alert(a + b);
```
The prompt returns user input as a string.
If you input `1` and `2`, the output would be the same  with this code:
```javascript
let a = "1"; // prompt("First number?", 1);
let b = "2"; // prompt("Second number?", 2);

alert(a + b); // 12
```

>[!check] Convert strings to numbers
>For example: Using `Number()` or prepending them with `+`
>
>right before `prompt`:
>```javascript
>let a = +prompt("First number?", 1);
>let b = +prompt("Second number?", 2);
>
>alert(a + b); // 3
>```
>
>or in the `alert`:
>```javascript
>let a = prompt("First number?", 1);
>let b = prompt("Second number?", 2);
>
>alert(+a + +b); // 3
>```



