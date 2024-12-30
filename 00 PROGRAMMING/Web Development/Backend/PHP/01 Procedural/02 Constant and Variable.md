---
topic: php
---
1-0.

Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Constant & Variables

--- 


> [!info] Variables
> `Variables` can be __changed__
> ```php
> $firstName = 'Johnny';
> $firstName = 'Bravo';
> 
> echo $firstName; // Bravo
> ```

>[!abstract] Constant
>`Constant` cannot be changed.
>To define a `constant`:
>```php
>define('name', 'value');
>```
>`constant` doesn't need Dollar Signs `$`
>```php
>define('STATUS_PAID', 'paid');
>
>echo STATUS_PAID;
>```
>
>> [!tip] Check if a constant __has been defined__
>> ```php
>> // returns boolean 1 if true and Empty or Nothing if false
>> echo defined('STATUS_PAID'); // 1
>> ```
>
>
>> [!tip] Const vs Define()
>> `const` are defined at a __compile time__
>> `define()` are defined at a __runtime__
>> For example:
>> `define` __will work__ inside `if` statement but ___not `const`___
>> ```php
>> if(true) {
>> 	const F00 = 'bar'; //ERROR
>> 	define('STATUS_PAID', 9); // WORKS!
>> }
>> ```
>
>
>> [!tip] Dynamic Constant Name
>> defining a `constant` name from a `variable`
>> ```php
>> $paid = 'PAID';
>> 
>> define('STATUS_' . $paid, 4);
>> 
>> echo STATUS_PAID; // 4
>> ```

>[!info] Variable Variables
>Making a `variable` with the __name being the value of another `variable`__
>```php
>$foo = 'bar';
>
>$$foo = 'baz';
>// the same as $bar = 'baz';
>
>// DIFFERENT WAYS OF PRINTING:
>echo $foo, $bar;
>
>echo $foo, $$foo;
>
>// ENCLOSING WITH DOUBLE QUOTATION MARKS 
>echo "$foo, {$$foo}";
>// or
>echo "$foo, ${$foo}";
>```
