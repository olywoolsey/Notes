# Propositional Logic
#logic #COMP1421 
## Proposition
- declarative statement (true XOR false)
	- Convention uses p, q, r, s, p<sub>1</sub>...
	- Natural numbers start from 0 (unless denoted N<sub>>0</sub>)
	- truth denoted as T or 1
	- false denoted as F or 0 or⊥
	- All propositional logic can be displayed in [[Truth Tables]] and visa versa
	- [[../Logic/Logic Laws]]
---
## Symbols
- Logically equal:     $\equiv$
- [[../Logic/Logically implies]]:   |=
- Negation: ¬
- Conjunction: $\wedge$
- Disjunction: $\vee$
- [[Truth Tables#Implication $ rightarrow$|Implication]]: $\rightarrow$
- [[Truth Tables#Bi-conditional $ leftrightarrow$|Biconditional]]: $\leftrightarrow$
---
## Tautology
- True under every truth assignment(every row in the truth table is true)
- **Logical Equivalence**
	- $p \equiv q$ if $p \leftrightarrow q$ is a tautology
## Contradiction
- False under every truth assignment(every row in the truth table is false)
## Contingency
- is neither a tautology or a contradiction

---
## Logical Bidmas
| operator | Precedence |
| -------- | ---------- |
| ¬        | 1          |
| $\wedge$        | 2          |
| $\vee$        | 2          |
| ->       | 3          |
| <->      | 3          |
- Brackets should be used when there's operators with the same precedence
	eg; $p \rightarrow q \leftrightarrow r$

## Syntax tree
-
		/\
	   /  \
  $\vee$           ->
/     \        /   \
p     q    ¬      r
             |
             p
---

### Literal
- is either a variable, or negation of the variable
- p is the positive literal
- ¬p is the negative literal 
### Disjunctive Normal Form (DNF)
- Disjunctive means 'or' - V
- a dis-junction of conjunctions of literals (no T or F)
- a bunch of 'and' clauses all 'or'ed together
### Conjunctive Normal Form (CNF)
- Conjunctive means 'and' - $\wedge$
- a conjunction of dis-junctions of literals (no T or F)
- a bunch of 'or' clauses all 'and'ed together
---

### T or F
- as T or F can't appear in CNF or DNF you need to replace them
- T would equal p $\vee$ ¬p
- F would equal p $\wedge$ ¬p 
### Theorem
For every propositional formula p there is a formula p\d and p\c in DNF and CNF respectively
- this is true as for every propositional formula you can write a truth table then follow instructions at start of notes to create a formula in DNF to create an equivalent formula
### Finding logic from a truth table:
#### DNF
1. find a formula for every row that satisfies the assignment(is true) that satisfies only that row
2. or all the formulas together
#### CNF
1. replace each occurence of T and F with their logical equivelnces
2. replace each p <-> q with q -> q /\ q-> p
3. replace each q -> p by ¬q V p
4. apply DeMorgans and double negation till all in literals
5. apply distributive law
	**or**
1. find a formula for every row that dissatisfies the assignment(is false), that satisfies only that row
2. add all the formulas together