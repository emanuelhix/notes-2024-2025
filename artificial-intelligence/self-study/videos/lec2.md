# Lecture 2  

## Agents  

### Reflex Agents  
- Act based on the current state (and possibly memory).  
- Ignore future consequences (utility).  
- Can be optimal but often "get stuck."  

### Planning Agents  
- Act based on estimated utility.  
- Require a world model.  
- Prioritize future benefits over immediate progress.  

## Search Problems  

### Key Concepts  
- **State space**: All possible world states.  
- **Successor function**: Defines state transitions, actions, and costs.  
- **Start state & goal test**: Defines the initial state and success criteria.  
- **Solution**: A sequence of actions from start to goal.  

## State Space Details  

### Types of States  
- **World state**: Full environment details (e.g., Pac-Man’s grid, dots, ghosts).  
- **Search state**: Only relevant details for planning a solution.  

### Counting World States (Pac-Man Example)  
- 120 grid positions  
- 30 food dots  
- 12 ghost positions, 2 ghosts  
- 4 Pac-Man directions  
- Total states: \(120 \times 2^{30} \times 12^2 \times 4\)  

This is quite a lot. We'll investigate ways to trim this down later.

## Quiz: "Safe Passage"  

### Problem  
Pac-Man must eat all dots while ghosts are in "scared" mode.  
Two approaches:  
1. Ignore ghosts and focus on dots.  
2. Treat ghosts as moving dots for higher score.  

### Successor Function Design  
- **State includes**: Pac-Man’s position, dot & power pellet statuses, scared timer.  
- **Walls are excluded**: They are static and handled implicitly in the successor function (no transitions through walls).  

## State Space Graphs  
- Represents search problems mathematically.  
- **Nodes**: World configurations.  
- **Arcs**: Successor transitions.  
- **Goal test**: Checks if a goal node is reached.  
- **Each state appears once** (unlike trees).  
- Too large to store entirely in memory.  

## Search Tree  
- "What if" tree of plans and outcomes.  
- **Root**: Start state.  
- **Differs from state space graph**: Shows possible plans (sequences of actions and their results), not just state condensed state transitions.  

## BFS vs. DFS  

### When does each work best?  
- **DFS**: Better for deep solutions or when solutions exist in multiple places.  
- **BFS**: Best when the solution is close to the start state (shallow).  
- **BFS generally outperforms DFS**, but not always.  

## UCS 

Fringe becomes a priority queue, with the priority being the cumulative cost.
The strategy: expand the cheapest node (i.e. the node with the lowest cost, the one at the front of the priority queue) first.
