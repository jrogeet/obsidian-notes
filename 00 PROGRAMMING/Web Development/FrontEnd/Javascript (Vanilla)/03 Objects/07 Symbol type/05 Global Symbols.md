---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #Symbol 
∗:[[01 Javascript|JavaScript]] 

---
# Global Symbols

--- 
> [!info]
> Global Symbols are application-wide symbol, accessible everywhere in the code.

`Symbol.for(key)` either __Read/Return__ or  __Create__ the Symbol (if it doesn't exist yet).
```javascript
// read from the global registry
let id = Symbol.for("id"); // if the symbol did not exist, it is created
// read it again (maybe from another part of the code)
let idAgain = Symbol.for("id");

// the same symbol
alert(id === idAgain ); // true
```

> [!question] What is the benefits of using __Global Symbols__ instead of just a normal, ___string-property___?
> - Symbols are unique, even with the same description
> - __Immutable__ can't be accessed and modified with `Object(keys)` and `for...in`
> - Encapsulation, they are __hidden__ so they can't be accidentally be accessed.
> 
> -  **Standardization and Interoperability**: Symbols can be used to establish standard symbols or APIs across different parts of an application or even different libraries, promoting interoperability and consistency.
> - **Third-party Libraries**: Symbols can be useful in scenarios involving third-party libraries or plugins to define properties that won't clash with those defined in the application code.

