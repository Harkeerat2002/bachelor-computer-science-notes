#lectureNote
# The Art of Conjecture
- Certain knowledge vs Probable opinion
- Use **statistics** to understand how certain I can be of a claim

# Logic of Scientific Discovery
- ## Non-scientific Statements
	- **Cannot be proved or disapproved**
		- *cats are better than dogs*
		- *death sentence is morally wrong*
- ## Scientific Statements
	- **Can be tested empirically**
		- *cats are better than dogs at climbing trees*
		- *USI classes make students sleepy*

# Testing Hypothesis
- To confirm or dis-confirm
- ## Isolating Cause - Control Condition
	- **Control Group = Experimental Group - Cause**
- ## Randomization
	- **Difficult to have exactly identical conditions for many factors**
		- Human variation: age, IQ-level, skills, education
		- Starting conditions: time of day, weather, mood
	- **Randomization**
		- Allocation participants and experimental conditions randomly to control and experimental group
- ## Controlling a confounding variable
	- ### Experimental Design
		- **Confounding Variables are typically set to a *fixed value***
			- If I am experimenting a new IDE for developers, I can balance the experimental and control group in terms of programming kills (confounding variables).
			- Such procedure is known as Blocking: The arrangement of Experimental units (e.g., participants) into groups (blocks) of similar conditions.
	- ### Non-experiments (e.g., observational studies)
		- **We use statistics to "even out" their effects**
			- We suspect that the programming language used may have an impact on the likelihood of introducing bugs. When collecting data we keep track of the programming language used by each developer, then group results by these factors later.
# Key Terms in Experimental Design
- **Independent Variable (IV):**
	- The suspected cause for observed change, hence of primary interest.
	- Values will be **manipulated** by the experimenter (e.g., present/absent, intensity).
	- Also known as: *Factor* of the experiment.
- **Dependent Variable (DV):**
	- Value will be **measured** by the experimenter.
- **Confounding Variable**
	- Variable that can influence both IV and DV, causing spurious influence.
	- Must be **controlled** by the experimenter.
- ## In a Nut-Shell:
	- **Independent Variable:** What you Change?
	- **Control Variable:** What you keep the same?
	- **Dependent Variable:** What you measure?

# Designing Good Experiments
- ## Three Aims for research
	- **Valid:**
		- Actually shows what you intended to demonstrate.
	- **Reliable:**
		- Can be repeated (by yourself) and reproduced (by others).
		- Can be generalized beyond particular experiment.
	- **Important:**
		- Subjective, but good to strive for lasting contribution
		- Invalid/unreliable is always unimportant
- ## Maximizing Validity
	- **Internal Validity**
		- Issue if the obtained measures are not due to your manipulations, but caused by other factors.
		- Requires ruling out confounding variables
		- Can be addressed by good experimental design
	- **External Validity**
		- Issues if results are not generalizable but only apply to narrow population/conditions you tested
		- Require use of intuition, judgment.
- ### Internal Validity Threats
	- **Group Threat**
		- Control & experimental groups are too different
	- **Time Threat (w/ people)**
		- Maturation (learning effect, tiring effect)
		- Passage of time and historical events introduce behavioral changes
	- **Time Threat (w/ measurement)**
		- Machines get better/worse (e.g., battery level)
		- Experimenter gets better at using instruments
	- **Differential Morality**
		- People drop out from control/experimental group. Maybe only very motivated people are left.
	- **Experimenter Effect**
		- People behave differently when measured
		- **Evaluation apprehension:** Anxiety of being tested
		- **Social Desirability:** People want to look good
		- **Demand Characteristics:** People want to please, what to make experiment "work"
- ### External Validity
	- **Using Special Participant Groups**
		- Most popular group in SE paper: CS undergraduate students as representative of developers.
		- Volunteers often have higher respect for science
		- Best: Random sample, stratified/representative example
	- **Using too few participants/instances**
		- Hard to generalize from only a few instances
		- Use statistics to learn how many data points we need to generalize to a specific population