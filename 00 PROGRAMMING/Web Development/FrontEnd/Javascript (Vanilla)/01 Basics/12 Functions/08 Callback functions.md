---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions 
∗:[[01 Javascript|JavaScript]] 

---
# 02 Callback functions

--- 
```javascript
function ask(question, yes, no) {
	if (confirm(question)) yes()
	else no();
}

function showOk() {
	alert( "You agreed." );
}

function showCancel() {
	alert( "You canceled the execution");
}

// usage: functions showOK, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```
The function ask the `question` and, depends on the user's answer, call `yes()` or `no()`
- Arguments `showOk` and `showCancel` of `ask` are called __callback functions__ or just __callbacks__.
	- `showOk` becomes the callback for "_yes_" answer, and `showCancel` for "_no_" answer.

>[!tip] Using __Function Expressions__ to  shorten:
>```javascript
>function ask(question, yes, no) {
>	if(confirm(question)) yes()
>	else no();
>}
>
>ask(
>	"Do you agree?",
>	function() { alert("You agreed."); },
>	function() { alert("You cancelled the execution."); }
>);
>```
>- here, functions are declared inside `ask(...)` call.
>- They have no name, and so are called __anonymous__
>	- Such functions are ___not accessible outside of___ `ask`
>		- because they're not assigned to variables
