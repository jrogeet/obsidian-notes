---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #operators
∗:[[01 Javascript|JavaScript]] 

---
# 02 Maths

--- 
>[!example] The following math operations are supported:
> - Addition `+`,
> - Subtraction `-`,
> - Multiplication `*`,
> - Division `/`,
> - Remainder `%`,
> - Exponentiation `**`

### Remainder %
- Not related to percents
- The result of `a % b` is the __remainder__ of the integer division of `a` by `b`
```javascript
alert( 5 % 2 ); // 1, the remainder of 5 divided by 2
alert ( 8 % 3 ); // 2, the remainder of 8 divided by 3
alert ( 8 % 4 ); // 0, the remainder of 8 divided by 4
```

### Exponentiation **
`a ** b` raises `a` to the power of `b`
```javascript
alert ( 2 ** 2 ); // 2² = 4
alert( 2 ** 3 ); // 2³ = 8
alert( 2 ** 4); // 2⁴ = 16
```

Exponentiation is defined for non-integer numbers as well.

Square root exponentiation by ½:
```javascript
alert( 4 ** (1/2) ); // 2 (power of 1/2 is the same as a square root)
alert( 8 ** (1/3) ); // 2 (power of 1/3 is the same as cubic root)
```