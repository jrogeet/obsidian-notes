---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions
∗:[[01 Javascript|JavaScript]] 

---
# Arrow functions

--- 
Useful for simple actions -- one-liners

```javascript
let func = (arg1, arg2, ..., argN) => expression;
```
- Creates a function `func` that accepts arguments `arg1...argN`
- Then evaluates the `expression` on the right side
	- and returns its result
>[!info] It's the shorter version of:
>```javascript
>let func = function(arg1, arg2, ..., argN) {
>	return expression;
>}
>```

>[!Example]
>```javascript
>let sum = (a, b) => a + b;
>
>/* This arrow function is a shorter form of: 
>
>let sum = function(a, b) {
>	return a + b;
>};
>*/
>  
>  alert( sum(1, 2) ); // 3
>```
>>[!Tip] 
>>- If there are __only one argument__, parentheses around parameters can be omitted
>>```javascript
>>let double = n => n * 2;
>>// roughly the same as: let double = function(n) { return n * 2 }
>>
>>alert( double(3) ); // 6
>>```
>> - If there are __no argument__, parentheses are empty, BUT ___they must be present___:
>> ```javascript
>> let sayHi = () => alert("Hello!");
>> 
>> sayHi();
>> ```

>[!TIP] Arrow functions can be used in the same way as __Function Expressions__
>```javascript
>let age = prompt("What is your age?", 18);
>
>let welcome = (age < 18) ?
>	() => alert('Hello!') : 
>	() => alert("Greetings!");
>	
>welcome();
>```

---

# Multiline arrow functions
For multiple expressions and statements,
We can enclose them with `curly braces`
- but, It requires a `return` statement within them to return a value
```javascript
let sum = (a, b) => { // the curly brace opens a multiline function
	let result = a + b;
	return result;
};

alert( sum(1, 2) ); // 3
```


---
### More examples:

>[!example]
>Rewrite with arrow functions:
>```javascript
>function ask(question, yes, no) {
>	if (confirm(question)) yes();
>	else no();
>}
>
>ask(
>	"Do you agree?",
>	function() { alert("You agreed."); },
>	function() { alert("You canceled the execution."); }
>);
>```
>> [!done] with Arrow functions
>>```javascript
>>function ask(question, yes, no) {
>>	if (confirm(question)) yes();
>>	else no();
>>}
>>
>>ask(
>>	"Do you agree?",
>>	() => alert("You agreed."),
>>	() => alert("You canceled the execution.")
>>);
>>```

