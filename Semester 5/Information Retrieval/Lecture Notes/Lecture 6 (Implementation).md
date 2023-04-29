#lectureNote
# Document Indexing
- How do we detect noise?
- How can we distinguish it from content?
- **Several Techniques proposed:**
	- **Finding Content Blocks:**
		- *Cumulative Distribution:*
			- Make a cumulative distribution of tags in the example web page
			- Main text content of the page corresponds to the ***plateau*** in the middle of the distribution.
		- *Document Object Model (DOM):*
			- Another approach uses the Document Object Model structure and visual (layout) features. If available
- **Document:** Anything which one may search for, which contains information in different media (text, image, ...)
- **Text Document:** Description in a natural language
- **Indexing:** Convert documents to data structures to enable fast search (pre-computing as much as we can)
- **Inverted Index:** It is the dominating indexing method for supporting basic search algorithms. However before that the documents needs to be *prepossessed*.

# Processing Text
- **Converting** *words* in **documents** to the *index* terms
- Why?
	- Matching the exact string of characters typed by the user is too restrictive
	- Not all words are of equal value in a search
	- Sometimes not clear where words begin and end.
## Text Statistics
- Huge variety of words used in text but many statistical characteristics of word occurrences are predictable.
- Retrieval models and ranking algorithms depend heavily on statistical properties of words.
### Zipf's Law:
- Distribution of words frequencies is very *skewed*.
- **Zipf's Law:**
	- The *rank (r)* of a word times its *frequency (f)* is approximately a *constant (k)*
		- Assuming words are ranked in order of decreasing frequency
		- Probability of Occurrences by Rank (Graph)

# Text Indexing
- Steps:
	- **Tokenization**
	- **Stopword Removal**
	- **Stemming**
	- **Part of Speech (POS) tagging and a contiguous sequence of N items from a given sample of POS (N-Grams)**
	- **Build Inverted Index**

## Tokenizing
- **Tokenizing** = Breaking down words in appropriate sequences of characters.
- **Examples:**
	- *Bigcorp's 2007 bi-annual report showed profits rose 10%*
	- *bigcorp 2007 annual report showed profits rose*
- Small decisions in tokenizing can have major impact on effectiveness of some queries.
### Tokenizing Process:
- Use **parser to identify** appropriate parts of document to **tokenize**.
	- Identify title, author, important sections, etc.
	- Index every word is any sequence of alphanumeric characters, terminated by a space or special character, with everything converted to lower-case.

## Stopping
- Function words have little meaning on their own
	- to, an , a, the, and, or , not ,by, off, with, ...
	- Recognizable because they have high occurrence frequencies
- They are treated as **stopwords** (i.e. removed)
	- reduce index space, improve response time, improve effectiveness
- Stopword list can be **created from high-frequency words** or based on a standard list.
	- High Frequency part from Zipf's Law
- Best policy to index all the words in documents and then make the decision.

## Stemming
- Many morphological variations of words
	- **inflectional** (plurals, tenses)
	- **derivational** (making verbs nouns etc.)
- In most cases, these have the same or very similar meanings
- Stemmers attempt to reduce morphological variations of words to a common stem.
	- Usually involves **removing** suffixes
	- Generally a **small** but **significant** **effectiveness** **improvement**
- **Approaches:**
	- **Algorithmic:** uses program to determine related words
		- *suffix-s* remove 's' endings assuming plural or third person in verb
		- produces stems not words
		- *Example:* Porter Stemmer
	- **Dictionary-based:** uses list of related words
		- remove endings based on a dictionary
			- produce real words, not stems
			- Much more precise, but expensive to run
		- *Example:* Krovetz Stemmer

## POS tagging and N-grams
- **Part-Of-Speech (POS)** **tagging** is the process of marking up a word in a text as corresponding to a particular part of speech, based on both its definition and its context.
- POS taggers use statistical models of text to predict syntactic tags of words
- It is the most accurate approach to identify the role of a word in text, but is also the most **expensive**.
### Word N-Grams:
- POS tagging is too slow for large collections
- Phrases can be defined as simple noun groups
- **Definition:** Phrase is any sequence of n words known as n-grams
- N-grams typically formed from overlapping sequences of words
- Follows the Zipf's distribution

## Build Inverted Index
- Dictionary: Modest Size
	- Needs fast random access
	- Preferred to be in memory
- Postings: Huge
	- Sequential access is expected
- **Constructing Inverted Index:**
	- Main difficulty is to build such a huge index with limited memory
	- Memory-based methods: not usable for large collections
-   Step I: collect local tuples (termID, docID, freq)
-   Step 2: sort local tuples (to make "runs")
-   Step 3: pair-wise merge runs
-   Step 4: Output inverted file

# Efficiency Improvement
- **Caching**
- Keep only the most promising accumulators
- Need parallel processing