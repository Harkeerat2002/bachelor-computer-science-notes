# Unit 8
- #### Database Design
	- Main uses addressed generally in physical design
		- **Storage Media**
		- **File Structures**
		- **Indexes**
	- A **file** as a physical entity: a sequence of fixed size blocks (on the disk), but not necessarily physically contiguous (the blocks could be dispersed).
	
- #### Logical Files: Records
- #### Physical Files: Blocks
- #### Cost Model: Number of Block Accesses
	- Reading or writing a block **costs one time unit**.
	- Processing In RAM is *free*.
	- **GOAL:** Minimize the number of block accesses.
	- Organize the physical database so that you make as much use as possible from any block you read/write.
- #### Files Organization
	- File Organization tried to provide:
		- When you read a bock you get *many* useful records
	- indexes try to provide:
		- You know where blocks containing useful records are
	- **Heap:**
		- Everything has linear cost
	- **Sorted Sequence:**
		- generally *log(n)*
	- **Hashing**
		- For *large* queries
		- Between 1 and N
	- **2-3 Trees**
		- for *large* and *ranged* queries
- #### Indexes
	- **Indexing Maintenance cost**
	- ##### Dense Index Files
		- An index is **dense** if for every key appearing in (some record) of the data file, a dedicated pointer to the block containing the record appears in (some record) of index file.
	- ##### Sparse Index Files
		- A index is **sparse** if for every key appearing in (some record) of the data file, there is no dedicated pointer to the block containing the record.
	- ##### Clustered Data Files
	- ##### Unclustered Data Files
	- **Quality of Choice:**
		- *Sparse Index and Unclustered file*: generally bad, cannot easily find records for some keys.
		- *Dense Index and Clustered File*: genrally unnecessarily large index.
		- *Dense Index and Unclustered File*: good, can easily find the record for every key.
		- Sparse Index and Clustered File: Best
- #### B+ Trees
	- It has to satisfy the conditions:
		- It is rooted (it has a root)
		- It is directed (order of children matters)
		- All paths from root to leaves are of same length
	- Calculating Optimal parameter and block accesses
- #### Primary vs Secondary Indexes
	- Useful for **ranged** queries.
	- Use **secondary index on value** to get relevant keys, then use **primary index** on key **to get records**.