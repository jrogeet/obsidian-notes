---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #object
∗:[[01 Javascript|JavaScript]] 

---
# Objects

--- 
>[!info] Object
> Objects are used to store keyed collections of various data and more complex entities.
> - Created with figure brackets `{...}` with an optional list of properties.
> 	- A property is a "__key:value__" pair,
> 	- where `key` is a _string_ (aka "__property name__"), 
> 	- `value` can be __anything__.
> 
> ```javascript
> let user = {               // an object
> 	name: "John",          // by key "name" store value "John"
> 	age: 30                // by key "age" store value 30
> }
> ```
> 
> `user` object has two properties:
> 1. First has the name "`name`" and value "`John`".
> 2. Second has the name "`age`" and value "`30`".
> 
>>[!tip] Add, Remove and Read files any time.
>>- __READ__:
>>```javascript
>>// get property values of the object:
>>alert( user.name ); // John
>>alert( user.age ); // 30
>>```
>> - __ADD__:
>> ```javascript
>> user.isAdmin = true;
>> ```
>> ![[Pasted image 20240112192338.png]]
>> - __DELETE__:
>> ```javascript
>> delete user.age;
>> ```
>> ![[Pasted image 20240112192354.png]]
>
>> [!TIP] Multiword Property names:
>> _Multiword Property_ mush be __quoted__.
>> ```javascript
>> let user = {
>> 	name: "John",
>> 	age: 30,
>> 	"likes birds": true    // multiword property name must be quoted
>> }
>> ```
>> ![[Pasted image 20240112192631.png]]
>
>> [!tip] __"Trailing"__ or __"Hanging"__ comma.
>> Makes it easier to add/remove/move around properties, because all lines become alike.
>> The last property in the list may end with a comma:
>> ```javascript
>> let user = {
>> 	name: "John",
>> 	age: 30,
>> }
>>```



