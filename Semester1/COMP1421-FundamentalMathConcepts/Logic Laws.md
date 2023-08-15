#logic #COMP1421 
## Idempotent Law
- p $\wedge$ p $\equiv$ p
- p V p $\equiv$ p
## Commutative Law
- p $\wedge$ q $\equiv$ q $\wedge$ p
- p V q $\equiv$ q V p
## Associative Law
- (p $\wedge$ q) $\wedge$ r $\equiv$ p $\wedge$ (q $\wedge$ r)
- (p $\vee$ q) $\vee$ r $\equiv$ p $\vee$ (q $\vee$ r)
## Absorption Law
- p $\wedge$ (p $\vee$ q) $\equiv$ p
- p $\vee$ (p $\wedge$ q) $\equiv$ p
## Distributive Law
- p $\wedge$ (q $\vee$ r) $\equiv$ (p $\wedge$ q) $\vee$ (p $\wedge$ r)
- p $\vee$ (q $\wedge$ r) $\equiv$ (p $\vee$ q) $\wedge$ (p $\vee$ r)
## Double Negation
- ¬¬p $\equiv$ p
## De Morgans Law
- ¬(p $\wedge$ q) $\equiv$ (¬p $\vee$ ¬q)
- ¬(p $\vee$ q) $\equiv$ (¬p $\wedge$ ¬q)
## Tertium non Datur
- p $\wedge$ ¬p $\equiv$ F
- p $\vee$ ¬p $\equiv$ T
## Identity Law
p $\wedge$ T $\equiv$ p
p $\vee$ F $\equiv$ p
## Domination Law
p $\vee$ T $\equiv$ T
p $\wedge$ F $\equiv$ F
## Equivalences using conditional statements
1. p → q ≡ ¬p ∨ q
2. p → q ≡ ¬q → ¬p
3. p ∨ q ≡ ¬p → q
4. p ∧ q ≡ ¬(p → ¬q)
5. ¬(p → q) ≡ p ∧ ¬q
6. (p → q) ∧ (p → r ) ≡ p → (q ∧ r )
7. (p → r ) ∧ (q → r ) ≡ (p ∨ q) → r
8. (p → q) ∨ (p → r ) ≡ p → (q ∨ r )
9. (p → r ) ∨ (q → r ) ≡ (p ∧ q) → r
## Equivalences using biconditional statements
1. p ↔ q ≡ (p → q) ∧ (q → p)
2. p ↔ q ≡ ¬p ↔ ¬q
3. p ↔ q ≡ (p ∧ q) ∨ (¬p ∧ ¬q)
4. ¬(p ↔ q) ≡ p ↔ ¬q