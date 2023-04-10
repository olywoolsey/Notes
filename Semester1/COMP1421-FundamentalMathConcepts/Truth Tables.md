#logic
## Truth assignment
- assigning each propositional variable a truth value(each row in the truth table)

## Propositional Logic Truth Tables
##### Negation: ¬
| P   | ¬P  |
| --- | --- |
| F   | T   |
| T   | F   |

##### Conjunction(And): $\bigwedge$
| p   | q   | p$\vee$q  |
| --- | --- | ---- |
| T   | T   | T    |
| T   | F   | F    |
| F   | T   | F    |
| F   | F   | F    |

##### Dis-junction(Or): $\bigvee$
| p   | q   | p$\vee$q  |
| --- | --- | ---- |
| T   | T   | T    |
| T   | F   | T    |
| F   | T   | T    |
| F   | F   | F    |

##### Implication: $\rightarrow$
- p is hypothesis
- q is conclusion
- p->q is a conditional statement
| p   | q   | p->q |
| --- | --- | ---- |
| T   | T   | T    |
| T   | F   | F    |
| F   | T   | T    |
| F   | F   | T    |
- proposition p->q is the converse of q->p
- the contra-positive of p_>q is ¬p->¬q

##### Bi-conditional: $\leftrightarrow$ 
- Also (p->q)$\wedge$(q->p)
- p if and only if q
| p   | q   | p<->q |
| --- | --- | ---- |
| T   | T   | T    |
| T   | F   | F    |
| F   | T   | F    |
| F   | F   | T    |
