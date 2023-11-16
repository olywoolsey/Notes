#COMP1421 #COMP2421
## General matrix form
A _matrix_ can have any number of rows and any number of columns...
$A =\begin{pmatrix} A_{11} & A_{12} & A_{13} & \cdots & A_{1n} \\ A_{21} & A_{22} & A_{23} & \cdots & A_{2n} \\ A_{31} & A_{32} & A_{33} & \cdots & A_{3n} \\ \vdots & \vdots & \vdots & & \vdots \\ A_{m1} & A_{m2} & A_{m3} & \cdots & A_{mn} \end{pmatrix}$
This example has $m$ rows and $n$ columns.  
We call $A$ an $m×n$ matrix
- The values of $A_{ij}$ are known as coefficients of $A$
- $A=B$ if all coefficients are equal and is the same dimensions
### Matrix Addition
- Must be same size
- $C_{ij} = A_{ij} + B_{ij}$
### [[Vectors]]
- A matrix with only one row or columns
- $\begin{pmatrix} 1 2 3 \end{pmatrix}$called a row vector
- $\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$called a column vector
### Dot Product
- [[Vectors]] must have the same length
- multiply corresponding elements then add together
- $\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} .\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} = 1 + 4 + 9 = 14$
### Matrix Multiplication
- $AB$ Possible if the number of columns in $A$ equals the number of rows in $B$
- For every element in the matrix dot the column vector of the first matrix($A$) with the row vector of the second($B$)
- result will be size of rows of $A$ and columns of $B$
	- i.e. if $A$ = m x n and $B$ = p x j
	- can multiply is n = p
	- then: $AB$ = m x j
 I LOVE MATRICES
