#COMP2421 
## Finite precision number systems
- Computers store numbers with **finite precision**, i.e. using a finite set of bits (binary digits), typically 32 or 64 of them.
- Many numbers cannot be stored exactly
    - Some numbers cannot be represented precisely using **any** finite set of digits:  
        e.g. $\sqrt{2}$=1.14142…, $\pi$=3.14159…, etc.
    - Some cannot be represented precisely in a given number base:  
        e.g. 19=0.111… (decimal), 15=0.00110011… (binary).
    - Others can be represented by a finite number of digits but only using more than are available: e.g. 1.526374856437 cannot be stored exactly using 10 decimal digits

## Normalised systems
### A general representation
Any finite precision number can be written using the floating point representation
$$x = b_1 b_2 b_3...b_{t-1} b_t * \beta^e$$
- The digits $b_i$ are integers satisfying $0\leq b_i \leq \beta - 1$
- The **mantissa**, $b_1 b_2 b_3...b_{t-1} b_t$ contains $t$ digits.    
- $\beta$ is the **base** (always a positive integer).
- $e$ is the integer **exponent** and is bounded $(L \leq e \leq U)$.
$(\beta , t, L, U)$ fully defines a finite precision number system.
### Normalisation
**Normalised** finite precision systems will be considered here for which $$b_1 \neq 0, (1 < b_1 \leq \beta - 1)$$
