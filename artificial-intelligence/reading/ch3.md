# Chapter 3

### open-loop system

when the agent ignores its percepts, which disconnects it from learning from its environment
this is generally only good to use if the agent is operating in a perfectly predictable environment (i.e. its deterministic, the agent knows everything about it, and nothing in the environment is hidden from the agents percepts).

### close-loop system

the opposite of an open-loop system. 
the agent must use its percepts to navigate the environment because there are tings hidden to the agent, the agent cannot predict certain aspects, the environment is not determinstic (and therefor, for all these reasons, unpredictable).

## formulating problems

### abstraction

intuitively, abstraction just means removing detail from something to make it more generalized.

#### good problem formulation

it is said that a good formulation "has the right level of detail," i.e. its abstracted such that the agent doesnt have too much detail (this can lead to the agent being unable to arrive at a solution)

### valid abstraction

a valid abstraction is one such that the agent can solve the problem in a more complicated environment.
so, even thoug the environment is getting more complicated, we dont have to change the way  we formulated the problem.
this is pretty dependent though. maybe we say an abstraction is valid if the environment gets more complicated and it still works, rather than saying the abstraction is perfectly valid and always works dependent of the environment.

## standardized problems

### grid world problem

a problem that exists in a 2d, rectangular array with square cells where agents can move cell to cell.
cells may have objecst the agent can act on.

### states

an environment with n cells will have n * b^n states,
where b is the number of possibilites a cell can have.

#### example

if a cell can have two possibilities, and there are say, 5 cells, then the number of possibilites is 5 * 2^5

#### egocentric actions

actions that are defined relative to the agent. i.e., turn 90 degrees, flip upside down, move forward, move backward,  etc.

## search algorithms

### search tree

each node in a search tree is mapped to a state within the state space, 
each edge in a search tree cooresponds to actions,
the root of the tree corresponds to the initial state

### state tree expansion

expansion is achieved by considering all actions available from a state tree's node, starting first with the initial state
we can see where an an action leads by analyzing the result function f(node, action)->node.
this is basically just a nfa.

### depth first search

from the root node, arbitrarily pick a node to go to.


### breadth first search
### uniform cost search
### A*
