# Homework 5
*Harkeerat Singh Sawhney*

## A. Data Structures
### 1. Heap:
#### a. 
If the heap does not need to be "compacted" then it would take 1 operation.
#### b.
If the heap needs to be "compacted" then it will always take N operations.
### 2. Sorted Sequence:
For sorted sequence, it usually takes between $\log N$ or $\log N + N$ operations. However, it would take $\log N + N$ operation depending on the variant. For instance, if a "null" value can be put instead of the real value, then it would cause the sequence to grow unnecessarily.

## B. Index and File
### 1. Dense Index and Sparse Index
#### a. Dense Index:
An index is dense when it has index entries for every search key value in the database file. This helps to search faster, however it needs more space to store index records.

![[Pasted image 20220513095405.png]]
*Figure 1: Dense Indexing*

The Figure 1 is an example of Dense Indexing, In Figure 1, the method record contains search key value and the points to the real record on the disk.
#### b. Sparse Index:
As compare to Dense Index, Sparse Index appears for only some value in the file. Hence, due to this, it is much slower to locate the records. However, as compare to Dense Indexing, it has small size of index, which in return meant the maintaining the index is also easier.
![[Pasted image 20220513095906.png]]
*Figure 2: Sparse Indexing*

The Figure 2 is the example of Sparse Indexing, in which not all the values of the file are indexed.

### 2. Clustered File and Unclustered File
#### a. Clustered File
If is a file is sorted, and then it tends to be a Clustered file. In more detail, if a Data file tends to be clustered if whenever some block B contains records with key values x and y, such that x < y, and key value z, such that x < z< y appears anywhere in the data file, then it must be in block B.
![[Pasted image 20220513213815.png]]
*Figure 3: Clustered File Example*
In the above figure is the example of the clustered file with a sparse index. 

#### b. Unclustered File
If the file were first not sorted with contiguous, and then the blocks were not dispersed is Unclustered File. 
![[Pasted image 20220513225422.png]]

### 3. Four Different Types of Choices for building Indexes
1. **Dense Index Clustered File:**
	There are generally unnecessarily since they have a large index, which is not necessarily.
2. **Sparse Index Clustered File:**
	These are the best since it increases the resource availability. It's also because they have a sorted file, and the sparse index has fewer indexes, which is easier to find the records, and not unnecessarily storing the indexes as well.
3. **Dense Index Unclustered File:**
	They are good since they can easily find the records for every key. However, it does store all the indexes, which can be taxing on the system.
4. **Sparse Index Unclustered File:**
	They are generally bad or the worst since they cannot easily find records for some keys. Since we do know where the data is stored.
## C. B+ Trees
### 1.
What do we know so far:
- Data containing $2^{35}$ bytes
- Disk is organized into blocks each containing $2^9$ bytes
- ID: 14 bytes
- Salary: 7 bytes
- Data Of Birth: 9 bytes
- Comment: 8 bytes

Hence, from this we know that since they're $2^{35}$ each block is holding $2^{9}$ = 512 bytes. Therefore, there would be $2^{26}$ blocks, hence a block address can be specified in 26 bits. Along with that, 4 bytes would be allocated to a block address. 

We know that a node in the B-tree will contain some m pointer and m-1 keys, so then in order to find out what is the largest possible value of m so that a node fits, we use the following expressions.

$$
\begin{align}
(m) \times (size \space of \space pointers) + (m - 1) \times (size \space of \space key) \leq (size \space of \space the \space block) \\

(m) \times 4 + (m-1)(14) \le 512 \\
5m + 14m - 14 \le 512 \\
18m - 14 \le 512 \\
18m \le 526 \\
m \le 29.22 \\
m = 29
\end{align}
$$
We can also derive from this that a block address can be between 2 and 29, and also an internal node will be between 2 and 29 children. Therefore, between 2 and 29 pointers came out of the root, while between 15 ($\frac{29}{2}$) and 29  pointers came out of a non-root.

Hence, now making the table, we know the following; the narrow tree would contain only 15 pointers, while the wide tree would contain 29 pointers. 

**Node in a Narrow Tree:**
We know the following from the above information as well:
$$
\begin{align}
\bigg[\frac{P}{2}\bigg] \\
=\bigg[\frac{29}{2}\bigg] \\
\approx 14.9 \\
= 15
\end{align}

$$
Therefore,
$$
\begin{align}
Level \space 1 \rightarrow 1 \space (root) \\
Level \space 2 \rightarrow 2 \times 1 = 2 \\
Level \space 3 \rightarrow 2 \times 15 = 30\\
Level \space 4 \rightarrow 15 \times 20 = 450 \\


\end{align}
$$
Hence, the table would look as the following:

| Level | Nodes in a Narrow Tree |
| ----- | ---------------------- |
| 1     | 1                      |
| 2     | 20                     |
| 3     | 30                     |
| 4     | 450                    |

**Node in a Wide Tree:**
$$
\begin{align}
Level \space 1 \rightarrow 1 \space (root) \\
Level \space 2 \rightarrow 29 \times 1 = 29 \\
Level \space 3 \rightarrow 29 \times 29 = 841\\
Level \space 4 \rightarrow 841 \times 29 = 24389 \\
\end{align}
$$
Hence the table would look as the following:

| Level | Nodes in a Narrow Tree |
| ----- | ---------------------- |
| 1     | 1                      |
| 2     | 29                     |
| 3     | 841                    |
| 4     | 24389                  |

Therefore, in the end the following table is given:

| Level | Nodes in a Narrow Tree | Nodes in a Wide Tree |
| ----- | ---------------------- | -------------------- |
| 1     | 1                      |  1                   |
| 2     | 2                      |  29                  |
| 3     | 30                     | 841                  |
| 4     | 450                    | 24389                |
From this it can be seen that **450** is the narrowest possible tree whereas **24389** is the widest possible tree.

#### 2.
As compare to the hashing, B+ tree would be better. Due to such a large range, if hashing is used it would end up being very inefficient. This will lead to more operation happening which would end being very expensive.

#### 3. 
Since, in this case, the size of the data is not a concern, then hashing would be a better solution. With hashing it would be much easier to get the data and less expensive as well.

## D. Merge Join
### 1. Description of the Algorithm
1. Using the Merge-Sort Algorithm for R and S. 
2. Blocks from R and S which are of the same size RAM(8) are read first and sorted. 
3. Merge-Sort is again used to double the size by dividing the number of sequences.
4. Going through both R and S to make sure that the elements are appearing in both of them, since they are now sorted. 
5. Minimum size between R and S is 5000. 

### 2. Allocation of RAM
We know the following:
- R(A, B) = 5000 blocks
- R(C, D) = 8000 blocks

Hence, when we need to sort R it will be:
$$
\begin{align}
8 \times 2^x > 5000 \\
\therefore x = 10
\end{align}
$$
And when we sort S:
$$
\begin{align}
8 \times 2^y > 8000 \\
\therefore y = 14
\end{align}
$$
Hence the total cost, which is below 5000 blocks accessed is:
$$
\begin{align}
2 \times 10 \times 5000 + 2 \times 14 \times 80000 + (5000 + 80000) + 5000 = 2,430,000
\end{align}
$$
