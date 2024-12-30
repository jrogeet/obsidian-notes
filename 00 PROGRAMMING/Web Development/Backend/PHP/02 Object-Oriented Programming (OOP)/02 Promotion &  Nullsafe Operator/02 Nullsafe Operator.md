---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
- Prevents ___ERRORS___ when chaining `properties` and `methods` even 1 of them is `NULL`
- When a `property` or `method` is `NULL`, it automatically __discards__ everything next to it(or to the right)
>[!note]- the `Codes` for the example below
> - _Customer.php_
> ```php
> class Customer
> {
> 	public ?PaymentProfile $paymentProfile = null;
> }
> ```
> - _PaymentProfile.php_
> ```php
> class PaymentProfile
> {
> 	public int $id;
> 	
> 	public function __construct()
> 	{
> 		$this->id = rand();	
> 	}
> }
> ```
> - _Transaction.php_
> ```php
> declare(strict_types = 1);
> 
> class Transaction
> {
> 	public ?Customer $customer = null;
> 	
> 	public function __construct(
> 		private float $amount,
> 		private string $description	
> 	) {
> 	
> 	}
> }
> ```



Makes `customer` __Nullsafe__:
```PHP
$transaction->customer?->paymentProfile->id;

$transaction->getCustomer()?->getPaymentProfile()?->id;
```

> [!tip] Using `Null Coelscing` Instead
> `Null Coelscing` could work,
> ```php
> $transaction->customer->paymentProfile->id ?? 'foo';
> ```
> but it WON'T WORK with `methods`
> ```php
> $transaction->getCustomer()->getPaymentProfile()->id ?? 'foo';
> ```
