(content:nonregular)=
# Non-regularity

Not all languages are regular languages, that is, there exists languages where there does not exists a finite state automaton that recognises it. Without appropriate techniques it is challenging to demonstrate that a language is not regular. You would have to demonstrate that for every deterministic finite state automaton that it does not recognise the language. However, there are an infinite number of deterministic finite state automata and therefore this strategy does't work. In this section we introduce a technique for demonstrating that a language is not regular. 

## Pumping Lemma for Regular Languages


````{prf:lemma} Pumping Lemma for Regular Languages
:label: pumping_lang_reg

If $A$ is a regular language, then there is a number $p$ (the *pumping length*) where if $s$ is any string in $A$ of length at least $p$, then $s$ may be divided into three parts, $s = xyz$, satisfying the following conditions:

1. for each $i \geq 0$, $xy^iz \in A$,
2. $|y| > 0$, and
3. $|xy| \leq p$.


````
Note what the statement of the pumping lemma for regular languages says. **For all** regular languages, **there exists** a number $p$ such that **for all** sufficiently long strings $s$, **there exists** a subdivision of $s$ such that the conditions hold ture. The statement is a quantified logic statement with nested quantifiers.

````{prf:proof}

Let $M = (Q, \Sigma, \delta, q_1, F)$ be a deterministic finite automaton that recognises language $A$ and let $p = |Q|$. Let $s=s_1,\ldots, s_n$ be a string in $A$ of length $n$ where $n \geq p$. Let $r_1, \ldots, r_{n+1}$ be the sequence of states that $M$ enters while processing $s$, so $r_{i+1} = \delta(r_i, s_i)$ for $1 \leq i \leq n$. This sequence of states has length $n+1$, which is at least $p+1$. By the pigeonhole principle in the first $p+1$ elements of the sequence there must exist a repeated state. Let $r_j$ be the first instance of the repeated state and let $r_l$ be the second instance of the repeated state. Because $r_l$ occurs among the first $p+1$ elements in the sequence starting from $r_1$, we have that $l \leq p+1$. Let $x = s_1,\ldots, s_{j-1}$, $y=s_j, \ldots, s_{l-1}$ and $z=s_l,\ldots,s_n$.

As $x$ takes $M$ from $r_1$ to $r_j$, $y$ takes $M$ from $r_j$ to $r_j$, and $z$ takes $M$ from $r_j$ to $r_{n+1}$ (recall that $r_{n+1}$ is an accepting state) then $M$ accepts $xyz$. The automaton $M$ also accepts $xy^iz$ where $i \geq 0$. We know that $j \not= l$, so $|y| > 0$ and $l \leq p+1$ so $|xy| \leq p$.

````

The name 'pumping lemma' comes from the observation that strings can be 'pumped' (made bigger) by repeating the $y$ section of the string whilst still remaining in the language. The pumping lemma for regular languages is useful when trying to show that a language is not regular, we will see an example of this later in this section. Note what the statement of the pumping lemma for regular languages says, if a language is regular then it can be pumped. However the reverse of the statement is not the case, that is, there are some non-regular languages which can be pumped. The consequence of this is that the pumping lemma **can't** be used to prove that a language is regular.

## Myhill-Nerode theorem

The Myhill-Nerode theorem is a fundamental result in the theory of formal languages, which provides a necessary and sufficient condition for a language to be regular. Specifically, the Myhill-Nerode theorem states that a language is regular if and only if $L_{\sim}$ has a finite number of equivalence classes, and the number of equivalence classes is equal to the number of states in the minimal deterministic finite state automaton.

In this context $L_{\sim}$ is an equivalence relation defined as $x L_{\sim} y$ if there exists a $z$ such that $xz \in L \leftrightarrow yz \in L$.

The Myhill-Nerode theorem has several important applications:

1. It can be used to prove that two regular languages are different, by constructing a string that is accepted by one language and rejected by the other.

2. It can be used to show that a language is not regular, by demonstrating that there exists a string that cannot be distinguished from any other string by a finite automaton.

3. It can be used to design efficient algorithms for minimising finite automata, which are used to recognise regular languages.

4. It can be used to prove that certain problems, such as the word problem for finitely generated monoids, are undecidable.

5. It can be used to prove the existence of non-regular languages, such as the language of all palindromes over a given alphabet.

The proof of the Myhill-Nerode theorem is an advanced topic which won't be covered in the lectures but you are encouraged to read and understand it [Myhill-Nerode theorem](https://en.wikipedia.org/wiki/Myhill%E2%80%93Nerode_theorem).

## A non-regular language

We will apply the pumping lemma for regular languages to show that $\{0^n1^n\mid n\geq 0\}$ is not regular.


````{prf:theorem} 
:label: not_reg

$\{0^n1^n\mid n\geq 0\}$ is not regular

````
````{prf:proof}

We proceed by contradiction. Assume that $\{0^n1^n\mid n\geq 0\}$ is regular. From Theorem~\ref{thm:pumping} we know that there is a pumping length $p$. We choose $s=0^p1^p$, clearly $s \in \{0^n1^n\mid n\geq 0\}$ and as $|s| > p$ the pumping lemma says $s$ can be divided into three sections $x, y$ and $z$ such that $s=xyz$, where for any $i \geq 0$ the string $xy^iz \in \{0^n1^n\mid n\geq 0\}$. We consider three cases;


1. The string $y$ consists of only zeros. In this case $xyyz$ consists of more zeros than ones and therefore is not a member of $\{0^n1^n\mid n\geq 0\}$. This is a contradiction, violating condition 1.

2. The string $y$ consists of only ones. In this case $xyyz$ consists of more ones than zeros and therefore is not a member of $\{0^n1^n\mid n\geq 0\}$. This is a contradiction, violating condition 1.

3. The string $y$ consists of both zeros and ones. In this case $xyyz$ may contain the same number of zeros and ones, however, they will appear out of order in the string and therefore $xyyz$ is not a member of $\{0^n1^n\mid n\geq 0\}$. hence we reach a contradiction that $\{0^n1^n\mid n\geq 0\}$ is regular.


The three cases above cover all eventualities, there is no way of splitting the string into three parts that does not fall into one of the three cases. In each case we reach a contradiction. Therefore $\{0^n1^n\mid n\geq 0\}$ is not regular.

````

