# Section 2.1
1. **List five nonproprietary Internet applications and the application-layer protocols that they use.**
	The Web: HTTP; file transfer: FTP; remote login: Telnet; e-mail: SMTP; BitTorrent file sharing: BitTorrent protocol
2. **What is the difference between network architecture and application architecture?**
	The network architecture refers to the organizations of the communication process into the five-layer Internet architecture. 
	The application architecture is designed by the application developer, and is also dictated by it the broad structure as well. 
3. **For a communication session between a pair of processes, which process is the client and which is the server?**
	The process which initiates the communication is the client, whereas the process which accepts the communication is the server. 
4. **For a P2P file-sharing application, do you agree with the statement, “There is no notion of client and server sides of a communication session”? Why or why not?**
	No, because the peer which is starts the communication sessions is the client, and the peer which accepts it is the server.
5. **What information is used by a process running on one host to identify a process running on another host?**
	There are 3 information which is used to identify a process running on another host. It is the IP address and host and port number of the process. 
6. **Suppose you wanted to do a transaction from a remote client to a server as fast as possible. Would you use UDP or TCP? Why?**
	You would use UDP, as for the speed you need UDP doesn't do the handshake, and is also very light weighted.
7. **Referring to Figure 2.4, we see that none of the applications listed in Figure 2.4 requires both no data loss and timing. Can you conceive of an application that requires no data loss and that is also highly time-sensitive?**
	Example for this would be a application such as Google Docs, where the timing is very sensitive, since it should be instant and also no data loss can be tolerated.
8. **List the four broad classes of services that a transport protocol can provide. For each of the service classes, indicate if either UDP or TCP (or both) provides such a service.**
	It is Reliable Data Transfer, Timing, Security and Throughput. TCP provides Reliable Data Transfer is provided by TCP. The rest of none of them provide that.
9. **Recall that TCP can be enhanced with SSL to provide process-to-process security services, including encryption. Does SSL operate at the transport layer or the application layer? If the application developer wants TCP to be enhanced with SSL, what does the developer have to do?**
	SSL operates at the application layer. The SSL socket takes unencrypted data from the application layer, encrypts it and then passes it to the TCP socket. If the application developer wants TCP to be enhanced with SSL, she has to include the SSL code in the application.
# Section 2.2
10. **What is meant by a handshaking protocol?**
	Handshaking protocol is a protocol when there is a connection established between a client and a server. For instance, the HTTP uses a three-way handshake, in which the first handshake is when the client sends a small TCP segment to the server, the server acknowledges and respond with a small TCP segment, and finally the client acknowledges back to the server. 
11. **Why do HTTP, FTP, SMTP, and POP3 run on top of TCP rather than on UDP?**
	The reasons such protocols runs on TCP not UDP is because TCP guarantees reliable data transfer, for which such protocols are used. In the other hand, UDP doesn't guarantee this, hence they are not used for that. 
12. **Consider an e-commerce site that wants to keep a purchase record for each of its customers. Describe how this can be done with cookies.**
	When, for the first time, the user goes onto the website, the site creates a unique number and stores it into its database. It then assigns that number as the cookie header, and stores the information on the client's device. Once the client comes back again onto the website, then it would use the cookies' header to get the information the client has. 
13. **Describe how Web caching can reduce the delay in receiving a requested object. Will Web caching reduce the delay for all objects requested by a user, or for only some objects? Why?**
	Web caching can reduce the delay in receiving a requested object, because instead of the client connected to the server address of the website, it instead connects to the Web Cache serve, from which it will see if it has the desired object or not. If it does, then in a very low latency it would return the object. It would reduce the delay for all the objects, since with caching it would give bandwidth to those objects which are not cached, leading to a much less delay. 
14. **Why is it said that FTP sends control information “out-of-band”?**
	The reason why it is said the FTP sends control information "out-of-band" is because there are 2 TCP connections in which FTP sens information. Once is a data information and other is for control information. Due to this, control information is "out-of-band".