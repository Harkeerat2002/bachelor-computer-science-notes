*Harkeerat Singh Sawhney* & *Mak Fazlic*
#assignment
# Exercise 2:
*Kruskal's Algorithm* is an algorithm which is used to find the minimum spanning tree for a connected weighted graph. It takes a graph as an input and then finds its subsets of the edges of that graph which could form a tree that includes every vertex, and also has the minimum sum of the weights among all the tress that can be formed from the graph. 

Kruskal’s Algorithm, are part of *greedy algorithms* in which they tend to find the local optimum in the hopes of finding the global optimum. In  Kruskal’s Algorithm the following steps takes place:
 1. Sort the edges by the ascending edge weight
 2. Walk through the sorted edges and look at the two nodes the edge belongs to, if the nodes already unified we don't include this edge, otherwise we include it and unify the nodes.
 3. The algorithm terminates when every edge has been processed or all the vertices have been unified.

As it can be seen while implementing the  Kruskal’s Algorithm, all the edges which are using subsets are kept in track. This is why in this case Union-Find is needed. Each of the edges are stored as a set containing the two vertices in which each of this contains sets of elements. Then with Disjoint Set Data structure it keeps track of all these sets and makes sure every set is unique. Now when it comes to the complexity of Kruskal’s Algorithm with and without Union-Find. When considering the time complexity of Kruskal’s Algorithm without Union-Find we need to consider the following functions:
  - Make_subset function
  - Find Function
  - Union Function
Time Complexity of the make-set function is a fairly simple function which tends to create a subset of every vertex on the edge of the graph. Hence, the time complexity is **O(V)** where V is all the vertices. The Time complexity of the Find Function would be **O(V^2)**. Also we need to consider the algorithm such as merge sort which is **O(E(log(E)))** where E is the number of edges. Therefore the complexity would be **O(V^2)** without Union-Find implementation.

Now consider the time complexity of the Kruskal’s Algorithm with Union Find we would have to consider the following:
  - Sorting edges using the merge sort = **O(E(log(E)))**.
  - The function make_set = **O(V)**
  - The improved function of *union* and *find*= **O(E(log(E)))**
  - 
Hence in this case the time complexity would be **O(E(log(E)))**. As it can be seen Union-Find Improves the time complexity for *union* and *find*.
