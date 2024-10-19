## Nondeterministic FSMs

why should we have NDFAs?  
    DFAs can become quite complicated. we should use NDFAs to simplify our diagrams, with the understanding that NDFAs can always be collapsed (expanded, really) down to DFAs. generally, as a language becomes more complex, and its alphabet increases in size, we can imagine many examples that would take forever and ever to define as DFAs.

definition 
    (K, sigma, delta, s, A) where:
    K is a finite set of states, 
    sigma is an alphabet,
    s in K is the start state (its included in K, so one of our defined states has to also be a start state)
    A subset K is the set of final accepting states, meaning every element of A must also be in K,
    delta is the transition relation, it is a finite subset of:
        (K x (sigma U {epsilon})) x K
        basically, each element of the transition relation (which itself defines the language), has (state, input symbol or epsilon) pair and new state

let w be an element of sigma*, then
    M accepts w iff at least one of its computations accepts (if the configuratoin is an accepting configuratoin)
    M rejects w iff none of its computation accepts (if there are no accepting configurations)
L(M) denotes the language accepted by M, which containts the est of all strings accepted by M

differences between NDFA and DFA
    these differences mainly occur from the fact that delta can be any arbitrary transition *relation*, whereas with DFAs delta must be a transition *function*. in other words, functions are well-defined and relations are a lot looser when it comes to input and outputs. in other words, delta may not be a function.
    1. NDFA can simply halt without accepting (in this case, there are no transitions defined for a particular state that was just entered). recall that halting simply means that there is no way to process an input.
    2. NDFA may enter a state where two or more moves are possible . why?
        1. out of some state q, we may have to transitions defined for the same character
        2. out of some state q, epsilon can be defined as a transition. if the machine transitions under epsilon, no input is consumed. this is different than DFAs because DFAs cannot transition under epsilon. remember that any string can have infinite numberes of epislon attached to them, so we can just pull off one of these infinite numbers of epislons, never actually consuming part of our non-empty string. it may be better to say that a machine always consumes input, but practically, an NDFA can just keep consuming epsilons.

discussing acceptance
    how do we actually determine what an NDFA accepts?
    we can say that if there is *at least one* set of configurations that ends in an accepting state, and there is no input left to be processesd, then the NDFA accepts that input.
    that is, there may be dozens and dozens of configurations for a particular input that do not accept, or that do not define transitions such that we run out of inputs, but if there is at least one, we can say the language accepts it.

fun non-dterminism example:
    missing-letter language
    let sigma = {a,b,c,d}, define L = {w : there is a symbol a in sigma not appearing in w}

handling epsilon transitions
    we say that, for any NDFA called M, M consumes no input if it takes epsilon.
    we can define an algorithm (there is actually a formal definition for this function, but i find it easier to understand just looking at the algorithm)
    eps(q: state) = 
    1. result = {q}
    2. while there exists some p in result, and some r not in result, and some transition (p, epsilon, r) in delta exists: do
    3. return result

this algorithm is guaranteed to halt, meaning, it is guaranteed to return something.
each time through the loop, it adds an element. when there are no elements left, it halts.
its important to remember that NFAs are not defined for infinite inputs, but if we did have infinite input, then i suppose we could say this isnt guaranteed to halt. 

theorem: if there is a DFA for L, there is an NFA for L. in other words, for every DFA, there is an equivalent NFA (by equivalence, we mean they accept the same language).

proof by construction:


## ndfsom to dfsm algorithm

nfa-to-dfa(M: dfa) =
    1. for each state q in K do:
        compute eps(q) // these are used later in the algorithm
    2. s'=eps(s)
    3. compute T': *(T is the transition function)*
        3.1 active-states = {s'}  

## questions
    how is A x B defined (where A and B are sets)?
    