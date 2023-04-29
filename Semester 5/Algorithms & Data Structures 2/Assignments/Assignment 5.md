*Harkeerat Singh Sawhney & Mak Fazlic*
#assignment
## Exercise 1
![[algoAssignmentEx1.excalidraw|650]]
Therefore, as it can be seen from above the maximal *s-t* flow in the network is **21**. The computation is done above.

## Exercise 2

### a)
We should first prove that there exists an s-t cut (A,B), such that the value of f = cap(A, B) and that the f is the max flow. We should show that for all s-t cuts (A, B) and all flows f: $c(A,B) \geq f$ 

We know that flow is the sum of the flow on all edges sticking out of the source minus the sum of the flow on all edges sticking into the source. So therefore f could be rewritten as follows:
$$
|f| = \sum_{e \in E^+(s)}f(e) \space - \sum_{e \in E^-(s)}f(e)
$$
We can now rewrite the sum by looking at all the vertices in A. It should also be considered that A contains the source but not the sink.
$$
|f| = \sum_{e \in E^+(s)}{f(e)}\space - \sum_{e \in E^-(s)}{f(e)} = \sum_{v \in A} \bigg( \sum_{e\in E^{+}(V)} - \sum_{e\in E^{-}(V)} \bigg)
$$
For each vertex in A we sum of the flow leaving the vertex minus the flow entering it. However due the conservation of he flow the term $\sum_{e\in E^{+}(V)} - \sum_{e\in E^{-}(V)}$ is going to be 0 for all vertices except for the source.
![[algoAssignment5Exc2.excalidraw|625]]

As it can be seen from above figure we can have 4 cases for edges. Edges in which both the endpoints are in A. Edges with both endpoints in B. Edges going from B to A, or edges going from A to B. 

Edges with both end points in A (points v and W) will contribute once positively (sticks out of v) and once negatively (sticks into W). Hence this edge will show up twice in the sum, which is once positively and once negatively which cancels out in the end. Edges both endpoints in B (points x and y) would not show up in the sum at all. Edges going from A to B will show up once positively in the sum since the starting point is in A. It will not show up negatively since the end point is in B. Similarly edges going from B to A will show up once negatively sine the end point is in A. 

Hence from this we can derive that edges with both end points in A or with both end points in B  contribute 0 to the sum. Therefore we can rewrite the sum as a sum of all edges sticking out of A minus all edges sticking into A.
$$
|f| = \sum_{e \in E^+(s)}{f(e)}\space - \sum_{e \in E^-(s)}{f(e)} = \sum_{v \in A} \bigg( \sum_{e\in E^{+}(V)} - \sum_{e\in E^{-}(V)} \bigg) = \sum_{e \in E^{+}(A)} f(e) \space - \sum_{E^{-}(A)} f(e) 
$$

It should be noticed that due to the capacity constraints all terms in the left sum is smaller or equal to the edges. Since the flow cannot be negative each term in the right sum is greater of equal to 0.
$$
\sum_{e \in E^{+}(A)} f(e) \space \leq c(e)\space and \sum_{E^{-}(A)} f(e) \geq 0
$$
Therefore, we can rewrite the equation as bellow:
$$
|f| = \sum_{e \in E^+(s)}{f(e)}\space - \sum_{e \in E^-(s)}{f(e)} = \sum_{v \in A} \bigg( \sum_{e\in E^{+}(V)} - \sum_{e\in E^{-}(V)} \bigg) = \sum_{e \in E^{+}(A)} f(e) \space - \sum_{E^{-}(A)} f(e) \leq \sum_{e \in E^{+}(A)} f(e) = \sum_{e \in E^{+}(A)} f(e) = c(A,B)
$$
Hence we have shown that for any flow and any s-t cut the value of the flow is less then or equal to the value of the cut. Therefore it means that it states the max flow of a graph is equal to the minimum cut. 

Now minimum cut corresponds to the sum of capacities of some set of edges in the graph. If one of those edge's capacity is increased (or decreased) by 1 it would also effect the minimum cut by 1 as well. Since we have proved that the minimum cut is equal to maximum flow, it would as well effect the maximum flow by 1 too. Therefore, if the edge lies in the min cut, and it is changed then max flow would be changed by 1 otherwise it would stay the same. Hence proving this statement.  

### b)
We have a max s-t flow f on G, and also a edge with the capacity Ce. The basic premise of the algorithm is to use the max flow min cut theorem (which states that max flow = min cut) to find if the edge E is in the min cut or not. If it is in the min cut, then we increase the value of max flow by 1, otherwise we keep it the same. 

We can accomplish this by making a residual graph on the original in which we increase the capacity of the edge E by 1. By doing a search on this graph (e.g. BFS) we can determine if there is an increase on the maximum flow or not. If there is a path we then return the max s-t flow + 1, otherwise the max s-t flow stays unchanged. The search BFS has complexity O(Edges + Vertices) which is in our case O(m + n). 

### c)
We are using the same initial reasoning as the previous question, in which we see if the edge lies in the min cut or not. In this case we again make a residual graph on the original and see that if the edge E has the capacity or not. If it does has the capacity to decrease (meaning it won't go negative) then we decrease it without effecting the max s-t flow. 

However if there is no capacity for the edge, we instead have to update the max flow. The complexity stays the same, because we use the same search algorithm and the updating of the value of the max flow is constant time. 

