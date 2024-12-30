---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!INFO] Method Chaining
>
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
> 	public function addTax(float $rate): Transaction
> 	{
> 		$this->amount += $this->amount * $rate / 100;
> 		
> 		return $this;
> 	}
> 
> 	public function applyDiscount(float $rate): Transaction
> 	{
> 		$this->amount -= $this->amount * $rate / 100;
> 		
> 		return $this;
> 	}
> 	
> 	// To atleast view the amount:
> 	public function getAmount(): float 
> 	{
> 		return this->$amount;	
> 	}
> 	
> 	// DESTRUCT METHOD:
> 	public function __destruct()
> 	{
> 		echo 'Destruct ' . $this -> description . '<br />';	
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
> $amount = (new Transaction(100, 'Transaction 1'))
> 	->addTax(8)
> 	->applyDiscount(10)
> 	->getAmount();
> 
> var_dump($amount); // Destruct Transaction 1, float(97.2)
> ```
> - `Destruct` happened __first__ because there's no __reference__ available to the `object`
> 
> ```php
> declare(strict_types=1);
> 
> require_once '../Transaction.php';
> 
> $transaction = (new Transaction(100, 'Transaction 1'))
> 	->addTax(8)
> 	->applyDiscount(10)
> 
> 
> var_dump($transaction->getAmount()); // float(97.2) Destruct Transaction 1
> // OR
> $amount = $transaction->getAmount();
> var_dump($amount); // float(97.2) Destruct Transaction 1
> ```
>
>> [!tip] Calling Destructors
>> `destructor` can also be called with:
>> ```php
>> unset($transaction);
>> // AND
>> $transaction = null;
>> ```
>> `Exit`ing script will automatically call the `destructor`
>> ```php
>> exit; // Destructor will still be called
>> ```

