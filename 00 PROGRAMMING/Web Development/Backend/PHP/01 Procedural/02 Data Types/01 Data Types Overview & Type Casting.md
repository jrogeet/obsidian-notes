---
topic: php
---


Tags/Topics: #php #datatypes 
∗:[[0 PHP|PHP]]

---
# Data Types & Type Casting

--- 

> [!abstract] Scalar Types
> ```php
> # BOOLEAN
> # bool - true / false
> $completed = true;
> 
> # INTEGER
> # int - 1, 2, 3, 8, -5 (no decimal)
> $score = 75;
> 
> # FLOAT (DECIMAL)
> # float - 1.5, 0.1, 0.005, -15.8
> $price = 0.99;
> 
> # STRING
> # string - "Gio", "Hello World"
> $greeting = 'Hello Gio';
> 
> echo $completed . '<br />'; // 1
> echo $score . '<br />'; // 75
> echo $price . '<br />'; // 0.99
> echo $greeting . '<br />'; // Hello Gio
> ```
> 

> [!tip] ## Get Types of a Variable
>> [!example] gettype($variable);
>> ```php
>> echo gettype($price); // double
>> echo gettype($score); // int
>> echo gettype($completed); // boolean
>> echo gettype($greeting); // string
>> ```
>
>> [!example] var_dump($variable);
>> Prints the `value` and `data type`
>> ```php
>> var_dump($price); // float(0.99) 
>> var_dump($greeting); // string(9) "Hello Gio"
>> var_dump($score); // int(75)  
>> ```

>[!abstract] Compound Types
>
>> [!info] Array
>> ```php
>> $companies = [1, 2, 3, 0.5, -9.2, 'A', 'b', true];
>> print_r($companies);
>> ```
>
>> [!example] More:
>>  - Object
>>  - Callable
>>  - Iterable

>[!abstract] 2 Special Types
> - resources
> - null


>[!tip] Type Juggling / Type Coercion
>PHP converts a value based on context.
>PHP will throw an error, if it can't convert dynamically.
>```php
>function sum(int $x, int $y) {
>	var_dump($x, $y);
>	return $x + $y;
>}
>
>$sum = sum(2.5, '3');
>
>echo $sum; // int(2) int (3) 5
>```

>[!caution] Strict Type
>```php
>declare(strict_types=1);
>```


>[!tip] Type Casting
>Force a variable to be a certain data type
>```php
>$x = (int) '5';
>
>var_dump($x); // int(5)
>```
