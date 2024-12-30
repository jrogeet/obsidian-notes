---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!abstract]
> A combination of `__sleep`, `__wakeup` & `\Serializable` Interface
> - When `__serialize` or `__unserialize` is __present__ together with `__sleep` or `__wakeup`
> 	- `__sleep` and `__wakeup` __will get ignored__


> [!info] `__serialize()`
> ```php
> public function __serialize(): array
> {
> 	return [
> 		'id' => $this->id,
> 		'amount' => $this->amount,
> 		'description' => $this->description,
> 		'creditCardNumber' => base64_ encode($this->creditCardNumber),
> 		'foo' => 'bar',	
> 	]
> }
> ```
> ___OUTPUT___:
> ![[Pasted image 20240330032807.png]]
> - `__serialize()` must return an __array that represents the `object`__

>[!info] `__unserialize()`
> Gets the `data` that was __Unserialized__ as the __ARGUMENT__
> ```PHP
> public function __unserialize(array $data): void
> {
> 	var_dump($data);
> }
> ```
> ```php
> $str = serialize($invoice);
> 
> $invoice2 = unserialize($str);
> ```
> ___OUTPUT___:
> ![[Pasted image 20240330033345.png]]
> ---
> ![[Pasted image 20240330033501.png]]
> ![[Pasted image 20240330033530.png]]

