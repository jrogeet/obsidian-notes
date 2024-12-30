---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #Symbol
∗:[[01 Javascript|JavaScript]] 

---
# Design

--- 
>[!abstract] "Hidden" property
> Symbols allow us to __create “hidden” properties of an object__, that no other part of code can accidentally access or overwrite.
> 
>> [!example]
>> Working with `user` objects __that belong to a third-party code__.
>> ```javascript
>> let user = { // belongs to another code
>> 	name: "John"
>> }
>> 
>> let id = Symbol("id");
>> 
>> user[id] = 1;
>> 
>> alert( user[id] ); // we can access the data using the symbol as the key
>> ```
>
>> [!tip] Benefit of using `Symbol("id")` over _string_ `"id"`
>> If the `object` __belongs to another codebase__, Using `Symbol()` will ___not affect the original___ `object`.
>> The new `Symbol()` property is only accessible where it's created.
>> 
>> Meanwhile, using __string__ `"id"` or __property__ ___affect the original codebase___ or `object`.



