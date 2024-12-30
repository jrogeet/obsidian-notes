---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] Union `+`
> Appends items from an `Array` to  another, __If they don't exist IN THE SAME `INDEX`__
> ```php
> $x = ['a', 'b', 'c'];
> $y = ['d', 'e', 'f', 'g', 'h'];
> 
> $z = $x + $y;
> 
> print_r($z); // Array ( [0] => a[1] => b[2] => c[3] => g[4] => h)
> ```
> 
>> [!tip] Associated Arrays
>> ```php
>> $x = ['a' => 1, 'b' => 2, 'c' => 3];
>> $y = ['a' => 9, 'd' => 4, 'e' => 5, 'f' => 6, 'g' => 7, 'h' => 8];
>> 
>> $z = $x + $y;
>> 
>> print_r($z); // Array ( [a] => 1[b] => 2[c] => 3[d] => 4[e] => 5 [f] => 6 [g] => 7 [h] => 8)
>> ```

> [!info] Equality operators `==`/ `!=` and `===` / `!==`
> Checks if both array has the same items
> 
> ```php
> $x = ['a' => 1, 'b' => 2, 'c' => 3];
> $y = [d' => 4, 'e' => 5, 'f' => 6, 'g' => 7, 'h' => 8];
> 
>$z = $x == $y;
> 
> var_dump($z); // bool(false)
>```
>
>- The `key` and the `value` has to be the same to be equal
>```php
> $x = ['a' => 1, 'b' => 2, 'c' => 3];
> $y = ['a' => 1, 'c' => 3,  'b' => '2'];
> 
> // LOOSE comparison
>$z = $x == $y; // TRUE, even if it doesn't have the same order
> // STRICT comparison
> $z = $x === $y; // FALSE ('b' => 2 and 'b' => '2') and it doesn't have the SAME ORDER
> 
>```
