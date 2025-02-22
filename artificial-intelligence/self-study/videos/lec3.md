# Lecture 3

## General Tree Search

### Algorithm

```lua
function TreeSearch(problem, strategy)
	initTreeSearch(problem.initialState)
	while true do
		if #getCandidates() == 0 then
			return failure
		end 
		leafNode = choose(strategy)
		if contains(node, goalState) then
			return solution -- the list of actions to take
		else
			newNodes = expand(leafNode)
			add(newNodes, treeSearch)
		end
	end
end
```

#### Remarks

- All search algorithms differ only in their fringe strategy (i.e., which nodes are expanded first).
- A priority queue generalizes both stack and queue behaviors.

## Informed Search

### Search Heuristics
- Estimate how close a state is to a goal.
- Evaluated at each node.

#### Heuristic Design
- Heuristics estimate distance to the goal.
- Evaluation functions estimate utility gained or lost by entering a state.

##### Examples
- Manhattan distance
- Straight-line distance

### Greedy Search
Expands the node that seems closest to the goal, based on a heuristic.

```py
nextExpansion = min([for frontierNode in frontierNodes: heuristic(frontierNode)])
```

#### Remarks
Heuristic values often decrease with depth, making greedy search resemble depth-first search in small graphs.

## A* Search
Combines concepts from UCS and Greedy Search.

### UCS | g(n)
Expands the least costly path. No heuristic is used.

### Greedy Search | h(n)
Expands the node with the lowest heuristic, ignoring actual costs.

### A* | f(n) = g(n) + h(n)

### When Should A* Terminate?
A* terminates when it dequeues a goal node, ensuring all transition sequences are considered.

#### What Does the * in A* Mean?
The * indicates optimality.

#### When is A* Optimal? (Admissible Heuristics)
A* is optimal if:
\[ 0 \leq h(n) \leq h^*(n) \]
where \( h^*(n) \) is the true cost to the nearest goal.  
The heuristic should never overestimate this cost.

### Designing Heuristics for A*
- A* is implemented once; designing an admissible heuristic is the challenge.
- Heuristics often assume a relaxed version of the problem.

### Graph Search
Graph search avoids expanding redundant states by tracking visited nodes.
- Preserves completeness
- Maintains optimality

### Consistency of Heuristics
A heuristic is consistent if:
\[ h(A) - h(C) \leq cost(A, C) \]  
This ensures \( f \) values never decrease along a path, making A* optimal.