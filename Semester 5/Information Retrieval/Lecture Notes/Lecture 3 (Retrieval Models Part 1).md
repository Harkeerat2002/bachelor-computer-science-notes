#lectureNote
# Retrieval Models
- Retrieval Process is based on a *retrieval model* that matches a query with a document.
- There are at least **two classes of retrieval models**:
	- **Set-Based Models:**
		- Boolean Model
	- **Similarity-Based Models / Ranked Retrieval**
		- Vector Space Model
		- Probabilistic Model
		- Language Model
		- Topic Model
		- ...

## Boolean Model
- Two possible outcomes for query processing.
	- 0 or 1, or better TRUE and FALSE
- **Advantages:**
	- Results are predictable, relatively easy to explain
	- Many different features can also be incorporated.
	- Efficient Processing since many documents can be eliminated from search
- **Disadvantages:**
	- Effectiveness depends entirely on user
	- Simple queries usually do not work well
	- Complex queries are difficult to think and write.

# Ranked Retrieval
- Is a lot better as documents are presented according to how much they match the query.
- **Ranking Function:** A good ranking function should rank relevant documents on top of non-relevant ones.
- **Relevance:**
	- Models **differ** based on the definition of relevance.
	- Relevance = Similarity
- **Key Challenge:** How to estimate the likelihood that document d is *relevant* to query q.

## Different Ranked Retrieval Models
- **Similarity-Based Model:**
	- Vector Space Model
- **Probabilistic Model:**
	- Classic Probabilistic Model
	- Language Model
	- Topic Model
- **Probabilistic Inference Model:**
- **Axiomatic Model:**
## Common Ideas of Ranked Retrieval Models:
![[Screenshot_20220926_150856.png|500]]


## Vector Space Model (VSM):
- A simple yet effective method of designing ranking functions for information retrieval.
- In this model, documents and queries are assumed to be **part of a t-dimensional vector** space, where **t** is the number **index terms**.
- VS model is a **framework**.
- In this framework, we make some **assumptions** that we represent each document and query by a term **vector**.
- Each term defines one dimension. N terms define an **N-dimensional space**.
- **What VSM does not say:**
	- How to define/select the *basic concept*
	- How to place docs and query in the space
		- Term weight in query indicates importance of term
		- Term weight in docs indicates how well the term characterizes the doc
		- What is the best way to calculate them

### Simplest VSM:
- We consider only the **presence/absence** of a term.
- **Problems of the Simplest VSM:**
	![[Screenshot_20221024_150339.png]]
### Term Frequency Vector (TF):
- Term frequency is a measure that denotes how frequently the term *t* appears in the document *d*.
- **Example:**
		![[Screenshot_20221024_150704.png|450]]
- **Problem with TF:**
	- It cannot identify important term, hence as seen in above example the value of presidential is more, but about also has the same importance.
### Inverse Document Frequency (IDF)
- Improvement to Term Frequency Vector
- It is same as TF but **penalized** popular terms.
- **Example**
	- ![[Pasted image 20221024151307.png|450]]
	- ![[Screenshot_20221024_151324.png|450]]
- **Problem with VSM with TF-IDF:**
	- As it can be seen in the example, the value is very high. Since a document could have a very high frequency of the words it can easily cheat the system and get high value.

### TF Transformation:
- To solve the problem with VSM with TF-IDF, TF Transformation is implemented.
- Sub linear TF Transformation is needed to
	- Captures the intuition of diminishing return from higher TF
	- Avoids dominance by one single term over all other.
- **Transformation** is needed that:
	- Has an upper bound
	- Is robust and effective
# Document Length Normalization
- **Penalize** a long document with a document length normalizer.
- A document is long because:
	- It has more words -> **more** penalization.
	- It has more contents -> **less** penalization.
- **Pivoted Length Normalization:**
	- average doc length as *pivot*.
