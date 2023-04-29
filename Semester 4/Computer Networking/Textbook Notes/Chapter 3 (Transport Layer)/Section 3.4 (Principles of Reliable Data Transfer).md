![[pmcj0xgn.bmp]]
- A data transfer is **reliable** if
    - **no** transferred data bits are **corrupted** (flipped from 0 to 1, or vice versa) or **lost,**
    - and **all** transferred data bits are **delivered in** the **order** in which they were sent.
- The TCP offers a reliable data transport service
- The general problem of reliable data transfer is the central importance of networking.
- The above figure illustrates the framework for our study of reliable data transfer.
- The service abstraction provided to the upper-layer entities is that of a reliable channel through which data can be transferred.
- With a reliable channel, no transferred data bits are corrupted or lost, and all are delivered in the order in which they are sent.
- It is the responsibility of a **reliable data transfer protocol** to implement this service abstraction.

## 3.4.1 Building a Reliable Data Transfer Protocol

### rdt1.0: Reliable transfer over a reliable channel