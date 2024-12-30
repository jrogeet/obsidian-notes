---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #Symbol
∗:[[01 Javascript|JavaScript]] 

---
# Symbol.keyFor

--- 
- `Symbol.for(key)`

```javascript
// get symbol by name
let sym = Symbol.for("name");
let sym2 = Symbol.for("id");

// get name by symbol
alert( Symbol.keyFor(sym) ); // name
alert( Symbol.keyFor(sym2) ); // id
```

> [!tip] `Symbol.keyFor` only works with __Global Symbol__
>  `Symbol.keyFor` uses the __Global Symbol registry__
>  It doesn't work with ___Non-global symbols___
>  ```javascript
>  let globalSymbol = Symbol.for("name");
>  let localSymbol = Symbol("name");
>  
>  alert( Symbol.keyFor(globalSymbol) ); // name, global symbol
>  alert( Symbol.keyFor(localSymbol) ); // undefined, not global
>  
>  alert( localSymbol.description ); // name
>  ```
