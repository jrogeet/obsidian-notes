---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

Convert `array` to `object`:
```php
$arr = [1, 2, 3];

var_dump((object) $arr);
```

Output:
![[Pasted image 20240326165601.png]]

#### Accessing properties
```php
$arr = [1, 2, 3];
$obj = (object) $arr;

var_dump($obj->{1}); // OUTPUT: int(2)
```


> [!tip] scalar property
> - __Integer__ to `object`
> ```php
> $obj = (object) 1;
> 
> var_dump($obj->scalar); // int(1)
> ```
> 
> - __Boolean__ to `object`
> ```php
> $obj = (object) true;
> 
> var_dump($obj->scalar); // bool(true)
> ```

> [!info] NULL to object
> Converting __NULL__ to an `object` will result to an ___EMPTY OBJECT___
> ```php
> $obj = (object) null;
> var_dump($obj);  
> ```
