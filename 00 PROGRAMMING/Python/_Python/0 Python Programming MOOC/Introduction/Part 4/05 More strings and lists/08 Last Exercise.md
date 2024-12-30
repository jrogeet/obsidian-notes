

# My Answer:
```python
def average(a, b):
    bList = []
    for x in range(len(b)):
        lone = b[x] // 10
        bList.append(lone)

    aList = []
    for x in range(len(a)):
        lone = bList[x] + a[x]
        aList.append(lone)

    ave = sum(aList) / len(aList)
    return ave, aList


def percentage(per, a):
    ps = 0
    for x in range(len(per)):
        if per[x] >= 15 and a[x] >= 10:
            ps += 1
    perc = float((ps / len (per)) * 100)
    return perc


def grade(exp, a):
    stars = [0, 0, 0, 0, 0, 0]

    for x in range(len(exp)):
        if exp[x] >= 15 and exp[x] <= 17 and a[x] >= 10:
            stars[1] += 1
        elif exp[x] >= 18 and exp[x] <= 20 and a[x] >= 10:
            stars[2] += 1
        elif exp[x] >= 21 and exp[x] <= 23 and a[x] >= 10:
            stars[3] += 1
        elif exp[x] >= 24 and exp[x] <= 27 and a[x] >= 10:
            stars[4] += 1
        elif exp[x] >= 28 and exp[x] <= 30 and a[x] >= 10:
            stars[5] += 1
        else:
            stars[0] += 1

    fgrade = ''
    for x in range(5, -1, -1):
        fgrade += f'  {x}: '
        fgrade += '*' * stars[x]
        fgrade += '\n'
    return fgrade

def main():
    a = []
    b = []

    while True:
        exex = input('Exam points and exercises completed: ')
        sfdr = exex.split()
        if exex == '':
            break
        else:
            a.append(int(sfdr[0]))
            b.append(int(sfdr[1]))
    print('Statistics:')
    ave, gra = average(a, b)
    print(f'Points average: {ave}')
    print(f'Pass percentage: {percentage(gra, a):.1f}')
    print('Grade distribution:')
    print(grade(gra, a))
    
main()


```



# Model Solution:
```python
def exam_and_exercise_completed(inpt):
    space = inpt.find(" ")
    exam = int(inpt[:space])
    exercise = int(inpt[space+1:])
    return [exam, exercise]
 
def exercise_points(amount):
    return amount // 10
 
def grade(points):
    boundary = [0, 15, 18, 21, 24, 28]
    for i in range(5, -1, -1):
        if points >= boundary[i]:
            return i
 
def mean(points):
    return sum(points) / len(points)
 
def main():
    points = []
    grades = [0] * 6
    while True:
        inpt = input("Exam points and exercises completed: ")
        if len(inpt) == 0:
            break
 
        exam_and_exercises = exam_and_exercise_completed(inpt)
        exercise_pnts = exercise_points(exam_and_exercises[1])
        total_points = exam_and_exercises[0] + exercise_pnts
 
        points.append(total_points)
        grd = grade(total_points)
        if exam_and_exercises[0] < 10:
            grd = 0
        grades[grd] += 1
 
    pass_pros = 100 * (len(points) - grades[0]) / len(points)
 
    print("Statistics:")
    print(f"Points average: {mean(points):.1f}")
    print(f"Pass percentage: {pass_pros:.1f}")
    print("Grade distribution:")
    for i in range(5, -1, -1):
        stars = "*" * grades[i]
        print(f"  {i}: {stars}")
 
main()
```





# Question:
In this exercise you will write a program for printing out grade statistics for a university course.

The program asks the user for results from different students on the course. These include exam points and numbers of exercises completed. The program then prints out statistics based on the results.

Exam points are integers between 0 and 20. The number of exercises completed is an integer between 0 and 100.

The program kees asking for input until the user types in an empty line. You may assume all lines contain valid input, which means that there are two integers on each line, or the line is empty.

And example of how the data is typed in:

Sample output

Exam points and exercises completed: **15 87** Exam points and exercises completed: **10 55** Exam points and exercises completed: **11 40** Exam points and exercises completed: **4 17** Exam points and exercises completed: Statistics:

When the user types in an empty line, the program prints out statistics. They are formulated as follows:

The exercises completed are converted into _exercise points_, so that completing at least 10% of the exercises grants one point, 20% grants two points, and so forth. Completing all 100 exercises grants 10 exercise points. The number of exercise points granted is an integer value, rounded down.

The grade for the course is determined based on the following table:

|exam points + exercise points|grade|
|---|---|
|0–14|0 (i.e. fail)|
|15–17|1|
|18–20|2|
|21–23|3|
|24–27|4|
|28–30|5|

There is also an exam cutoff threshold. If a student received less than 10 points from the exam, they automatically fail the course, regardless of their total number of points.

With the example input from above the program would print out the following statistics:

Sample output

Statistics:
Points average: 14.5
Pass percentage: 75.0
Grade distribution:
  5:
  4:
  3: *
  2:
  1: **
  0: *

Floating point numbers should be printed out with one decimal precision.

**NB:** this exercise doesn't ask you to write any specific functions, so you should **not** place any code within an `if __name__ == "__main__"` block. If any functionality in your program is e.g. in the `main` function, you should include the code calling this function normally, and not contain it in an `if` block like in the exercises which specify certain functions.

**Hint:**

The user input in this program consists of lines with two integer values:

Sample output

Exam points and exercises completed: **15 87**

You have to first split the input line in two and then convert the sections into integers with the `int` function. Splitting the input can be achieved in the same way as in the exercise [First, second and last words](https://programming-23.mooc.fi/part-4/2-more-functions#programming-exercise-first-second-and-last-words), but there is a simpler way as well. The string method `split` will chop the input up nicely. You will find more information by searching for _python string split_ online.