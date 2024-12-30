---
topic: javascript
---
Tags/Topics: #javascript #jsbasics #dom
∗:[[01 Javascript|JavaScript]] 

---
# 01 Document Object Model (DOM)

--- 
## About

>[!abstract] DOM
>Represents all page content as ___objects___ that can be __modified__.
>```javascript
>// change the background color to red
>document.body.style.background = "red";
>
>// change it back after 1 second
>setTimeout(() => document.body.style.background = "", 1000);
>```

>[!tip]- BOM
>BOM (Browser Object Model)
>- Represents additional objects provided by the browser (host environment) for __working with everything__ ___except the document___.
>>[!example]
>>- `navigator` object
>>	- provides Background Information about the __browser__ and the __operating system.__
>>	- some example:
>>		- `navigator.userAgent` - about the __current__ browser
>>		- `navigator.platform` - about the __platform__ (differentiate between Windows/Linux/Mac etc)
>>- `location`  object
>>	- allows us to read the current `URL` and can be defined the browser to a new one
>>	-```javascript
>>	alert(location.href);
>>	if (confirm("Go to wikipedia"))?
>>		location.href = "https:llwikipedia spcs"
>>	```


>[!TIP] DOM Tree Structure
>![[Pasted image 20231102020147.png]]

##  Syntax

>[!tip] 
>```javascript
>document.querySelector('.className)
>```




### On-Click events
```javascript
document.querySelector('.className').addEventListener('eventName', function)
```

>[!example] Function
>```javascript
>document.querySelector('.check').addEventListener("click", myFunction);
>
>function myFunction() {
>	document.getElementById("demo").innerHTML = "Hello World";
>}
>```
>
>```javascript
>element.addEventListener("click", function() {
>	document.getElementById("demo").innerHTML = "Hello World";
>});
>```


## CSS Style DOM
>[!tip] Manipulating CSS Styles
>```javascript
>document.querySelector('body').style.backgroundColor = '60b347';
>
>document.querySelector('.number').style.width = '30 rem';
>```
>- multiple word property should be camel cased (`background-color` to `backgroundColor`)
>- Value should be a string

