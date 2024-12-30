---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
Triggered when you try to __Call the `object` directly__


```php
namespace App;

class Invoice
{
	public function __invoke()
	{
		var_dump('invoked');
	}
}
```

- Useful for __SINGLE ACTION `CLASSES`__ or __SINGLE RESPONSIBILITY `CLASSES`__
```PHP
class ProcessInvoice
{
	public function __invoke()
	{
		var_dump('invoked');
	}
}
```
- this only serves one purpose, to process the invoice