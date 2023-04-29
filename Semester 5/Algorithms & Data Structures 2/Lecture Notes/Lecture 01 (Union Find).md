#lectureNote
## Data Structures for Disjoint Sets:
- Problem in a wide range of applications
- Two Operations:
	- **Find**:
		- The unique set that contains a given element
	- **Unite**:
		- Two sets into one.

## Disjoint Sets (Union-Find):
- Maintain a collection of **disjoint dynamic sets** 
	- ${S_1, S_2, ...., S_k }$. 
- Each set is identified by a **representative**
	- **representative**: *one member* of the set
	- it does not matter which, as long as:
		- If we ask for the set representative twice (without modifying the set), we get the same answer both times

## Example of Union-Find:
![[Pasted image 20230105181425.png|500]]
- For graph G=(V, E), two vertices are in the same connected component if there is a path between them
- **Problem:** Compute the connected components of G
- Use Union-Find
	- Place **each vertex of the graph in its own set**
	- For **each edge (u, v)**, unite the sets containing u, v
	- After processing all edges, **two vertices are in the same connected component iff the corresponding objects are in the same set.**

## Operations (Union-Find):
- **Make-Set(x)**: 
	- Creates a new set whose only element is x
	- Complexity *O(1)*
- **Union(x, y):** 
	- Unites the sets that contain x and y into a new set that is the union of $S_x \cup S_y$
		- representative: any member of $S_x \cup S_y$
		- destroy the two original sets or better absorb the one set into the other
- **Find-Set(x):** Returns a point to the representative of the unique set of containing x.
	- - Complexity *O(1)*

### Weighted Union Heuristic:
- Always **append** the **shorter list onto the longer**.
- A **sequence** of m operations on n elements takes **O(m+nlogn n)** time.
- On *average*, this Union operations will take **O(log n)** time
- *Worst Case* of one Union Operations is **O(n)**.
- **Theorem:** With weighted union, a sequence of m operations on n elements takes O(m + n log n) time.

# Disjoint Set Forests
- Set Represented as a rooted tree
	- Each tree represents a set
	- **Each node points only to its parent**
	- **Root is** the set **representative**
## Union-Find Operations
- **Make-Set:**
	- Creates a tree with just one node
- **Find-Set:**
	- Follow parent pointers all the way to the root
	- Nodes visited on this path to root constitute the find-path
	- Time: O(height of tree)
- **Union:**
	- Make the root of one tree point to the root of the other
		- fast after find-set

### Union by Rank
- Make the root of the shorter tree point to the root of the taller tree
	- ![[Screenshot_20230109_155825.png|475]]
### Path Compression
- Simple and VERY effective
- Every time you perform a **Find-Set** make **every node visited** on the find-path **point directly to the root**.
	- ![[Screenshot_20230109_155936.png]]

### Run Time
- Worst case cost per operation is still **O(log n)**