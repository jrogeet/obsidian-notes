---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #numbers
∗:[[01 Javascript|JavaScript]] 

---
# Design

--- 

> [!info] #### Underscores `_`
> We can write numbers with __Underscore__ `_` __for READABILITY__
> JavaScript ___ignores___ `_` ___between digits___
> ```javascript
> // INSTEAD OF WRITING 1 BILLION like this:
> let billion = 1000000000;
> 
> // we can use UNDERSCORE _ as the SEPARATOR:
> let billion = 1_000_000_000;
> ```

Though we try to avoid writing a lot of zeroes.

> [!tip] ### Shortening Zeroes:
> We can shorten a number by adding the __letter__ `"e"` to it and __specifying the zeroes count__:
> ```javascript
> let billion = 1e9; // 1 billion, literally: 1 and 9 zeroes
> 
> alert( 7.3e9 ); // 7.3 billions (same as 73000000000 or 7_300_000_000)
> ```
>> [!abstract] In other words
>> `e` multiplies the number `1` with the given zeroes count.
>> ```javascript
>> 1e3 === 1 * 1000; // e3 means *1000
>> 1.23e6 === 1.23 * 1000000; // e6 means * 1000000 - the answer is 1,230,000
>> ```
>
>
>> [!abstract] Microdecimals
>> A ___negative number___ after `"e"` means a __division by 1__ with the given number of zeroes
>> 1 microsecond (one millionth of a second):
>> ```javascript
>> let mcs = 0.000001;
>> 
>> let mcs = 1e-6; // five zeroes to the left from 1
>> ```
>> There are ___6___ if we count them, so its `1e-6`
>>
>> ```javascript
>> // -3 divides by 1 with 3 zeroes
>> 1e-3 === 1 / 1000; // 0.001
>> 
>> // -6 divides by 1 with 6 zeroes
>> 1.23e-6 === 1.23 / 1000000; // 0.00000123
>> 
>> // an example with a bigger number
>> 1234e-2 === 1234 / 100; // 12.34, decimal point moves 2 times
>> ```



