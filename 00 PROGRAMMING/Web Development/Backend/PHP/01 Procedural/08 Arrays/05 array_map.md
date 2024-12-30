---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] 
> Applies `callback` to __each element__ of the given `array`.
> 
> Example: Multiplies each element to 3
> ```php
> $array = [1, 2, 3, 4, 5, 6];
> $array = array_map(fn($number) => $number * 3, $array);
> ```
> Multiple Arrays:
> - `values` will be re-Indexed
> 	- Not preserving it's `keys`
> ```php
> $array1 = ['a' => 1, 'b' => 2, 'c' => 3];
> $array2 = ['d' => 4, 'e' => 5, 'f' => 6];
> 
> $array = array_map(fn($number1, $number2) => $number1 * $number2, $array1, $array2);
> ```

