---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Comparison Operators

--- 


### Equal or Not Equal
```php
$x = 5;
$y = 3;

var_dump($x == $y); // bool(true)
var_dump($x != $y); // bool(false)
// Almost the same as (!=):
var_dump($x <> $y); // bool(false)

// STRICT:
var_dump($x === $y); // bool(false)
var_dump($x !== $y); // bool(true)
```

`==` automatically convert values:
```php
$x = 5;
$y = '5';

var_dump($x == $y); // bool(true)
var_dump($x === $y); // bool(false)


var_dump(0 == "a"); // bool(false)
var_dump("1" == "01");  // bool(true)
var_dump("10" == "1e1");  // bool(true)
var_dump(100 == "1e2"); // bool(true)

```

>[!example]
>```php
>$x = 'Hello World';
>$y = strpos($x, 'H'); // strpos finds the letter 'H' then RETURN its INDEX
>
>if ($y == false) { 
>	echo 'H Not Found';
>} else {
>	echo 'H Found at index ' . $y;
>}
>
>```
> - `'H'` is in __Index__ `0`, and `0 == false` is __True__.
>
>Use strict comparison:
>```php
>if ($y === false) { 
>	echo 'H Not Found';
>} else {
>	echo 'H Found at index ' . $y;
>}
>```



### Greater or Less than

```php
$x = 5;
$y = 3;

var_dump($x < $y); // bool(false)
var_dump($x > $y); // bool(true)
var_dump($x <= $y); // bool(false)
var_dump($x >= $y); // bool(true)

// SPACESHIP operator
// returns 0 if EQUAL, -1 if LESS THAN, 1 if GREATER THAN
var_dump($x <=> $y); // int(1)
```


### Ternary Operator
```php
$result = $y === false ? 'Return if TRUE' : 'Return if FALSE'
```

> [!tip] __Stacking__ Ternary Operator
> Use __Parentheses `( )`__ when stacking Ternary Operators
>```php
>$age = 25;
>$status = ($age >= 18) ? (($age < 21) ? "Young Adult" : "Adult") : "Minor";
>
>echo $status;
>```


### Null Coelscing operator

```php
$x = null;
$y = $x ?? 'Hello';

var_dump($y); // string(5) "Hello"

$x = false;
$y = $x ?? 'Hello';

var_dump($y); // bool(false)
```
