#lectureNote
# Pull vs Push
- **Pull Mode (search engines):**
	- User initiates the access process to find the relevant text data, typically by using a search engine.
	- Usually needed when the user needs an ad hoc information i.e., a temporary information needed that might disappear once the need is satisfied.
	- Has two types **querying** and **browsing**.
- **Push Mode (recommender systems):**
	- System initiates the process to recommend a set of relevant information items to the user.
	- This mode of information access is more useful when satisfying a long standing information need of a user or analyst.
	- Stable information is needed or system has good knowledge about a user's need.
- **Pull vs. Push: an Analogy**
	1. **Pull:** consumer enters in shop and ask for a specific product:
		- Product is *pulled* to the customer
	2. **Push:** consumer receives the advertisement of a product and decides to buy it.
		- Product is *pushed* to the customer via the advertisement system to which customer must subscribe (and might decide at some point to unsubscribe)
# Querying vs Browsing
- **Querying:**
	- User enters (keyword) query, system returns relevant documents.
	- Works well when users know what keywords to use to specify what they want.
- **Browsing:**
	- User navigate into relevant information by following a path enabled by the structures imposed on documents.
	- Works well when users want to explore information, do not know what keywords to use, and/or cannot easily enter a query.
- **Query vs Browsing:**
	- Sightseeing: do you know address of an attraction?
		- Yes (**querying**): take a taxi and go directly to the site
		- No (**browsing**): walk around or take a taxi to a nearby place then walk
	- Information seeking: do you know exactly what you want to find?
		- Yes (**querying**): use the right keywords as a query and find the information directly
		- No (**browsing**): browse the information space or start with a rough query and then browse

# Browsing Traces
- Browsing leaves a trace that can be used to **model** the user behavior.
- A browser travel is a **log** of each action conducted by a website page.
- This includes the request for information and the time it takes for each request to complete.
- **Examples:**
	- Search for *Lugano* and reach the page of the university; which pages did you go through:

# Search Engine Architecture
- A **software architecture** consists of software components, the interface provided by those components, and the relationships between them.
- The software architecture of a search engine is determined by two requirements
	- **Effectiveness** (quality of results)
	- **Efficiency** (response time and throughput)

# The Full IR Process
![[Screenshot_20221024_133904.png|500]]

# The IR Sub-Processes
- **Indexing Process**
- **Query Process**
- **Retrieval Process**
- **The Relevance Feedback Process**

## Indexing Process
- **Text Acquisition**
	- Identifies and stores documents for indexing
- **Text Transformation**
	- Transforms documents into *index* terms or *features*
- **Index Creating**
	- Takes index terms and creates data structures (*indexes*) to support fast searching.

## Query and Retrieval Process
- **User interaction**
	- Supports creating of query, display of results
- **Ranking and Retrieval**
	- Uses query and indexes to generate ranked list of documents
- **Evaluation**
	- Monitors and measures effectiveness and efficiency

## Relevance Feedback Process
- **User Evaluation**
	- User assesses the effectiveness of system
- **User Feedback**
	- Supports refinement of query, display of results
- **Ranking and Retrieval**
	- System regenerates ranked list of documents

# IR (Information Retrieval)
- There are several **reasons why IR is difficult**:
	- **Under-specified:** A **query** is usually quite short **and** incomplete
	- **Ambiguous:** The information needed may be difficult to **describe** **precisely**, especially when the user isn't familiar with the topics.
	- **Fact Search:** Precise understanding of the document content is difficult.
	- **Scaling**: The internet is very big.
## Formal Formulation of IR
![[Pasted image 20220926144416.png|600]]

## TR vs Database Retrieval
- **Information:**
	- Unstructured/Free Text *vs* Structured data
	- Ambiguous *vs* Well-defined Semantics
- **Query:**
	- Ambiguous *vs* Well-Defined Semantics
	- Incomplete *vs* Complete Specification
- **Answers:**
	- Relevant Documents *vs* Matched Records

## Document Selection vs. Document Ranking
- **Document Selection:**
	- Implementation of a *binary classifier* to classify a document as either relevant of non-relevant with respect to a particular query.
	- Also known as Boolean Retrieval
- **Document Ranking:**
	- Implementation a ranking function to rank all the documents in descending values. 
	- System only needs to decide if one doc is more likely relevant than another.
	- User would then browse the ranked list and stop whenever they consider it appropriate.
	- Also known as Ranked Retrieval
- **Problems of Document Selection:**
	- The classifier is not going to be very accurate.
	- Even if it is accurate, all relevant documents are not equally relevant.
	- Ranking is generally preferred.
- **Justification for Document Ranking**
	- The utility of a document to a user is independent of the utility of any other document.
	- A user will browse the results sequentially. 

