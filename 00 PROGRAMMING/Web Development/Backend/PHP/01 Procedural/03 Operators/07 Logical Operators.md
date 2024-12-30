---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Logical Operators

--- 

### AND `&&`  Operator
```php
$x = true;
$y = false;
var_dump($x && $y); // bool(false)

$x = true;
$y = true;
var_dump($x && $y); // bool(true)
```

### OR `||` Operator
```php
$x = 1;
$y = 0;
var_dump($x || $y); // bool(true)

$x = 0;
$y = true;
var_dump($x || $y); // bool(true)

$x = 0;
$y = false;
var_dump($x || $y); // bool(false)
```
- As soon as a `True` value appeared, the rest of the values is not evaluated.

### NOT `!` Operator
```php
$x = 1;
$y = 1;

var_dump(!$x && $y); // bool(false)
```

>[!example] Examples:
> - `||`
>```php
>$x = true;
>$y = false;
>
>function Hello() {
>	echo 'Hello World';
>	
>	return false;
>}
>
>var_dump($x || Hello()); // bool(true)
>```
> - `&&`
>```php
>$x = true;
>$y = true;
>
>function Hello() {
>	echo 'Hello World';
>	
>	return false;
>}
>
>var_dump($x && Hello()); // Hello Worldbool(false)
>```
>```php
>$x = false;
>$y = false;
>
>function Hello() {
>	echo 'Hello World';
>	
>	return false;
>}
>
>var_dump($x && Hello() || true); // bool(true)
>```
