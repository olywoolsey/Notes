#logic #COMP1421 
## Cantor's definition
A set is a gathering together into a whole of definite, distinct objects of our perception or of our thought – which are called elements of the set.’
- not the most formal statement, bit naive
## Notation
- x $\in$ A denotes that x is an element of the set A
- x $\notin$ A denotes that x is not an element of the set A
- use Braces around the set {..}
- use := not =
- commas can be used instead of "and"
- cardinality: the number of elements in a given mathematical set
- for n ∈ N, we let $A^n$ := A × ... × A, where this is product consists of n factors
- {x ∈ A | x has property (properties) P}

### Roster method (extensional set notation)
- list all the values
- split with commas
- In a very large set can use a ... notation
- A := {0,1,2,3,4,5}   or   A :={0,1,...,5}

### Set Builder notation (intentional set notation)
- can also define a set by using characteristics
- if can't think of a way to express in maths then using natural language 
- B := {x | x ∈ A  and x is even} // {x ∈ A | x is even } // {x | x is a natural number and x is even and 0 ≤ x ≤ 5}.
- | is read 'such that' or 'with the property that'    ( can use : )

## Important functions of a set
- elements can't occur multiple times     {1,2,3,4} = {1,2,2,3,4,4}
- don't come with a fixed ordering          {1,2,3,4} = {4,2,1,3}
- can built from "atomic" or "composed" elements. Sets can be arbitrarily complex

## Notation for Standard sets of numbers
$\mathbb{N}$   := {0, 1, 2, 3, · · · } set of natural numbers
$\mathbb{Z}$   := {0, 1, −1, 2, −2, 3, −3, · · · } set of integers
$\mathbb{Z}^+$ := {1, 2, 3, · · · } set of positive natural numbers
$\mathbb{Q}$   := { ab | a, b ∈ Z, b 6 = 0} set of rational numbers
$\mathbb{R}$   := the set of real numbers
$\mathbb{R}^+$ := the set of positive real numbers

## Empty Set
- set that contains no elements
- We denote it by $\emptyset$, or by {}
- A set with exactly one element is also called a singleton set.
- A common error is to confuse $\emptyset$ with {$\emptyset$}
	- an empty set is not equiv to a set that contains an empty set

## Venn Diagrams
- graphic representation of sets
- In Venn diagrams the universal set U, which contains all the objects under consideration, is represented by a rectangle
- Inside the rectangle are circles that represent sets

## Comparing Sets
- when manipulating sets they also follow some of the [[Logic Laws]]
- intersection: A $\cap$ B := {x: x $\in$ A and x $\in$ B}
- union: A $\cup$ B := {x: x $\in$ A or x $\in$ B}
- difference: A - B := {x $\in$ A : x $\notin$ B}
- symmetric difference: A $\oplus$ B := (A - B) $\cup$ (B - A)
	Note that A − B is sometimes denoted by A \\ B, and A ⊕ B by A $\triangle$ B
### Subsets and supersets
A & B are sets
- A is a subset of B (short: A ⊆ B), if every element of A is also an element of B
- A is a proper subset of B (short: A $\subset$ B), if A ⊆ B and A != B
- A is a superset of B (short: A ⊇ B), if B ⊆ A
- A is a proper superset of B (short: A $\supset$ B), if A ⊇ B and A != B

## Power Set
- the power set of a set is the the set that contains all subsets
- $\mathcal{P}$(S) := {X | X ⊆ S}
- e.g. $S:={a, 3}$ $\rightarrow$ $\mathcal{P}(S) := \{\emptyset , \{a\}, \{3\}, \{a,3\}\}$

## Tuple
- Denoted with ( )
- Order Matters  (1 , 2) $\neq$ (2 , 1) 
- The Cartesian product of two sets A, B, denoted by A × B, is the set of ordered pairs (a, b), where a belongs to A and b belongs to B.

## The Compliment
- We would like the complement of a set A, short $\bar{A}$ , to be the set of all elements, that do not belong to A.
- $\bar{A}$ := {x: x $\notin$ A}
- the compliment of the empty set would contain everything and cause Russel's Paradox
- this is why a sets are considered in a fixed universe: U (which is its own set)

## Russel's Paradox
