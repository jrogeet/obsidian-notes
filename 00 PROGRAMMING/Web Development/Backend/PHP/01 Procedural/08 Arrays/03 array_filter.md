---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] Syntax:
> ___Iterates___ each item of an `array` and ___pass it___ on a given `callback`,
> If the __Result__ of the `callback` is `TRUE` then ___it  goes___ to the __resulting `array`__
> ```php
> $array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
> 
> $even = array_filter($array, fn($number) => $number %2 === 0 ); // Gets every ODD number
> ```

> [!tip] Specify whether the `Callback` will get the `key` or `value`
> - Use the `keys` of the `array` in the __callback__
> `ARRAY_FILTER_USE_KEY`
> ```php
> $even = array_filter ($array, fn($number) => $number % 2 === 0, ARRAY_FILTER_USE_KEY); // Passes the KEYS of an array as an ARGUMENT to the Callback
> ```
> - Uses __BOTH__ the `keys` and `values` as ___Argument___ to the __Callback__
> ```php
> $even = array_filter ($array, fn($value, $key) => $number % 2 === 0, ARRAY_FILTER_USE_BOTH);
> ```

>[!caution] No callback
>All __Falsy__ values will be filtered out.
>```php
>$array = [1, 2, 3, 4, 5, 6, false, 0.0, [], 0 ];
>$even = array_filter($array); // 1, 2, 3, 4, 5, 6
>```
