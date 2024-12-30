---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!abstract]


>[!example] Exception
>```php
>namespace App;
>
>class Invoice
>{
>	public function __construct(public Customer $customer)
>	{
>		
>	}
>	
>	public function process(float $amount): void
>	{
>		if ($amount <= 0) {
>			throw_new \InvalidArgumentException('Invalid invoice amount');
>		}
>		
>		// CUSTOM EXCEPTION
>		if (empty($this->customer->getBillingInfo())) {
>			throw new MissingBillingInfoException('Missing billing information');
>		}
>		
>		echo 'Processing' . $amount . ' invoice - ';
>		
>		sleep(1);
>		
>		echo 'OK' . PHP_EOL;
>	}
>}
>```
>
>```php
>use App\Customer;
>user App\Invoice;
>
>require_once __DIR__ ./../vendor/autoload.php';
>
>$invoice = new Invoice(new Customer());
>
>$invoice->process(-25);
>```
>___OUTPUT___:
>![[Pasted image 20240330034809.png]]


> [!tip] __Custom Exceptions__
> ```php
> if (empty($this->customer->getBillingInfo())) {
> 	throw new MissingBillingInfoException();
> }
> ```
> 
> ```php
> namespace App\Exception;
> 
> class MissingBillingInfoException extends \Exception
> {
> 	protected $message = 'Missing billing information';
> }
> ```
> ![[Pasted image 20240330035437.png]]


> [!info] Catch
> ```php
> try {
> 	$invoice->process(25);
> } catch(\App\Exception\MissingBillingInfoException $e) {
> 	echo $e-> getMessage() . ' ' . $e->getFile() . ':' . $e->getLine() . PHP_EOL;
> }
> ```
> ![[Pasted image 20240330040933.png]]
> - the __variable `object`__ -- `$e` is OPTIONAL
> 
>  ```php
> try {
> 	$invoice->process(25);
> } catch(\App\Exception\MissingBillingInfoException) {
> 	echo 'Some error' . PHP_EOL;
> } catch(\InvalidArgumentException) {
> 	echo 'Invalid argument exception' . PHP_EOL;
> }
> ```
>> [!TIP] If the __HANDLING__ of both types of `exceptions` are the same:
>> ```php
>> 	$invoice->process(25);
>> } catch(\App\Exception\MissingBillingInfoException | \InvalidArgumentException $e) {
>> 	echo $e->getMessage()  . PHP_EOL;
>>} 
>> ```

 >[!info] Finally
 >Executes regardless an `Exception` happens or not.
 >```php
 >try {
 >	$invoice->process(25);
 >} catch(\Exception $e) {
 >	echo $e->getMessage() . PHP_EOL;
 >} finally {
 >	echo 'Finally block' . PHP_EOL;
 >}
 >```
 >___OUTPUT___:
 >![[Pasted image 20240330044526.png]]
 >> [!TIP] Return 
 >> the `return` statement from the __Finally__ block will be executed,
 >> if `Try` and `Catch` also has `return` statements.
 >> ```php
 >> require_one __DIR__ . '/../vendor/autoload.php';
 >> 
 >> var_dump(process());
 >> 
 >> function foo() {
 >> 	echo 'foo' . PHP_EOL;
 >> 	
 >> 	return false;
 >> }
 >> 
 >> function process()
 >> {
 >> 	$invoice = new Invoice(new Customer(['foo' => 'bar']));
 >> 	
 >> 	try {
 >> 		$invoice->process(-25);
 >> 		
 >> 		return true;
 >> 	} catch(\Exception $e) {
 >> 		echo $e->getMessage() . PHP_EOL;
 >> 		
 >> 		return foo();
 >> 	} finally {
 >> 		echo 'Finally block' . PHP_EOL;
 >> 		
 >> 		return  -1;
 >> 	}
 >> }
 >> ```
 >> ___OUTPUT___:
 >> ![[Pasted image 20240330050620.png]]

> [!abstract] Error Hierarchy
> ![[Pasted image 20240330050958.png]]



> [!info] Global exception handler
> Register __Global Exception handler__ using:
> ```php
> set_exception_handler(function(\Throwable $e)
> 	{
> 		var_dump($e->getMessage());
> 	}
> ) ;
> ```

---
>[!example]
>```php
>public function process(float $amount): void
>{
>	if ($amount <= 0) {
>		throw InvoiceException::invalidAmount();
>	}
>	
>	if (empty($this->customer->getBillingInfo())) {
>		throw InvoiceException::missingBillingInfo();
>	}
>	
>	echo 'Processing $' . $amount . ' invoice - ';
>	
>	sleep(1);
>	
>	
>}
>```
>
>```php
>class InvoiceException extends \Exception
>{
>	public static function missingBIllingInfo():static
>	{
>		return new static('Missing billing info');
>	}
>	
>	public static function invalidAmount()
>	{
>		return new static('Invalid Invoice number');
>	}
>}
>```
>___OUTPUT___:
>![[Pasted image 20240330052225.png]]
