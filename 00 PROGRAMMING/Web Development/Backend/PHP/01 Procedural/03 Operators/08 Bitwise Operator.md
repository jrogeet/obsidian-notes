---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Design

--- 
- ### & AND
```php
$x = 6;
$y = 3;

// 110
// &
// 011
// ---
// 010 = 2

var_dump($x & $y); // int(2)
```

- ### | OR
```php
$x = 6;
$y = 3;

// 110
// |
// 011
// ---
// 111 = 7

var_dump($x $ y); // int(7)
```
- ### ^ XOR
```php
$x = 6;
$y = 3;

// 110
// ^
// 011
// ---
// 101 = 5

var_dump($x $ y); // int(5)
```
- ### ~ Negation
```php
$x = 6;
$y = 3;

// 110
// ~
// 011
// &
// 011
// ---
// 001 = 1

var_dump($x $ y); // int(1)
```
- ### << Shift bits to Left
	- Moves the bits to the __Left__, effectively __multiplying__ the `number` __by 2__ for each position shifted.
```php
$x = 6;
$y = 3;

// 110
// <<
// 110000 = 48


var_dump($x << $y); // int(48)
```
- ### >> Shift bits to Right
	- Moves the bits to the __Right__, effectively __dividing__ the `number` __by 2__ for each position shifted.
```php
$x = 6;
$y = 3;

// 110
// >>
// 0


var_dump($x >> $y); // int(0)
```
```php
$x = 6;
$y = 1;

// 110
// >>
// 11

var_dump($x >> $y); // int(3)
```