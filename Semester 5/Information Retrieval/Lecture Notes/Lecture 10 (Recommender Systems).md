#lectureNote
- Push Mode (**Recommender Systems**)
	- System Takes initiative
	- Stable Information need or system has good knowledge about a user's need
- Two types of **Recommender Systems**:
	- *Filtering*
	- *Routing*
## Information Filtering vs Information Retrieval
- **Information Filtering** deals with dynamic collections, and generates long and elaborated profiles and filter. It also serves long term information needs
- **Information Retrieval** Deals with static collections. In this case it serves short-lived queries.
## Information Filtering vs Routing
- **Information Filtering** chooses documents to show based on a binary decision.
- **Routing** relies on ranking in order to determine the best results. 

# Information Filtering
- 3 Main types of Information Filtering:
	- **Content-Based IF
	- **Collaborative (or social) IF**
	- **Use-Based IF**
## Content-Based Filtering (CB)
- Makes filtering decisions for an individual user based on what we learned the user likes and dislikes.
- Infers individual's interest/preferences from user feedback on past actions.
- **General Idea:**
	- Given a user *u*
	- Predict *u's* preferences based on previous item preferences expressed by the user.
	- Preference can be based on the similarity between items.
- **Problems
	- *Filtering Decision (Binary Classifier)*
	- *Initialization*
		- Initialize the filter based on only the profile text or very few examples.
	- *Learning from Limited Relevance Judgments*
## Collaborative Filtering (CF)
- Makes filtering decisions for an individual based on the judgments of other users.
- Predicts users preferences based on the preferences of other users.
- CF is based on the user profiles comparison.
- The aim is to recommend/suggest documents (items) to users who share similar tastes.
- **Assumptions:**
	- User with the same interest will have similar preferences
	- Users with similar preferences probably share the same interest.
	- Sufficiently large number of user preferences needs to be available (if not, there will be a cold start problem)
- **Improvements:**
	- *Dealing with missing values.*
	- *Inverse User Frequency (IUF)*
- **Problems**
	- *Size of Data*
		- Need large group of users
		- Need relatively large number of rating/purchases
	- *Cold Start*
## Use-Based IF
- **Mission Statement:**
	- Identifies documents that semantically relevant to a user interest profile by inferring relevant documents from user actions.
- System tracks user's behavior
- **Problems:**
	- Profiles can be very messy
	- Intrusive
