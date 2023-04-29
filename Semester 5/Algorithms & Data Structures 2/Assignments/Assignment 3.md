*Harkeerat Singh Sawhney & Mak Fazlic*
#assignment

## Exercise 1
In order to compute the convex layers of P in $O(n^2)$ time, we must find an implementation of Convex Hull, which is less than $n^2$. We can consider the following 2 implementations of the Convex Hull, which is Jarvis's Algorithm and Graham's Algorithm. Since Jarvis's Algorithm has the complexity of $O(n^2)$ we would not be able to consider it. However, the complexity for Graham's Algorithm is $O(n Log n)$ time. 

The problem which we have with the Graham's Algorithm is the way it sorts its point. It sorts its points by finding by the angle, and because of this for our implementation every time when we calculate the Convex Hull, we would again need to sort all the points. This would cause an increase in the complexity, by a lot. 

Therefore, we would want to sort it on the x-coordinate instead of an angle. This would be done by computing the hull in two steps, by producing the upper and lower parts of the hull. This modification to the Graham's Algorithm is also known as the Andrew's Monotone Chain Algorithm. This algorithm first sorts the points by the x-coordinate (which is the reason we are using this). It then constructs the upper hull and the lower hull, and then combines it together. Bellow is the visual implementation of this algorithm:
![[Pasted image 20221107223532.png]]

Hence the following would the approach which would be used to solve this problem of ours. 

**Theory of the Pseudo Code:**
1. Sort the points according to increasing order of their x-coordinates, denoted $<p1, p2, .... pn>$ (in case of a tie, sort by y-coordinate).
2. *U* and *L* are empty list both representing the vertices of the upper and lower hulls respectively.
3. An initial While loop, in which until **P** (points) does not become empty it would keep on iterating through with Step 4, 5, 6 and 7.
4. **Calculation of the Lower Hull:** Iterating through the *points* $(1, 2, .... , n)$ and having a while condition in which if L (Lower Hull) is not containing at least 2 points and the sequence of the last the 2 points of L and the point $p_i$ does not make a counter-clockwise turn then the last point of L should be removed. *Otherwise* if the while condition is satisfied and is exited from the loop, then append $p_i$ to the L and **remove** $pi$.
5. **Calculation of the Upper Hull:** It is the same concept as the Lower Hull, but instead we would be iterating through $(n, n-1, ......, 1)$. 
6. Once we have gotten the *U* and *L* then we remove the last point of each list since it would be the same for both the lists. We then join L and U together, in which we would obtain the convex hull of this iteration and is stored separately.
7. U and L both would be equated to empty list. Then until the ***condition 2*** is satisfied.
8. Return all the Convex Hulls for each iteration.

**Pseudo Code (From above explanation):**
```
Modified_Graham_Algorithm(Input):
	P = Input // A list of P of point in the plane
	P_Sorted = Sort the points of P by x-coordinate in linear time

	U = [] // Empty List of Upper Hulls
	L = [] // Empty List of Lower Hulls
	while ( P_Sort != EMPTY):
		for i in range n:
			While (L is containing at least 2 points and its sequence
			of L and the point P[i] is not making a counter-clockwise turn)
				L.lastPoint.Remove // Removing the last element of L
			L += P[i]
			P[i].remove
		for i in [n, n-1, ...., 1]:
			While (U is containing at least 2 points and its sequence
			of U and the point P[i] is not making a counter-clockwise turn)
				U.lastPoint.Remove // Removing the last element of U
			U += P[i]
			P[i].remove
		Convex_Hull_Iteration = L + U
		U & L = []
```

**Complexity Analysis:**
The complexity for this would be $O(n^2)$ since the main complex part for this Graham's Algorithm is the sorting part which is $O(n)$. From their onward each iteration would then make the total complexity $O(n^2)$. 

## Exercise 2
**A):**
The way this algorithm can be implemented is that since we know the vertices are sorted, we can check that with a node, the following two nodes are rotated correctly or not. If the turn is wrong, then we can remove that vertices and the calculation for that specific vertices could be redone. In this case the complexity would be $O(n)$ since the sorting part is already done which is usually the part which takes has the longest complexity in the algorithm.  

**B):**
This algorithm is not a contradiction to the theorem on the lower bound of the convex hull computation time complexity, since as already mentioned before the vertices are already sorted. Hence due to this we are able to obtain the complexity of $O(n)$ since they the part which is the sorting is the most expensive section of the algorithm.
