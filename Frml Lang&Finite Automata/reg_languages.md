# Regular Languages

In the context of formal languages, a language is a set of strings of symbols over an alphabet. For example, the set of all strings over the alphabet $\{\texttt{a}, \texttt{b}, \texttt{c}, \ldots, \texttt{z}\}$ that contain an even number of a's and an odd number of b's is a language.

Languages can be classified based on the kinds of patterns that they contain. Some common types of languages include regular languages, context-free languages, and context-sensitive languages. Each of these types of languages can be recognised by a different type of machine, such as a finite state automaton, a pushdown automaton, or a linear-bounded automaton. We will study some of these languages later in this module.

````{prf:definition} Regular Language
:label: reg_lang

A language is called a **regular language** if some deterministic finite automaton recognises it.

````

If there does not exists a finite automaton that recognises a given language $L$, then $L$ is said to be **non-regular**. 

The language of a machine $M$ will be denoted as $L(M)$. We say that a machine $M$ recognises a language $L$ if $L(M)=L$.
