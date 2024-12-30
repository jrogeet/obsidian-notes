---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# non-existing property Problem

--- 
>[!example]- Why Optional Chaining?
>For example, there's a `user` object which stores the information of our users.
>Most users have addresses in `user.address` property, with the street `user.address.street`
>BUT some ___did not provide them___.
>
>We'll get an __error__ if we attempt to get `user.address.street`
>```javascript
>let user = {}; // a user without "address" property
>
>alert(user.address.street); // Error!
>```
> - as `user.address` is ___undefined___ 
> 	- attempting to get `user.address.street` results with an error.
> 
>> [!abstract] In web development:
>> ```javascript
>> // document.querySelector('.elem') is null if there's no element
>> let html = document.querySelector('.elem').innerHTML; // ERROR if it's NULL
>> ```
>>  If the element doesn't exist, we'll get an error accessing `.innerHTML`
>>  
>>  If there's actually an event in the program that __absence of element is `normal`__, 
>>  `html = null` is preferable than an ___ERROR___.
>>> [!question] How can we do this?
>>> This works, no error.
>>> 	But inelegant since `user.address` __appeared twice__ in the code.
>>> ```javascript
>>> let user = {};
>>> 
>>> alert(user.address ? user.address.street : undefined);
>>> ```
>>> The same code with `document.querySelector`:
>>> but still not good since `document.querySelector('.elem')` appeared twice.
>>> ```javascript
>>> let html = document.querySelector('.elem') ? document.querySelector('.elem').innerHTML : null;
>>> ```
>>> It would be ugly writing this in deep nested properties:
>>> ```javascript
>>> let user = {}; // user has no address
>>>
>>alert(user.address ? user.address.street ? user.address.street.name : null : null);
>>> ```
>>>>[!tip] a Little better way to write it: `&&` operator:
>>>>AND'ing ensures all components exist (___if not, the evaluation stops___), but still __NOT IDEAL__
>>>>property names are still duplicated
>>>>```javascript
>>>>let user = {}; // user has no address
>>>>
>>>>alert( user.address && user.address.street && user.address.street.name ); // undefined (no error)
>>>>```

>[!info] ##### __Optional Chaining__
> Optional Chaining __`?.`__  ___stops the evaluation if the value before___ __`?.`__ is `undefined` or `null` and returns `undefined`.
> 
>> [!example] 
>> __`value?.prop`__ works as:
>> - `value.prop`, if `value` exists,
>> - otherwise (when `value` is `undefined/null`) it returns `undefined`.
>
> ```javascript
> let user = {}; // user has no address
> 
> alert( user?.address?.street ); // undefined (no error)
> ```
>> [!example] `document.querySelector`:
>> ```javascript
>> let html = document.querySelector('.elem')?.innerHTML; // will be undefined, if there's no element
>> ```
>
>```javascript
>let user = null;
>
>alert( user?.address ); // undefined
>alert( user?.address.street ); // undefined
>```
>
>>[!tip] 
>>__`?.`__ makes the value __before it__ optional, but ___Not any further___.
>>
>> EXAMPLE:  `user?.address.street.name`
>> `?.` allows __`user`__ to safely be `null/undefined` but only for __`user`__
>
>
>> [!caution] Don't overuse optional chaining
>> `?.` should be used only if its ok for something to not exist.
>> Example:
>> `user` must exist, but `address` is optional:
>> 	- `user.address?.street` ___but not `user?.address?.street`___
>
>> [!danger] Variable before `?.` __must be declared__
>> if `user` variable doesn't exist, `user?.anything` results in an ERROR!
>> ```javascript
>> // ReferenceError: user is not defined
>> user?.address;
>> ```
>
>> [!tip] Short-cirtuit
>>  `?.` immediately STOPS (short-circuit) if the left part doesn't exist:
>>  ```javascript
>>  let user = null;
>>  let x = 0;
>>  
>>  user?.sayHi(x++); // no "user", so the execution doesn't reach sayHi call and x++
>>  
>>  alert(x); // 0, value not incremented
>>  ```
>
>> [!abstract] Other variants `?.()`, `?.[]`
>> `?.` is not an operator, but special syntax construct
>> Also works for __functons and square brackets__
>> ```javascript
>> let userAdmin = {
>> 	admin() {
>> 		alert("I am admin");
>> 	}
>> };
>> 
>> let userGuest = {};
>> 
>> userAdmin.admin?.(); // I am admin
>> 
>> userGuest.admin?.(); // nothing happens (no such method)
>> ```
>>  - `?.()` works whether a function exists or not.
>> 	 - if it's not then it will stop without errors.
>> - `?.[]` can also be used instead of dot `.`
>> ```javascript
>> let key = "firstName";
>> 
>> let user1 = {
>> 	firstName: "John"
>> };
>> 
>> let user2 = null;
>> 
>> alert( user1?.[key] ); // John
>> alert( user2?.[key] ); //undefined
>> ```
>>> [!tip] `?.` with `delete`
>>> ```javascript
>>> delete user?.name; // delete user.name if user exists
>>> ```
>>
>>> [!danger] `?.` only for __Reading__ and __Deleting__, NOT ___WRITING___.
>>> ```javascript
>>> let user = null;
>>> 
>>> user?.name = "John"; // Error, doesn't work
>>> // because it evaluates to: undefined = "John"
>>> ```








