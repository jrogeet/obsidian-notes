---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 
Normal Function:
```php
$array2 = array_map(function($number) {
	return $number * $number;
}, $array);
```

> [!info] Arrow Function Version:
> ```php
> $array2 = array_map(fn($number) => $number * number, $array);
> ```
> We can use `variables` in the __Parent/Local Scope__ without the need for `use()`:
> BUT __CANNOT BE MODIFIED__
> ```php
> $y = 5;
> $array2 = array_map(fn($number) => $number * number * ++$y, $array);
> 
> echo $y; // 5
> ```
