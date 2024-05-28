# Languages

- A language is a set of strings of symbols over an alphabet. 
- For example, the set of all strings over the alphabet $\{\texttt{a}, \texttt{b}, \texttt{c}, \ldots, \texttt{z}\}$ that contain an even number of a's and an odd number of b's is a language.

Languages can be classified based on the kinds of patterns that they contain. Some common types of languages include regular languages, context-free languages, and context-sensitive languages. Each of these types of languages can be recognised by a different type of machine, such as a finite state automaton, a pushdown automaton, or a linear-bounded automaton.
## Regular Languages

>[!info] Definition (Regular Language)
> A language is called a **regular language** if some deterministic finite automaton recognises it.

If there does not exists a finite automaton that recognises a given language $L$, then $L$ is said to be **non-regular**. 

The language of a machine $M$ will be denoted as $L(M)$. We say that a machine $M$ recognises a language $L$ if $L(M)=L$.
## Context Free Language

> [!Info] Definition
> A language is called a **context-free language** (CFL) if some context-free grammar generates it.

If there does not exists a context-free grammar that generates a given language $L$, then $L$ is said to be **non-context-free**. 

The **language of a grammar**, denoted $L(G)$ (a slight corruption of notation), is $\{w \in \Sigma^* \mid S \stackrel{\ast}{\Rightarrow} w\}$.

# Language relating to Turing machines

## Recursively enumerable languages 

The collection of strings a machine $M$ accepts is the language of $M$, denoted $L(M)$. The language $L(M)$ is the language recognised by $M$.

> [!quote] Turing-recognisable (recursively enumerable language)
> A language is called **Turing-recognisable**, or simply **recognisable**, if there exists some Turing machine that recognises it.
### Enumerators

An **enumerator** is a special type of Turing machine that instead of accepting or rejecting the machine outputs a set of strings which it accepts. We can think of the Turing machine as having some printing device attached to it, each time the machine decides that a string is accepted the string is printed by the printer. There is a connection between enumerators and the languages that can be recognised by a Turing machine.

> [!Theorm]
> A language is Turing-recognisable if and only if some enumerator enumerates it.

### Proof
We must prove two directions. Firstly, if some enumerator $E$ enumerates a language $A$ then there is a Turing machine $M$ that recognises $A$. We prove this by describing a Turing machine $M$ given an enumerator. The Turing machine $M$ behaves in the following way on input $w$:

1. Run $E$. For every string $x$ outputted by $E$ compared it with $w$.
2. If $w = x$ then $M$ will output _accept_.

Clearly the machine $M$ accepts $w$ if $w$ is in the list of enumerated strings.


Secondly, if some Turing machine $M$ recognises a language $A$ then there exists an enumerator $E$ that enumerates $A$. We prove this by constructing an enumerator $E$ given a Turing machine $M$ that recognises $A$. Let $s_1, s_2, \ldots$ be the strings over the alphabet of $M$. The enumerator behaves in the following way: 

1. For $i = 1, 2, \ldots$
2. Run machine $M$ for $i$ steps on each of the input $s_1, \ldots, s_i$.
3. If any computation accepts then output the corresponding $s_j$.

The machine $E$ emulates the parallel execution of $M$ on all strings over the alphabet of $M$. If a string is accepted by $M$ it will be output by $E$. Note that $E$ will output each accepted string an infinite number of times.

> [!Recursively enumerable]
A language is **recursively enumerable** if there exists an enumerator that enumerates it.

## Recursive languages

When a Turing machine processes an input there are three possible outcomes. The machine can either terminate in an accepting state, terminate in a rejecting state or loop forever. It is difficult to distinguish a Turing machine that is looping from a machine that is simply taking a long time to compute. It is preferable for a machine to either terminate in an accepting state or terminate in a rejecting state, excluding the possibility of looping forever. Such a Turing machine is called a **decider**. A decider that recognises some language $L$ is said to decide $L$.

>[!definition] Turing decidable (recursive language)
A language is called **Turing-decidable**, or simply **decidable**, if there exists some Turing machine that decides it.