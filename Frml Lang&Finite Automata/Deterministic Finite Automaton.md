# Deterministic finite automaton
#COMP2321
- (Finite State Machine)
- a 5-tuple $(Q, Σ, δ, q_0, F)$, where
	- $Q$ is a finite set called the states
	- $\sum$ is a finite set called the alphabet
	- $δ : Q × Σ \rightarrow Q$ is the transition function
	- $q_0 ∈ Q$ is the start state
	- $F ⊆ Q$ is the set of accepting states
## Formal Definition of Computation
We have developed an intuition of computation in the deterministic finite automaton model but we require a formal definition. This does not introduce any new concepts, instead it will formalises our intuition. Let  be a finite automaton and let  be a string where  for . The automaton  **accepts**  if a sequence of states  exists such that:
1. $r_0 = q_0$
2. $\delta (r_i, w_{i+1}) = r_{i+1} \text{ for } 0 \leq i < n$
3. $r_i \subset F$

Put simply, the first condition says that the sequence of state must start with the start state. The second condition says that the sequence of states progresses in accordance with the transition function and the third condition says that the final state is an accepting state. We say that an automaton  recognises a language  if .

If a **deterministic** automaton does not accept a given string then the machine **rejects** the string, and the string is not part of the language recognised by the automaton.

## Graphical Representation
![](Images/DFA.png)
