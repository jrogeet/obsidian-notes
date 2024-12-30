![[Pasted image 20221216212230.png]]

# Sample Space
Sample Space are the different possible outcomes that may occur. Imagine a dice with six faces can have 6 possible outcomes. These possible outcomes are the basis, not only in computer games, but most chance games that ever existed. Let us determine how this concept works and how can we use it in decision making.

# Counting Principles
**Sum Rule** – Suppose that an event can be performed by either of two different  procedures, with m possible outcomes for the first procedure and n possibilities  for the second. If the two sets of possible outcomes are disjoint, then, the  number of possible outcomes for the event is m+n.  

**Product Rule** – In a sequence of n1 events in which the first has m possibilities  
and the second event has n2, and the third event has n3, and so forth, the total  
number of possibilities of the sequence will be n1(n2)(n3)...(nk).  

**Factorial Notation** – n!


An **Outcome** is the result of a single trial of a probability experiment.  
A **Sample Space** is the set of all possible outcome of a probability experiment.

An **Event** is a collection of one or more outcomes of an experiment.  

A **Simple Events** is an event that includes one and only one of the outcomes for  
an experiment and is denoted by E, also called Elementary Event.  
To pick 1 red card from a deck of cards.  

A **Compound Event** is a collection of more than one outcome for an experiment,  
also called **Composite Event.**  
To pick 1 red card then followed by another red card from a deck of cards.

# Permutation and Combination

### Permutation
is an arrangement of all or part of a number of things in a definite order. The number of permutations of n objects taken r at a time is given by:
$$
P=\frac{n !}{(n-r) !}
$$

- Permutation with Repeated Elements
$$
P_n=\frac{n !}{n_{1} !\left(n_{2} !\right)\left(n_{3} !\right) \ldots} \text { where } n_1+n_2+n_3=n
$$
- Circular Permutation
$$
P_c=(n-1) !
$$
### Combination

Combination is a grouping or selection of all or part of a number of things ( or objects) without reference to the arrangement of the things selected. The number of combinations of `n` objects taker `r` at a time is given by:
- Combination
$$
C(n, r)=\frac{n !}{(n-r) ! r !}
$$
- Combination of different things taken any number at a time
$$
C_n=2^n-1
$$
Example problems:
1. How many ways can you arrange all the letters in the word `MATH` ?  
$$4 *3*2*1 = 24$$
$$
 _4P_4=\frac{4 !}{(4-4) !}=\frac{4 !}{0 !}
$$
2. How many ways can you arrange 2 of the letters in the word `MATH`
$$4 *3 = 12$$
$$
_4 P_2=\frac{4 !}{(4-2) !}=\frac{4 !}{2 !}
$$
$$=\frac {4*3*2*1}{2*1} = 12$$

3. How many numbers between `1` and `100` (inclusive) are divisible by 5 or 8?
$$5 = 20$$
$$8 = 12$$
We will combine both numbers but if there is a duplicate it will only count as `1`.
In total there is `30` numbers because `40` and `80` is also divisible by `5`
$$= 30$$

4. You need to put your reindeer, Lancer, Gloopin, Rudy, and Bloopin, in a single-file line to pull your sleigh. However, Gloopin and Rudy are best friends, so you have to put them next to each other, or they won't fly.

We can count Gloopin and Rudy as `1` so there's only `3` reindeers, now theres only `3!` or `3*2*1` which is equal to `6`.
But we can also make Rudy as first then Gloopin as second, and there would also be `6` outcomes.
so `6*2 = 12`

5. **How many unique ways are there to arrange the letters in the word PRETTY?**

There are `6` letters so its `6!` or `6*5*4*3*2*1` which is equal to `720` , but there is **2 T's** in PRETTY so we're gonna divide 6! to 2!
$$
\frac{6 !}{2 !}=\frac{720}{2}=360
$$
6. **How many numbers between 111 and 100100100 (inclusive) are divisible by 333 or 101010?**

There are `33` numbers divisible by 3 between 1 and 100, and `10` numbers divisible by 10 between 1 and 100.

$$33 + 10=43$$
And there is 3 Numbers that is divisible by both 3 and 10 which is `30`,`60`, and `90`. So we're gonna subtract `43` to `3`.
$$43-3=40$$
Subtracting, there are 43 - 3 = **`40`** numbers divisible by 3 or 10.


# Probability

## Classical Probability
- Each outcome in a sample space is equally likely.
$$
P(E)=\frac{\text { Number of outcomes in event } E}{\text { Number of outcomes in sample space }}
$$
>EXAMPLE:
	 The probability of winning a 1000-ticket raffle with one ticket is 1 / 1000

## Empirical Probability
- Based on observations obtained from probability experiments.
$$
P(E)=\frac{\text { Frequency of event } E}{\text { Total frequency }}=\frac{f}{n}
$$
Commonly used on Surveys - Data Collection.

>EXAMPLE:
After looking at the data from last election, you believe the probability of randomly choosing a voter and them being younger than 35 years old is 30%

## Subjective Probability
- Intuition, educated guesses, and estimates.
- e.g. A doctor may feel has a 90% chance of a full recovery. 

Doctors, Sports Analysists, Weather Man

>EXAMPLE:
After looking at your knee, A doctor claims that the probability you will go back to playing sports is 70%

![[Pasted image 20221220110156.png]]
![[Pasted image 20221220110133.png]]
![[Pasted image 20221220110119.png]]