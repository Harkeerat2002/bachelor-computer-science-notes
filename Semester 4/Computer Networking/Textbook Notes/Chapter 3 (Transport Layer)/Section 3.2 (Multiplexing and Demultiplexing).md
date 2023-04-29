- Extending the **host-to-host** delivery service provided by the network layer to a **process-to-process** delivery service for applications running on the hosts.
- Needed for all computer networks.
- At the destination host, the transport layer receives segments from the network layer just below.
- The transport layer has the responsibility of delivering the data in these segments to the appropriate application process running in the host.
![[nma0erwx.bmp]]
- **Example Explanation:**
    - Suppose you are downloading web pages while running one FTP session and two Telnet sessions. (Having 4 network processes running)
    - When the transport layer in your computer receives data from the network layer below, it needs to direct the received data to one of these four processes.
    - A process can have one or more **sockets, and** doors through which data passes from the network to the process and through which data passes from the process to the network.
    - As shown in the above figure, the transport layer in the receiving host does not actually deliver data directly to a process, but instead to an intermediary socket.
    - How a receiving host directs an incoming transport-layer segment to the appropriate socket.
    - Each transport-layer segment has a set of fields in the segment for this purpose.
    - At the receiving end, the transport layer examines these fields to identify the receiving socket and then directs the segment to that socket.
    - This job of delivering the data in a transport-layer segment to the correct socket is called **demultiplexing.**
    - The job of gathering data chunks at the source host from different sockets, encapsulating each data chunk with header information to create segments, and passing the segments to the network layer is called **multiplexing.**
- **Multiplexing at Sender:**  
    - Handle data from multiple sockets, and add transport header (later used for demultiplexing).
- **Demultiplexing at receiver:**  
    - Use header info to deliver receiver segments to the correct socket.
- **How Demultiplexing works**  
    - Host Receives IP datagrams
        - Each datagram has a source IP address, destination IP address
        - Each datagram carries one transport-layer segment
        - Each segment has a source, destination port number
    - The host uses **IP addresses and Port Numbers** to direct segments to the appropriate socket
![[59jrabxu.bmp]]
- **Port Numbers**
    - Port number: **16-bit** number
    - Port numbers from 0 to 1023 called **well-known port numbers**
    - Each application is assigned a default port number
### Connection-less Multiplexing and Demultiplexing
- When creating a segment to send into the UDP socket, the sender must specify:
    - Destination IP address
    - Destination port #
- When receiving host receives UDP segment:
    - Checks destination port in the segment
    - Direct UDP segment to the socket with that port.
![[miqa75wf.bmp]]
### Connection-Oriented Multiplexing and Demultiplexing
- TCP socket identified by **4-tuple**
    - Source IP address
    - Source port number
    - Destination IP address
    - Destination port number
- Demux: receiver uses **all four values** (4-tuple) to direct segment to appropriate socket
- The server may support many **simultaneous TCP sockets**
    - Each socket is identified by its own 4-tuple
    - Each socket is associated with a different connecting client
![[ikrvgi3a.bmp]]