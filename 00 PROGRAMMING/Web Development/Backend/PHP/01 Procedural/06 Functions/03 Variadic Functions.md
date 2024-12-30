---
topic: php
---


Tags/Topics: #php #functions
∗:[[0 PHP|PHP]]

---
# Design

--- 

### "Splat" Operator `...`
Put as many as much `arguments` and store it in an `array` parameter.

```php
declare(strict_types=1);

function sum(...$numbers): int|float {
	$sum = 0;
	
	foreach($numbers as $number) {
		$sum += $number;
	}

	return $sum;
	// This code does the same above:
	// return array_sum($numbers);
}


$a = 6.0;
$b = 7;

echo sum($a, $b, 50, 100, 25, 8, 9) . '<br />'; // 205
```

The __Splat operator__ can be used AFTER the FIXED number of `parameters`
```php
function sum(int|float $x, int|float $y, ...$numbers) :int|float {
	return $x + $y + array_sum($numbers);
}
```

> [!tip] Specific Data type in the `array parameter`
> ```php
> // Expect an Int or Float in $numbers
> function sum(int|float $x, int|float $y, int|float ...$numbers) :int|float {
> 	return $x + $y + array_sum($numbers);
> }
> 
> $a = 6.0;
> $b = 7;
> 
> echo sum($a, $b, 50, '100', '25', 8, 9) . '<br />'; // FATAL ERROR! 
> ```

> [!info] Argument unpacking with splat
> ```php
> // Expect an Int or Float in $numbers
> function sum(int|float $x, int|float $y, int|float ...$numbers) :int|float {
> 	return $x + $y + array_sum($numbers);
> }
> 
> $a = 6.0;
> $b = 7;
> $numbers = [50, 100, 25.90, 8, 9];
> 
> echo sum($a, $b, ...$numbers) . '<br />'; 
> ```
