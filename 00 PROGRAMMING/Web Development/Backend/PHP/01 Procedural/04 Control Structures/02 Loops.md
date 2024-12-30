---
topic: php
---


Tags/Topics: #php #controlstructure
∗:[[0 PHP|PHP]]

---
# Design

--- 

### While
> [!abstract] While Loop
> ```php
>$i = 0;
>
>while ($i <= 15) {
>	echo $i;
>}
>```
>Embedded in HTML:
>```php
>while ($i <= 15):
>	echo $i;
>endwhile;
>```


> [!info] Break
> ```php
> $i = 0;
> 
> while (true) {
> 	while ($i > 10) {
> 		break 2;
> 	}
> }
> ```
> - The `2` next to `break` means to __get out of the loop 2 LEVELS__
> 	- So, it will get out of `while($i >10)` and `while(true)`

> [!info] Continue
> Skips to the next iteration
> ```php
> $i = 0;
> 
> while ($i <= 15) {
> 	if ($i % 2 === 0) {
> 		i++;
> 		
> 		continue;
> 	}
> 	
> 	echo $i++ . ','; // 1, 3, 5, 7, 9, 11, 13, 15,
> }
> ```

#### Do-While
> [!abstract] Do-While Loop
> Runs `do` __1 time__, then checks `while` if `do` will run again
> ```php
> $i = 0; // 0123456789101112131415
> $i = 25; // 25
> do {
> 	echo $i++;
> } while ($i <= 15);
> ```

### For Loop
> [!abstract] For Loop
> ```php
> for ($i = 0; $i < 15; $i++) {
> 	echo $i;
> }
> 
> // Empty (Inf Loop)
> for (; ; ) {
> 	echo $i;
> }
> 
> for ($i = 0; $i < 15; print $i, $i++) { // 01234567891011121314
> }
> 
> for ($i = 0; print $i, $i < 15; $i++){ //0123456789101112131415
> }
> 
> // ARRAYS
> $text = ['a', 'b', 'c', 'd'];
> for ($i  = 0, $length = count($text); $i < $length; $i++) {
> 	echo $text[$i] . '<br />';
> }
> ```
>
>> [!info] Embedded in HTML
>> ```php
>> for ():
>> 	...
>> endfor;
>> ```
```
```

### For Each Loop

> [!abstract] For Each
> ```php
> $programmingLanguages = ['php', 'java', 'c++', 'go', 'rust'];
> 
> foreach($programmingLanguages as $language) {
> 	echo $language . '<br />';
> }
> 
> // GET KEYS OF ARRAY
> foreach($programmingLanguages as $key => $language) {
> 	echo $key . ': ' . $language . '<br />';
> }
> ```
> 
> MODIFY THE VALUES:
> Add an ampersand `&`
> - __References the Original__ Values of the `Array`
> ```php
> foreach($programmingLanguages as $key => &$language) {
> 	$language = 'php';
> }
> 
> print_r($programmingLanguages); // Array ([0] => php [1] => php [2] => php [3] => php [4] => php)
> ```
>> [!caution] Using `&` references the Original Values
>> After the `foreach` loop, `&$language` still references to the __last item__
>> ```php
>> foreach($programmingLanguages as $key => &$language) {
>> 	echo $key . ': ' . $language . '<br />';
>> }
>> 
>> $language = 'php'; // ['php', 'java', 'c++', 'go', 'php']
>> 
>> // USE unset to destroy the variable
>> unset($language);
>> ```
>
>
>> [!tip] Iterating on different types `string` & `array` from an __Associative array__
>> ```php
>> $user = [
>> 	'name' => 'Gio',
>> 	'email' => 'gio@email.com',
>> 	'skills' => ['php', 'graphql', 'react'],
>> ];
>> 
>> // ERROR: Array to string conversion
>> foreach($user as $key => $value) {
>> 	echo $key . ': ' . $value . '<br />';
>> } 
>> 
>> // json_encode
>> foreach($user as $key => $value) {
>> 	echo $key . ': ' . json_encode($value) . '<br />';
>> } 
>> 
>> // implode
>> foreach($user as $key => $value) {
>> 	echo $key . ': ' . implode($value) . '<br />';
>> } 
>> 
>> //
>> foreach($user as $key => $value) {
>> 	echo $key . ': ';
>> 	
>> 	if (is_array($value)) {
>> 		foreach($value as $skill) {
>> 			echo $skill . ' - ';
>> 		}
>> 	} else {
>> 		echo $value;
>> 	}
>> 	
>> 	echo '<br />';
>> } 
>> ```
>
>
>> [!info] Embedded in HTML
>> ```php
>> foreach ():
>> 	...
>> endforeach;
>>```
>>

 


