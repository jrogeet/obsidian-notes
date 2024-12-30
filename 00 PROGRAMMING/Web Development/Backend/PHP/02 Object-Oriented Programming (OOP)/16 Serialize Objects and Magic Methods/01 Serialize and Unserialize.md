---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!abstract]
> The `serialize()` function in PHP is used to convert a PHP value into a storable representation, which is a `string`. 
> This `string` representation can then be saved to a __file__, a __database__, or __transmitted across a network__.

> [!info] `serialize`
> ```php
> echo serialize(true) . PHP_EOL;
> echo serialize(1) . PHP_EOL;echo serialize(true) . PHP_EOL;
> echo serialize(2.5) . PHP_EOL;
> echo serialize('hello world') . PHP_EOL;
> echo serialize([1, 2, 3]) . PHP_EOL;
> echo serialize(['a' => 1, 'b' => 2]) . PHP_EOL;
> ```
> ___OUTPUT___:
> ![[Pasted image 20240330024705.png]]

>[!INFO] `unserialize`
>```php
>var_dump(unserialize(serialize(['a' = 1, 'b' => 2])));
>```
>___OUTPUT___:
>![[Pasted image 20240330024903.png]]
>- `unserialize`-ing __CREATES A NEW__ `OBJECT`
>```PHP
>$invoice = new Invoice();
>
>$str = serialize($invoice);
>
>$invoice2 = unserialize(str);
>
>var_dump($invoice, $invoice2, $invoice === $invoice2);
>```
>___OUTPUT___:
>![[Pasted image 20240330030616.png]]

> [!CAUTION] 
> Failed serialization results to `boolean false`
> ![[Pasted image 20240330031139.png]]
> ___OUTPUT___:
> ![[Pasted image 20240330031228.png]]
