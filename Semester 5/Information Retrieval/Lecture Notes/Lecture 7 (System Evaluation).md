#lectureNote
# Evaluation
- **Evaluation** is concerned with assessing if the system carries out its tasks properly
	- It is the key difference to building *effective* and *efficient* search engines
- **What to measure?**
	- **Efficiency:** How quickly can a user get the results? How much computing resources are needed to answer a query?
		- Measuring space and time overhead
	- **Effectiveness:** How good are the search results?
		- Measuring a system's ability of ranking relevant documents on top of non-relevant ones
	- **Usability:** How useful is the system for real use tasks
		- Requires doing user studies of the full system
- Effectiveness, efficiency and **cost** are related
- Effectiveness is more important to users than efficiency, but efficiency should not be forgotten.
- **Why Effectiveness?**
	- Assess the actual utility of an IR system
	- Compare different systems and methods

# The Cranfield Evaluation Methodology
- Primary approach to evaluate IR system's effectiveness
- **Idea:** Build reusable test collections and define measures of effectiveness.
- A test collection can then be reused many times to compare different systems

# TREC: an Evaluation Initiative
- Encourage research in IR evaluation and compares IR systems

# Effectiveness Measures for Retrieval Sets
- The two main effectiveness measures of IR are **Precision** and **Recall**
## Classification Errors
- **False Positive:**
	- ratio of non-relevant documents that are retrieved
- **False Negative:**
	- ratio of relevant document that are not retrieved
## F1 Score
- It is the **harmonic mean** of recall and precision.

# Focusing on Top Documents
- Users tend to look at only the top part of the ranked result list to find relevant documents
- Hence in this case Recall is not appropriate.

