---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
 >[!info] `list`
 >Assigns the `values` of an __Array__ to `variables`:
 >```php
 >$array = [1, 2, 3, 4];
 >
 >list($a, $b, $c, $d) = $array;
 >
 >// SHORTHAND
 >[$a, $b, $c, $d] = $array; // 1, 2, 3, 4
 >
 >```
 >
 >Skip Elements:
 >```php
 >[$a, , $c, ] =$array; // 1, 3
 >```
 >
 >Nested Arrays:
 >```php
 >$array = [1, 2, [3, 4]];
 >[$a, $b, [$c, $d]] = $array;
 >```
 >
 >Specify `keys`:
 >```php
 >$array = [1, 2, 3];
 >
 >[1 => $a, 0 => $b, 2 => $c] = $array; // 2, 1, 3
 >
 >```



