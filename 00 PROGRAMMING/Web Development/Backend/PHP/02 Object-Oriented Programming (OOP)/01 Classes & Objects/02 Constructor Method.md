---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 


> [!INFO] Constructor Method
> A special function / ___Magic Method___
> - Called when a __new instance__ of the `class` is created.
> ```php
> class Transaction
> {
> 	// Setting the amount to private because it shouldn't be change-able
> 	private float $amount;
> 	private string $description;
> 
> 
> 	public function __construct(float $amount, string $description)
> 	{
> 		$this->amount = $amount;
> 		$this->description = $description
> 	}
> 
> 	public function addTax(float $rate)
> 	{
> 		$this->amount += $this->amount * $rate / 100;
> 	}
> 
> 	public function applyDiscount(float $rate)
> 	{
> 		$this->amount -= $this->amount * $rate / 100;
> 	}
> 	
> 	// To atleast view the amount:
> 	public function getAmount(): float 
> 	{
> 		return this->$amount;	
> 	}
> }
> ```
> 
> _In another file:_
> ```php
> declare(strict_types=1);
> 
> require_once '../Transaction.php';
> 
> // Classes & Objects
> $transaction = new Transaction(100, 'Transaction 1');
> 
> $transaction->addTax(8); // 108
> $transaction->applyDicount(10); // 97.2
> 
> ```

