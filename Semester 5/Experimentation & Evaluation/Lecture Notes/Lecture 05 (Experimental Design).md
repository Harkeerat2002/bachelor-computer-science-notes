#lectureNote
# John Stuart Mill (Lecture 02)
- ## Agreement
		- Overlapping conditions, same effect
		- if **ABC** -> **abc** and **CDE** -> **cde** then **C** -> c
- ## Disagreement
		- Missing condition, no effect
		- if **ABC** -> **abc** and **AB** -> **!c** then **C** -> **c**
- ## Concomitant Variables
		- Stronger condition and effect
		- if **ABC** -> **abc** and **ABCC** -> **abccc** then **C** -> **c**
- ## Residues
		- Individual conditions don't show effect
		- if **ABC** -> **abc** and **A** -> **a!c** and **B** -> **b!c** then **C** -> **c**

# Test Driven vs Standard
- **Test Driven:** Write the Test-Code First, and then write the Code to cover the test.
- **Standard Driven:** Write the Code then write the Test Code to cover the test.

# Independent Variable
- ## Test One-Factor-At-Time (OFAT)
		- Test different IDEs first (by keeping constant the rest) development then and finally programming languages
		- **Disadvantages:** The interactions between the different factors is not seen.
- ## Full Factorial Design
		- Test Combination of factors.
		- K factors each having n levels = $n^k$ tests
		- **Disadvantages:** Its very expensive to run. Learning Effect.
- ## Fractional Factorial Design
		- To be used when there are too many factors
		- **Disadvantage** The more we reduce, the less we can analyze interactions.

# Null Hypothesis (H*o*)
- No statistical significance exists in a set of given observation.
- There is no statically significant difference between the productivity of developers when using TDD and the standard development process.
- *It's easier to disprove then to prove.*

# Experimental Design
- ## Between Group Design
	- Random Allocation of all the participants
	- ![[Pasted image 20230124160235.png]]
	- **Disadvantage:** Groups may end up being very different as compare to each other
	- **Advantage:** When the population is very huge, or there is no information on the population
- ## Within Subjects Design
	- Each participant taking part on both the control and the experimental group in different order
	- ![[Pasted image 20230124160508.png|625]]
	- **Disadvantage:** The order can be the problem, as there is the Learning Effect and the Tiring Effect as well

# True Experiment
- ## Characteristics:
	- ### Manipulation of Independent Variables
	- ### Randomized Groups
	- ### Control Groups

# Beyond Experiment
- ## Quasi Experiment
	- No randomized groups
- ## Survey
	- Self-reports instead of measurements.
	- **Problem:** Selection Bias
- ## Case Study
	- Observation of participants over long period of time.
	- **Problem:** Usually hard to generalize
- ## Naturalistic Observations
	- **Problem:** No awareness of participants that they're studied.