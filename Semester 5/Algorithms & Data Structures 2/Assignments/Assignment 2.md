*Harkeerat Singh Sawhney & Mak Fazlic*
#assignment
## Exercise 1:

```
Modified_Interval_Search_Tree (T, i):
	x = T.root
	while x != T.nil
		if i does not overlap x.int
			if x.left != T.nil and x.left.max > i.low
				x = x.left
			else x = x.right
		else if x != T.nil and i does overlap x.int
			if minoverlap > x 
				minoverlap = x
	return minoverlap
			 
```
The modification which needs to be done to the normal Interval Search tree, is that instead of quitting the loop after finding an overlap, we keep track of the minimum low endpoint. Hence, once the loop terminated the overlap which is stored would be returned. This is the difference between normal Interval Search Tree and the modified one.

## Exercise 2:
```
BST(S)
	if S = 0
		return NULL
	y = median of S
	L = endpoints p <= y
	R = endpoints p >= y
	t = new IntervalTreeNode(y)
	t.left = BST(L)
	t.right = BST(R)
	return t		

PrimaryTree(S)
	Sy = Sorting of all endpoints of all segments in S according to y-coordinate
	T = BST(Sy)             // Creation of the Tree
	return T

Preprocess(S)
	T = PrimaryTree(S)     // Construction of the Sweep Line Status T

	for i = 1 to numberOfRectangle
		insert(left_edges(i), Q)       // adding edges to event Q
		insert(right edges(i), Q)
	

RectangleIntersections(S)
	Preeprocess(S)       // Creating the Interval Tree for the y coordinates
	

	while (Q =! NULL)
		Q = Q.next()     // Q = (x_i, y_iL, y_iR, t)
		if (t = left)
			QueryInterval(y_iL, y_iR, T.root())
			InsertInterval(y_iL, y_iR, T.root())
		else
			DeleteInterval(y_iL, y_iR, T.root())
		
```

**`RectangeIntersections(S)`**:
   This method takes in the set of the rectangle and then returns the intersected rectangle pairs. It first calls the `Preeprocess` which creates the Interval Tree we can be used to find the intersections.
**`Preprocess(S)`**:
  It takes in the set of rectangles (S) and then outputs the basic structure of the interval tree T and the event queue Q.
**`PrimaryTree(S)`**:
  It takes set of rectangles (S) and then returns the basic structure of the interval tree T. It also takes the endpoints of all the segments and sorts it all. 
**`BST(S)`**:
  It makes the initial interval tree with the list of Sy and creates a binary search tree in it.



## Citation
- Answer to the **Question 14.3-7** in Textbook
- https://cw.fel.cvut.cz/b201/_media/courses/cg/lectures/09-intersect.pdf