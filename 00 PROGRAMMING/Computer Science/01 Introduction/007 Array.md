---
Course: CS50
Topic: Array
Week: 2
tags:
  - computerscience
  - cs50
  - c_lang
  - "#array"
---

- `bool` 1 byte
- `int` 4 bytes
- `long` 8 bytes
- `float` 4 bytes
- `double` 8 bytes
- `char` 1 byte
- `string` ? bytes

```c
#include <stdio.h>

int main(void)
{
	// Scores
	int score1 = 72;
	int score2 = 73;
	int score3 = 33;
	
	// Print average
	printf("Average: %f\n", (score1 + score2 + score 3) / 3.0);
}
```
![[Pasted image 20240702193743.png]]
- each `variables` are stored somewhere in the computer's memory
- each `BOXES` represents a __byte__ each 
	- `variable` took _4 squares_ since `int` is __4 bytes__ 


# Array

- ! Works, BUT NOT EFFICIENT:
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	int scores[3];
	scores[0] = get_int("Score: ");
	scores[1] = get_int("Score: ");
	scores[2] = get_int("Score: ");
	
	printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
}
```

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	int scores[3];
	for (int i = 0; i < 3; i++)
	{
		scores[i] = get_int("Score: ");
	}
	
	printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / 3.0);
}
```

- c Efficient way:
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
	const int N = 3;
	int scores[N];
	for (int i = 0; i < N; i++)
	{
		scores[i] = get_int("Score: ");
	}
	
	printf("Average: %f\n", (scores[0] + scores[1] + scores[2]) / (float) N);
}
```

![[Pasted image 20240702200025.png]]

```C
int array[] = {73, 72, 33};
```

