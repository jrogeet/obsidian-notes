---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Object references and copying

--- 
When an object variable is copied, the _reference_ is copied, but the __object itself is not duplicated__.
>[!info]- Why?
>_Primitive_ values: `string`, `numbers`, `booleans`, etc. are always copied "__as a whole value__".
>```javascript
>let message = "Hello!";
>let phrase = message;
>```
>`message` and `phrase` are independent variables storing the same value `Hello!`.
>
>__Objects__ are stored and copied "__by reference__".
>A `variable` in an `object` stores the "address in memory" of the `object`.
>```javascript
>let user = {
>	name: "John"
>}
>```
>![[Pasted image 20240113224905.png |300]]
>The `object` is stored somewhere in memory (at the right of the picture), while `user` variable has a "__reference__" to it.

```javascript
let user = { name: "John" };

let admin = user; // copy the reference
```

![[Pasted image 20240114112903.png | 500]]
There's still __one object__, but `two variables` that _reference it._
>[!tip] Use either variable to access and modify the object:
>```javascript
>let user = { name: 'John' };
>
>let admin = user;
>
>admin.name = 'Pete'; // changed by the "admin" reference
>
>alert(user.name); // 'Pete', changes are seen from the 'user' reference
>```


## Comparison by reference
`Two objects` are _equal only_ if they are the `same object`.
```javascript
let a = {};
let b = a; // copy the reference
alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true
```

These `two independent objects` are __not equal__, even tho they're both _empty_.
```javascript
let a = {};
let b = {}; // two independent objects


alert( a == b); // false
```



>[!important] `const` objects can be __modified__
>```javascript
>const user = {
>	name: "John"
>};
>
>user.name = "Pete"; 
>
>alert(user.name); // Pete
>```
>
>The _value_ of `user` is __constant__, it must always __reference the same object__, but `properties` of that object are _free to change._
>
>It will only give an error if we try to set `user=...` as a __WHOLE__.
