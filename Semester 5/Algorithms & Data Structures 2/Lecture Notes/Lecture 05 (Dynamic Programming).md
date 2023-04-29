#lectureNote
# Standard Algorithmic Techniques
- **Greed**: Build up solution incrementally, myopically optimizing some local criterion
- **Divide-and-Conquer:** Break up a problem into two sub-problems, solve each sub-problem independently, and combine solution to sub-problem to form solution to original problem.
- **Dynamic Programming:** Break up a problem into a series of (overlapping) sub-problems and build up solutions to larger and larger sub-problems.
	- Not a specific algorithm, but a technique
	- Used for optimization problems
# Interval Scheduling
- ![[Screenshot_20230118_203918.png]]
- **Problem:**
	- *Input* A set of n jobs. Job j starts at $s_j$ and finishes at $f_j$.
	- Two jobs **compatible** if they don't overlap
	- **Goal:** Find a *maximum cardinality* subset of *mutually compatible* jobs
- ## Greed Algorithm Implementation
	- Consider jobs in increasing order of finish time. Take each job provided it's compatible with the ones already taken.
