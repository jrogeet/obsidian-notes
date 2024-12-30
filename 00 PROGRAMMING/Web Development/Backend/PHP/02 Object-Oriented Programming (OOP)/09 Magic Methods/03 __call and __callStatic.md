---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info]  `__call`
> - Called when an __Inaccessible `Method`__ is __CALLED__
>```php
>public function __call(string $name, array $arguments)
>{
>	var_dump($name, $arguments);
>}
>```
>- In this case, we `var_dump` the `Method`'s name and it's `Properties`
>
>> [!example]
>> What if the `METHOD` __accepts some `arguments`?__
>> ```php
>> class Invoice
>> {
>> 	protected function process()
>> 	{
>> 		var_dump($amount, $description);	
>> 	}
>> 	
>> 	public function __call(string $name, array $arguments)
>> 	{
>> 		if (method_exists($this, $name))
>> 		{
>> 		// INSTEAD OF:
>> 		// $this->$name($arguments);
>> 			call_user_func_array([$this, $name], $arguments);
>> 		}	
>> 	}
>> }
>> ```


>[!info] `__callStatic`
> - Called when an __Inaccessible STATIC `Method`__ is __CALLED__
> ```php
> public static function __callStatic(string $name, array $arguments)
> {
> 	var_dump('static', $name, $arguments);
> }
> ```
