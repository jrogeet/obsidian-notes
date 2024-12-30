---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #functions 
∗:[[01 Javascript|JavaScript]] 

---
# 04 Default values

--- 
If a function is called. but an __argument is not provided__, 
the value becomes `undefined`

```javascript
// showMessage(from, text)

showMessage("Ann");
```
- There's no error. 
- This call would output: `*Ann*: undefined`
	- as the value `text` isn't passed, it becomes `undefined`

>[!Info]- Default parameters in __OLD__ JavaScript code
>```javascript
>function showMessage(from, text) {
>	if (text === undefined) {
>		text = 'no text given';
>	}
>	
>	alert( from + ": " + text);
>}
>```
>... Or using the `||` operator
>```javascript
>function showMessage(from, text) {
>	// If the value of text is falsy, assign the default value
>	// this assumes that text == "" is the same as no text at all
>	text = text || 'no text given';
>	...
>}
>```



>[!tip]+
>Specify the "`default`" value for a parameter using `=`:
>```javascript
>function showMessage(from, text ="no text given") {
>	alert( from + ":  " + text );
>}
>
>showMessage("Ann"); // Ann: no text given
>```
>- If there's no value given to `text` the `="no text given"` will take its place.

>[!EXAMPLE] Evaluation of default parameters
> ```javascript
> function showMessage(from, text = anotherFunction()) {
> 	// anotherFunction() only executed if no text given
> 	// its result becomes the value of text
> }
> ```
> A __default parameter__ is evaluated every time the function is called ___without the respective parameter___.
> `anotherFunction()` isn't called if a value is provided to `text`

>[!tip] Assigning default values for parameters after the function declaration
> ```javascript
> function showMessage(text) {
> // ..
> 
> 	if (text === undefined) { // if the parameter is missing
> 		text = 'empty message';
> 	}
> 	
> 	alert(text);
> }
> 
> showMessage(); // empty message
> ```
> with `||` operator:
> ```javascript
> function showMessage(text) {
> 	// if text is undefined or otherwise falsy, set it to 'empty'
> 	text = text || 'empty';
> 	...
> }
> ```
> with nullish coalescing operator `??` (better when most falsy values such as `0` should be considered "normal"):
> ```javascript
> function showCount(count) {
> 	// if count is undefined or null, show "unknown"
> 	alert(count ?? "unknown");
> }
> 
> showCount(0); // 0
> showCount(null); // unknown
> showCount(); // unknown
> ```




