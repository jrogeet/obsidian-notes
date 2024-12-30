---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
Return a `null` or an `array`

###### Problem:
```php
require_once __DIR__ . '/../vendor/autload.php';

$invoice = new App\Invoice();

var_dump($invoice);
```
```php
namespace App;

class Invoice
{
	private float $amount;
	private int $id;
	private string $accountNumber;
}
```
- This prints out __EVERY `PROPERTY`__ of the `CLASS`
	- ___EVEN THE `PRIVATE` ONCE___

---
We can specify __WHICH TO RETURN__ using `__debuginfo`

```php
namespace App;

class Invoice
{
	private float $amount;
	private int $id = 1;
	private string $accountNumber = '0123456789';

	public function __debugInfo(): ?array
	{
		return [
			'id' => $id,
			'accountNumber' => '****' . substr($this->accountNumber, -4),
		];
	}
}
```

```php
require_once __DIR__ . '/../vendor/autload.php';

$invoice = new App\Invoice();

var_dump($invoice);
```
__OUTPUT__:
![[Pasted image 20240329061117.png]]
