!!# Notation


For the most part of this module will we use the notation from the "Introduction to the Theory of Computation" {cite}`sipser` book. However we will deviate slightly in the following way, for consistency with Fundamental Mathematical Concepts.

The set of **natural numbers**, denoted $\mathbb{N}$, is the set $\{1,2,3, \ldots\}$ (note that the element $0$ is not included). The set of **Integers**, denoted $\mathbb{Z}$, is the set $\{\ldots, -2,-1, 0, 1, 2, \ldots\}$.

A **sequence** of objects is a list of these objects in some order. A sequence is denoted using parentheses. For example, $(4,2,3)$ is the sequence containing three elements; $4$ is the first element, $2$ is the second element and $3$ is the third element. A sequence may be finite or infinite. Finite sequences are often called tuples. A $k$-tuple is a tuple containing $k$ elements.

A **String** is a sequence of **symbols**. The set of symbols from which the elements of a string come from is called the **alphabet**. The alphabet may vary depending on the application. The only requirement is that the alphabet is a non-empty and finite set. Generally we denote the alphabet in a particular context as $\Sigma$ or $\Gamma$. The elements of an alphabet are typeset in a typewriter font to differentiate them from normal text. For example;

$\Sigma_1 = \{\texttt{0},\texttt{1}\}$

$\Sigma_2 = \{\texttt{a}, \texttt{b}, \texttt{c}, \texttt{d}, \texttt{e}, \texttt{f}, \texttt{g}, \texttt{h}, \texttt{i}, \texttt{j}, \texttt{k}, \texttt{l}, \texttt{m}, \texttt{n}, \texttt{o}, \texttt{p}, \texttt{q}, \texttt{r}, \texttt{s}, \texttt{t}, \texttt{u}, \texttt{v}, \texttt{w}, \texttt{x}, \texttt{y}, \texttt{z}\}$


A **string over an alphabet** is a finite sequence of symbols from that alphabet, usually written next to each other, without commas. For example if $\Sigma = \{\texttt{0}, \texttt{1}\}$ then $\texttt{010011010}$ is a string over $\Sigma$. If $w$ is a string over $\Sigma$ then the length of $w$, denoted $|w|$, is the number of symbols in the sequence. The string of length zero is called the $\textbf{empty string}$ and is denoted $\epsilon$. If $w$ has length $n$ we can write $w = w_1,w_2,\ldots, w_n$ where $w_i \in \Sigma$ for $1 \leq i \leq n$. The $\textbf{reverse}$ of a string over an alphabet is the string in the opposite order, that is, if $w = w_1,w_2,\ldots, w_n$ is a string over an alphabet $\Sigma$ then the reverse of $w$, denoted $w^{\mathcal{R}}$, is the string $w = w_n,\ldots,w_2, w_1$. A string is a **sub-string** of $w$ if it appears consecutively within $w$. We call $x$ the $\textbf{prefix}$ of a word $w$ if $w=xy$ for some string $y$. The $\textbf{concatenation}$ of two string $x= x_1, \ldots, x_n$, $y=y_1,\ldots, y_m$, denoted $xy$, is the string $w = x_1\ldots x_ny_1\ldots y_m$. The $\textbf{Kleene star}$ is a unary operator that constructs a set of elements given a set of elements. If $\Sigma$ is a finite alphabet then $\Sigma^*$ is the set of all finite length strings over that alphabet. Note if $\Sigma$ is finite then $\Sigma^*$ is countably infinite. 

 Greek letters will be used through this module, below is a table of Greek letter.


| Symbol                | Name    |
| --------------------- | ------- |
| $\alpha$              | alpha   |
| $\beta$               | beta    |
| $\gamma$ $\Gamma$     | gamma   |
| $\delta$ $\Delta$     | delta   |
| $\epsilon$            | epsilon |
| $\zeta$               | zeta    |
| $\eta$                | eta     |
| $\theta$ $\Theta$     | theta   |
| $\iota$               | iota    |
| $\kappa$              | kappa   |
| $\lambda$ $\Lambda$   | lambda  |
| $\mu$                 | mu      |
| $\nu$                 | nu      |
| $\xi$   $\Xi$         | xi      |
| $o$                   | omicron |
| $\pi$ $\Pi$           | pi      |
| $\rho$                | rho     |
| $\sigma $ $\Sigma$    | sigma   |
| $\tau$                | tau     |
| $\upsilon$ $\Upsilon$ | upsilon |
| $\phi$ $\Phi$         | phi     |
| $\chi$                | chi     |
| $\psi$ $\Psi$         | psi     |
| $\omega$ $\Omega$     | omega   |