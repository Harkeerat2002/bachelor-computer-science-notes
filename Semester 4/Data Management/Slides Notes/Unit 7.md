# Unit 7

* Logical Database Design
  * We will need to examine whether the specific choice of tables is food for
    * *Storing the Information needed*
    * *Enforcing Constraints*
    * *Avoiding anomalies, such as redundancies*
* Need for Decomposition of Tables
  * Sometimes some information can be better represented than the way it is currently represented.
  * ![[Screenshot_20220628_141656.png|350]]
  * ![[Screenshot_20220628_141719.png|350]]
* Natural Join
  * Given several tables, say R1, R2, ..., Rn, their **natural join** is computed using the following “template”:
  * ![[Screenshot_20220628_141845.png|300]]
  * **Natural Join** is:
    * Cartesian join with condition of equality on corresponding columns.
    * Only one copy of each column is kept.
* Normalization and Normal Forms
  * **Normalization** deals with *reorganizing* a relational database by, generally, breaking up tables (relations) to remove various anomalies.
* Functional Dependencies:
  * Functional dependencies means that if a value of P is specified, it *forces* some (specific) value of Q; in other words: Q is a function of P
  * ![[Screenshot_20220628_143032.png|350]]
    * **Our Rules:**
      1. A student can have only one birth year: *S → B*
      2. A teacher has to charge the same fee from every student he teaches : *T → F*
      3. A teacher can teach only one course (perhaps at different times, different offerings, etc.c, but never another course) : *T → C*
      4. A student can take a course from one teacher only: *SC → T*
    * **Possible Primary Keys:**
      * S determines B
      * T determines F
      * T determines C
    * ![[Functional Dependencies.excalidraw|600]]
  * Types of Functional Dependencies
    * Partial Dependencies
      * When the *left* one is a key and *right* is not a key.
    * Transitive Dependencies
      * When *both* the sides aren't a key.
    * Into the key Dependencies
      * When the *right* side is a key.
* First Normal Form: 1NF
  * It means that there are no repeating groups and the number of columns is fixed: in other words, this is a relation, nothing new defined for historical reasons.
* Second Normal Form: 2NF
  * **First Normal Form**
  * No partial Dependencies
  * The decomposition was a lossless join decomposition
* Third Normal Form: 3NF
  * **Second Normal Form**
  * No transitive dependencies.
  * Decomposition was a lossless join decomposition
* Lossless Join Decomposition
  * **Lossless Join Decomposition** is another term for information not being lost, that is, we can reconstruct the original table by *combining* information from the two new tables.
* Boyce-Codd Normal Form (BCNF)
  * **First Normal Form**
  * Every functional dependency is from a full key.
  * Decomposition was a lossless join decomposition.
* 3NF vs BCNF
  * A table in BCNF is automatically in 3NF as no bad dependencies are possible.
  * Generally, normalize up to 3NF and not up to BCNF.
    * So the database is not fully normalized
  * Luckily, when this is done, frequently *automatically* BCNF is achieved.
* Multivalued Dependencies
* Fourth Normal Form: 4NF
* Minimal Cover for a Set of Dependencies
* Algorithmic Technique for finding keys
  * ![[Drawing 2022-06-28 15.03.10.excalidraw|500]]
* Algorithm Technique for computing a minimal cover
* Algorithmic technique for obtaining a decomposition