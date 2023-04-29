#lectureNote
# Convex Hulls
- **Convex Set:** For every two points in the set, the line segment joining them is also in the set.
- **Smallest:** It means the common intersection of all convex shapes enclosing the given set of points.
	- Rubber band around points
- ## Developing an Algorithms
	- **Property:** Vertices of convex hull are **input points.**
	- **Property:** The supporting line of any convex hull edge has all input points on one side.
	- ### Inefficient Algorithm:
		- ![[Screenshot_20230117_165636.png|325]]
		- **Description:**
			- For each pair of points construct its connecting segment and *supporting line*.
			- Find all the segments whose supporting lines divide the plane into two halves, such that one half plane contains *all* the other points.
			- Construct the convex hull out of these segments.
		- **Time Complexity:**
			- $O(n^3)$
- ## Convex Hull: Properties
	- Point $p_0$ (bottom-most point) **must** be on the convex hull.
	- As we walk from $p_0$ and counterclockwise on the convex hull, **every turn must be a left turn.**
	- Leftmost and Rightmost points **must** be on the hull.
	- Upper Hull and Lower Hull (Compute Both)
- ## Orientations
	- Given an ordered triple of points <p, q, r> in the plane, we say that they have *positive orientation* if they define a **counterclockwise** oriented triangle, *negative orientation* if they define a **clockwise** oriented triangle, and *zero orientations* if they are **col linear**.
	- ![[Screenshot_20230117_171218.png]]
- ## Algorithms
	- ### **Graham's Scan**
		- ![[Screenshot_20230118_142217.png]]
		- **YouTube Link:** https://www.youtube.com/watch?v=SBdWdT_5isI&t=203s
		- **Two Implementations of Graham's Scan:**
			- *Simple:* Sort by x-coordinate
			- *Original:* Sort points with respect to polar angle from that point
		- **Pseudo Code (Sort by x-coordinate)**
			1. Sort the points according to increasing order of their x-coordinates, denoted $p_1, p_2, .... , p_n$.
			2. Push $p_1$ and then $p_2$ onto S
			3. for $i \leftarrow 3, ..., n$ do:
				- while ($|S| \ge$ and Orient ($p_i$, $S[top]$, $S[top - 1]$ ) $\le 0$) pop S
				- push $p_i$ onto S
		- **Complexity:** $O(n log \space n)$ 
	- ### **Divide and Conquer**
	- ### **Jarvis March / Gift Wrapping**
	- ### **Quick Hull**
		- **Best Case:** Split as evenly as possible
			- *Time Complexity:* $n log(n)$ 
		- **Worst Case:** Split as unevenly as possible
			- *Time Complexity:* $nh = n^2$ 
	