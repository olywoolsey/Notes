# Closure properties of regular languages

The concept of closure is a concept that appears across mathematics and computer science. A set $A$ is **closed** with respect to some operation if when the operation is applied to one or more element of $A$ the result is also an element of $A$. This should not be unfamiliar from arithmetics, the integers $\mathbb{Z}$ are closed with respect to addition ($+$).

We will show that the set of Regular languages are closed a number of operations. These operations are chosen because we will use them later in the modules.

## Complement

> [! info] Definition
> Let $A$ be languages over some finite alphabet $\Sigma$.
> 
> *Complement*: $\overline{A} = \{x \in \Sigma^* \mid x \not\in A\}$ 

> [! info]
> Regular languages are closed with respect to complement

To prove that Regular languages are closed with respect to the complement operation, we must prove that for an arbitrary regular language there exists a deterministic finite state automaton that recognises the complement.
### Proof
````{prf:proof}
Let $A$ be a regular language and let $M=(Q, \Sigma, \delta, q, F)$ recognise $A$. We construct an automaton $M'=(Q', \Sigma', \delta', q', F')$ that recognises $\overline{A}$.

- $Q'=Q$
The set of states is the same as the automaton $M$.
- $\Sigma'=\Sigma$
The alphabet is the same as the automaton $M$.
- $\delta'=\delta$
The transition function is the same as the automaton $M$.
- $q'=q$
The start state is the same as the automaton $M$.
- $F' = Q \setminus F$
The set of final states is all states in $M$ that are not final states.

The automaton $M'$ recognises $\overline{A}$ as any computation of $M$ that ends in a none final state, and therefore is rejected, will end in a final state in $M'$ and will be accepted.

The automaton $M'$ is a finite state automaton and therefore by {prf:ref}`reg_lang` $\overline{A}$ is a regular language.
````

````{prf:example}
Consider the following deterministic finite automata.

```{figure} ../../../images/complement_example.png

$M_1$
```

The automata $M_1$ recognises the unary language (a language over an alphabet with a single symbol) which contains strings who length is an integer multiple of 3, i.e., the following strings are in $L(M_1)$; $\epsilon$, $111$, $111111$. The language is regular as there exists a deterministic finite state automata that recognises it. The complement of $L(M_1)$ is the language which contains the strings who length is $1 \mod 3$ or $2 \mod 3$. Following the construction from the proof of {prf:ref}`regclosecomplement` we obtain the following automaton.

```{figure} ../../../images/complement_complement_example.png

A deterministic finite state automata that recognised $\overline{L(M_1)}$.
```
````

## Union

> [! info] Definition: Union
> Let $A$ and $B$ be languages over some finite alphabets $\Sigma_{A}$ and $\Sigma_{B}$ respectively.
> 
> *Union*: $A \cup B = \{x \in (\Sigma_{A} \cup \Sigma_{B})^* \mid x \in A \text{ or } x \in B\}$

> [! info] Theorm: 
Regular languages are closed with respect to finite union.
````

To prove that Regular languages are closed with respect to the finite union operation, we must prove that for any arbitrary pair of regular languages there exists a deterministic finite state automaton that recognises their union.

````{prf:proof}
Let $A$ and $B$ be regular languages and let $M_1 = (Q_1, \Sigma_1, \delta_1, q_1, F_1)$ recognise $A$ and let $M_2 = (Q_2, \Sigma_2, \delta_2, q_2, F_2)$ recognise $B$. We construct a deterministic finite state automaton $M = (Q, \Sigma, \delta, q, F)$ that recognises $A \cup B$, assuming $\Sigma_1 = \Sigma_2$. The construction can be generalised for when $\Sigma_1 \not = \Sigma_2$.


- $Q = \{(r_1, r_2) \mid r_1 \in Q_1, r_2 \in Q_2\}$.
The set of states of $M$ is the **Cartesian product** of the sets $Q_1$ and $Q_2$.
- $\Sigma = \Sigma_1 \cup \Sigma_2$
The alphabet is the union of the alphabets from $M_1$ and $M_2$.
- $\delta$ is defined as follows; for each $(r_1, r_2) \in Q$ and for each $a \in \Sigma$. The transition function keeps track of which states $M_1$ and $M_2$ would be in if they had processed the same portion of the input string as $M$.
```{math}
\delta((r_1,r_2), a) = (\delta_1(r_1,a), \delta_2(r_2, a))
```

- $q$ is the pair $(q_1, q_2)$
The initial state is the pair that contains the initial state of $M_1$ and the initial state of $M_2$.
- $F$ is defined as follows. The automaton $M$ should accept the string if the final state is a pair that contains either a final state from $M_1$ or a final state from $M_2$.
```{math}
F = \{(r_1, r_2) \mid r_1 \in F_1 \text{ or } r_2 \in F_2\}.
```

The automaton $M$ by construction accepts exactly $A \cup B$. By {prf:ref}`reg_lang` $A \cup B$ is a regular language.
````
An alternative proof of {prf:ref}`regcloseunion` that uses non-determinism can be found in {cite}`sipser` [Theorem 1.45]. The proof above can be modified easily to relax the condition that $\Sigma_1 = \Sigma_2$.

````{prf:example}
Consider the Languages, over the alphabet $\{0,1\}$, $L_1 = \{x \mid x \text{ starts with } 1 \text{ and } |x| = 0 \mod 2 \}$ and $L_2 = \{x | x \text{ starts with } 0 \text{ and } |x| = 1 \mod 2\}$. Observe that $L_1$ and $L_2$ are regular languages.

Consider the following deterministic finite automata.

```{figure} ../../../images/union_l1.png

$M_1$ recognises $L_1$.
```

```{figure} ../../../images/union_l2.png

$M_2$ recognises $L_2$.
```

The langauges $L_1$ and $L_2$ are regular langauges as there exists a deterministic finite automata that recognise them. The language $L_1 \cup L_2$ is also regular. Following the construction from the proof for {prf:ref}`regcloseunion` we can construct the following deterministic finite automaton that recognises $L_1 \cup L_2$.

- $Q = \{(a,b) \mid a \in \{q_0, q_1, q_2, q_3\}, b \in \{q_0, q_1, q_2, q_3\}\}$
- $\Sigma = \{0,1\}$
- The initial state is $(q_0, q_0)$
- $\delta = \{(((q_0,q_0),0),(q_3,q_1)),(((q_0,q_0),1),(q_1,q_3)),(((q_0,q_1),0), (q_1,q_3)),(((q_0,q_1),1),(q_1,q_2)),$
$(((q_0,q_2),0),(q_3,q_1)),(((q_0,q_2),1), (q_1,q_1)),(((q_0,q_3),0), (q_3,q_3)),(((q_0,q_3),1),(q_1,q_3)),$
$(((q_1,q_0),0), (q_2,q_1)),(((q_1,q_0),1), (q_2,q_3)),(((q_1,q_1),0), (q_2,q_2)),(((q_1,q_1),1),(q_2,q_2)),$
$(((q_1,q_2),0),(q_2,q_1)),(((q_1,q_2),1), (q_2,q_1)),(((q_1,q_3),0), (q_2,q_3)),(((q_1,q_3),1),(q_2,q_3)),$
$(((q_2,q_0),0), (q_1,q_1)),(((q_2,q_0),1),(q_1,q_3)),(((q_2,q_1),0),(q_1,q_2)),(((q_2,q_1),1),(q_1,q_2)),$
$(((q_2,q_2),0), (q_1,q_1)),(((q_2,q_2),1),(q_1,q_1)),(((q_2,q_3),0), (q_1,q_3)),(((q_2,q_3),1),(q_1,q_3)),$
$(((q_3,q_0),0),(q_3,q_1)),(((q_3,q_0),1),(q_3,q_3)),(((q_3,q_1),0),(q_3,q_2)),(((q_3,q_1),1),(q_3,q_2)),$
$(((q_3,q_2),0),(q_3,q_1)),(((q_3,q_2),1),(q_3,q_1)),(((q_3,q_3),0),(q_3,q_3)) ,(((q_3,q_3),1),(q_3,q_3))\}$

- $F = \{(a, b) \mid a \in \{q_3\} \text{ or } b \in \{q_3\}\}$.
````

## Intersection

````{prf:definition} Intersection
:label: intersection

Let $A$ and $B$ be languages over some finite alphabets $\Sigma_{A}$ and $\Sigma_{B}$ respectively.

*Intersection*: $A \cap B = \{x \in (\Sigma_A \cup \Sigma_B)^* \mid x \in A \text{ and } x \in B\}$

````

````{prf:theorem}
:label: regcloseintersection
Regular languages are closed with respect to finite intersection.

````

To prove that Regular languages are closed with respect to the finite intersection operation, we must prove that for any arbitrary pair of regular languages there exists a deterministic finite state automaton that recognises their intersection.

````{prf:proof}
Let $A$ and $B$ be regular languages and let $M_1 = (Q_1, \Sigma_1, \delta_1, q_1, F_1)$ recognise $A$ and let $M_2 = (Q_2, \Sigma_2, \delta_2, q_2, F_2)$ recognise $B$. We construct a deterministic finite state automaton $M = (Q, \Sigma, \delta, q, F)$ that recognises $A \cap B$, assuming $\Sigma_1 = \Sigma_2$.

- $Q = \{(r_1, r_2) \mid r_1 \in Q_1, r_2 \in Q_2\}$.
The set of states of $M$ is the **Cartesian product** of the sets $Q_1$ and $Q_2$.
- $\Sigma = \Sigma_1 \cup \Sigma_2$
The alphabet is the union of the alphabets from $M_1$ and $M_2$.
- $\delta$ is defined as follows; for each $(r_1, r_2) \in Q$ and for each $a \in \Sigma$. The transition function keeps track of which states $M_1$ and $M_2$ would be in if they had processed the same portion of the input string as $M$.
```{math}
\delta((r_1,r_2), a) = (\delta_1(r_1,a), \delta_2(r_2, a)).
```

- $q$ is the pair $(q_1, q_2)$
The initial state is the pair that contains the initial state of $M_1$ and the initial state of $M_2$.
- $F$ is defined as follows
```{math}
F = F_1 \times F_2.
```
The automaton $M$ should accept the string if the final state is a pair that contains a final state from $M_1$ and a final state from $M_2$. The automaton $M$ by construction accepts exactly $A \cap B$.

By {prf:ref}`reg_lang` $A \cap B$ is a regular language.

````
The proof above can be modified easily to relax the condition that $\Sigma_1 = \Sigma_2$.


````{prf:example}
Consider the Languages, over the alphabet $\{0,1\}$, $L_1 = \{x \mid x \text{ starts with } 1 \text{ and } |x| = 0 \mod 2 \}$ and $L_2 = \{x | x \text{ starts with } 0 \text{ and } |x| = 1 \mod 2\}$. Observe that $L_1$ and $L_2$ are regular languages.

Consider the following deterministic finite automata.

```{figure} ../../../images/union_l1.png

$M_1$ recognises $L_1$.
```

```{figure} ../../../images/union_l2.png

$M_2$ recognises $L_2$.
```

The langauges $L_1$ and $L_2$ are regular langauges as there exists a deterministic finite automata that recognise them. The language $L_1 \cap L_2$ is also regular. Following the construction from the proof for {prf:ref}`regcloseintersection` we can construct the following deterministic finite automaton that recognises $L_1 \cap L_2$.

- $Q = \{(a,b) \mid a \in \{q_0, q_1, q_2, q_3\}, b \in \{q_0, q_1, q_2, q_3\}\}$
- $\Sigma = \{0,1\}$
- The initial state is $(q_0, q_0)$
- $\delta = \{(((q_0,q_0),0),(q_3,q_1)),(((q_0,q_0),1),(q_1,q_3)),(((q_0,q_1),0), (q_1,q_3)),(((q_0,q_1),1),(q_1,q_2)),$
$(((q_0,q_2),0),(q_3,q_1)),(((q_0,q_2),1), (q_1,q_1)),(((q_0,q_3),0), (q_3,q_3)),(((q_0,q_3),1),(q_1,q_3)),$
$(((q_1,q_0),0), (q_2,q_1)),(((q_1,q_0),1), (q_2,q_3)),(((q_1,q_1),0), (q_2,q_2)),(((q_1,q_1),1),(q_2,q_2)),$
$(((q_1,q_2),0),(q_2,q_1)),(((q_1,q_2),1), (q_2,q_1)),(((q_1,q_3),0), (q_2,q_3)),(((q_1,q_3),1),(q_2,q_3)),$
$(((q_2,q_0),0), (q_1,q_1)),(((q_2,q_0),1),(q_1,q_3)),(((q_2,q_1),0),(q_1,q_2)),(((q_2,q_1),1),(q_1,q_2)),$
$(((q_2,q_2),0), (q_1,q_1)),(((q_2,q_2),1),(q_1,q_1)),(((q_2,q_3),0), (q_1,q_3)),(((q_2,q_3),1),(q_1,q_3)),$
$(((q_3,q_0),0),(q_3,q_1)),(((q_3,q_0),1),(q_3,q_3)),(((q_3,q_1),0),(q_3,q_2)),(((q_3,q_1),1),(q_3,q_2)),$
$(((q_3,q_2),0),(q_3,q_1)),(((q_3,q_2),1),(q_3,q_1)),(((q_3,q_3),0),(q_3,q_3)) ,(((q_3,q_3),1),(q_3,q_3))\}$
- $F = \{(q_3,q_3)\}$.
````


## Concatenation

> [! info] Definition: Concatination
> Let $A$ and $B$ be languages over some finite alphabets $\Sigma_{A}$ and $\Sigma_{B}$ respectively.
> *Concatenation*: $A \circ B = \{xy \in (\Sigma_A \cup \Sigma_B)^* \mid x \in A \text{ and } y \in B\}$

> [! info] Theorm
> Regular languages are closed with respect to concetenation.

To prove that Regular languages are closed with respect to the concatenation operation, we must prove that for any arbitrary pair of regular languages there exists a deterministic finite state automaton that recognises their concatenation, or there exists a non-deterministic finite state automaton that recognises their concetenation (Why? see {prf:ref}`reg_lang_ndfsm`). 
## Kleene star
> [! info] Definition: Star
Let $A$ be a language over some finite alphabet $\Sigma$.
> 
> *Star*: $A^* = \{x_1x_2\ldots x_k \in \Sigma^* \mid k \geq 0 \text{ and } x_i \in A \text{ for each } 1\leq i \leq k \}$

> [! info] Theorm
> Regular languages are closed with respect to Kleene star.

To prove that Regular languages are closed with respect to the Kleene star operation, we must prove that for an arbitrary regular languages there exists a deterministic finite state automaton that recognises the Kleene star of the language, or there exists a non-deterministic finite state automaton that recognises the Kleene start of the language (Why? see {prf:ref}`reg_lang_ndfsm`).