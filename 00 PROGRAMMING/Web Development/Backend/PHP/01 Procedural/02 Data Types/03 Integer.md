---
topic: php
---


Tags/Topics: #php #datatypes 
∗:[[0 PHP|PHP]]

---
# Integers

--- 

>[!abstract]
>Numbers with __no decimal points__
>
>Integers can be also define as __Hexadecimal__, __Octal__ and __Binary__
>```php
>// HEXADECIMAL
>$x = 0x2A;
>echo $x; // 42
>
>// OCTAL
>$x = 055;
>echo $x; // 45
>
>// BINARY
>$x = 0b11;
>echo $x // 3
>```
>
>> [!caution] Out of bounds Integer
>> Integers become __float__ when out of bounds
>> ```php
>> $x = PHP_INT_MAX + 1;
>> ```
>> `PHP_INT_MAX` is the __maximum value of integer__, when we add `1` it's out of bounds and ___it became a `float`___
>
>
>> [!tip] Conversions
>> ```php
>> $x = (int) true; // 1
>> $x = (int) false; // 0
>> $x = (int) 5.98; // 5
>> $x = (int) '5.9'; // 5
>> $x = (int) '87waaw'; // 87
>> $x = (int) 'test'; // 0
>> $x = (int) null; // 0
>> $x = (int) '2_000_000'; // 2
>> 
>> ```
>
>
>> [!info] `is_int($var)`
>> __Check whether a variable is an `integer`__
>> ```php
>> $x = null;
>> var_dump(is_int($x)); // bool(false)
>> $x = (int) null;
>> var_dump(is_int($x)); // bool(true)
>> ```
>
>
>> [!tip] Readability
>> Use __Underscores__ `_` for readability of numbers
>> ```php
>> $x = 2_000_000;
>> ```




