#lectureNote
#  Feedback Modules
- Users make explicit relevance judgments on the initial results (judgments are reliable, but users don't want to make extra effort).
- **Three major form of feedback:**
	1. **Relevance:** User indicate expressively documents that are relevant to the query
	2. **Pseudo:** System assumes the top retrieved documents are relevant
	3. **Implicit:** System Monitors what the user does and based on that makes some assumptions on document relevance
- These are used in different scenarios and applications:
## Relevance Feedback
- **User makes explicit relevance judgments** on the system results.

## Pseudo/Blind/Automatic Feedback
- Top-k initial results are simply **assumed to be relevant**

## Implicit Feedback
- **User-clicked docs are assumed to be relevant:** skipped those non-relevant (judgments are not completely reliable)

# Feedback in Vector Space Model
- How can a TR system learn from examples to improve retrieval accuracy?
	- **Positive Examples:** docs known to be relevant
	- **Negative Examples:** docs known to be non-relevant
- General Method: **Query Modification**
	- **Adding new (weighted) term** (query expansion)
	- **Adjusting weights** of old terms
## Rocchio Feedback
 ![[Screenshot_20221025_140305.png|600]]
- You want to move the query vector as close to the relevant documents and far away from non-relevant documents.
- **Rocchio in Practice:**
	- **Negative (non-relevant)** examples are not very and import and rarely used. 
		1. Negative Documents tend to distract the query in all directions. Positive Documents tends to be clustered together
		2. Avoid **over-fitting** (keep relatively high weight on the original query), since the sample is already very small, and those terms are typed in by users (user decided that they are important)
	- This can be **used for relevance feedback and pseudo feedback** as well. The **β** should be set to a **larger** value for relevance feedback than for pseudo feedback.
	- Usually Robust and effective