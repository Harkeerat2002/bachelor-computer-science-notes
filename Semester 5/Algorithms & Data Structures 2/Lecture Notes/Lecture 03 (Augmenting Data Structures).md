- **Rare** to **create** **completely** new data structures
- Often: Augment a standard data structure.
	- Store additional Information
	- Create additional operations
	- The added information must be **updated** and maintained without loss of efficiency.
# Augmenting Red Black Trees
- Two Examples:
	- **Order Statistics on a dynamic set**
		- find $i^{th}$ **smallest element**
		- find **rank** of given element
	- **Maintaining a dynamic set of intervals**
		- given a query interval find an interval in the set that overlaps it.
- ## Red-Black Trees
	- In a Red Black tree the height of the tree remains always $O(log \space n)$
	- All operations take $O(log \space n)$ time
	- Insertion, deletion perform rotations to maintain RB properties.
	- ### Dynamic Order Statistics
		- Given a **dynamic** set of elements, determine the element with $i^{th}$ **smallest** key
		- ![[Pasted image 20230115143835.png|625]]
		- Supports the following Dynamic-Set Operations from R-B trees plus extra bellow:
			- **OS-SELECT(x, i):** Return pointer to node containing the **ith smallest** key of the sub tree rooted at x.(return the node of rank i).
			- **OS-RANK(T, x):** return the rank of x in the linear order of the set determines by in-order walk of T.
		- #### Order Statistic Tree
			- Red Black tree with **extra info:**
				- x.key
				- x.color
				- x.left, x.right, x.p
				- **x.size**
			- **x.size = x.left.size + x.right.size + 1**
			- ![[Pasted image 20230115144644.png|675]]
		- #### Maintaining the Size
			- **Phase 1:** Go down the tree inserting new node as child of existing node.
			- **Phase 3:** Go up tree performing rotations to maintain RB properties.
		- **Complexity:** O(log n)
- ## Interval Trees
	- Augment Red Black Trees to support operations on a **dynamic set of intervals**.
	- Two intervals i and i' do not overlap iff
		- **i.high < i'low** or **i'.high < i.low**
	- Support the following operations:
		- **Interval-Insert (T, x):** adds x to T (x.int)
		- **Interval-Delete(T, x)**
		- **Interval-Search(T, i):** Returns a pointer to an interval x in T such that **x.int overlaps i**; returns nil if no such elements exists.

# Pseudo Code
```
OS-SELECT(x, i)
	r = x.left.size + 1     // r = rank of node x
	if i == r
		return x
	elseif i < r
		return OS-SELECT(x.left, i)
	else return OS-SELECT(x.right, i - r)	
```

```
OS-RANK(T, x)
	r = x.left.size + 1
	y = x
	while y != T.root
		if y == y.p.right  // y is a right child
			r = r + y.p.left.size + 1
		y = y.p
	return r
```
