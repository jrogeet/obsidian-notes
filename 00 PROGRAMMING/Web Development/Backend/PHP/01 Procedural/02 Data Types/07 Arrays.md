---
topic: php
---


Tags/Topics: #php #datatypes 
∗:[[0 PHP|PHP]]

---
# Design

--- 
>[!abstract] Array
>```php
>$programmingLanguages = ['PHP', 'Java', 'Python'];
>$programmingLanguges = array('PHP', 'Java', 'Python');
>```
>> [!info] Indexing and Accessing elements
>> ___Numeric `Array` Keys___ __CANNOT be negative__ just like in `strings`
>> ```php
>> echo $programmingLanguages[0]; // PHP
>> echo $programmingLanguages[-1]; // ERROR (Undefined array key -1)
>> ```
>>
>>>[!tip] Check __if `Array` key EXISTS__:
>>>- `isset()`
>>> 	- `isset` checks if a `key` __EXISTS__ ___AND IS NOT `null`___
>>>```php
>>isset($programmingLanguages[3]); // True or False
>>>```
>>> - `array_key_exists`
>>> 	- difference with `isset` is `array_key_exists` returns __True__ or ___False___  even if the value is `null`
>>> ```php
>>>$array = ['a' => 1, 'b' => null];
>>> array_key_exists('a', $array);
>>> 
>>> isset($array['b']);
>>> ```
>>
>>
>>> [!tip] Changing Elements
>>> ```php
>>> $programmingLanguages[1] = 'C++';
>>> ```
>>
>>
>>> [!tip] Printing arrays
>>> ```php
>>> echo var_dump($programmingLanguages);
>>> print_r($programmingLanguages);
>>> 
>>> echo '<pre>';
>>> print_r($programmingLanguages);
>>> echo '</pre>';
>>> ```
>>
>>
>>> [!tip] Get __number of elements__ in an `Array`
>>> ```php
>>> echo count($programmingLanguages); // 3
>>> ```
>>
>>
>>> [!tip] Add elements to an `Array`
>>> pushes elements to an `array`
>>> ```php
>>> $progrmamingLanguages[] = 'C++';
>>> ```
>>>
>>>> [!info] Add multiple elements to an `Array`
>>>> ```php
>>>> array_push($programmingLangugaes, 'C++', 'C', 'GO');
>>>> ```
>>
>>
>>> [!info] Naming `array` __keys__ (__Associative Arrays__):
>>> ```php
>>> $programingLanguages = [
>>> 	'name' => 'value';
>>> 	'php' => '8.0',
>>> 	'python' => '3.9'
>>> ];
>>> ```
>>>
>>>> [!tip] Adding elements to Associative arrays
>>>> ```php
>>>> $programmingLanguages['go'] = '1.15';
>>>> 
>>>> $newLanguage = 'go';
>>>> $programmingLanguages[$newLanguage] = '1.15';
>>>> ```
>>>
>>>> [!abstract] Multi-dimensional arrays
>>>> ```php
>>>> $programmingLanguages = [
>>>> 	'php' => [
>>>> 		'creator' => 'Rasmus Lerdorf',
>>>> 		'extension' => '.php',
>>>> 		'website' => 'www.php.net',
>>>> 		'isOpenSource' => true,
>>>> 		'versions' => [
>>>> 			['version' = > 8, 'releaseDate' => 'Nov 26, 2020'],
>>>> 			['version' = > 7, 'releaseDate' => 'Nov 28, 2019'],
>>>> 		],
>>>> 	], 
>>>> 	// etc ...
>>>> ];
>>>> ```
>>>>
>>>>> [!tip] Accessing multi-dimentional arrays elements
>>>>> ```php
>>>>> echo $programmingLanguages['php']['website']; // www.php.net
>>>>> echo $programmingLanguages['php']['versions'][0]['releaseDate']; // Nov 26, 2020
>>>>> ```
>>>>
>>>>
>>>>> [!tip] Same name keys
>>>>> The __Last declaration__ will be stored.
>>>>> ```php
>>>>> $array = [true => 'a', 1 => 'b', '1' => 'c', 1.8 => 'd', null => 'e']; // d
>>>>> 
>>>>> echo $array[null];
>>>>> echo $array[''];
>>>>> ```
>>
>>
>>> [!info] Removing an element 
>>> from the __END__:
>>> ```php
>>> array_pop($array);
>>> ```
>>> from the __BEGINNING__:
>>> ```php
>>> array_shift($array);
>>> ```
>>> 
>>>> [!info] `unset`
>>>> Unlike `pop` or `shift`, __unset__ doesn't re-arrange ___keys___ or the ___length___ of an array.
>>>> ```php
>>>> // deleting the whole array
>>>> unset($array);
>>>> 
>>>> // specific index
>>>> unset($array[50], $array[1]);
>>>> ```
>>
>>
>>> [!tip] Casting
>>> ```php
>>> $x = 5;
>>> 
>>> (array) $x;
>>> ```
>>










 



