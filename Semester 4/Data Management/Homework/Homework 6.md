# Homework 6
*Harkeerat Singh Sawhney*

## Question 1
### a)
In order to find which transactions need to be redone, it is first important to see how to scan in order to get the **Redo List**. In order to get the Redo List, first one would need to start scanning the log backwards, from the end until one reaches the first checkpoint record one sees. Therefore, for every transaction for which one has a **commit** record, it should be added to the redo list. Therefore, the list is as following, since only **T5** has committed. Hence, it as follows:
$$
Redo \space List = [T5]
$$
### b)
Similarly as **a)** first, let's see how to get the list of the transactions. Using the same logic as the first questions, the difference is that, for every transaction for which one has the **start** record but not a commit record, that should be added to the undo list. Also, for each transaction that is listed in the checkpoint record for which there is no commit record, it should also be added to the undo list. Hence, in the undo list there is **T6** since it starts but doesn't commit. Also, there is **T3**, since that also starts but doesn't commit.  Hence, it as follows:
$$
Undo \space List = [T6, T3]
$$
### c)
The transaction which are not affected by the failure, would just be everything which is not in the **Redo List** and **Undo List**. Hence, it as follows:
$$
Not \space Affected \space List = [T1, T2, T4]
$$
## Question 2
### a)
**Conflict Graph of Question A**
![[image_0004.png]]
As it can be seen above, there is a cycle between **T5** and **T4**, which means that the schedule would **not** be serializable.

### b)
**Conflict Graph of Question B**
![[image_0010.png]]
Through this graph, it can be seen that it's showing that the Conflict Graph is linear. Hence, this mean that the schedule would **be** serializable. Hence, it means that it is equal to the following serial history `[T1, T2, T3, T4, T5]`.

## Question 3
### a)
The possible values after the crash are as follows:
$$
\begin{align}
a = 1, 2 \\
b = 2, 3 \\
c = 0, 1
\end{align}
$$
### b)
In order to find the values which are recover first we need to know the **Redo List** and **Undo List**. Hence, the list is as follows:
$$
\begin{align}
Redo \space List = [T2] \\
Undo \space List = [T4, T3] \\
\end{align}
$$
Now we can use the theory of recovering with Check pointing. We know the following:
> Going backwards from the end of the log, for each record belonging to an **undo** transaction, perform undo.

> Going forwards from the checkpoint record to the end of the log, for each record belonging to a **redo** transaction, perform redo.

Hence, the following are the actual writes:
$$
\begin{align}
c := 0 \\
b := 2 \\
a := 2
\end{align}
$$
Therefore, looking at the actual writes and comparing to the possible values, the following are the final values after recovery. 
$$
\begin{align}
a = 2 \\
b = 2 \\
c = 0
\end{align}
$$
## Question 4
**Yes** the strict two-phase locking always produces serial schedules. This is because of the following theorem:
>  If all the transactions in the system follow the two-phase locking protocol, then the conflict graph is acyclic (and therefore the history is serializable)

**Assuming the following Lemma:**
	If $T1 \rightarrow T2$ in the conflict graph, the $L1 < L2$ in time (L1 was earlier than L2). 

**Proof for the Answer:**
Assuming by contradiction, that a history obtained following 2PL contains a cycle $T1 \rightarrow T2, T2 \rightarrow T3, ..... , Tn \rightarrow T1$. 
By the Lemma we know the following:
	- L1 < L2
	- L2 < L3
	- ....
	- Ln < L1
Therefore:
$$
L1 < L2 < L3 < ... < Ln < L1
$$
Hence there could not have been a cycle and the history was **serializable**.

