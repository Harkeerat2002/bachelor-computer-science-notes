# Section 1.3: The Network Core
## 1.3.1 Packet Switching:
- In a network application, end systems exchange **messages** with each other.
- To send a message from a source end system to a destination end system, the source breaks long messages into smaller chunks of data known as **packets.**
- Between source and destination, each packet travels through communication links and **packet switches.**
- Packets are transmitted over each communication link at a rate equal to the _full_ transmission rate of the link.
- So, if a source end system or a packet switch is sending a packet of _L_ bit over a link with transmission rate _R_ bit/sec, then the time to transmit the packet is: 
$$
Transmission \space Rate = \frac{L}{R} \space seconds
$$
### Store-and-forward Transmission:
- Store-and-forward transmission means that the packet switch **must** receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link.
- ![[Pasted image 20220607170652.png]]
- Considering a general case of sending one packet from source to destination over a path consisting of `N` links each of rate `R`. Hence, the `end-to-end delay` is as follows:
$$
d_{end-to-end} = N\frac{L}{R}
$$
### Queuing Delays and Packet Loss
- Each packet switch has multiple links attached to it.
- For each attached link, the packet switch has an **output buffer,** which stores packets that the router is about to send into that link
- Output buffers play a key role in packet switching.
- If an arriving packet needs to be transmitted onto a link but finds the link busy with the transmission of another packet, the arriving packet must wait in the output buffer.
- In addition to the store-and-forward delays, packets suffer output buffer **queuing delays.** Due to the amount of buffer space being finite, an arriving packet may find that the buffer is completely full of other packets waiting for transmission.
    - In this case, **packet loss** will occur - either the arriving packet or one of the already-queued packets will be dropped.
    - ![[Pasted image 20220607171328.png]]
### Forwarding Tables and Routing Protocols
- How does the router determine which link it should forward the packet onto?
- Every end system as an address called an IP address.
- The address has a hierarchical structure.
- When a packet arrives at a router in the network, the router examines a portion of the packet’s destination address and forwards the packet to an adjacent router.
- More specifically, each router has a **forwarding table** that maps destination addresses to that router’s outbound links.
- The internet has a number of special **routing protocols** that are used to automatically set the forwarding tables. 
- A routing protocol may, for example, determine the shorted path from each destination and use the shortest path results to configure the forwarding tables in the routers.
## 1.3.2 Circuit Switching:
- In Circuit Switching, it uses **reserved resource allocation**, which means that the resources needed along a path to provide for communication between the end systems are *reserved* for the duration of the communication session between the end systems.
- There is a dedicated circuit for every connection between sender/receiver
- End-to-end process between sender/receiver
- Analogy on Circuit Switching:
	- ![[Pasted image 20220607172924.png]]
### Multiplexing in Circuit-Switched Networks:
- A circuit in a link is implemented with either **frequency-division multiplexing (FDM)** or **time-division multiplexing (TDM)**. 
- **FDM:**
	- With FDM, the frequency spectrum of a link is divided up among the connections established across the link.
	- Specifically, the link dedicates a frequency band to each connection for the duration of the connection.
	- ![[Pasted image 20220607174343.png]]
- **TDM:**
	- For TDM link, time is divided into frames of fixed duration, and each frame is divided into a fixed number of time slots. 
	- When the network established a connection across a link, the network dedicates one time slot in every frame to this connection. 
	- These slots are dedicated for the sole use of that connection, with one time slot available for use to transmitted connection's data. 
	- ![[Pasted image 20220607174413.png]]
## Packet Switching vs Circuit Switching:
![[Pasted image 20220607173536.png]]