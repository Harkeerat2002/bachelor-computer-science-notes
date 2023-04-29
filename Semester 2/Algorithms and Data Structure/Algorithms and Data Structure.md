#subject
[Semester:: 2]   •   [Year:: 1]   •   [ECT:: 6]• [Completed:: ✅]
# Analyzing an Algorithm

1.  Is the Algorithm _**correct**_?
    1.  _For every valid input, does it terminate?_
    2.  _If so, does it do the right thing?_
2.  How much _**time**_ does it take to complete?
3.  Can we do _**better**_?

# Python Syntax

To _**run**_ a python program in the terminal:

```bash
python3 <file_Name>
```

To _**run**_ a python program in the terminal, but interactive:

```bash
python3 -i <file_Name>
```

_**Sharing**_ Python Code:

```bash
pastebinit -f python -i find_element_distance_1.py -b paste.ubuntu.com
```

## Arrays

It is a sequence of values, that are continuous, which can be accessed by the index or position.

_**Declaring**_ an Array:

```python
A = [1, 2, 3]
```

_**Accessing**_ the first element which is pushed:

```python
A[0]
```

_**Changing**_ the element of the 2nd element:

```python
A[1] = 'another_element'
```

Using a _**variable**_ to access the position of the array:

```python
A[i]
```

## Loops

It means to run a specific program over again and over again, until some condition is satisfied.

_**While loop**_ is a loop which only runs the code, when the condition is satisfied:

```python
while i<6:
    print(A[i])
    i = i + 1
```

There are two Types of _**for loops**_:

_**In-Range**_ which runs the program and keeps on increasing the value of x to a finite number:

```python
for x in range(10):
    print(x)
```

_**Values in the array**_ which runs the program and gets all the values from the array:

```python
A = [1, 2, 3, 4]
for a in A:
	print(x)
```

# Complexity of the Program

We measure the **complexity** of the program, depending on how much **time** it takes. The **size** is measured in **bits**. The complexity of an algorithm is measured in the worst case usually. Bellow is the scale as to how the **difference** between **time complexity**:
$$ 1 < log(n) < \sqrt(n) < n \times log(n) < n^n $$

## Big-O Notation (O):
- Big-O notation specifically describes the worst case scenario.  
- It represents the upper bound running time complexity of an algorithm.
- Mathematical Representation:
	- Let f and g be function of n where n is natural number denoting size of steps of the algorithm then:    
$$ f(n) = O(g(n)) \iff c.g(n) $$

## Big-Omega Notation (Ω):
- Big Omega notations specifically describes best case scenario.
- It represents the lower bound running time complexity of an algorithm.
- Basically it tells you what is the fastest time/behavior in which the algorithm can run.
- Mathematical Representation:
    - Let f and g be function of n where n is natural number denoting size of steps of the algorithm then $f(n) = Ω(g(n)) \iff c.g(n)$
    - 
## Big-Theta Notation (**θ**):
- Big Omega notation specifically describes average case scenario.
- It represents the most realistic time complexity of an algorithm.
- Usually Big θ is used when the worst case and best case of the algorithm are the same.
- Mathematical Representation:
    - Let f and g be functions of where n is natural number denoting size or steps of the algorithm then $f(n) = θ(g(n)) \iff c.g(n)$

# Sorting Algorithms
These are algorithm's which sort the array in ascending or descending order, or just depending on what the question is asking.
## Insertion Sort:

![[insertionSort.png|350]]
The Green values, are the one which is compared to the rest of the red ones. The red ones are the sorted array, while the green value is taken to compare against the sorted array. It takes the next value, and compares it to all the previous ones.

**Code of Insertion Sort:**
```python
# In place: YES
# Worst-case:   \\\\Theta(n^2)
# Average-case: \\\\Theta(n^2)
# Best-case:    \\\\Theta(n)
def insertion_sort(A):
    for i in range(1,len(A)):
        value = A[i]
        j = i
        while j > 0 and A[j - 1] > value:
            A[j] = A[j-1]
            j = j - 1
        A[j] = value
```

## Selection Sort:
It takes the first value, and compares it to the rest of the next values in the array. If there is any value which is smaller the first one then it swaps with it. After that it continues the same procedure with the next one.

**Code of Selection Sort:**
```python
# In place: YES
# Worst-case:   \\\\Theta(n^2)
# Average-case: \\\\Theta(n^2)
# Best-case:    \\\\Theta(n^2)
def selection_sort(A):
    for i in range(len(A)-1):
        for j in range(i+1, len(A)):
            if A[i] > A[j]:
                A[i], A[j] = A[j], A[i]

```

## Bubble Sort:
You start from the last value in the array, and compare to the previous one, until you reach x (part of for loop). If the previous value is greater than you switch. After that the value of x increases by one.

**Code of Bubble Sort:**
```python
# In place: YES
# Worst-case:   \\\\Theta(n^2)
# Average-case: \\\\Theta(n^2)
# Best-case:    \\\\Theta(n^2)
def bubble_sort(A):
    for i in range(len(A)):
        j = len(A) - 1
        while j > i:
            if A[j] < A[j-1]:
                A[j], A[j-1] = A[j-1], A[j]
            j-= 1

```

## Merge Sort:
Divides the array in the two, and separates the as a left and right array. Then keeps on doing it by recursively calling itself so that left and right array has 1 value in it. Then compares left and right array, and puts them in the order, until it merges the whole array back together.

**Code of Merge Sort:**
```python
# In place: NO
# Worst-case:   \\\\Theta(nlogn)
# Average-case: \\\\Theta(nlogn)
# Best-case:    \\\\Theta(nlogn)
import merging_algorithms as m
def MergeSort(A):
    if len(A) == 1:
        return A
    pivot = len(A)//2
    A_left = MergeSort(A[:pivot])
    A_right = MergeSort(A[pivot:])
    return m.merge(A_left, A_right)

```

# Searching Algorithms

## Binary Search:
Takes a sorted array, and then takes the middle point and sees if it is equal, greater or lesser then the given value to find. If it is equal, it would return that value. If it is smaller, than the given value, then it makes the middle point as the end. If it is bigger, then it makes the beginning as middle index.

**Code of Binary Search:**
```python
# Input: sorted sequence
# complexity: nlogn
def binary_search(A,x):
    begin = 0
    end = len(A)
    while begin < end:

        # picks index in the middle
        m = (begin + end) // 2
        if A[m] == x:
            return True
        elif A[m] > x:
            end = m
        else:
            begin = m + 1   # Why '+ 1'
    return False

```

## Linear Search:
Starts from the first value in the array and checks if it is equal to the input array. Very linear, and checks quickly.

**Code of Linear Search:**
```python
# Complexity: n
def linear_search(A,x):
    for i in A:
        if i == x:
            return True
    return False

```

# Elementary Data Structures

## Stack:
- The ubiquitous "_**last-in first-out**_" container (LIFO)
- Push means adding the element to the stack (at top)
- Pop means returning the value at the top of the stack, and removing it as well.

**Code of Stack:**
```python
S = [None]*100                  # "data", fixed-size array where we
                                # store the elements of the stack
N = 0                           # "meta-data"

def push(x):
    # puts element x at the top of the stack, if space permits
    global S,N
    if N < len(S):
        S[N] = x
        N = N + 1
    else:
        print('stack overflow')

def pop():
    global S,N
    if N > 0:
        N = N - 1
        return S[N]
    else:
        print('stack underflow')

def is_empty():
    global S,N
    return N == 0

```

## Queue:
- The ubiquitous "_**first-in first-out**_" container (FIFO)
- Queue could be expressed in a circle. Hence, if the "back" reaches the maximum size of the array, then it overwrites the first the element in the Queue.

**Code of Queue:**
```python
Q = [None]*100   # fixed-size array to store the elements in the queue

Front = 0        # points to the element that is in front of the queue

Back = 0         # points to the first element past the last in the
                 # queue, which is where you would enqueue the next
                 # element

def next(p):
    global Q
    p = p + 1
    if p == len(Q):
        p = 0
    return p

def is_empty():
    global Front, Back
    return Front == Back

def is_full():
    global Front, Back
    return next(Back) == Front

def enqueue(x):
    global Q, Front, Back
    if is_full():
        print('queue full')
    else:
        Q[Back] = x
        Back = next(Back)

def dequeue():
    global Q, Front, Back
    if is_empty():
        print('queue empty')
    else:
        x = Q[Front]
        Front = next(Front)
        return x

```

## Linked List:
A _**linked list**_ is a data structure in which the objects are arranged in a linear order. Unlike an array, however, in which the linear order is determined by the array indices, the order in a linked list is determined by a pointer in each object. Linked list provide a simple, flexible representation for dynamic sets.

![[linkedList.png]]

- List-Insert means the add elements at the beginning of the list.
- List-Delete means the remove the element "x" from the list.
- List-Search means to find the elements whose key is in the list.

**Code of Linked List:**
```python
class list_element:
    def __init__(self):
        self.value = None
        self.next = None
        self.prev = None

L = list_element()
L.next = L
L.prev = L

def print_all():
    x = L.next
    while x != L:
        print(x.value)
        x = x.next

def insert_after(x, v):
    n = list_element()
    n.value = v
    n.prev = x
    n.next = x.next
    n.prev.next = n
    n.next.prev = n

def insert_before(x, v):
    n = list_element()
    n.value = v
    n.prev = x.prev
    n.next = x
    n.prev.next = n
    n.next.prev = n

```

# Binary Search Tree

A binary search tree is organized, as the name suggests, in a binary tree, as shown in bellow image. We can represent such a tree by a linked data structure in which each node is an object. In addition to a _key_ and satellite data, each node contains attributed _left, right_ and _p_ that point to the nodes corresponding to its left child, its right child, and its parent, respectively. If a child or the parent is missing, the appropriate attribute contains the value NIL (in python None).

![[binarySearchTree.png]]

The keys in a binary search tree are always sorted in such a way as to satisfy the _**binary-search-tree property:**
- Let _**x**_ be a node in a binary search tree. If _**y**_ is a node in the left subtree of _**x**_, then _**y.key <= x.key**_. If y is a node in the right subtree of _**x**_, then _**y.key >= x.key**_.
- _**Complexity**_ of a walking through a Binary Search Tree is _**O(n)**_

## Searching:
Checks if the given value is not null, neither is the current node's key is not null. Otherwise, then checks if input value is smaller than the current node's key, and if it goes to the left node, otherwise it goes to the right node.

```python
def bst_search(t, k): #t = current node, k = searching key
    while t != None and t.key != k:
        if k > t.key:
            t = t.right
        else:
            t = t.left
    return t != None

```

## Minimum and Maximum:
We can always find an element in a binary search tree whose key is a minimum by following _left_ child pointers from the root until we encounter a _null_. Hence, the following code shows that:

```python
def bst_minimum(t) #t = root node
	while t.left != None:
        t = t.left
    return t

```

It is the same concept for the maximum, however it would be done by going from root to the _right_ child pointer, until _null_ is encountered. The following code shows that:

```python
def bst_maximum(t) #t = root node
	while t.right != None:
        t = t.right
    return t

```

## Successor and Predecessor:
This could be broken into 2 cases. If the right subtree of node _x_ is nonempty, then the successor of _x_ is just the leftmost node in x's right subtree. For example the successor of the node with key in above binary tree example, is the node with the key 6 (second BST). However, maybe the right subtree is empty, hence one must go back to the parent as the next. Hence the following code represents that:

```python
def bst_successor(t):
    # next node in the natural order of keys
    if t.right != None:
        return bst_minimum(t.right)
    # go up at most until we reach the root (parent == None)
    # or until the current node is the left child of its parent
    p = t.parent
    while p != None and p.left != t:
        t = p
        p = p.parent
    return p

```

The same logic is used for the Predecessor as well, except, it would look at right.

```python
def bst_predecessor(t):
    # next node in the natural order of keys
    if t.left != None:
        return bst_max_node(t.left)
    # go up at most until we reach the root (parent == None)
    # or until the current node is the right child of its parent
    p = t.parent
    while p != None and p.right != t:
        t = p
        p = p.parent
    return p

```

## Insertion and Deletion:
In order to insert a node into the Binary search tree, firstly there we have to get to the node's parent in the tree. That could be simply done by while loop where it keep on comparing if it should go left or right. Hence the code is as follows _(page 315)_:

```python
def bst_insertion(T, z):
    y = None
    x = T.root
    while x != None:
        y = x
        if z.key < x.key:
            x = x.left
        else:
            x = x.right
    z.parent = y
    if y == None:
        T.root = z  #tree T was empty
    elif z.key < y.key:
    	y.left = z
    else:
        y.right = z

```

For deletion read page 316:

## Code of Binary Search Tree:

```python
import sys

##############
class Node:
    def __init__(self,value):
        self.key = value
        self.left = None
        self.right = None
        ###
        self.parent = None
##############

def bst_minimum(t):          #t = root node
    while t.left != None:
        t = t.left
    return t

def bst_maximum(t):          #t = root node
    while t.right != None:
        t = t.right
    return t

def bst_successor(t):
    # next node in the natural order of keys
    if t.right != None:
        return bst_minimum(t.right)
    # go up at most until we reach the root (parent == None)
    # or until the current node is the left child of its parent
    p = t.parent
    while p != None and p.left != t:
        t = p
        p = p.parent
    return p

def bst_predecessor(t):
    # next node in the natural order of keys
    if t.left != None:
        return bst_maximum(t.left)
    #
    # go up at most until we reach the root (parent == None)
    # or until the current node is the right child of its parent
    p = t.parent
    while p != None and p.right != t:
        t = p
        p = p.parent
    return p

def bst_search(t, k):
    while t != None and t.key != k:
        if k > t.key:
            t = t.right
        else:
            t = t.left
    return t != None

def bst_insertion(T, z):
    y = None
    x = T.root
    while x != None:
        y = x
        if z.key < x.key:
            x = x.left
        else:
            x = x.right
    z.parent = y
    if y == None:
        T.root = z  #tree T was empty
    elif z.key < y.key:
    	y.left = z
    else:
        y.right = z

```

# Red-Black Trees

A _**red-black tree**_ is a binary search tree with one extra bit of storage per node: its color, which can be either **RED** or **BLACK**. By constraining the node colors on any simple path from the root to a leaf, red-black tree ensure that no such path is more than twice as long as any other, so that the tree is approximately _**balanced**_.

Therefore, each node of the tree now contains the attributes _color, key , left, right, and pointer_. If a child or the parent of a node does not exits, the corresponding pointer attribute of the node contains the value NIL. We shall regard these NILs as being pointers to leaved (external nodes) of the binary search tree and the normal, key-bearing nodes as being internal nodes of the tree. A red-black tree is a binary tree that satisfies the following **red-black properties:**

- Ever node is either red or black
- The root is black
- Every leaf (NIL) is black
- If a node is red, then both its children are black.
- For each node, all simple paths from the node to descendant leaves contain the same number of black nodes.

**Example of a Red-Black Trees:**

![[redBlackTrees.png]]

# Elementary Graph Algorithms

Graph can be represented between two standard ways: 
$$ G = (V, E) $$
- _**V**_ is the set of _**vertices**_ (also called _**nodes**_)
- _**E**_ is the set of _**edges**_

**Directed Graph** has edges with directions, whereas **Undirected Graph** has edges, with no directions.

## Reading the Graph:

In order to read the graph, there are 3 elements which must be taken in consideration. There are as following:
- **Adjacent** _(indexed by Node ID)_
- **Vertices** _(indexed by Node ID)_
- **Vertices Index** _(Dictionary name --> Node ID)_

### Code of reading the Graph:
```python
Adj = []		# (indexed by Node ID)
V = []			# (indexed by Node ID)
V_idx = {}		# (Dictionary name --> Node ID)

def read_graph(f):
    global Adj, V, V_idx
    for line in f:
        u = None
        for v_name in line.strip().split():		# to split the lines for the input
            if v_name in V_idx:
                v = V_idx[v_name]				# storring the index of the vertex
            else:
                v = len(V)						# Storring the current length of what is in the list
                V_idx[v_name] = v				# If the vertex isn't in V_idx then it would store it in V_idx
                V.append(v_name)				# Appending the vertex in V
                Adj.append([])					# Making an empty list inside Adj
            if u == None:
                u = v
            else:
                Adj[u].append(v)				# Adding the adjucent vertex to the dictionary

```

## BFS (Breath-First-Search)

Goes through all the edges of the first vertex, then does the same for its edges vertex, until every vertex is reached.

**Example of BFS:**
![[bfsConnected.png|550]]

### Code of BFS:
```python
def bfs():
    n = len(V)
    src = 0

    Visited = [False]*n
    D = [None]*n                    # distances from the source node src
    P = [None]*n
    #
    D[src] = 0
    P[src] = src                    # by definition -- doesn't make much sense anyway
    #
    Q = [src]
    head = 0
    Visited[0] = True
    #
    while head < len(Q):
        v = Q[head]
        head = head + 1
        for u in Adj[v]:
            if not Visited[u]:
                P[u] = v
                D[u] = D[v] + 1
                Visited[u] = True
                Q.append(u)

    for i in range(n):
        print('node',V[i],'is at distance',D[i],'from node',V[src])

```

In order to check if all the vertex are connected to each, it has to be checked that there each vertex is connected to something. For instance, bellow in the code it checks if it does that.

**Example of Not Connected Graph:**

> Alice Bob Alice Charlie Charlie Bob Eve

**Example of Connected Graph:**

> Alice Eve Bob Alice Charlie Charlie Bob Eve Charlie

### Code of BFS Connected:
```python
def is_connected():
    global Adj, V
    n = len(V)
    Visited = [False]*n
    Q = [0]
    head = 0
    Visited[0] = True
    count = 1
    print(V[0])
    while head < len(Q):
        v = Q[head]
        head = head + 1
        for u in Adj[v]:
            if not Visited[u]:
                print(V[u])
                Visited[u] = True
                Q.append(u)
                count = count + 1
    if count == n:
        print('connected')
    else:
        print('disconnected')

```

### Full Code of Graph with BFS:
```python
Adj = []		# (indexed by Node ID)
V = []			# (indexed by Node ID)
V_idx = {}		# (Dictionary name --> Node ID)

def read_graph(f):
    global Adj, V, V_idx
    for line in f:
        u = None
        for v_name in line.strip().split():		# to split the lines for the input
            if v_name in V_idx:
                v = V_idx[v_name]				# storring the index of the vertex
            else:
                v = len(V)						# Storring the current length of what is in the list
                V_idx[v_name] = v				# If the vertex isn't in V_idx then it would store it in V_idx
                V.append(v_name)				# Appending the vertex in V
                Adj.append([])					# Making an empty list inside Adj
            if u == None:
                u = v
            else:
                Adj[u].append(v)				# Adding the adjucent vertex to the dictionary

if __name__ == "__main__":
    import sys
    read_graph(sys.stdin)
    print('Vertex:')
    for i in range(len(V)):
        print(i, V[i])
    print('Edges:')
    for v in range(len(V)):
        for w in Adj[v]:
            print(v,w, '(', V[v], '-->', V[w], ')')

def is_connected():
    global Adj, V
    n = len(V)
    Visited = [False]*n
    Q = [0]
    head = 0
    Visited[0] = True
    count = 1
    print(V[0])
    while head < len(Q):
        v = Q[head]
        head = head + 1
        for u in Adj[v]:
            if not Visited[u]:
                print(V[u])
                Visited[u] = True
                Q.append(u)
                count = count + 1
    if count == n:
        print('connected')
    else:
        print('disconnected')

def bfs():
    n = len(V)
    src = 0

    Visited = [False]*n
    D = [None]*n                    # distances from the source node src
    P = [None]*n
    #
    D[src] = 0
    P[src] = src                    # by definition -- doesn't make much sense anyway
    #
    Q = [src]
    head = 0
    Visited[0] = True
    #
    while head < len(Q):
        v = Q[head]
        head = head + 1
        for u in Adj[v]:
            if not Visited[u]:
                P[u] = v
                D[u] = D[v] + 1
                Visited[u] = True
                Q.append(u)

    for i in range(n):
        print('node',V[i],'is at distance',D[i],'from node',V[src])

```