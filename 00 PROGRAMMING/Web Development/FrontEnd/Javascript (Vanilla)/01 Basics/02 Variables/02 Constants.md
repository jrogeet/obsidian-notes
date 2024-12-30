---
topic: javascript
---
Tags/Topics: #javascript #jsbasics
∗:[[01 Javascript|JavaScript]] 

---
# 02 Constants

--- 
Constant (unchanging) variable
- Constant makes the variable's value never change

```javascript
const myBirthday = '18.04.1982';
```

- Variables declared using ___const___ are called "constants"
	- They can't be reassigned
```javascript
const myBirthday = '18.04.1992';

myBirthday = '01.01.2001'; // error, can't reassign the constant!
```

## Uppercase Constants
Constants are commonly used as aliases for difficult-to-remember values
- Used as aliases for "hard-coded" values.

```javascript
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "00F";
const COLOR_ORANGE = "FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```
Benefits:
- `COLOR_ORANGE` is much easier to remember than `"#FF7F00"`.
- It is much easier to mistype `"#FF7F00"` than `COLOR_ORANGE`.
- When reading the code, `COLOR_ORANGE` is much more meaningful than `#FF7F00`.
