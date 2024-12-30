---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!caution] Same name as a `Built-in Class`
> If you have a `class` with the __SAME NAME__ as a `Built-in Class`,
> It would get the ___local___ `class` that you created.


> [!tip] Import from `GLOBAL` not ___Local Namespace___
> ```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(new \DateTime());	
> 	}
> }
> ```
> - add a _Backslash_ (`\`) like `\DateTime()`
> 
> Another Way:
> - Using `use` keyword, Instead of _backslash_
> ```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> use DateTime;
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(new DateTime());	
> 	}
> }
> ```

> [!tip] Importing from other folder
> Two ways:
> 1. _Backslash_ before it
> ```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> use DateTime;
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(new \Notification\Email());
> 	}
> }
> ```
> 2. `use` keyword:
> ```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> use DateTime;
> use Notification\Email; // IMPORT
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(new Email())	
> 	}
> }
> ```

> [!info] How about `Functions`?
> `functions` __when NOT FOUND__ in ___LOCAL namespace___ 
> __FALLSBACK__ into the ___GLOBAL namespace___
> ```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(explode(',', 'hello, world'));	
> 	}
> }
> ```
> ---
> 
> if it exists ___locally___:
> use _backslash_
> 
>```php
> declare(strict_types = 1);
> 
> namespace PaymentGateway\Paddle;
> 
> class Transaction
> {
> 	public function __construct()
> 	{
> 		var_dump(\explode(',', 'hello, world'));	
> 	}
> }
> 
> function explode($separator, $str)
> {
> 	return 'foo';
> }
> ```




