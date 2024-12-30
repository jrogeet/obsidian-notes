---
Course: CS50
Topic: Strings
Week: 2
tags:
  - computerscience
  - cs50
  - c_lang
  - "#strings"
---

- ? A `string` is simply an [[007 Array| Array]]  of variables of type `char`: an array of characters.

```c
#include <stdio.h>

int main(void)
{
	char c1 = 'H';
	char c2 = 'I';
	char c3 = '!';

	printf("%c%c%c\n"2, c1, c2, c3); // HI!
	printf("%i %i %i\n"2, c1, c2, c3); // 72 73 33
}
```

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string s = "HI!";
	printf("%s\n", s);
}
```


```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string s = "HI!";
	printf("%c%c%c\n", s[0], s[1], s[2]);
}
```
![[Pasted image 20240702211724.png]]


> [!question] How does the computer know where `string` ends?
> There's a __sentinel value__ at the end of every `string` in a computer's memory
> ![[Pasted image 20240702212002.png]]
> - The __sentinel value__ are all ___0 Bytes___
> 
>   Shorthand notation:
> ![[Pasted image 20240702212212.png]]
> 
> also called __`NUL`__
>![[Pasted image 20240702213015.png]]


- ! not efficient:
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string s = "HI!";
	string t = "BYE!";
	
	printf("%s\n", s);
	printf("%s\n", t);
}
```
![[Pasted image 20240702214724.png]]

- c efficient way:
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string words[2];
	
	words[0] = "HI!";
	words[1] = "BYE!";
	
	printf("%s\n", words[0]);
	printf("%s\n", words[1]);
}
```
- each `string`
![[Pasted image 20240702215308.png]]
- each `char` (2-Dimensional [[007 Array | ARRAY]] )
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string words[2];
	
	words[0] = "HI!";
	words[1] = "BYE!";
	
	printf("%c%c%c\n", words[0][0], words[0][1], words[0][2]);
	printf("%c%c%c%c\n",words[1][0], words[1][1], words[1][2], words[1][3]);
}
```
![[Pasted image 20240702215321.png]]

- x In the image above, it seems that both strings are next to each other in the array.
- Can we access a `char` or a `string` from the other string?
	- c YES!
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	string words[2];
	
	words[0] = "HI!";
	words[1] = "BYE!";
	
	printf("%i%i%i%i%i\n", words[0][0], words[0][1], words[0][2], words[0][3], words[0][4]);
	
	
	// printf("%c%c%c%c\n",words[1][0], words[1][1], words[1][2], words[1][3]);
}
```
- `[0][0]` is 72 or  __H__
- `[0][1]` is 73 or  __I__
-  `[0][2]` is 33 or  __!__
-  `[0][3]` is 0  or __NUL__
-  `[0][4]` is 66 or __B__

> [!example] Example: Getting __Length of a String__
> 
> ```c
> #include <cs50.h>
> #include <stdio.h>
> 
> int string_length(string s);
> 
> int main(void)
> {
> 	string name = get_string("Name: ");
> 	int length = string_length(name);
> 	printf("%i\n", length);
> }
> 
> int string_length(string s)
> {
> 	int n = 0;
> 	while (s[n] != '\0')
> 	{
> 		n++;
> 	}
> 	return n;
> }
> ```
> 
> but there's already a library for this:
> ```c
> #include <cs50.h>
> #include <stdio.h>
> #include <string.h>
> 
> int main(void)
> {
> 	string name = get_string("Name: ");
> 	int length = strlen(name);
> 	printf("%i\n", length);
> }
> ```
> Another Example:
> ```c
> #include <cs50.h>
> #include <stdio.h>
> #include <string.h>
> 
> int main(void)
> {
> 	string s = get_string("Input: ");
> 	printf("Output: ");
> 	for (int i = 0; n = strlen(s); i < n; i++)
> 	{
> 		printf("%c", s[i]);
> 	}
> 	printf("\n");
> }
> ```
> - `int i = 0` is `int`
> - but also the `n = strlen(s)`



> [!example] Using ASCII for lowercase to UPPERCASE Conversion
> ```c
> #include <stdio.h>
> #include <string.h>
> 
> int main(void)
> {
> 	string s = get_string("Before: ");
> 	printf("After: ");
> 	for (int i=0, n = strlen(s); i < n; i++)
> 	{
> 		// If lowercase
> 		if (s[i] >= 'a' && s[i] <= 'z')
> 		{
> 			// printf("%c", s[i] - 32);
> 			printf("%c", s[i] - ('a' - 'A'));
> 		}
> 		else
> 		{
> 			printf("%c", s[i]);
> 		}
> 	}
> 	printf("\n");
> }
> ```
> 
> - c easy way: `toupper` function by ctype.h
> ```c
> #include <stdio.h>
> #include <string.h>
> 
> int main(void)
> {
> 	string s = get_string("Before: ");
> 	printf("After: ");
> 	for (int i=0, n = strlen(s); i < n; i++)
> 	{
> 		printf("%c", toupper(s[i]));
> 	}
> 	printf("\n");
> }
> ```

