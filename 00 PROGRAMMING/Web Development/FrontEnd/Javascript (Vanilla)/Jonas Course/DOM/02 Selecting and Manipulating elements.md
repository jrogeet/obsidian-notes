---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# Select and Manipulate

--- 
>[!info] Select
>Selecting an element
>```javascript
>document.querySelector('.element')
>```

>[!info] Manipulating
> ```javascript
> document.querySelector('.message').textContent = 'Correct Number!';
> 
> document.querySelector('.number').textContent = 13;
> document.querySelector('.score').textContent = 10;
> ```
>  - select the element using `document.querySelector('.element')`
>  - change its text content using `.textContent = 'New Text';`

>[!tip] selecting value
>Selecting and Reading the value of an element.
>```javascript
>document.querySelector('.guess').value;
>document.querySelector('.guess').value = 23;
>```
> - Get the value of an element using `.value`
