---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 
> [!info] Abstract Class
> - Can't instantiate `abstract classes`
> 	- ___CANT CREATE___ `OBJECT`
> 	- __CAN ONLY BE__ `EXTENDED`
> - Have the `Method`'s __Signature__ and __definition__
> 	- but ___NOT___ the actual ___IMPLEMENTATION___
> - the ___IMPLEMENTATION___ is done in the `CHILD CLASSES`
>> [!note] 
>> A `class` is a _BLUEPRINT_ for an __object__
>> an `ABSTRACT class` is a _BLUEPRINT_ for its __CHILD CLASSes__
>>
>> `ABSTRACT` can only be __PUBLIC__ or __PROTECTED__
>> since it is needed by it's `Child Classes`



>[!example]
>_Index.php_
>```php
>require_once __DIR__ .'/../vendor/autoload.php';
>
>$fields = [
>	new \App\Text('textField'),
>	new \App\Checkbox('checkboxField'),
>	new \App\Radio('radioField'),
>];
>
>foreach($fields as $field) {
>	echo $field->render() . '<br />';
>}
>```
>
>_Field.php_
>```php
>namespace App;
>
>abstract class Field
>{
>	public function __construct(protected string $name)
>	{
>	
>	}
>	
>	abstract public function render(): string;
>}
>```
>
>_Text.php_:
>for Text Fields
>```php
>namespace App;
>
>class Text extends FIeld
>{
>	public function render(): string
>	{
>		return <<<HTML
>		<input type="text" name="{$this->name}" />
>		HTML;
>	}
>}
>```
>
>_Boolean.php_
>for boolean fields (`true/false`, `on/off`)
>```php
>namespace App;
>
>abstract class Boolean extends Field
>{
>	
>}
>```
>
>_Checkbox.php_
>```php
>namespace App;
>
>class Checkbox extends Boolean
>{
>	public function render(): string
>	{
>		return <<<HTML
>		<input type="checkbox" name="{$this->name}" />
>		HTML;
>	}
>}
>```
>
>_Radio.php_
>```php
>namespace App;
>
>class Checkbox extends Boolean
>{
>	public function render(): string
>	{
>		return <<<HTML
>		<input type="radio" name="{$this->name}" />
>		HTML;
>	}
>}
>```
>


