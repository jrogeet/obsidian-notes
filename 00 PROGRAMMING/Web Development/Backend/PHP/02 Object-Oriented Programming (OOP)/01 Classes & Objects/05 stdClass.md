---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
```php
$str = '{"a":1, "b":2, "c":3 }';

// 2nd Parameter as TRUE to return it as an ASSOCIATIVE ARRAY
$arr = json_decode($str, true);

var_dump($arr);
```
Output:
![[Pasted image 20240326164843.png]]

__NOT PASSING__ the `2nd Parameter`:
```php
$str = '{"a":1, "b":2, "c":3 }';

// 2nd Parameter as TRUE to return it as an ASSOCIATIVE ARRAY
$arr = json_decode($str);

var_dump($arr);
var_dump($arr->a) // OUTPUT: int(1)
```
Output:
![[Pasted image 20240326164957.png]]


> [!tip] Custom `stdClass`
> ```php
> $obj = new \stdClass();
> 
> $obj->a = 1;
> $obj->b = 2;
> 
> var_dump($obj)
> ```
> Output:
> ![[Pasted image 20240326165327.png]]
