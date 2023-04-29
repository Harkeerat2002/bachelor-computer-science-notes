# Section 1.1
1. **What is the difference between a host and an end system? List several different types of end systems. Is a Web server an end system?**
	The difference between a host and an end system is that there is no difference. Both the words are used in the same context. There are several types of end systems, for instance PCs, workstations, web server, mail server. Web Server is indeed an end system. 
3. **Why are standards important for protocols?****
	Standards are important for the protocols, since there are needed so that other people can create networking systems and also products which can interoperate.
# Section 1.2
`Irrelevent Questions, hopefully they wont come.`
# Section 1.3
11. **Suppose there is exactly one packet switch between a sending host and a receiving host. The transmission rates between the sending host and the switch and between the switch and the receiving host are R1 and R2, respectively. Assuming that the switch uses store-and-forward packet switching, what is the total end-to-end delay to send a packet of length L? (Ignore queuing, propagation delay, and processing delay.)**
	
12. **What advantage does a circuit-switched network have over a packet-switched network? What advantages does TDM have over FDM in a circuit-switched network?**
	Circuit-switched networks tend to have the capability to reserve all the resources for the communication to take place. Hence, it provides a guarantee, that the current connection will have at least a certain minimum bandwidth. Whereas, in Packet switched network, they cannot provide this guarantee. 
	FDM needs to be provided with a sophisticated analog hardware, to get the correct frequency, which could be a tricky procedure to fine tune. In the other, TDM does not require that. 
13. **Suppose users share a 2 Mbps link. Also suppose each user transmits continuously at 1 Mbps when transmitting, but each user transmits only 20 percent of the time. (See the discussion of statistical multiplexing in Section 1.3.)**
	- **When circuit switching is used, how many users can be supported?**
		It would be 2 users, since 1 users needs 1Mbps to transmit, whereas the available link is a 2Mbps link. Hence, it would be supported for 2 users.
	- **For the remainder of this problem, suppose packet switching is used. Why will there be essentially no queuing delay before the link if two or fewer users transmit at the same time? Why will there be a queuing delay if three users transmit at the same time?**
		There would be no queuing delay, if two or fewer users try to access it, because let's assume that the maximum number of users try to access it, which is 2, then they would be using 2 Mbps combines. However, that is still fine since the link is 2Mbps.
	- **Find the probability that a given user is transmitting.**
		Probability that a given user is transmitting is 0.2 (Answer in the question itself).
	- **Suppose now there are three users. Find the probability that at any given time, all three users are transmitting simultaneously. Find the fraction of time during which the queue grows.**
		
# Section 1.4
16. **Consider sending a packet from a source host to a destination host over a fixed route. List the delay components in the end-to-end delay. Which of these delays are constant and which are variable?**
	There would be 4 delays which would occur when sending a packet from a source host to a destination host over a fixed route. The delays would, Queuing Delay, Processing Delay, Propagation Delay, Transmission Delay. All of the delays would be constant instead of Queuing delay, which has a variable.
18. **How long does it take a packet of length 1,000 bytes to propagate over a link of distance 2,500 km, propagation speed 2.5 · 108 m/s, and transmission rate 2 Mbps? More generally, how long does it take a packet of length L to propagate over a link of distance d, propagation speed s, and transmission rate R bps? Does this delay depend on packet length? Does this delay depend on transmission rate?**
19. **Suppose Host A wants to send a large file to Host B. The path from Host A to Host B has three links, of rates R1 = 500 kbps, R2 = 2 Mbps, and R3 = 1 Mbps.** 
	- **Assuming no other traffic in the network, what is the throughput for the file transfer?**
		The throughput would be the link with the minimum rate, which is R1 (500kbps)
	- **Suppose the file is 4 million bytes. Dividing the file size by the throughput, roughly how long will it take to transfer the file to Host B?** 
	- **Repeat (a) and (b), but now with R2 reduced to 100 kbps.**
20. **Suppose end system A wants to send a large file to end system B. At a very high level, describe how end system A creates packets from the file. When one of these packets arrives to a packet switch, what information in the packet does the switch use to determine the link onto which the packet is forwarded? Why is packet switching in the Internet analogous to driving from one city to another and asking directions along the way?**
# Section 1.5
22. **List five tasks that a layer can perform. Is it possible that one (or more) of these tasks could be performed by two (or more) layers?**
	Five generic tasks are error control, flow control, segmentation and reassembly, multiplexing, and connection setup. Yes, these tasks can be duplicated at different layers. For example, error control is often provided at more than one layer.
23.  **What are the five layers in the Internet protocol stack? What are the principal responsibilities of each of these layers?**
		The five layers in the Internet Protocol Stack are, Application Layer, Transport Layer, Network Layer, Link Layer, Physical Layer.
		Application Layer is where the network application and their application-layer protocol resides. 
		Transport Layer is where the application-layer messages between application endpoints are transferred.
		Network Layer is where it moves the network-layer packets known as datagrams from one host to another. 
		Link Layer is where it routes a datagram through a series of routers between the source and destination. 
		Physical Layer is to move the individual bits withing the frame from one node to the next.
24.  **What is an application-layer message? A transport-layer segment? A network layer datagram? A link-layer frame?**
	 Application-layer message: data which an application wants to send and passed onto the transport layer; transport-layer segment: generated by the transport layer and encapsulates application-layer message with transport layer header; network-layer datagram: encapsulates transport-layer segment with a network-layer header; linklayer frame: encapsulates network-layer datagram with a link-layer header.
26. **Which layers in the Internet protocol stack does a router process? Which layers does a link-layer switch process? Which layers does a host process?**
	The router is process through the Network, Link and Physical Layer.
	The link-layer switch process is process through the Link Layer.
	The host process is through Application Layer.