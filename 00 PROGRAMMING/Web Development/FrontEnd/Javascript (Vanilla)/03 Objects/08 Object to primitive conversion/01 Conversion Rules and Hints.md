---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 


> [!abstract] ## [Summary](https://javascript.info/object-toprimitive#summary)
>The object-to-primitive conversion is called automatically by many built-in functions and operators that expect a primitive as a value.
>There are 3 types (hints) of it:
> - `"string"` (for `alert` and other operations that need a string)
 > - `"number"` (for maths)
> - `"default"` (few operators, usually objects implement it the same way as `"number"`)
>
> The specification describes explicitly which operator uses which hint.
>
> The conversion algorithm is:
> 1. Call `obj[Symbol.toPrimitive](hint)` if the method exists,
> 2. Otherwise if hint is `"string"`
> - try calling `obj.toString()` or `obj.valueOf()`, whatever exists.
> 3. Otherwise if hint is `"number"` or `"default"`
>  - try calling `obj.valueOf()` or `obj.toString()`, whatever exists.

---
# Conversion Rules

--- 



> [!info] Type conversions
> - All __objects__ are `true` in boolean context
> - ___Numeric conversion___ happens when we subtract or apply mathematical functions to objects.
> - ___String conversion___ happens when we output an object with `alert(obj)`



---
# Hints


>[!example] 3 Variants of Type Conversion
> They are called __Hints__
>> [!tip] `"string"`
>> Object-to-String conversion, an operation on an `object` that expects a __string__, like `alert`:
>> ```javascript
>> // output
>> alert(obj);
>> 
>> // using object as a property key
>> anotherObj[obj] = 123;
>> ```
>
>
>> [!tip] `"number"`
>> Object-to-Number conversion, like doing maths:
>> ```javascript
>> // explicit conversion 
>> let num = Number(obj);
>> 
>> // maths (except binary plus)
>> let n = +obj; // unary plus
>> let delta = date1 - date2;
>> 
>> // less/greater comparison
>> let greater = user1 > user2;
>> ```
>
>
>> [!tip] `"default"`
>> When the operator is "__not sure__" or unclear what type to expect.
>> 
>> If a binary __plus__ (`+`) has an `object` as ___Argument___ or __compared__ using (`==`) , it uses `default` hint to convert it.
>> ```javascript
>> // binary plus uses the "default" hint
>> let total = obj1 + obj2;
>> 
>> // obj == number uses the "default" hint
>> if (user == 1) { ... };
>> ```
>> ALL __Built-in Objects__ (except `Date` object) implement `"default"` conversion the same way as `"number"`.

> [!abstract] Conversion Process:
> JavaScript find and call __Three object methods__:
> 1. Call `obj[Symbol.toPrimitive](hint)` - method with the __symbolic key__ `Symbol.toPrimitive` (system symbol), __if such method exists__.
> 2.  Otherwise if __hint__ is `string`
> 	- try calling `obj.toString()` or `obj.valueOf()`, whatever exists
> 3. Otherwise __if hint is__ `"number"` or `"default"`
> 	- try calling `obj.valueOf()` or `obj.toString()`, whatever exists.

