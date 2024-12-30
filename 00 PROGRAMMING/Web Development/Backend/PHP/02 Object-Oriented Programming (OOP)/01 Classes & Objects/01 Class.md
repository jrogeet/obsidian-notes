---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

> [!info] `Class`
> - Class __Name__ could begin with `Letters` or `Underscores` (`_`)
> - Recommended is `1` Single __Class__ per File and nothing else in that File.
>> [!example]
>>
>>> [!note] _Transaction.php_
>>> ```php
>>> // Defining a CLASS
>>> class Transaction
>>> {
>>> 	public $amount;
>>> 	public $description;
>>> }
>>> ```
>>
>> - `public` means it's available to those interacting with the `object` __even outside of the `class`__
>> 	- `public` properties _values_ can be changed.
>> - `properties` with No Value, are automatically set to `NULL`
>> 
>>> [!note] _In another file_:
>>> ```php
>>> require_once '../Transaction.php';
>>> 
>>> $transaction = new Transaction();
>>> 
>>> $transaction -> amount  = 15;
>>> 
>>> var_dump($transaction -> amount); // int(15)
>>> ```
>>
>> - `->` __Object operator__
>> 
>>> [!caution] Defining Property Types
>>> `Property` should ___NOT be accessed___ before _Initialization_
>>> ```php
>>> declare(strict_types=1);
>>> 
>>> class Transaction
>>> {
>>> 	public float $amount;
>>> 	public string $description;
>>> 	public $prop;
>>> }
>>> 
>>> // In another file:
>>>var_dump($transaction->amount); // FATAL ERROR!
>>>
>>> var_dump($transaction); // "amount" => uninitialized(float) "description"=>uninitialized(string)
>>> var_dump($transaction); // (same as above, then) "prop"=> NULL
>>> ```
