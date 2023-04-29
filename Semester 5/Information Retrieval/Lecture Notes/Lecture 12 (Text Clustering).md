#lectureNote
- Text Clustering is used in order to group similar objects together by discovering their natural structure.
## The Clustering Bias
- Any two objects can be similar, depending on how you look at them
- A user must define the perspective for assessing similarity.

# Clustering in Text Retrieval
- Text Clustering is useful for text mining and exploratory text analysis.
- **Different Utilization:**
	- Link Text Objects
	- Create a Structure on the Text Data
- Clusters can be created based on *concepts, topics or themes* It can be divided into two main categories.
	- **Similarity-Based Clustering**
	- **Model-Based Clustering**
## Similarity Based Clustering
- Explicitly define a similarity function to measure similarity between two text objects (by providing *clustering bias*).
- Find an optimal partitioning of data to **maximize intro group similarity** and **minimize inter-group similarity**.
- Two Strategies for obtaining optimal clustering:
	- Progressively construct a hierarchy of clusters **(*Hierarchical Clustering*)**
		- Bottom-Up
		- Top-Down
	- Start with an initial tentative clustering and iteratively improve it **(K-means)**.
- Two Representative Methods:
	- **Hierarchical Agglomerative Clustering (HAC)**
	- **K-means**
- They require a similarity function that is:
	- Symmetric
	- Normalized
### Agglomerative Hierarchical Clustering
- Simple Algorithm
	- Assume a similarity function to measure similarity between two objects
	- Gradually Group similar objects together in a bottom-up fashion form a hierarchy
	- Stop when some stopping criterion is met.
- Agglomeration Hierarchical Clustering (Small Groups to Bigger Groups)
- Divisive Hierarchical Clustering (Big Groups to Smaller Groups)
#### Clustering Strategies
- **Single Link:**
	- Creates *loose clusters*
- **Complete Link:**
	- Creates *tight clusters*
- **Average Link:**
	- Creates clusters *in between* the above two

## K-Means Clustering
- 