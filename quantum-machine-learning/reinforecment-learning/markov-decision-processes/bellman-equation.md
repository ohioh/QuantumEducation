---
description: '@glimpse [ coming soon ]'
---

# Bellman equation

@wiki [https://en.wikipedia.org/wiki/Bellman\_equation](https://en.wikipedia.org/wiki/Bellman\_equation)

The Bellman equation was formulated by [Richard Bellman](http://www.iumj.indiana.edu/IUMJ/FULLTEXT/1957/6/56038) as a way to relate the value function and all the future actions and states of an MDP.

![Bellman equation](<../../../.gitbook/assets/image (9).png>)

The function defines the value of a state as the sum over all discounted rewards which are weighted by the probability of their occurrence given by a certain policy π.

π(a∣s) is the therm as a probability of taking an action ( a ) in a state ( s ) under the policy π.

&#x20;π simply states what the agent ought to do in each state. This could be stochastic or deterministic.&#x20;
