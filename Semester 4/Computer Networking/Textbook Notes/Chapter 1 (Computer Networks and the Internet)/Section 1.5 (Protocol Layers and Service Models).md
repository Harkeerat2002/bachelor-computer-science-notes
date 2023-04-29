# 1.5 Protocol Layers and Their Service Models
## 1.5.1 Layered Architecture
### Protocol Layering
- Each protocol belongs to one of the layers, and each layer provides its service by:
    - performing certain actions withing that layer
    - by using the service of the layer directly below it
        - For example, the services provided by layer _n_ may include reliable delivery of messages from one edge of the network to the other. This might be implemented by using an unreliable edge-to-edge message delivery service for layer _n - 1,_ and adding layer _n_ functionality to detect and re-transmit lost messages.
- A protocol layer can be implemented in software, in hardware, or in a combination of the two.
![[Pasted image 20220608130520.png|200]]
- Taken together, protocols of various layers are called the protocol stack.
### Application Layer:
- The application layer where network applications and their application-layer protocols reside
- Example of application layer protocols
    - HTTP (Hypertext Transfer Protocol)
    - FTP (File Transfer Protocol)
    - SMTP (Simple Mail Transfer Protocol)
- A packet of information in the application later is referred to as a **message**
### Transport Layer:
- The Internet’s transport layer transports application-layer messages between application endpoints.
- Transport Layer protocols
    - TCP (Transmission Control Protocol)
    - UDP (User Data-gram Protocol)
- Packet of information at the transport layer is referred to as **segment's**
### Network Layer:
- The Internet’s network layer routes a datagram through a series of routers between the source and destination
- Only one network-layer protocol: **Internet Protocol (IP)**
- Responsible for moving **packets** from one host to another
### Link Layer:
- The link layer is responsible for moving a packet from one node (host or router) to the next node in the route
- Examples of link-later protocols
    - Ethernet
    - Wi-Fi
- A packet of information at the link layer is referred to as a **frame**
### Physical Layer:
- The physical layer is responsible for moving the individual bits within a frame from one node to the next
- Example of physical layers
    - Twisted-pair copper wire
    - Coaxial cable
    - Fiber optic cable
- Packet of information at the physical layer is the **bit**
## 1.5.2 Encapsulation:
- Adding additional information, to a packet so the packet can be sent in another hard level protocol. 
![[Pasted image 20220608131140.png]]

