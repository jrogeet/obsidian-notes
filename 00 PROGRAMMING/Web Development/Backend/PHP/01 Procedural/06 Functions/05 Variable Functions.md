---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 

```php
function sum(int|float ...$numbers): int|float {
	return array_sum($numbers);
}

$x = 'sum';

echo $x(1, 2, 3, 4);
```

Prevent an error, if not sure the `variable` is a __callable `function`__
```php
function sum(int|float ...$numbers): int|float {
	return array_sum($numbers);
}

$x = 'sum';

if (is_callable($x)) {
	echo $x(1, 2, 3, 4);
} else {
	echo 'Not Callable';
}

```