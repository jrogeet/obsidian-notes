---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 
a.k.a. __LAMBDA__ Functions
A __Semi-Colon__ `;` is ___REQUIRED___ after the anonymous function.
```php
function (int|float ...$numbers): int|float {
	return array_sum($numbers);
};
```

Accessing Outer Variables `use($___)`:
```php
$x = 1;
$sum = function (int|float ...$numbers) use($x): int|float {
	echo $x;
	return array_sum($numbers);
};
```
- inside the function `$x` is __copied__, not referenced.
- unless, you reference it with ampersand `&`
```php
$x = 1;
$sum = function (int|float ...$numbers) use(&$x): int|float {
	$x = 15;
	echo $x;
	return array_sum($numbers);
};

echo $x; // 15
```