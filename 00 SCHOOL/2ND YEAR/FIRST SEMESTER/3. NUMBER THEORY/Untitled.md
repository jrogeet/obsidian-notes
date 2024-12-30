# Triangular Numbers
## **Triangular Numbers**

**Triangular numbers are those that can be written as the sum of a consecutive series of (whole) numbers beginning with 1. Thus 6 is triangular because it is the sum of the first three numbers: 6 = 1 + 2 + 3. The first few triangular numbers are 1, 3, 6, 10, 15, 21, 28, 36, 45, and 55 [1]. We denote the nth triangular number by tn .**

**Thus**

         `t5=1+2+3+4+5=15.`

**More generally [1],  
**

                                    `tn = 1+2+3+... + (n−2) + (n−1) + n                               (1 .1)`

**The nth triangular number is given by the formula [1]:**

![TriangularNumberFormula2.png](https://olfu.instructure.com/users/450/files/1560265/preview?verifier=NAG97eTTR6BPDGTogcPNyOlAlwdoq6L3JfaLt2Lw)

**![TriangularNumberExample1.png](https://olfu.instructure.com/courses/140268/files/21293844/preview)**

**Again, let us list the first few triangular numbers:**

       `1, 3, 6, 10, 15, 21, 28, 36, 45, and 55`

**The sum of any two consecutive triangular numbers is a square. For**  
**example [1]:**    

              `t4 + t3  = 10 + 6 =16 = 42   and t5 + t4  = 15 + 10 = 25 = 52 `

**expressed by the formula [1]:**

                                                ` tn + tn-1 = n2                                                          (1.4)`

**Example:**

 **Verify (1.4) for n = 10.**

**Solution:**

**We have [1]:**

                 `t10 + t9 = 55 + 45 = 102`
## Congruence

![Congruence1.png](https://olfu.instructure.com/courses/140268/files/21293275/preview)

![Congruence2.png](https://olfu.instructure.com/courses/140268/files/21293269/preview)
# Odd and Even Numbers

## **!Example 1:**

**The sum of the first 5 odd numbers is 25 [1].**

**(Check this: 1 + 3 + 5 + 7 + 9  = 25 .)**

**Yet, another example:**

**More impressively, the sum of the first 100 odd numbers**  
**is 1002  = 10,000.**

**The great French mathematician LaGrange (1736–1813) showed in**  
**the late eighteenth century that every positive number can be written**  
**as a sum of four or fewer squares. Thus, for example, 30 = 25 + 4 + 1.**  
**Number theorists are fond of numbers, such as 40, which are the sum**  
**of only two squares (e.g., 40 = 36 + 4).**

**The Pythagoreans computed the sum of the first n powers of 2. Let**

## **![PythagorianEquation1-1.png](https://olfu.instructure.com/courses/140268/files/21293812/preview)**

![PythagorianEquation2-1.png](https://olfu.instructure.com/courses/140268/files/21293712/preview)

## **Deficient, Abundant, and Perfect Numbers**

**The Pythagoreans classified all numbers as deficient, abundant, or perfect.  
Given a number, find all of its proper factors, that is, all numbers  
that go into it (with the exclusion of the given number). The proper  
factors of 30, for example, are 1, 2, 3, 5, 6, 10, and 15 [1].**

**If the sum of the proper factors of n is less than n, we call n deficient.If  
the sum exceeds n, it is called abundant. If the sum equals n, we call it  
perfect. For example, 8 is deficient since 1 + 2 + 4 < 8, 18 is abundant  
since 1 + 2 + 3 + 6 + 9 > 18, and 28 is perfect since 1 + 2 + 4 + 7 + 14 =  
28. The smallest perfect number is 6. The first few perfect numbers  
are 6, 28, 496, and 8128. It is not known today whether there are infinitely  
many perfect numbers. Moreover, all known perfect numbers  
are even. No one knows if there are any odd perfect numbers! Incidentally,  
the smallest abundant odd number is 945, while the smallest  
abundant even number is 12 [1].**


# Mersenne Prime Numbers

## **Finding Perfect Numbers**

![PythagorianPrime1.png](https://olfu.instructure.com/courses/140268/files/21293620/preview)

![PythagorianPrime2.png](https://olfu.instructure.com/courses/140268/files/21293549/preview)

**A conjecture is that no odd number (odd number >1) is perfect [1].**

## Continued Fraction

![ContinuedFraction1.png](https://olfu.instructure.com/courses/140268/files/21293281/preview)

![ContinuedFraction2.png](https://olfu.instructure.com/courses/140268/files/21293289/preview)

# Prime Numbers & Proof by Contradiction

## Prime Numbers & Proof by Contradiction  
**

**The first few primes are 2, 3, 5, 7, 11, 13, 17, and 19. A number that has  
divisors (or factors) other than itself and 1 is called composite.  
A composite number must have a prime divisor. Let n be a composite  
number. Then it has a factor, say, m, smaller than n. For example,  
100 has the divisor 25. Now, if m is a prime, we have the desired prime  
divisor. If, on the other hand, m is composite, then m has a smaller  
divisor, say, k. Once again, if k is a prime, we have the desired prime  
divisor. If not, continue the process by producing a still smaller divisor,  
say, j,ofk. Note that these divisors (m, j, and k) are divisors of the  
original number, n. Now, this process can’t go on forever, since n has  
finitely many divisors. It follows that sooner or later, this process  
produces a prime divisor [1].**

**The great Greek geometer and number theorist Euclid, who lived in  
Alexandria, Egypt, circa 300 b.c., proved that there are infinitely many  
primes. He began by assuming that there are only finitely many  
primes and proceeded to obtain a contradiction. (The proof may have  
been known before Euclid wrote it down in his 13-volume book, “Elements.”[1])**

**If there are finitely many primes, call them a, b, c, and so on up to the  
supposed last (or greatest) prime, say, p. Then any number larger than p  
is a composite number, since we are assuming that p is the largest prime.  
Now, let N = abc…p (i.e., N is the product of all the primes), and then  
consider the larger number N + 1 (same as abc…p + 1). Since this  
number is greater than p,itisacomposite number. Then it must have  
a prime divisor. But this prime divisor is clearly a divisor of N (since  
N is the product of all the primes) and cannot, therefore, be a factor  
of N + 1. This is a contradiction! It follows that the initial assumption  
that there is a largest prime is mistaken. Then there are infinitely many  
prime numbers [1].**

**Example: Show using proof by contradiction that if the composite  
number n equals ab, where 1 < a ≤ b < n, then a ≤ n. Assume to the  
contrary that a > n. Then since b ≥ a, we have b ≥ n. Then  
ab > n × n, in which case ab > n, a contradiction.  
As a consequence of the above example, to determine whether a given  
number is a prime, it suffices to check whether it is divisible by any of the  
numbers less than or equal to its square root [1].**

**Example:**

**Show that 41 is a prime number. Since 6 < 41 < 7, we only  
need to check the possible factors 2, 3, 4, 5, and 6.**

**Solution:**

**Since 2 does not go into 41, neither does 4 or 6. Finally, since neither 3 nor 5 goes into 41,**

**we are done. 41 is a prime number.**


# Proof By Construction

## PROOF BY CONSTRUCTION**

**Many proofs employ construction, that is, the claim of the theorem  
is proven by constructing a general example. Here are two theorems  
illustrating this idea. To understand the first proof, recall that n!, read  
“n factorial,” is the product of the first n positive integers, that is,**

**![ProofByConstructionFormula1.png](https://olfu.instructure.com/courses/140268/files/21293572/preview)**

    **Theorem: There are arbitrarily lengthy sequences of consecutive composite numbers.  
Proof: Consider the sequence of n − 1 consecutive numbers n!+2,n!+3, n!+4,…, n!+n.**

**These are all composite. To see this, observe that 2 is a factor of n! + 2, 3 is a factor of n! + 3,**

**4 is a factor of n!+4,…,and finally, n is a factor of n!+n, and the proof is over, since n may be chosen as large as we please.**


## Convergent

**Convergent**

![Convergent1.png](https://olfu.instructure.com/courses/140268/files/21293302/preview)

![Convergent2.png](https://olfu.instructure.com/courses/140268/files/21293312/preview)

# Sums of Two Squares

## **![SumOfTwoSquares1.png](https://olfu.instructure.com/courses/140268/files/21293988/preview)  
**

**Example:**

**Since 50 = 5 × 10, and since 5 = 4 + 1 and 10 = 9 + 1,**

**it** **follows by the above remark**  **that 50 can be written as the sum of two** **squares in two different ways.**

**Guesswork yields 25 + 25 and 49 + 1.**

# Building a Proof on Prior Assertions

## **![PriorAssertion1.png](https://olfu.instructure.com/courses/140268/files/21293817/preview)  
**

![PriorAssertion2.png](https://olfu.instructure.com/courses/140268/files/21293226/preview)

## Diophantine Equation

![Diophantine1.png](https://olfu.instructure.com/courses/140268/files/21293321/preview)

![Diophantine2.png](https://olfu.instructure.com/courses/140268/files/21293134/preview)
