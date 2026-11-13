# Comp Neuro Notes

## Attractor states

- Attractor states come from a dynamical system
- A dynamical system is a set of variables together with all the rules that determine their time-evolution
    - State of the system: the instanteous value of these variables
    - State: a point (vector) in the state space space (set of all states)
- Attractor: the minimal set of states in a state space to which all nearby states eventually flow

## Construction of neural attractors

- The general principle underlying the formation of non-trivial attractor states in neural circuits is *strong recurrent positive feedback*
- Common ways to characterize the relationship between synaptic weights and attractor dynamics:
    1. Forward problem: ask what attractors states a given set of weights produces
    2. Inverse problem: given a set of attractors, what network structure could generate it?