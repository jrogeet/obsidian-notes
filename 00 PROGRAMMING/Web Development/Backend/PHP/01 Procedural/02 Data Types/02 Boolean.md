---
topic: php
---
Tags/Topics: #php #datatypes 
∗:[[0 PHP|PHP]]

---
# Boolean Data Type

--- 

>[!info] Boolean
>The value __`true`__ or ___`false`___ of a variable is __NOT Case-Sensitive__
>```php
>$isComplete = True;
>$isComplete = TRUE;
>$isComplete = true;
>
>// Example Use-Case:
>if ($isComplete) {
>	// do something
>} else {
>	// do something else
>}
>```

>[!tip] Values that __evaluates to `false`__
>
> - __Integers__ `0`, `-0` = ___`false`___
> - __floats__ `0.0`, `-0.0` = ___`false`___
> - __Empty String__ `''` = ___`false`___
> - __String `0`__ `'0'` = ___`false`___
> - __Empty Array__ `[]` = ___`false`___
> - __null__ = ___`false`___

> [!tip] `is_bool` 
>__Check whether a variable is a  boolean or not__
> ```php
> $isBoolean = false;
> echo is_bool($isBoolean); // 
> var_dump(is_bool($isBoolean)); // bool(true)
> 
> $isBoolean = (string) true;
> echo is_bool($isBoolean); // 1 
> var_dump(is_bool($isBoolean)); // bool(false)
> ```


