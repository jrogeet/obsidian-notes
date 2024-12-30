---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #Symbol
∗:[[01 Javascript|JavaScript]] 

---
## Symbol Type

--- 

>[!abstract] #### Symbol type
>Only __two primitive types__ may serve as object property keys:
> - __STRING__ type, or
> - __SYMBOL__ type
> 
> ___Any other types___ are automatically converted to `string`.
> - `obj[1]` equals `obj["1"]`
> - `obj[true]` equals `obj["true"]`

> [!tip] Summary:
>  - `Symbol()` are like __unofficial property__ of an `object`.
>  - Not written directly, but associates itself to the `object`. (Like adopted itself to the `object`).
>  - Each `Symbol()` has __unique id__ even if they have the ___same description___.
>  - __Only accessible in the file where it's created/it's scope__.

>[!info] #### Symbols
> A __"symbol"__ represents a unique identifier.
> 
> Can be created using `Symbol()`:
> ```javascript
> let id = Symbol();
> ```
>> [!tip] Symbol Name
>>  Symbols can be given a description, useful for debugging
>>  ```javascript
>>  // id is a symbol with the description "id"
>>  let id = Symbol("id");
>>  ```
>>  -  __Symbols are UNIQUE__
>>  - Symbols with the ___same description___ are different.
>>  - The `description` is just a __label__ that __doesn't affect anything__.
>> ```javascript
>> let id1 = Symbol("id");
>> let id2 = Symol("id");
>> 
>> alert(id1 == id2); // false
>> ```
>>> [!danger] Symbols don't auto-convert to a string
>>> `alert` converts almost any value.
>>> __Symbols__ don't auto-convert.
>>> ```javascript
>>> let id = Symbol("id");
>>> alert(id); // TypeError: Cannot convert a Symbol value to a string
>>> ```
>>>> [!done] Show __Symbol__:
>>>>  - `toString()`:
>>>> ```javascript
>>>> let id = Symbol("id");
>>>> alert(id.toString()); // Symbol(id), now it works
>>>> ```
>>>> - `symbol.description`
>>>> ```javascript
>>>> let id = Symbol("id");
>>>> alert(id.description); // id
>>>> ```
>>>> 







