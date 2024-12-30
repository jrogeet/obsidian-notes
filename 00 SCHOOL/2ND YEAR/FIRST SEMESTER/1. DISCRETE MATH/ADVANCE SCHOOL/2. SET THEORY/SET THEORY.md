# SET THEORY
- A set is a collection of objects called elements.

      $\{1, 2, 3\} = A$
- Sets can be `finite` or `infinite`
	$A = \{1, 2, 3, 4, 5, 6, 7, 8, 9\}$
	$Z = \{1, 2, 3, 4, ...\}$

Additional Points:
- Repeated elements are listed once
$\{a,b,a,c,b,a\} =  \{a,b,c\}$
- <mark class="hltr-orange">There is **NO ORDER** in a set.</mark> 
$\{3,2,1\} = \{1,2,3\}$
$= \{2,1,3\}$
##### Common Sets
- Natural Numbers
	$$N = \{0,1,2,3,...\}$$  $$OR $$   $$\{1,2,3,...\}$$
- Integers
	$$Z = \{...,-2,-1,0,1,2,...\}$$
- Rational Numbers
	$$Q = \{\frac{1}{1}, \frac{1}{2}, \frac{1}{3}, \frac{2}{3}\}$$
## Elements and Cardinality
<center><mark class="hltr-orange">Cardinality (size)</mark> </center>

Let  $C = \{yellow,blue,red\}$

<mark class="hltr-">Yellow</mark> is an element of `C`
>$$Yellow \in C$$


<mark class="hltr-green">Green</mark> is not an element of `C`
>$$Green \notin C$$

The cardinality(size) of `C is 3`
>$$|C|=3$$

## The Empty Set
The Empty Set symbol:    
> ${{\phi}}=\{\}$

It is the only set that has a size of 0
>$|\phi|= 0$

but, What is the size of a **set** containing <mark class="hltr-orange">the Empty Set</mark> ?
> $|\{\varnothing\}|= 1$

The answer is 1, because the BIG SET has 1 element.

BUT, it's different to the set that contains **NOTHING**.
> $|\{\}|=0$

## Set-Builder Notation
1. $\cdot \mathbb{Q}=\{\ldots, 1 / 1,1 / 2,1 / 3,2 / 3, \ldots\}$

$$=\left\{\frac{m}{n} \mid m, n \in \mathbb{Z}, n \neq 0\right\}$$

2. $2 \mathbb{Z}=\{\ldots,-4,-2,0,2,4, \ldots\}$

$$\left\{2 n \mid \begin{array}{l}n \in \mathbb{Z}\end{array}\right\}$$

3. `Desk = {drink, laptop, microphone}`
$$=\{x \mid x\;is\;on\;my\;desk \}$$
### Example:
![[Pasted image 20221107111639.png| 300]]
List the elements of D.
$$1, 2, 3,4 ,5$$

What is the cardinality of D?
$$|D| = 5$$
What is the cardinality of ![[Pasted image 20221107111838.png | 150]]
![[Pasted image 20221107112051.png | 325]]
![[Pasted image 20221107112243.png | 325]]

<br>
<br>


# RELATIONS and FUNCTIONS

<br>


### Relations of relations
- **Reflexive** - For all `X`, we have `xRx` or it means `X` is related to itself.
![[Pasted image 20221107185455.png| 300]]
- **Symmetric** - For all elements `X` and elements `Y`, if `X` is related to `Y` then `Y` is related to `X`
![[Pasted image 20221107185540.png| 300]]
- **Transitive** - For 3 elements `X,Y` and `Z`, If `X` is related to `Y` and `Y` is related to `Z `then `X` is also related to `Z`.
![[Pasted image 20221107185908.png | 300]]

### Functions
![[Pasted image 20221108093142.png | 300 ]]
This function maps an element of `X` into an element of `Y`,
![[Pasted image 20221108093227.png | 300]]
Which we will call it `Y1`
![[Pasted image 20221108093248.png | 300]]
![[Pasted image 20221108093439.png | 500]]
Wherever we put the elements in `X` it will always be maps to `Y` and what we call the `Y` is **RANGE**.
![[Pasted image 20221108093703.png | 350]]
The `REDZONE` here is part of the CODOMAIN but is not part of the RANGE
![[Pasted image 20221108093805.png | 300]]


## Domain and Range

The **domain and range** are defined for a [relation](https://www.cuemath.com/algebra/relations-in-math/) and they are the sets of all the x-coordinates and all the y-coordinates of ordered pairs respectively. For example, if the relation is, R = {(1, 2), (2, 2), (3, 3), (4, 3)}, then:

-   Domain = the set of all x-coordinates = {1, 2, 3, 4}
-   Range = the set of all y-coordinates = {2, 3}

We can visualize this here:

![[Pasted image 20221108111351.png]]


- DOMAIN - all of the first values (`X` coordinates)
- RANGE - all of the second values (`Y` coordinates)

- CONTINUOS GRAPHS - Graphs with `CONNECTED LINES` or `CURVES` (includes values that are not integers)
- DISCRETE GRAPHS - Graph that contains `POINTS` that are only Integers. **There is not a line connecting the points**.

<br>
<br>


![[Pasted image 20221108095315.png]]
DISCRETE GRAPH

- Domain: X
`{-3, -2, -1, 0, 1, 2}`
- Range: Y
`{4, 3, 2, 1, 0, -1}`

![[Pasted image 20221108095506.png]]
CONTINUOS GRAPH
- Domain: X
`-7, ≤ x ≤ 6`
- Range: Y
`-5 ≤ y ≤ 4`

![[Pasted image 20221108095806.png]]
DISCRETE GRAPH
- Domain: X
`{1 , 2, 3, ... , 9}`
- Range: Y
`{50, 100, 150, ... , 400}`

![[Pasted image 20221108100036.png]]
CONTINUOUS GRAPH
- Domain: X
`All Real Numbers (ARN) or -∞ ≤ X ≤ ∞`
- Range: Y
`All Real Numbers (ARN) or -∞ ≤ Y ≤ ∞`

![[Pasted image 20221108100506.png]]
CONTINUOUS GRAPH
- Domain: X
`1 ≤ X ≤ 5`
- Range: Y
`3 ≤ Y ≤ 4`

![[Pasted image 20221108100724.png]]
DISCRETE
- Domain: X
`{1, 4, 8}`
- Range: Y
`{1, 4}`

## Domain and Range of Function
The **domain and range of a function** are the components of a [function](https://www.cuemath.com/calculus/What-are-functions/). The domain is the set of all the input values of a function and range is the possible output given by the function. Domain→ Function →Range. If there exists a function f: A →B such that every element of A is mapped to elements in B, then A is the domain and B is the co-domain. The image of an element 'a' under a relation R is given by 'b', where (a,b) ∈ R. The range of the function is the set of images. The domain and range of a function is denoted in general as follows: Domain(f) = {x ∈ R} and range(f)={f(x) : x ∈ domain(f)}

![[Pasted image 20221108111524.png]]
The domain and range of this function f(x) = 2x is given as domain D ={x ∈ N } , range R = {(y): y = 2x}

## Algebra of Function
If `f` and `g` are functions, and `X` is an element of the domain of each function, then
$$(f + g) (x) = f(x) + g(x)$$
$$(f - g)(x) = f(x) - g(x)$$
$$(f * g)(x) = f(x) * g(x)$$
$$(\frac{f}{g})(x)= f\frac{x}{g(x)}, g(x) ≠ 0 $$