# Context Free Grammar
> [!Info] Definition
> A **context-free grammar** is a 4-tuple $(V,\Sigma, R, S)$, where
> 1. $V$ is a finite set called the **variables**,
> 2. $\Sigma$ is a finite set, disjoint from $V$, called the **terminals**,
> 3. $R$ is a finite set of **rules**, with each rule being a variable and a string of variables and terminals, and
> 4. $S \in V$ is the **start variable**.

## Chomsky Normal Form
> [!Info] Defintion
> Chomsky normal form
A context-free grammar is in **Chomsky normal form** if every rule is of the form
> 1.  $A \rightarrow BC,$ or
> 2. $A \rightarrow \texttt{a}$
> 
> where $\texttt{a}$ is any terminal and $A$, $B$, and $C$ are any variables-- except that $B$ and $C$ may not be the start variable. In addition, we permit the rule $S \rightarrow \epsilon$, where $S$ is the start variable.

###  Proof
1. Add a new start variable $S_0 \rightarrow S$
2. Remove all  $A \rightarrow \epsilon$ where $A$ is not the start variable. For each occurrence of an on the right hand side of a rule, we add a new rule with that occurrence deleted
3. Remove all $A\rightarrow B$ and replace with $B\rightarrow\dots$ so that $A\rightarrow\dots$  so that there are no single variables on the RHS
4. Remove all occurrences of $A\rightarrow {Variables}$ where ${Variables} \neq 2$ and ensure no occurences of $A\rightarrow Bc$ by replacing with $A\rightarrow BC\text{ and new rule} C\rightarrow c$

