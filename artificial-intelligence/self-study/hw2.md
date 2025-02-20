# Homework 2 Notes

## Minimax

This algorithm is used to determine the optimal move for a player, assuming their opponent is also playing optimally.

### Maximizer

Tries to get the highest score possible 

### Minimizer

Tries to get the lowest score possible

### Game state

If the maximizer is winning, the score of the board tends in the positive direction.
If the minimizer is winning, the score of the board tends in the negative direction.

### Top level view of the algorithm

This is a backtracking algorithm, meaning that all moves are considered, then the best move is considered at the end and traversed.

https://www.geeksforgeeks.org/minimax-algorithm-in-game-theory-set-1-introduction/
