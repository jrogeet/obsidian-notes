---
topic: loops with conditions
part: "3.1"
---
Author: [University of Helsinki](https://programming-23.mooc.fi/)
Type: Website
Topics: #python #mooc #loops #conditional 
Link: [Python Programming MOOC 2023](https://programming-23.mooc.fi/)
∗:[[00 PROGRAMMING/Python/_Python/Python]] 

---
# 02 Initialisation, condition and update

--- 
## Steps to Create a Loop

Creating a loop generally involves three steps: initialization, condition, and updating the iteration variables.

### Initialization

Initialization refers to setting the initial value(s) of the variable(s) used in the loop's condition. These variables are often called iteration or iterator variables. Initialization is performed before the loop is entered for the first time.

### Condition

The condition specifies how long the loop should be executed. It is set at the beginning of the loop. The loop will continue executing as long as the condition evaluates to `True`.

### Updating Iteration Variables

During each iteration of the loop, the variables involved in the condition are updated. This ensures that with each repetition, the loop progresses closer to its conclusion.

These three steps work together to control the execution of the loop, defining its behavior and determining when the loop should terminate.

![[Pasted image 20230828182503.png]]

## Components of a Loop

A loop consists of three crucial components: initialization, condition, and updating iteration variables. Neglecting any of these components can lead to incorrect loop behavior.

### Omission of Update Step

If the update step is omitted from a loop, it can lead to an infinite loop where the loop's condition is never met. Consider this example:

```python
number = 1

while number < 10:
    print(number)

print("Execution finished.")
```

- In this case, the value of `number` remains unchanged.
- The loop continues to execute endlessly, repeatedly printing the value 1.
- The program is stuck in the loop until manually interrupted.

To ensure proper loop functioning, all three components must be properly included, allowing the loop to progress correctly and eventually meet its termination condition.
