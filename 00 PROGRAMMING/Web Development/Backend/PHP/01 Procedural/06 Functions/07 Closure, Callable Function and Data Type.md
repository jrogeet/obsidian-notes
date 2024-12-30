---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 
>[!info] Closure
>Is the type of __Anonymous Function__ where we can access ___Outer Variables___.
>```php
>$x = 1;
>$sum = function (int|float ...$numbers) use ($x): int | float {
>	$x = 15;
>}
>```


> [!info] Callable Function
> Are functions that are used as a __parameter__ to another Function.
> Built-in functions in php that expect a function as parameter:
> - `array_map`
> - `array_filter`
> - `usort`
> - etc.
### Example and it's 3 Ways

1. 
```php
$array = [1, 2, 3, 4];

array_map(function($element){
	return $element * 2;
}, $array );

echo '<pre>';
print_r($array); // 1, 2, 3, 4

print_r($array2); // 2, 4, 6, 8
echo '</pre>';
```

2. __Anonymous Function__
```php
$x = function($element) {
	return $element * 2;
};

$array2 = array_map($x, $array);
```

3. Defining a __Function with a Name__
```php
function foo($element) {
	return $element * 2;
}

$array2 = array_map('foo', $array);
```


```php
$sum = function(callable $callback, int|float ...$numbers): int|float {
	return $callback(array_sum($numbers));
};

echo $sum('foo', 1, 2, 3, 4);

function foo($element) {
	return $element * 2;
}
```

