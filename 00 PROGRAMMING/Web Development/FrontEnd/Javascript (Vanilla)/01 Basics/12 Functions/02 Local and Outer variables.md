---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions 
∗:[[01 Javascript|JavaScript]] 

---
# 02 Local and Outer variables

--- 
>[!Tip] Local Variables
>Variables __declared inside a function__ is only visible inside that function
>```javascript
>function showMessage() {
>	let message = "Hello, I'm JavaScript!"; // local variable
>	
>		alert( message );
>}
>
>showMessage(): // Hello, I'm JavaScript!
>
>alert( message ); // <-- Error ! the variable is local to the function
>```


>[!Abstract] Global / Outer Variables
>A function __can access an `outer variable`__ as well
>```javascript
>let userName = 'John';
>
>function showMessage() {
>	let message = 'Hello, ' + userName;
>	alert(message);
>}
>
>showMessage(); // Hello, John
>```
>and can ___Modify___ as well
>```javascript
>let userName = 'John';
>
>function showMessage() {
>	userName = "Bob"; // (1) changed the outer variable
>	
>	let message = 'Hello, ' + userName;
>	alert(message);
>}
>
>alert( userName ); // John before the function call
>
>showMessage();
>
>alert( userName ); // Bob, the value was modified by the function
>```

>[!Caution] Global and Local variable with the __SAME NAME__
>The Local variable inside the function, _shadows_ the global variable
>```javascript
>let userName = 'John';
>
>function showMessage() {
>	let userName = "Bob"; // declare a local variable
>	
>	let message = 'Hello, ' + userName; // Bob
>	alert(message);
>	}
>	
>	// the function will create and use its own userName
>	showMessage();
>	
>	alert( userName ); // John, unchanged, the function did not access the outer variable
>```




