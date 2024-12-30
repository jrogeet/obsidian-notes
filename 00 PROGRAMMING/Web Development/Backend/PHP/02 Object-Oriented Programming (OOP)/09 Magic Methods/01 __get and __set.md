---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

>[!info] `__get`
>```php
>require_once __DIR__ . '/../vendor/autoload.php';
>
>$invoice = new App\Invoice();
>
>$invoice->amount;
>```
>
>
>```php
>namespace App;
>
>class Invoice
>{
>	public function __get(string $name)
>	{
>		var_dump($name); // string(6) "amount"
>	}
>}
>```

>[!info] `__set`
>```php
>public function __set(string $name, $value): void
>{
>	var_dump($name, $value);
>}
>```

>[!caution] 
>If the `property` actually __exists__, and is set to `PUBLIC`
>___None of the `methods` above will produce a value.___
>UNLESS it's in `PRIVATE` or `PROTECTED`:
>```php
>namespace App;
>
>class Invoice
>{
>	private float $amount; // the property is actually defined
>
>	public function __get(string $name)
>	{
>		var_dump($name); // string(6) "amount"
>	}
>	
>	public function __set(string $name, $value): void
>	{
>		var_dump($name, $value);
>	}
>}
>```

> [!example] `property_exists`
> ```php
> namespace App;
> 
> class Invoice
> {
> 	protected float $amount;
> 	
> 	public function __construct(float $amount)
> 	{
> 		$this->amount = $amount;	
> 	}
> 	
> 	public function __get(string $name)
> 	{
> 		if (property_exists($this, $name)) {
> 			return $this->$name;
> 		}	
> 		
> 		return null;
> 	}
> 	
> 	public function __set(string $name, $value): void
> 	{
> 		if (property_exists($this, $name)){
> 			$this->$name = $value;
> 		}
> 	
> 	}
> }
> ```

>[!example] `array_key_exists`
> ```php
> namespace App;
> 
> class Invoice
> {
> 	protected array $data;
> 	
> 	public function __get(string $name)
> 	{
> 		if (array_key_exists($name, $this->data)) {
> 			return $this->$data[$name];
> 		}	
> 		
> 		return null;
> 	}
> 	
> 	public function __set(string $name, $value): void
> 	{
> 		$this->data[$name] = $value;
> 	
> 	}
> }
> ```
