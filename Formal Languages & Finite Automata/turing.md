# Turing machines

## Deterministic Turing machines

To capture the essence of a Turing machine we should consider the transition function. The transition function $\delta$ takes the form $Q \times \Gamma \rightarrow Q \times \Gamma \times \{\text{L},\text{R}\}$. That is, when a machine is in a certain state $q$ and the head is over a tape cell containing a symbol $a$, and if $\delta(q,a) = (r, b, L)$, the machine will transition to state $r$ write the symbol $b$ in the cell previously containing the symbol $a$ and then move the head left by one cell.

A **Turing machine** is a 7-tuple $(Q,\Sigma, \Gamma, \delta, q_0, q_\text{accept}, q_\text{reject})$, where
1. $Q$ is a finite set called the **states**,
2. $\Sigma$ is a finite set called the **input alphabet** not containing the **blank symbol** $\sqcup$,
3. $\Gamma$ is a finite set called the **tape alphabet**, where $\sqcup $\in \Gamma$ and $ \Sigma \subseteq \Gamma$,
4. $\delta : Q \times \Gamma \rightarrow Q \times \Gamma \times \{\text{L},\text{R}\}$ is the **transition function**, \label{def:dtmdelta}
5. $q_0 \in Q$ is the **start state**,
6. $q_\text{accept} \in Q$ is the **accept state**, and 
7. $q_\text{reject} \in Q$ is the **reject state**, where $q_\text{accept} \not=q_\text{reject}$.
   
### Computation of a Turing machine

To define the computation of a Turing machine we must first define a Turing machine configuration. As a Turing machine computes, changes occur in the current state, the current tape contents and the current head location. A setting of these three items is called a **configuration** of the Turing machine. Configurations are often represented in a specific format. For a state $q$ and two strings $u$ and $v$ over the tape alphabet $\Gamma$, we write $u\,q\,v$ for the configuration where the current state is $q$, the current tape content is $uv$ and the current head location is the first symbol of $v$. The tape will contain \sqcup in all tape cells after the end of $v$.

We say that a configuration $C_1$ **yields** a configuration $C_2$ if the Turing machine can legally go from $C_1$ to $C_2$ in one step. This is defined formally as follows. Suppose that we have $a,b, c \in \Gamma$, as well as $u, v \in \Gamma^*$ and states $q_i$ and $q_j$. In the case $ua\,q_i\, bv$ and $u\, q_j \, acv$ are two configurations we say that 
\[ua\,q_i\, bv \text{ yields } u\, q_j \, acv\]
if $\delta(q_i, b) = (q_j, c, L)$. This accounts for left moves of the tape head. For right moves we say
\[ua\,q_i\, bv \text{ yields } uac\, q_j \, v\]
if $\delta(q_i, b) = (q_j, c, R)$.

There is a special case to consider, when the head is at the leftmost position. We say $q_i \,bv$ yields $q_j \, cv$ if the transition is left moving and $c\, q_j \, v$ if the transition is right moving.

The **start configuration** of $M$ on input $w$ is the configuration $q_0 \, w$, which indicates that the machine is in the start state $q_0$ with its head at the leftmost position on the tape. In an **accepting configuration**, the state of the configuration is $q_{\text{accept}}$. In an **rejecting configuration**, the state of the configuration is $q_{\text{reject}}$. Accept configurations and reject configurations are **halting configurations** and yield no further computations. A Turing machine $M$ accepts a string $w$ if a sequence of configurations $C_1, \ldots C_k$ exists,where

1. $C_1$ is the start configuration of $M$ on input $w$,
2. each $C_i$ yields $C_{i+1}$, and 
3. $C_k$ is an accepting configuration.

## Non-deterministic Turing machines

A non-deterministic Turing machine is defined in a similar manner to all non-deterministic automata we have encountered so far. During the processing on the input a non-deterministic Turing machine may branch, each branch following one possible state from the set defined by the transition function. {prf:ref}`ndtm` is the formal definition of a non-deterministic Turing machine. Take note to identify and understand the differences between the definition of the transition functions in {prf:ref}`ndtm` and {prf:ref}`dtm`.


A **non-deterministic Turing machine** is a 7-tuple $(Q,\Sigma, \Gamma, \delta, q_0, q_\text{accept}, q_\text{reject})$, where

1. $Q$ is a finite set called the **states**,
2. $\Sigma$ is a finite set called the **input alphabet** not containing the \textbf{blank symbol} \sqcup,

3. $\Gamma$ is a finite set called the **tape alphabet**, where \sqcup $\in \Gamma$ and $ \Sigma \subseteq \Gamma$,

4. $\delta : Q \times \Gamma \rightarrow \mathcal{P}({Q \times \Gamma \times \{\text{L},\text{R}\}})$ is the **transition function**, 
5. $q_0 \in Q$ is the **start state**,
6. $q_\text{accept} \in Q$ is the **accept state**, and 
7. $q_\text{reject} \in Q$ is the **reject state**, where $q_\text{accept} \not=q_\text{reject}$.

Every non-deterministic Turing machine has an equivalent deterministic Turing machine.