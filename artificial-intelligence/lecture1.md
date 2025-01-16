# Lecture 1

## Agents 

"Percieves" its environment via **sensors**, acts on the environment via **actuators**.

### Reflex Agent

Intuitively, makes decisions "in the moment," doesn't consider future outcomes.
- Chooses actions based on the *current* state of the environment.
- It's decision mechanism is more or less just "if-else" rules.

#### Pacman Example

**Reflex function**: "Move towards the nearest dot and eat it".
- The reflex function describes the action that the agent should take based on the current environment.
**Goal**: Eat all of the dots.


### Planning Agent

Analyzes outcomes of an action and chooses a strategy to complete the action.

### How do we define the "right" decision towards a goal?

Performance measurement **P** describes the outcome of actions.


#### Applications of Search Algorithms
##### Search Input

A state "space", which describes all the possible states.
In the class example, there are 2^9 possible states if pacman can walk on a 3x3 grid where each point can either have a dot or not.

A successor (transition) function, which describes how the agent should transition from one state to the next.
Formally, it is described as `t(current_state, action, cost)->next_state`.

##### Search Output

A sequence of legal actions that starts with the current states and ends with the goal state.

##### Example
