---
Course: CS50
Topic: command-line
Week: 2
tags:
  - computerscience
  - cs50
  - c_lang
---
Quick way of running programs through command-line.

```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
	if (argc == 2)
	{
		printf("hello, %s\n", argv[1]);
	}
	else
	{
		printf("hello, world\n");
	}
}
```

```
./greet David

OUTPUT: hello, David
```
- `argc` - the __number__ of command line _arguments_
- `argv` - an [[007 Array | array]] of the characters passed as _arguments_ at the command line.
```c
printf("hello, %s\n", argv[0]);
```
- This would result into: `hello, ./greet`
```c
printf("hello, %s\n", argv[2]);
```
- This would result into: `hello, (null)`

```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
	for (int i = 0; i < argc; i++)
	{
		printf("%s\n", argv[i]);
	}
}
```

```
./greet David Malan

OUTPUT: David
		Malan
```


### Exit

```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Missing command-line argument\n");
        return 1;
    }
    printf("hello, %s\n", argv[1]);
    return 0;
}
```
- `return 0;` - success


