---
subject: 
---
Tags:
Links:
Created: 2023-08-22

---
# Sets

---

A ___set___ is a collection of objects.

For example, the collection of the four letters _a_, _b_, _c_, and _d_ is a _set_, which we may name __L__; we write ___L = {a, b, c, d}___.

The objects comprising a set are called its ___elements___ or ___members___.
For example:
	_b_ is an element of the set __L__; in symbols, _b_ ∈ __L__.
	On the other hand _z_ is not an element of __L__
	and we write _z_ ∉ __L__.
	![[Pasted image 20230823175624.png | 400]]

In a set repetitions of the elements are not distinguished.
So the set _{red, blue, red}_ is the same set as __{red, blue}__.

Similarly, the order of the elements is immaterial;
For example:
	_{3, 1, 9}, {9, 3, 1}_ and _{1,3,9}_ are the same set.
	![[Pasted image 20230823180759.png | 400]]
	![[Pasted image 20230823175527.png | 400]]
In short, two sets are equal if and only if they have the same elements.

The size or cardinality of a set is the number of elements it contains.
So if ___A = {1, 2, 3}___
then the Cardinality of A is 3 / __| A | = 3__

_P = { p | p is a prime }_ then __| P | = ∞__

---
The elements of a set doesn't need to be related in any way;
For example:
	_{3, red, {d, blue}}_ is a set with __Three elements__,
	one which is itself a set.

### Singleton and Empty Set
A set that only has _ONE element_ is called __SINGLETON__.
For example:
	_{1}_ is the set with __1__ as its only element;
	So _{1}_ and __1__ are quite different.

A set that has _NO element_ is called the __empty set__.
and is denoted by _∅_.
	Any set other than the empty set is said to be nonempty.

---
### Infinite sets
Some sets cannot be written like the other sets by simply listing all their elements, separated by commas and included in braces.
For example:
	the set _N_ of natural numbers is __infinite__; we may suggest its elements by writing _N = {0, 1, 2, ...},_ by using the three dots and you intuition in place of an infinitely long list.

A set that is not infinite is __finite__.


### Set Builder Notation
In most cases we don't write out all the elements in a set but will write a shorthand description using ___set builder notation___
$$ P = \{p \ | \ p \ is \ a \  prime\} $$ 
"___p___ such that ___p___ is a prime"

Another way to specify a set is by referring to other sets and to properties that elements may or may not have.

If _B = {1, 3, 9}_ and __G = {3, 9}__, 
__G__  may be described as the set of elements of _B_ that are greater than 2

$$G=\{x: x \in B \text { and } x \text { is greater than } 2\}$$
In general, if a set _A_ has been defined and _P_ is a property that elements of _A_ may or may not have, then we can define a new set.
$$B=\{x: x \in A \text { and } x \text { has property } P \}$$
As another example, the __set of odd natural numbers__ is
$$O=\{x: x \in \mathbf{N} \text { and } x \text { is not divisible by } 2\}$$

---

# Subsets
A set is a subset of another if all its elements are also elements of another set.
![[Pasted image 20230823181700.png | 400]]
And we use this symbol __⊆__ to denote the _A_ is a subset of _B_.

___O___ ⊆ __N__, since each _Odd natural number_ is a __Natural number__.

If _A_ is a subset of __B__ but _A_ is not the same as __B__, 
we say that _A_ is a ___PROPER SUBSET___ of __B__ and write _A_ ⊂ __B__

If _A_ ⊆ _B_ and _B_ ⊆ _C_ then,  _A_ ⊆ _C_
![[Pasted image 20230823191203.png | 270]]
For Example:
![[Pasted image 20230823191308.png | 350]]
> [!NOTE]
> The ___EMPTY SET___ is a subset of every set.

For if __B__ is any set, then _⊘_ ⊆ __B__, since each element of _⊘_ (of which there are none) is also an element of __B__
Let __A__ be a set. Since _⊘_ has no elements, all the elements in _⊘_ must also be in __A__.
Therefore, _⊘_ ⊆ __A__.


# Union and Intersection
The ___union___ and __intersection__ are two ways of combining the elements in two sets into a new set.

## Union
The union of two sets is that set having as elements the objects that are elements of at least one of the two given sets, and possibly both. We use the symbol ___U___ to denote union.

The union of two sets ___A___ and __B__ is the set containing all the elements in ___A___ as well as the elements in __B__.

$$A \cup B=\{x \mid x \in A \text { or } x \in B\}$$
![[Pasted image 20230823194037.png | 400]]

For example,
$$\{1,3,9\} \cup\{3,5,7\}=\{1,3,5,7,9\}$$
### Properties of the Union
1. _A_ U __∅__ = ___A___
2. _A_ U _A_ = ___A___
3. if _A_ ⊆ __B__, then _A_  U __B__ = __B__
	![[Pasted image 20230823200935.png | 100]]
4. _A_ U __B__ = __B__ U _A_
5. _A_ U ( ___B___ U __C__ ) = ( _A_ U ___B___) U __C__
	![[Pasted image 20230823201234.png | 350]]
## Intersection
The intersection of two sets is the collection of all elements of the two sets have in common
$$A \cap B=\{x: x \in A \text { and } x \in B\}$$
![[Pasted image 20230823194432.png | 400]]
For example,
$$\{1,3,9\} \cap\{3,5,7\}=\{3\}$$
and
$$\{1,3,9\} \cap\{a, b, c, d\}=\emptyset$$
EXAMPLE:
Let _A = {0, 1}_ and __B = {1, 2, 3}__

1. What is _A_ U __B__?           { 0, 1, 2, 3 }
2. What is _A_ ⋂ __B__?           { 1 }

Let _A = {a ∈ N | a is odd }_ and __B = {b ∈ N | b is even}__

1. What is _A_ U __B__?            N
2. What is _A_ ⋂ __B__?            ∅

### Properties of the Intersection
1. _A_ ⋂ __∅__ = ∅
2. _A_ ⋂ __A__ = A
3. if _A_ ⊆ __B__, then _A_ ∩ __B__ = A
	![[Pasted image 20230823201614.png | 200]]
4. _A_ ∩ __B__ = __B__ ∩ _A_
5. _A_ ∩ ( ___B___ ∩ __C__ ) = ( _A_ ∩ ___B___) ∩ __C__
	![[Pasted image 20230823201750.png | 450]]

## Difference
The difference of two sets _A_ and __B__, denoted by _A_ - __B__, is the set of all elements of _A_ that are not elements of __B__.
$$A-B=\{x: x \in A \text { and } x \notin B\}$$

For example,
$$\{1,3,9\}-\{3,5,7\}=\{1,9\}$$


---
Certain properties of the set operations follow easily from their definitions.
For example, if _A_, _B_ and _C_ are sets, the following laws hold.
![[Pasted image 20230823202701.png | 550]]
![[Pasted image 20230823205840.png | 600]]
![[Pasted image 20230823205857.png | 500]]

---
### Disjoint
Two sets are _disjoint_ if they have no element in common, that is, if their intersection is empty.
It is possible to form intersections and unions of more than two sets.

If ___S___ is any collection of sets, we write __U s__ for the set whose elements are the elements of all the sets in ___S___.
For example,
	if _S = { {a, b}, {b, c}, {c, d} }_ then __U s = { a, b, c, d }___ ; and _S = {{n} : n ∈ N}_, that is, the collection of all the singleton sets with natural numbers as elements, then __U s = N__.
	In general,
	$$\bigcup S=\{x:x\in P{\mathrm{~for~some~set~}}P\in S\}. $$
	Similarly,
	$$\bigcap S=\{x:x\in P$ for each set $P\in S\}$$
### Power set
The collection of all subsets of a set _A_ is itself a set, called the ___power set___ of _A_ 
and denoted: 
$$2^{A} $$
For example, the subsets of _{ c, d }_ are __{ c, d}__ itself, the singletons _{ c }_ and __{ d }__ and the empty set _∅_, so
$$2^{\{c,d\}}=\{\{c,d\},\{c\},\{d\},\emptyset\}.$$

### Partition
A _partition_ of a nonempty set _A_ is a subset __II__ of 2^{A} such that _∅_ is not an element of __II__ and such that each element of _A_ is one and only one set in __II__.
That is, __II__ is a ___partition___ of _A_ if __II__ is a set of subsets of _A_ such that
	( 1 ) each element of __II__ is _nonempty_;
	( 2 ) distinct members of __II__ are _disjoint_;
	( 3 ) ___U II = A___
For example, _{ { a,b }, { c }, { d } }_ is a partition of _{ a,b,c,d }_ _ , but __{ { b,c }, { c, d }}__ is not.
The sets of even and odd natural numbers form a partition of ___N___.

