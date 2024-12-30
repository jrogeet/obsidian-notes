https://www.youtube.com/watch?v=-AJic0FjuAA&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=46&t=605s&ab_channel=ProgramWithGio

![[Pasted image 20240328202416.png]]

---

__Abstract Classes__ can also WORK WITH ___Interfaces___
![[Pasted image 20240328202508.png]]

```php
namespace App;

abstract class Field implements Renderable
{
	public function __construct(protected string $name)
	{
	
	}
}
```

_Renderable.php_:
```php
namespace App;

interface Renderable
{
	public function render(): string;
}
```