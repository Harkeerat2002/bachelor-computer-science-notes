#lectureNote
# Probabilistic Retrieval Models
- Estimating the probability of relevance.
- **Query Likelihood:** if a user likes document d, how likely would the user enter query q ( in order to retrieve d).

# Query Likelihood Retrieval Model
- **Assumption:** a user formulates a query based on an "imaginary relevant document"
- **Formula**: *p(q|d)* 

# Statistical  Language Model (LM)
- A probability distribution over word sequences
- Context-dependent
- Can also be regarded as **probabilistic mechanism** for generating text, thus also called a **generative model**. 
- **Why is a LM useful?**
	- Quantify the uncertainties in natural language.
	- Discovering word associations.
	- Allows the following possibilities:
		- **Speed Recognition**
		- **Text categorization**
		- **Information Retrieval**
## The Simplest Language Model : Unigram LM
- Generate text by generating each work **independently**.
- **Text** = sample drawn according to this **word distribution**.
- **Example:**
	- ![[Screenshot_20221025_101200.png]]
## Unigram Query Likelihood
- **Assumption:** Each query word is generated independently
- **Problem:**
	- A problem is query could have words which does not come at all in the document. Meaning this would cause the probability to be 0
- **Solution:**
	- How likely would we observe **this query** from **this doc model**.
## Smoothing in LM
- We are assuming that the user will sample a word from the document to formulate the query, and there is no chance of sampling any word that is not in the document.
- Hence we will assign non-zero  probabilities to words that are not observed in the data. This is called **smoothing**.
- Smoothing includes probabilities of unseen words. 
- **How to smooth a LM?**
	- Let the probability of an unseen word be proportional to its probability given by a reference LM.
	- The probability of an unseen word in d is assumed t be proportional to p(w|C)
	- Leads to a general ranking formula for query likelihood which account for TF-IDF weighting and document length normalization.
	- Scoring is primarily based on sum of weights on matched query terms
	- Without smoothing the model would ignore how frequently a term occurs in general. 
- **Two Smoothing Methods:**
	- Jelinek-Mercer: Fixed Coefficient linear interpolation
	- Dirichlet Prior: Adding pseudo counts; adaptive interpolation 
- Effective ranking are function obtained using pure **probabilistic** **modeling** and a few **assumptions**:
	- **Assumption 1:** A user formulates a query based on an *"imaginary relevant document"*
	- **Assumption 2:** Query words are generated independently
	- **Assumption 3:** Smoothing with p(w|C)
	- **Assumption 4:** Uses of JM or Dirichlet prior smoothing