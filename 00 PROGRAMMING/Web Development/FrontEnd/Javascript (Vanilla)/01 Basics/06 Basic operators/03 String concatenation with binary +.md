---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #operators
∗:[[01 Javascript|JavaScript]] 

---
# 03 String concatenation with binary +

--- 
if the binary `+` is applied to __strings__, it mergest (concatenates) them:
```javascript
let s = "my" + "string";
alert(s); // mystring
```

>[!caution] If __any__ of the operands is a ___string___, then the other one is converted to ___string___ too.
>It doesn't matter whether the first or second operand is the string
> ```javascript
> alert( '1' + 2 ); // "12"
> alert( 2 + '1' ); // "21"
> ```
> Here, first `+` sums two numbers, then adds the string ___1___: `4 + '1' = '41'`
> ```javascript
> alert( 2 + 2 + '1' ); // "41" and not "221"
> ```
> The first operands is a string, compiler treats the other two as strings too.
> ```javascript
> alert('1' + 2 + 2); // "122" and not "14"
> ```

---
### More:

- `"" + 1` converts `1` and `0`to a string : `"" + 1 = "1"`
```javascript
"" + 1 + 0 // = "10"
```

- Subtraction `-` __only works with numbers__, it converts _empty string_ `""` to `0`
```javascript
"" - 1 + 0 // = -1 
```

- The addition with a string appends the number `5` to the string.
```javascript
"  -9  " + 5 // = "  -9  5"
```

- The subtraction always converts to numbers, so it makes `" -9 "` a number `-9` (ignoring spaces around it).
```javascript
"  -9  " - 5 // = -14
```

- `null` becomes `0` after the numeric conversion
```javascript
null + 1 // = 1
```

- `undefined` becomes `NaN` after the numeric conversion.
```javascript
undefined + 1 // = NaN
```

- the string consists of __space characters__ and "regular" space between them, similar to an _empty string_, it becomes `0`
```javascript
" \t \n" - 2 // = -2
```


##### More:
```javascript
true + false = 1

6 / "3" = 2

"2" * "3" = 6

4 + 5 + "px" = "9px"

"$" + 4 + 5 = "$45"

"4" - 2 = 2

"4px" - 2 = NaN
```

