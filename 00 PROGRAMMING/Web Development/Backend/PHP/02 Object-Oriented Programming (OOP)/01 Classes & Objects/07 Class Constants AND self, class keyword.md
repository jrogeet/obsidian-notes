---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 


> [!info]
> ```php
> declare(strict_types = 1);
> 
> namespace App\PaymentGateway\Paddle;
> 
> class Transaction
> {
> 	public const STATUS_PAID = 'paid';
> 	public const STATUS_PENDING = 'pending';
> 	public const STATUS_PAID = 'declined';
> 	
> 	public function __construct()
> 	{
> 	}
> 	
> }
> ```

> [!tip] Accessing `CLass Constants` & `self` keyword
> - Outside
> ```php
> echo Transaction::STATUS_PAID;
> ```
> - Accessing Inside:
>  ```php
> declare(strict_types = 1);
> 
> namespace App\PaymentGateway\Paddle;
> 
> class Transaction
> {
> 	public const STATUS_PAID = 'paid';
> 	public const STATUS_PENDING = 'pending';
> 	public const STATUS_PAID = 'declined';
> 	
> 	public function __construct()
> 	{
> 		var_dump(Transaction::STATUS_PAID);
> 		// OR
> 		var_dump(self::STATUS_PAID);
> 	}
> 	
> }
> ```
> - `self` is like `this` in _Objects_
> 	- `self` refers to the __Current Class__


> [!info] `::class`
> Get the fully qualified`class Name`/ `namespace`:
> ```php
> $transaction = new Transaction();
> 
> echo Transaction::class;
> 
> echo $transaction::class;
> ```

>[!example]
>- _Index.php_
>```php
>use App\Enums\Status;
>use App\PaymentGateway\Paddle\Transaction;
>
>require_once __DIR__ . '/../vendor/autoload.php';
>
>$transaction = new Transaction();
>
>$transaction->setStatus(Status::PAID);
>
>var_dump($transaction);
>```
>- _Transaction.php_
>```php
>namespace App\PaymentGateway\Paddle;
>
>use App\Enums\Status;
>
>class Transaction
>{
>	private string $status;
>
>	public function __construct()
>	{
>		$this->setStatus(Status::STATUS_PENDING);
>	}
>	
>	public function setStatus(string $status): self
>	{
>		if (! isset(Status::ALL_STATUSES[$status])){
>			throw new \InvalidArgumentException('Invalid status');
>		}
>		$this->status = $status;
>		
>		return $this;
>	}
 >}
>```
>
>_Status.php_
>```php
>namespace App\Enums;
>
>class Status
>{
>	public const PAID = 'paid';
>	public const PENDING = 'pending';
>	public const DECLINED = 'declined';
>	
>	public const ALL_STATUS = [
>		self::PAID => 'Paid',
>		self::PENDING => 'Pending',
>		self::DECLINED => 'Declined',
>	];
>}
>```

