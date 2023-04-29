#lectureNote
 **YouTube Video:** https://www.youtube.com/watch?v=T7W5E-5mljc
# Amortized Analysis
- **Aggregate Analysis:** Like taking an *average*
	- Take total cost / number of operations
- **Amortized Analysis** is used to consider the overall effect of a set of multiple operations.
- Three Methods for amortized analysis
	- **Aggregate Analysis**
	- **Accounting Method**
	- **Potential Method**
- ## Example (Dynamic Storage Reallocation)
![[Screenshot_20230115_130619.png|500]]
![[Screenshot_20230115_131416.png|600]]
- ## Aggregate Analysis
	- The **simplest** way to perform **amortized analysis**.
	- Just **get an average**.
		- $$ O(Total \space Cost \div Number \space Of \space Operations)$$
	- **Calculations:**
		- O(Total Cost) = O(Σ cost of n operations) = O(Σ Cost of Cheap operations + Σ Cost of expensive Operations)
		- Total Cost (Expensive Operations) < 2 * Number of Operations
- ## Accounting Method & Potential Method
- **Potential** and **Accounting** methods involve assigning *costs* per operation
	- Operations have the same **cost**
	- Cheap operations are **overcharged**
	- Expensive operations are paid for by the **surplus**
	- **Accounting** method defines operation-dependent costs
	- **Potential** method defines operation-independent costs
	- Same results regardless