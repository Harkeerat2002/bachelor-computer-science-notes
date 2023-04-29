# 5.3: Multiple Access Links and Protocols
- A **point-point link** consists of a single sender at one send of the link and a single receiver at the other end of the link
- A **broadcast link** can have multiple sending and receiving nodes all connected to the same, single, shared broadcast channel. 
- There are many MAC protocols, but they can all be categorized in the following list:
	- **Channel Partitioning Protocols**
	- **Random Access Protocols**
	- **Taking-Turns Protocols**
- Desires for MAC:
	- When only one node is active, the active node has a throughput of R bps.
	- When M nodes are active, the active node has a throughput of nearly R/M bps
## 5.3.1 Channel Partitioning Protocols
- Three Different Techniques:
	- **Frequency-division Multiplexing (FDM)**
	- **Time-Division Multiplexing (TDM)**
	- **Code Division Multiple Access (CDMA)**
- **TDM:**
	- Divide time into time frames and further divides each time frame into N time slots
	- Disadvantage: A node is limited to a bandwidth
	- Advantage: Avoids Collision
- **FDM:** 
	- Creates N smaller channels of R/N bps out of the single, larger R bps channel.
	- Disadvantage: A node is limited to a bandwidth
	- Advantage: Avoids Collision
- **CDMA:**
	- Assigns different code to each node
	- if the codes are chosen carefully, different nodes can transmit simultaneously and yet have their respective receivers correctly receive a sender's encoded data bits. 
## 5.3.2 Random Access Protocols
- A Transmitting node always transmits at the full rat of the channel (R bps).
- When there is a collision, each node involved in the collision repeatedly retransmits its frame. 
- When there is a collision, it doesn't transmit instantly, instead it waits a random delay before retransmitting the frame.
### Slotted ALOHA:
- **Assumptions:**
	- all frames same size
	- time divided into equal size slots
	- nodes start to transmit only slot beginning
	- nodes are synchronized
	- if 2 or more nodes transmit in slot, all nodes detect collision
- **Operation:**
	- When node obtains fresh frame, transmits in next slot
		- *if no collision:* node can send new frame in next slot
		- *if collision:* node retransmits frame in each subsequent slot with probability *p* until success.
- **Advantages**:
	- Allows a node to transmit continuously at the full rate, R, when that node is the only active node.
	- Highly Decentralized
- **Disadvantages**:
	- Efficiency is poor sometimes. 
	- Collisions, wasting slots
	- idle slots
- **Calculation of the Efficiency:**
	- *p* = probability for each frame
	- *N* = nodes
	- *Probability a given node has a success is* = $p(1-p)^{N-1}$ 
	- *Probability that one of the N nodes has a success is* = $Np(1-p)^{N-1}$ 

### Pure ALOHA:
- In pure ALOHA, when a frame first arrives (that is, a network-layer datagram is passed down from the network layer to the sending node), the node immediately transmits the frame in its entirety into the broadcast channel.
- Unslotted Aloha: simpler, no synchronization
	- when frame first arrives: transmit immediately

### Carrier Sense Multiple Access (CSMA)
- Two Rules in CSMA:
	- **Listen Before Speaking**
	- **If someone else begins talking at the same time, stop talking**
	
## 5.3.3 Taking-Turns Protocols
- The **poling protocol** requires the node in a round-robin fashion. 
- The second, taking-turns protocol, is the **token-passing protocol**. A small, special-purpose frame known as a **token** is exchanged among the nodes in some fixed order.
- **Polling:**
	- master node *invites* other nodes to transmit in turn
	- typically used with *dumb* devices
	- concerns:
		- polling overhead
		- latency
		- single point of failure (master)
- **Token Passing:**
	- control **token** passed from one note to next sequentially
	- token message
	- concerns:
		- token overhead
		- latency
		- single point of failure (token)
