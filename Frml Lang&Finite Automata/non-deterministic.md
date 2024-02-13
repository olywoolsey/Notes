# Non-deterministic Finite State Automata (NFA)

The concept of non-determinism is a concept that appears throughout the topic of complexity and theory of computation. In the automata we have considered up to now the action of the automaton is known, given the current state and an input symbol the next state is determined by the transition function-- this is called determinism. In a non-deterministic automaton the next state is not determined by the current state and input symbol alone, there may be many choices for the next state.

In a [finite state automaton (FSA)](Deterministic%20Finite%20Automaton), non-determinism refers to the presence of multiple transitions out of a state that are labelled with the same symbol. This means that, given a certain input symbol and current state, there is more than one possible next state that the FSA could transition to.

Non-determinism can be useful in some cases because it allows the FSA to recognize multiple strings or patterns simultaneously. However, it can also make the FSA more difficult to design and understand, because there may be multiple possible paths through the FSA for a given input string.

Non-determinism can be contrasted with determinism, which refers to the case where there is only one possible transition out of each state for each input symbol. Determinism is often easier to work with.

From this idea it is clear to see a trivial transformation between a deterministic finite automaton and a non-deterministic finite automaton. {prf:ref}`nfa` formalises non-deterministic finite automaton.


````{prf:definition} Non-deterministic Finite State Automata
:label: nfa

A **non-deterministic finite automaton** is a 5-tuple $(Q,\Sigma,\delta, q_0, F)$, where

1. $Q$ is a finite set called the *states*,
2. $\Sigma$ is a finite set called the *alphabet*,
3. $\delta : Q \times \Sigma_\epsilon  \rightarrow \mathcal{P}(Q)$ is the *transition function*,
4. $q_0 \in Q$ is the *start state*, and
5. $F \subseteq Q$ is the set of *accepting states*.

 Where $\Sigma_\epsilon = \Sigma \cup \{\epsilon\}$.

````

From {prf:ref}`nfa` we can see that there are a number of differences between deterministic finite automaton and non-deterministic finite automaton. Firstly, every state in a deterministic finite automaton has exactly one exiting transition for each symbol in the alphabet. Whereas in non-deterministic finite automaton every state may have zero, one, or many exiting transitions for each symbol in the alphabet. Secondly, in a deterministic finite automaton each transition is associated with an element of the alphabet. In non-deterministic finite automaton transitions may be associated with an **empty transition** denoted by the $\epsilon$ symbol.

A non-deterministic finite automaton computes in a similar manner to deterministic finite automaton, however the transition function no longer provides a deterministic path of computation. One way of considering the computation of a non-deterministic finite automaton is to consider a branching finite automaton. At each symbol of the input, the automaton branches into multiple copies of the same automaton, one for each element of the elements in the set indicated by the transition function, each automaton proceeding in parallel. Each copy of the automaton takes one of the states from the set indicated by the transition function. Each of the automata will independently continue to branch as the automaton computes. The non-deterministic finite automaton accepts the string if any one of the copies of the automaton finishes reading in the input in an accepting state.

The $\epsilon$ symbol is a special symbol which indicates an empty transition. The automaton branches into multiple copies of the same automaton without consuming an element of the input.

## A formal description of computation

 Let $N = (Q, \Sigma, \delta, q_0, F)$ be a non-deterministic finite automaton and $w$ be a string over the alphabet $\Sigma$. We say that $N$ accepts $w$
if we can write $w=y_1,\ldots, y_n$ where $y_i \in \Sigma_\epsilon$ for $1 \leq i \leq n$ and there exists a sequence of states $r_0, \ldots, r_n$ where $r_i \in Q$ where $0 \leq i \leq n$, such that;


1. $r_0 = q_0$,
2. $r_{i+1} \in \delta(r_i, w_{i+1})$, for $0\leq i \leq n-1$, and
3. $r_n \in F$. 

This definition is similar to the definition of computation in deterministic finite state automata. The only minor differences are in criteria 2 to address the different in the definition of the transition function. The difference is that the '$=$' has been replaced by the '$\in$' symbol.

If a **non-deterministic** automaton does not accept a given string then the machine **rejects** the string, and the string is not part of the language recognised by the automaton.

## Pictoral representations of non-deterministic finite state automata

In a similar way as for deterministic finite state automata, non-deterministic finite state automata can be represented in a pictoral/diagrammatic fashion.

Let $M = (Q,\Sigma,\delta, q_0, F)$ where,
1. $Q = \{q_0, q_1, q_2, q_3, q_4\}$
2. $\Sigma = \{\texttt{0}, \texttt{1}\}$
3. $q_0$ is the start state
5. $F = \{q_4\}$, and
6. $\delta = \{((q_0, \epsilon),q_1),((q_0,\epsilon),q_2),((q_1, 1),q_4),((q_1, 1),q_1),((q_2,0),q_3),((q_2, 1), q_2),((q_3,0),q_2),((q_3,1), q_3),((q_3, 1), q_4)\}$
![](NFA.png)
The non-deterministic finite state automaton $M$ accepts strings if the string only contains the symbol $1$ and ends in a $1$, or if the string contains an odd number of $0$'s and ends in a $1$. The machine is non-deterministic for a number of reasons,

1. The state $q_0$ does not define a transition for the alphabet symbols $0$, and $1$. Also, the state has two distinct transitions for the empty string.
3. The state $q_1$ contains two distinct transitions for the symbol $1$. Also, the state does not define a transition for the symbol $0$.
4. The state $q_4$ does not define a transition for the symbols $0$ or $1$.

````{exercise}
:label: simple_nfa
Which of the following strings are accepted by the machine $M$? What is the computation of the machine on each string?

1. $\epsilon$
2. $10$
3. $0001$
````

````{solution} simple_nfa

1. The string $\epsilon$ is **rejected** by $M$. The computation is $q_0$.
2. The string $10$ is **rejected** by $M$. No computation terminates with the machine in $q_4$.
3. The string $01$ is **accepted** by $M$.  An accepting computation is $q_0, q_2,q_3,q_2,q_3, q_4$.
````