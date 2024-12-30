---
topic: php
---


Tags/Topics: #php #operators
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info]
> ```php
> $x = 5;
> 
> $x++; // Increment
> $x--; // Decrement
> ++$x; // Pre-Increment
> --$x; // Pre-decrement
> ```

```php
$x = 5;

echo $x++; // 5
echo $x; // 6

echo $x--; // 5
echo $x; // 4

echo ++$x; // 6
echo $x; // 6

echo --$x; // 4
echo $x; // 4

```


```php
$x = true;

echo ++$x; // 1

$y = null;
echo ++$y; // 1
echo --$y; // 1

$z = 'abc';
echo ++$z; // 'abd'
```