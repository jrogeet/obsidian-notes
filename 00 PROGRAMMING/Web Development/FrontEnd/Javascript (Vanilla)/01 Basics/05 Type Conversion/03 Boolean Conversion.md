---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 03 Boolean Conversion

--- 
[[04 Boolean | [ Boolean ] ]]

## Truthy and Falsy
>[!Example] Conversion Rule:
>- Values that are intuitively "empty", like:
>	- ___0___
>	- an empty string
>	- ___null___
>	- ___undefined___
>	- ___NaN___
>- become __False__
>- Other values become __True__
>
>|Value|Becomes…|
|---|---|
|`0`, `null`, `undefined`, `NaN`, `""`|`false`|
|any other value|`true`|

```javascript
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```

String with zero ___"0"___ is __true__
```javascript
alert( Boolean("0") ); // true
alert ( Boolean(" ") ); // spaces, also true (any non-empty string is true)
```

