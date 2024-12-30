---
topic: javascript
---
Tags/Topics: #javascript #jsbasics 
∗:[[01 Javascript|JavaScript]] 

---
# 01 Variables

--- 
Variable is a "named storage" for data.

Create a variable using the __let__ keyword.
```javascript
let message;
```

Put data using the assignment operator ___=___:
```javascript
let message;

message = 'Hello'; // store the string 'Hello in the variable named message'

alert(message);
```

Combine the variable declaration and assignment into a single line:
```javascript
let message = 'Hello!'; // define the variable and assign the value

alert(message); // Hello1
```



>[!tip]+ Multi-line Variables
>- not recommended for __readability__:
>```javascript
>let user = 'John', age = 25, message = 'Hello';
> ```
> Default:
> ```javascript
>let user = 'John';
>let age = 25;
>let message = 'Hello';
>```
> Other multi-line style:
> ```javascript
> let user = 'John',
> 	age = 25,
> 	message = 'Hello';
> ```
> 
> ```javascript
> let user = 'John'
> , age = 25
> , message = 'Hello';
> ```
> 

>[!Example]- Copy data from one variable to another
> ```javascript
>  let hello = 'Hello world!';
>
>let message;
>
>//copy 'Hello world' from hello into message
>message = hello;
>
>// now two variables hold the same data
>alert(hello);  //Hello world!
>alert(message); // Hello world!
> ```

>[!DANGER]- Declaring twice triggers an error
> A variable should be declared only once.
> ```javascript
> let message = "This";
> 
> // repeated 'let' leads to an error
> let message = "That"; // SyntaxError: 'message' has already been declared
> ```




## Variable Naming
>[!info]- Two limitations on variables names in JavaScript:
>1. The name must contain only letters, digits, or the symbol ___$___ and ___underline___ ( _ )
>2. The first character __must not be a digit__
> Valid names Examples:
> ```javascript
> let userName;
> let test123;
> ```
> ```javascript
> let $ = 1; // declared a variable with the name "$"
> let _ = 1; // and now a variable with the name "_"
> 
> alert($ + _); // 3
> ```
> Invalid variable names:
> ```javascript
> let 1a; // cannot start with a digit
> 
> let my-name; // hyphens ' - ' aren't allowed in the name
> ```
> 

>[!caution] Case matters
>Variables named ___apple___ and ___APPLE___ are two different variables.

>[!danger]- Reserved names
> [List of reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#keywords) which cannot be used as __variable names__.
> Examples: ___let___, ___class___, ___return___ and ___function___ are reserved.
> Syntax error:
> ```javascript
> let let = 5; // can't name a variable "let", error!
> let return = 5; // also can't name it "return" error!
> ```

 

