---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions 
∗:[[01 Javascript|JavaScript]] 

---
# 01 Function declaration

--- 
>[!INFO]
>Create a function:
>```javascript
>function name(parameter1, parameter2, ... parameterN) {
>	// body
>}
>```

```javascript
function showMessage() {
	alert( 'Hello everyone!' );
}

showMessage();
showMessage();
```

#### Function Inside a Code Block
>[!INFO] Function Declaration
>```javascript
>function sayHi() {
>	alert( "Hello" );
>}
>```
>>[!danger] Function Declaration within a code block
>> - If a Function Declaration is inside a __code block__,
>> 	- It's visible only inside that block
>> - BUT, Not outside of it.
>> ```javascript
>> let age = prompt("What is your age?", 18);
>> 
>> // conditionally declare a function
>> if(age < 18) {
>> 	
>> 	function welcome() {
>> 		alert("Hello!");
>> 	}
>> } else {
>> 	function welcome() {
>> 		alert("Greetings!");
>> 	}
>> }
>> 
>// ... use it later
>welcome(); // Error:  welcome is not defined
>> ```
>> 
>> > [!example] Another Example:
>> > ```javascript
>> > let age = 16; // take 16 as an example
>> > 
>> > if (age < 18) {
>> > // (runs)
>> > 	welcome();     
>> > 	
>> > 	function welcome() {   // Function declaration is avai
>> > 		alert("Hello!");       // everywhere in the block where it's declared
>> > 	}
>> > 	
>> > 	welcome();
>> > // (runs)
>> > } else {
>> > 	function welcome() {
>> > 		alert("Greetings!");
>> > 	}
>> > }
>> > 
>> > // Here we're out of curly braces,
>> > // so we can not see Function Declarations made inside of them
>> > 
>> > welcome(); // Error: welcome is not defined
>> > ```



---

### Function Expressions!![[07 Function expressions#01 Function expressions]]

---