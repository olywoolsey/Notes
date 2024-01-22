#logic #COMP1421 
- [[Propositional logic]] isn't always suitable ie, it doesn't work with variables
- Predicate logic includes variables
## One variable statement
- for the statement x > 3
1. subject: the variable x
2. the predicate: is greater than 3
	can also be written as P(x) where p denotes the predicate
	- The statement P(x) is also said to be the value of the propositional function P at x
	- Once a value has been assigned to the variable x, the statement P(x)becomes a proposition and has a truth value
	P(4) is True and P(2) would be false
- Have to specify the Domain (use [[Set Theory]] to do this)

## More than one variable
- denoted as P(x<sub>1</sub>,x<sub>2</sub>,x<sub>3</sub>,.......,x<sub>n</sub>):
- 0 variable predicates are propositional statements
- can then substitute all the values into the statement to get a true or false

## Quantification
### Universal
The universal quantification of P(x) is the statement‘
	P(x) for all values of x in the domain of x.’
- The notation ∀x P(x) denotes the universal quantification of P(x)
- The symbol ∀ is called the universal quantifier.
- We read ∀x P(x) as ‘for all x P(x)’ or ‘for every x P(x)’.
The domain of x is a set. We have to specify the domain of x.An element for which P(x) is false is called a counterexample to ∀x P(x).
	eg: Let P(x) be the statement x + 1 > x
	What is the truth value of the quantification ∀x P(x), where the domain consists of all real numbers?
	Solution: Because P(x) is true for all real numbers x, the quantification∀x P(x) is true
- to find a universal quantified false you only need to find one counter example
- Note that if the domain is empty, then ∀x P(x) is true for every propositional function P(x) because there are no elements x in the domain for which P(x) is false
- When the domain is finite then ∀x P(x) can be expressed as P(x<sub>1</sub>) ∧ P(x<sub>2</sub>) ∧ . . . ∧ P(x<sub>n</sub>)
### Existential
- there exists at least one x such that P(x)
- must specify the domain
- the notation ∃x P(x) denotes the existential quantification of P(x)
- The symbol ∃ is called the existential quantifier
- We read ∃x P(x) as ‘there exists an x P(x)’ or ‘there is an x P(x)

## Negating Quantified Statements
- De Morgans law for quantifiers
- Often not one way of modelling things
### Universal
- for the negation of ∀x P(x):
	- ¬∀x P(x) ≡ ∃x ¬P(x)
### Existential
- for the negation of ∃x Q(x):
	- ¬∃x Q(x) ≡ ∀x ¬Q(x)
![[../Pasted image 20221028091959.png]]

## Examples
1. **Negate "there is an honest politician"**
	- Let H(x) denote ‘x is honest’.
	- The statement ‘there is an honest politician’ is modelled by ∃x H(x),where the domain consists of all politicians.
	- The negation of this statement is ¬∃x H(x), which is equivalent to ∀x ¬H(x)
	- This negation can be expressed as ‘every politician is dishonest.’
2. ¬∀x (P(x) → Q(x)) $\equiv$ ∃x ¬(P(x) → Q(x)) $\equiv$ ∃x (P(x) ∧ ¬Q(x))
3. ∀x ∃y (x + y = 0)
	- where x is the set of all integers
	- where y is the set of all integers
	- for any number there exists at least one other number where x + y = 0
	- this is true as you can take the negative
4. ∀x ∀y ∀z ( (x + y ) + z = x + (y + z) )
	- is true
5. ∀x ∀y ((x > 0) ∧ (y < 0) → xy < 0)
	- x is an integer
	- y is an integer
	- the product of a positive number and a negative number is always negative

## The order in which different quantifiers appear matters!
- Let Q(x, y ) be the statement x + y = 0
-   ∀x ∃y Q(x, y )    and    ∃y ∀x Q(x, y ) 
	- ∀x ∃y Q(x, y ) means that for any number there exists a number which when added equals 0 therefore is true
	- ∃y ∀x Q(x, y ) means that for a specific number all numbers add to make zero which is false

## Empty Domains
- You should always define a domain for these logic statements
- If the domain is empty then:
	- $\forall x P(x)\equiv True$
	- $\exists x P(x) \equiv False$
 
## Logical Bidmas
| operator  | Precedence |
| --------- | ---------- |
| $\forall$ | 1          |
| $\exists$ | 1          |
| ¬         | 2          |
| $\wedge$  | 3          |
| $\vee$    | 3          |
| ->        | 4          |
| <->       | 4          |

## Free, Bound and Scope
- Free: Variable not in the quantifier 
- Bound: Variable is being quantified
- Scope: The part of a logical expression to which a quantifier is applied.
- Consider the formula ∃x (x + y = 1)
	The x variable is bound and the y variable is free
	The scope is $\exists x$
- An expression involving predicates and quantifiers, that does not have free variables is called a sentence of predicate logic