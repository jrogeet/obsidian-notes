---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 02 Numeric Conversion

--- 
Numeric conversion in mathematical functions and expressions happens automatically.

Example, when division ___/___ is applied to __non-numbers__:
```javascript
alert( "6" / "2" ); // 3, strings are converted to numbers
```

To convert a ___value___ to a number:
`Number(value)`

```javascript
let str = "123";
alert(typeof str); // strings

let num = Number(str); // becomes a number 123
alert(typeof num); // number
```

If the __string is not a valid number__,
the result of such a conversion is ___NaN___:
```javascript
let age = Number("an arbitrary string instead of a number");

alert(age);
```

>[!EXAMPLE] Numeric conversion rules:
>
> | Value | Becomes...|
> |---------|------------|
> |null|0|
> |true and false|1 and 0|
> |string| Whitespaces (includes spaces, tabs \\t, new lines \\n etc.) from the start and end are removed. If the remaining string is empty, the result is ___0___. Otherwise, the number is "read" from the string. An error gives ___NaN___.|
> 
> ```javascript
> alert( Number("   123   ") ); // 123
> alert( Number("123z") ); // NaN (error reading a number at "z")
> alert( Number(true) ); // 1
> alert( Number(false) ); // 0
> ```

>[!Note] __null__ and _undefined_ behave differently here:
>- __null__ becomes zero
>- _undefined_ becomes ___NaN___



