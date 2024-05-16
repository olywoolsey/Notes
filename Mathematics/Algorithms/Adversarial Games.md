# Adversarial Games
## Properties
- 2 Players (unless stated)
- Time limitations (either per move or whole game)

## Strategy
- Doesn't have to be good, a strategy
- Can depend on the opponents strategy
- **Winning Strategy:** one that will always win the game whatever moves the opponent(s) play
	- There cannot be a winning strategy for both players
	- A winning strategy may occur part way through the game
## Humans > Computers?
- As humans can easily remember the previous moves it can be easier to spot developing moves (Additive)
- Humans may be better at spotting bad things on the horizon than are brute force search techniques
## Minimax
- Moving to position with highest minimax value gives best achievable payoff assuming that the opponent always makes their best play
- Look ahead approaches (such as MiniMax) tend to do badly at the endgame play of chess.  
- Endgame strategies can involve quite long sequences of moves where a player gradually forces their opponent into a losing position
- It achieves perfect play for games that are simple enough for the algorithm to search right to its possible end states

## Randomness vs Uncertainty
Although closely related randomness and uncertainty are not the same thing.
The term ‘randomness’ is usually applied to situations where the range and frequency of outcomes is known. For instance, when rolling a standard die, each of the numbers 1–6 occurs with 1/6  
probability.
Taking into account the randomness of a dice roll is in most cases easier to model than the uncertainty of not knowing what your opponent will do in a given situation.