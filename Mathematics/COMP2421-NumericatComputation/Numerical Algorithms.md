# Numerical Algorithms
#COMP2421
- Numerical algorithms are those which operate on _[[Floating Point Numbers]]_.
- They are used to provide solutions (or approximations to solutions) of mathematical models of “real world” problems.
- Such problems arise in a very wide range of applications (a few examples to follow).
- An important feature of these algorithms is that they need to account for the fact that arithmetic with [[Floating Point Numbers]] is not exact!
### Applications I: Scientific and engineering computing
- Physical simulations are used for prediction in many different scientific and engineering areas.
- These models are hugely complex but also hugely important!
- Typically large physical domains are split up into small physical pieces which can be modelled more simply using techniques such as conservation laws
### Applications II: High performance graphics
- Realistic behaviour within games requires an accurate and efficient _physics engine_.
- Uses _Newton’s laws of motion_ to predict motion (e.g. projectiles, vehicles, etc) and impacts (e.g. crashes, collisions, etc).
- These are examples of dynamic models which must be solved and then rendered in “real time”.
### Applications III: Artificial intelligence
- Data mining requires complex models of very large data sets in order to extract useful information from them (e.g. Google PageRank)
- Self-driving cars, robotics and more rely on quick, accurate image processing and vision
- Much of AI boils down to _optimisation_ which requires special numerical methods
- [Unlock the Secrets of Machine Learning with Linear Algebra](https://www.univ.ai/blog/studying-linear-algebra)