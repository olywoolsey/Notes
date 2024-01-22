# SAT-Solving
#logic #COMP1421 
## Satisfiable
- has a truth assignment that makes it true
	- the truth assignment is called a satisfying assignment
- a formula that doesn't have an assignment that makes it true is called unsatisfiable
## SAT
- satisfiability problem of [[../Logic/Propositional logic]]
	- Input A propositional formula
	- Question Is the formula satisfiable?
- the truth table for this grows exponentially
- The area SAT-Solving of computer science deals with the task of developing procedures that solve the satisfiability problem for [[../Logic/Propositional logic]] and are much more efficient than the procedure using [[Truth Tables]].
## Cook's Theorem(1971)
- The satisfiability problem of [[../Logic/Propositional logic]] is NP complete
	**NP Complete:**
	that an‘efficient’ (i.e. polynomial time) algorithm for that problem is highly unlikely to exist