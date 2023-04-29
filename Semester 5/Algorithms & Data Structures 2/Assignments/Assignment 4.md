*Harkeerat Singh Sawhney & Mak Fazlic*
#assignment

## Exercise 1
## a)
![Excercise 1](Attachment/algorithmAndDatastructureAssignment4.png)
### b)
![Excercise 2](Attachment/algoassignment4b.png)

## Exercise 2
### a)
![Excercise 3](Attachment/algorithmDataStructure4c.png)
### b)
```
max = array of size n containing 0s
OPT(j)
{
	neighbours = array of all the neighbours of j
	for 
	if neighbours == EMPTY:
		return 0
	for n in neighbours:
		temp = OPT(n)
		if temp > max[n]
			max[n] = temp
	return 1 + max[n]		
}
```

We first find all the neighbors of the Vertices which shares an edge with `j` and add them to an array called as `neighbours`. Afterwards, we iterate through the neighbors and do a recursive call on it to find the last Vertex, while updating the max array. By doing this we get the longest path. 

For each vertex we have up to `n` vertices, so the complexity leads to $n^2$. 

### c)
We want to modify the previous pseudo code in such a way, that along with the longest path for the given Vertex, along with that we should return the longest path from Vertex 1 to Vertex N. 

```
max = array of size n containing 0s
v1_is_started = true
longest_path_v1 = 0
OPT(j)
{
	neighbours = array of all the neighbours of j
	if neighbours == EMPTY:
		return 0
	for n in neighbours:
		temp, temp1 = OPT(n)
		if temp > max[n]
			max[n] = temp
			
	if v1_is_started:
		neighbours_v1 = array of all the neighbours of v1
		if neighbours_v1 == EMPTY:
			maxV1 = 0
		else:
			for x in neighbours_v1:
				temp, temp1 = OPT(n)
				if temp1 > maxV1
					maxV1 = temp1
					
	return 1 + max[n], 1 + maxV1	
}
```

In our implementation along with calculating the maximum distance for Vertex J, we simultaneously calculate it for the Vertex 1 as well and return 2 answers as asked.

