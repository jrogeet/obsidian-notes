---
topic: php
---


Tags/Topics: #php #array
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info]
> Reduce the `array` to a Single Value
> `array_reduce($array, callback function)`
> ```php
> array_reduce($array, fn() => ;)
> ```
> 
> ![[Pasted image 20240316142218.png]]
> ```php
> $total = array_ reduce ($invoiceItems, fn($sum, $item) => $sum + $item['qty'] * $item['price']); // 258.9
> ```
> - `$sum` is the __Previous__ value
> 	- Initially, `$sum` is zero (`0`) or `null` 
> - `$item` is the current value
> To set the __Initial Value__:
> ```php
> $total = array_ reduce (
> 	$invoiceItems, 
> 	fn($sum, $item) => $sum + $item['qty'] * $item['price'],
> 	500
> 	); // 758.9
> ```

