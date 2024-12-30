---
Course: CS50
Topic: Compiling
Week: 2
tags:
  - computerscience
  - cs50
  - c_lang
---
To compile and run programs:
```
clang hello.c

./a.out
```

```
clang -o hello hello.c

./hello
```

- n To import libraries (e.g. the `cs50.h`):
```
clang -o hello hello.c -lcs50
```

but there's an easier way:
- n in CS50 we used these commands like `make hello.c`
	- which does __Compiling__ and _Importing Libraries_ automatically.
```
// Compile
make hello

// Run
./hello
```


> [!abstract]
> To compile and run programs:
> ```
> // Compile
> clang hello.c
> 
> // Run
> ./a.out
> ```
> 
> Renaming the run command:
>  ```
>  clang -o hello hello.c
>  ./hello
>  ```
>  
>  - n To import libraries (e.g. the `cs50.h`):
> ```
> clang -o hello hello.c -lcs50
> ```
> 
>> [!check] but there's an easier way:
>> - n in CS50 we used this command: `make hello`
>> 	- which does __Compiling__ and _Importing Libraries_ easier.
>> ```
>> // Compile
>> 
>> 
>> // Run
>> ./hello
>> ```

> [!info] Major Steps of __COMPILING__:
> 
>> [!example] First: PREPROCESSING
>> Where the header files is copied and pasted into the program:
>> 
>> ```c
>> // #include <cs50.h>
>> string get_string(string prompt);
>> 
>> // #include <stdio.h>
>> int printf(string format, ...);
>> 
>> int main(void)
>> {
>> 	string name = get_string("What's your name? ");
>> 	printf("hello, %s\n", name);
>> }
>> ```
>
>
>> [!example] Second: COMPILING
>> Where the `program` is converted into __Assembly__ code.
>>  ![[Pasted image 20240702172701.png]]
>
>
>> [!example] Third: ASSEMBLING
>> Convertion of the __Assembly__ code into _Machine Code_ by the compiler.
>> ![[Pasted image 20240702172813.png]]
>
>
>> [!example] Finally: LINKING
>> Code from the included __Libraries__ are also converted into _Machine Code_.
>> 	and combined to your code.
>> ![[Pasted image 20240702172941.png]]
>
>
