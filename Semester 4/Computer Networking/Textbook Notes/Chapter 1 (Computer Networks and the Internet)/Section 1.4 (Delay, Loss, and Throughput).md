# Section 1.4: Delay, Loss, and Throughput in Packet-Switched Networks
**Throughput:** The amount of data per second that can be transferred
## 1.4.1 Overview of Delay in Packet-Switched Networks:
- ![[Pasted image 20220608120019.png]]
- As a packet travels from one node (host or router) to the subsequent node (host or router) along this path, the packet suffers from several types of delays at each node along the path.
- The most important of these delays are the **nodal processing delay, queuing delay, transmission delay,** and **propagation delay;** together, these delays accumulate to give a **total nodal delay.**
### Types of Delay:
#### Processing Delay:
- The time required to examine the packet’s header and determine where to direct the packet is part of the **processing delay.**
- The processing delay can also include other factors, such as the time needed to check for bit-level errors in the packet that occurred in transmitting the packet’s bits from the upstream node to router A.
- This is usually given.
#### Queuing Delay:
- At the queue, the packet experiences a **queuing delay** as it waits to be transmitted onto the link.
- The length of the queuing delay of a specific packet will depend on the number of earlier-arriving packets that are queued and waiting for transmission onto the link.
- If the queue is empty and no other packet is currently being transmitted, then our packet’s queuing delay will be zero.
- The formula is later down
#### Transmission Delay:
- Assuming the packets are transmitted in a first-come-first-served manner, as is common in packet-switched networks, our packet can be transmitted only after all the packets that have arrived before it have been transmitted.
$$
Transmission \space Delay = \frac{L}{R}
$$
	where `L` is length packet (bit) and `R` is speed/rate transmission (bps).
#### Propagation Delay:
- Once a bit is pushed into the link, it needs to propagate to router B.
- The time required to propagate from the beginning of the link to router B is the **propagation delay.**
- The bit propagates at the propagation speed of the link.
- The formula for Propagation Delay is as following 
$$
Propagation \space Delay = \frac{d}{s}
$$
	where `d` = the distance between router A and router B, and `s` is the propagation speed of the link.
#### Comparing Transmission and Propagation delay
- The transmission delay is the amount of time required for the router to push out the packet; it is a function of the packet’s length and the transmission rate of the link but has nothing to do with the distance between the two routers.
- The propagation delay, on the other hand, is the time it takes a bit to propagate from one router to the next; it is a function of the distance between the two routers but has nothing to do with the packet’s length or the transmission rate of the link.
## 1.4.1 Queuing Delay and Packet Loss
- Unlike the other three delays, the queuing delay can vary from packet to packet.
- Traffic Intensity is as follows:
$$
Trafic \space Intensity = I = \frac{La}{R}
$$
	where `a` is the average rate of packet/sec.
- Hence, the queuing delay is as follows:
$$
Queuing \space Delay = I \frac{L}{R} \times (1-I)
$$
## 1.4.3 End-to-End Delay
- Now consider the total delay from source to destination.
- Assuming there are $N-1$ router between the source host and the destination host.
- Also assuming that the network is uncongested (so that queuing delays are negligible), the processing delay at each router and at the source host is $d_{proc}$, the transmission rate out of each router and out of the source host is $R \space bits/sec$, and the propagation on each link is $d_{prop}$.
- The nodal delays accumulate and give an end-to-end delay,
$$
d_{end-end} = N(d_{proc}+d_{trans}+d_{prop})
$$
