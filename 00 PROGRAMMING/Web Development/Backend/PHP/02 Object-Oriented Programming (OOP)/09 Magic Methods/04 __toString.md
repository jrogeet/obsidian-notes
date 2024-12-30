---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
Runs when interacting with `Methods` as `String` like __Echo-ing it__

```php
require_once __DIR__ .'/../vendor/autoload.php';

$invoice = new App\Invoice();

echo $invoice;
```

```php
namespace App;

class Invoice;

public function __toString(): string
{
	return 'hello';
}
```


##### Stringable
```php
var_dump($invoice instanceof Stringable);
```

P.S. The code below is not needed if `__toString()` __is already defined__:
```php
class Invoice implements \Stringable
{
	// ...
}
```

