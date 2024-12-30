---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 

### Clone

```php
$invoice = new \App\Invoice();

$invoice2 = clone $invoice;

var_dump($invoice, $invoice2, $invoice === $invoice2);
```

___OUTPUT___:
![[Pasted image 20240330023527.png]]
- `clone` __SHALLOW COPY__ the `properties` 
- and also __COPY THE `ID`__
- but THEY ARE STILL __DIFFERENT `OBJECTS`__

### Magic Clone Method
```php
namespace App;

class Invoice
{
	private string $id;

	public function __construct()
	{
		$this->id = uniqid('invoice_');
		var_dump('__construct');
	}

	public function __clone(): void
	{
		$this->id = uniqid('invoice_');
		var_dump('__clone');
	}
}
```

___OUTPUT___:
![[Pasted image 20240330024321.png]]
- `__construct()` __DOESN'T GET CALLED__ when `clone` is runned.