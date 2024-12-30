---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Handling Click events

--- 

>[!info]
>```javascript
>document.querySelector.('.check').addEventListener('click')
>
>document.querySelector.('.check').addEventListener('click', function() {
>	console.log(document.querySelector('.guess').value);
>		
>	document.querySelector('.message').textContent = 'Correct Number!';
>});
>```
> - First argument `('click', ... );`, is the __name of the event__ we're listening for.
> - Second argument `( ..., function() {});`, is the __function that will execute__ once the event happens.

>[!example]
>```javascript
>document.querySelector('.check').addEventListener('click', function () {
>	const guess = Number(document.querySelector('.guess').value);
>	console.log(guess, typeof guess);
>	
>	if (!guess) {
>		document.querySelector('.message').textContent = 'No number!';
>	}
>});
>```

