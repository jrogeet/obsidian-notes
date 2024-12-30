---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!abstract] difference
> - `__sleep()` - called __before the `serialization` happens__
> - `__wakeup()` - called ___after the `serialization` happens___

> [!info] 
> ```php
> class Invoice
> {
> 	public string $id;
> 	
> 	public function __construct (
> 		public float $amount,
> 		public string $description,
> 		public string $creditCardNumber	
> 	) {
> 		$this->id = uniqid('invoice_');	
> 	}
> 	
> 	public function __sleep(): array
> 	{
> 		return['id', 'amount'];	
> 	}
> 	
> 	public function __wakeup(): void
> 	{
> 		// TODO: Implement __wakeup() method.	
> 	}
> }
> public function __sleep(): array
> {
> 	return ['id', 'amount'];
> }
> ```
> ![[Pasted image 20240330032207.png]]
> - `__sleep` must return the __names__ of the `properties` that should be `serialized`
