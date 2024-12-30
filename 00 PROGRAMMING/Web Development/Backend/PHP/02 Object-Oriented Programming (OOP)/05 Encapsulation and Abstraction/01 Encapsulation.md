---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!abstract] Encapsulation
>-  Bundles `data` 
> 	- and `methods` that __operate in that__ `data`
> - Makes sure that `object` __manages it's own state__
> 	- `properties` shouldn't be modified outside the class.
> 	- 
>> [!caution] Example:
>> ```php
>> // ...
>> $transaction = new Transaction(25);
>> $transaction->process(); // Processing $25 transaction
>> 
>> // MODIFYING IT:
>> $transaction->amount = 125;
>> 
>> $transaction->process(); // Processing $125 transaction
>> 
>> ```
>> ---
>> ##### Getter and Setter Methods
>> ```php
>> class Transaction
>> {
>> 	private float $amount;
>> 	
>> 	public function __construct()
>> 	{
>> 	}
>> 
>> 	// prints the Amount
>> 	public function getAmount(): float
>> 	{
>> 		return $this->amount;	
>> 	}	
>> 	
>> 	// Modifies the Amount
>> 	public function setAmount(float $amount): float
>> 	{
>> 		$this->amount = $amount;	
>> 	}
>> 	
>> 	public function process()
>> 	{
>> 		echo 'Processing $' . $this->amount . ' transaction';
>> 	}
>> }
>> ```

