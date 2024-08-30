---

## Prerequisite Knowledge for the Course

### Graphs

**Types of Graphs:**
1. **Cyclic vs. Acyclic:**
   - **Cyclic:** Contains cycles (a path that starts and ends at the same vertex).
   - **Acyclic:** Contains no cycles.
2. **Connected vs. Disconnected:**
   - **Connected:** There is a path between any two vertices.
   - **Disconnected:** Some vertices are not reachable from others.
3. **Weighted vs. Unweighted:**
   - **Weighted:** Edges have weights (values).
   - **Unweighted:** Edges do not have weights.

**Degree of a Node:**
- The degree of a node is the number of edges connected to it.

### Trees

**Definition:**
- A tree is a connected, acyclic graph.

**Properties:**
- **Root Node:** A special starting node with no parent.
- **Parent/Child Relationship:** Each node (except the root) has exactly one parent and zero or more children.
- **Leaf Node:** A node with no children, typically found at the bottom of the tree.
- **Height:** The length of the longest path from the root to any leaf.

### Graph Algorithms

**Traversal Algorithms:**
- **Depth-First Search (DFS):** Visits nodes by exploring as far down a branch as possible before backtracking.
- **Breadth-First Search (BFS):** Visits nodes level by level from the starting node.

**Shortest Path Algorithms:**
- **Dijkstra's Algorithm:** Finds the shortest path from a starting node to all other nodes in a graph with non-negative edge weights.
- **Bellman-Ford Algorithm:** Finds the shortest path from a starting node to all other nodes, and can handle graphs with negative edge weights.

## Regular Languages

### Outline
When discussing regular languages, we will focus on:
1. **Finite Automata:** Mathematical models for recognizing patterns within input strings.
2. **Nondeterminism:** A property where an automaton can be in multiple states at once, or choose between multiple transitions.
3. **Regular Expressions:** A notation for specifying patterns in strings.
4. **Limitations:** Not all languages can be recognized by finite automata; non-regular languages are those that cannot be recognized by such machines. This is demonstrated using the **pumping lemma**.
<small> The pumping lemma is something we'll discuss later. Basically, it is used to prove that a language is NOT regular.' </small>

### Finite State Machine (FSM) or Finite Automaton

- **Definition:** A model of computation with a limited amount of memory, suitable for simple tasks like recognizing patterns or controlling systems with straightforward states.
- **Markov Chains:** A probabilistic extension of FSMs where the next state is determined by a probability distribution rather than deterministic transitions.

---
### Markov Chain Example

You have a jar with 7 distinct balls, and you want to know how many times you should draw with replacement to see every ball at least once. This is a classic problem that can be approached using the concept of the **Coupon Collector's Problem**.

In the Coupon Collector's Problem, you want to determine the expected number of trials needed to collect all unique items when each item is drawn with replacement.

**Expected Number of Draws:**
For \( n \) distinct items (or balls, in this case), the expected number of draws \( E(n) \) needed to see every item at least once is given by:

\[ E(n) = n \cdot \left(1 + \frac{1}{2} + \frac{1}{3} + \cdots + \frac{1}{n}\right) \]

where the sum inside the parentheses is the \( n \)-th Harmonic number \( H_n \). 

For \( n = 7 \) balls:

\[ E(7) = 7 \cdot \left(1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} + \frac{1}{6} + \frac{1}{7}\right) \]

Calculating the Harmonic number \( H_7 \):

\[ H_7 \approx 2.592857 \]

So:

\[ E(7) \approx 7 \cdot 2.592857 \approx 18.15 \]

Thus, you should expect to draw approximately 18.15 times to see all 7 distinct balls at least once.

### Finite Automaton Strict Definition (5-tuple)

A finite automaton (FA) is defined by a 5-tuple \( (Q, \Sigma, \delta, q_0, F) \), where:

1. **\( Q \)** is a finite set of states.
2. **\( \Sigma \)** is a finite set of symbols called the input alphabet.
3. **\( \delta \)** is the transition function, \( \delta: Q \times \Sigma \rightarrow Q \), which maps a state and an input symbol to the next state.
4. **\( q_0 \)** is the start state, \( q_0 \in Q \).
5. **\( F \)** is a subset of \( Q \) called the set of accept states (or final states).

Here's a brief review of each component:

- **States (Q)**: These represent all possible configurations or conditions of the automaton.
- **Input Alphabet (\( \Sigma \))**: This is the set of symbols that the automaton reads from its input tape.
- **Transition Function (\( \delta \))**: This function dictates how the automaton moves from one state to another based on the current input symbol.
- **Start State (\( q_0 \))**: This is the initial state of the automaton before any input is processed.
- **Accept States (F)**: These are the states where, if the automaton ends up after processing the input string, the string is considered accepted by the automaton.

**Cartesian Product of Sets**: In the context of the transition function \( \delta \), the Cartesian product \( Q \times \Sigma \) represents all possible pairs of states and input symbols. The transition function \( \delta \) takes each pair and assigns a new state.
---

### Language

**Definition:** A language of a machine \( M \) is the set of strings that \( M \) accepts. 

**Notation:** \( L(M) = A \)

##### Example
- Given: 
  - The string "1101" is accepted.
  - The string "110" is rejected.
- Conclusion: 
  - \( M \) accepts all strings that end with a "1".
  - Thus, \( L(M) = \{ w \mid w \text{ ends in a } 1 \} \).

**Note:** \( L(M) \) represents the set of strings that \( M \) recognizes or accepts. This is different from the set of all possible inputs to \( M \). The accepted set does not include strings that \( M \) rejects.

#### Notes
- We say that \( M \) "recognizes" or "accepts" a language \( A \).
- Both the state diagram and the formal description of a language provide the same information about \( M \).

---

### Formal Definition of Computation

Let \( M = (Q, \Sigma, \delta, q_0, A) \) be the 5-tuple definition of a finite state machine (FSM).  
Let \( w = w_1w_2 \ldots w_n \) be a string (word) where each \( w_i \) is a member of the alphabet \( \Sigma \).  
\( M \) accepts \( w \) if there is a sequence of states \( r_0, r_1, \ldots, r_n \) in \( Q \) that satisfies these three conditions:

1. \( r_0 = q_0 \) (The machine starts in the start state)
2. \( \delta(r_i, w_{i+1}) = r_{i+1} \) for \( i = 0, \ldots, n-1 \) (The machine transitions according to the transition function)
3. \( r_n \in A \) (The final state \( r_n \) is an accept state, so we accept the string)

---

### Regular Language

A language is called a **regular language** if some finite automaton can accept it.

#### Examples (Alphabet = \{0, 1\})
1. **Recognize strings with an odd number of 1s:**
   - \( W = \{ w \mid \text{number of } 1\text{'s in } w \text{ is odd} \} \)
2. **Recognize the substring "001":**
   - \( W = \{ w \mid \text{"001" is a substring of } w \} \)

#### Regular Operators
1. **Union (\( A \cup B \))**: Combines two languages.
2. **Concatenation (\( A \cdot B \))**: Forms a language from strings of \( A \) followed by strings of \( B \).
3. **Star (\( A^* \))**: Includes any number of concatenations of strings from \( A \), including the empty string.

---
