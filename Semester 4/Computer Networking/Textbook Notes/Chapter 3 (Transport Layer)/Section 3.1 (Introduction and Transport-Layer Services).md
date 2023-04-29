- A transport-layer protocol provides for **logical communication** between application processes running on different hosts
- By logical communication it means that from an application’s perspective, it is as if the hosts running the processes were directly connected; in reality, the hosts may be on opposite sides of the planet, connected via numerous routers and a wide range of link types.
![[cgtldy5f.bmp|650]]
- Transport-layer protocols are implemented in the end system but not in network routers.
- On the sending side, the transport layer converts the application-layer messages it receives from a sending application process into transport-layer packets, known as transport-layer segments in Internet terminology.
- This is done by breaking the application messages into smaller chunks and adding a transport-layer header to each chunk to create the transport-layer segment.
- **Receiver:** Reassembles segments into messages, passes to the Application layer.

## 3.1.1 Relationship Between Transport and Network Layers
- A transport-layer protocol provides logical communication between **processes running on different hosts.**
- A network layer protocol provides logical communication **between hosts.**
![[x1kp8wzc.bmp]]

## 3.1.2 Overview of the Transport Layer in the Internet
- **Transport Services and Protocols:**
    - Provide _logical communication_ between application processes running on different hosts.
    - Transport protocols actions in the end system:
        - Sender: breaks application messages into **segments,** passes them to the network layer
        - Receiver: Reassembles segments into messages, and passes them to the application layer.
- Two Distinct Transport-layer protocols are available to the application layer:
    - **UDP** (User Datagram Protocol)
    - **TCP** (Transmission Control Protocol)
- Transport-layer packet is referred to as a **segment.**
- Packets for UDP are referred to as data-gram
- **Internet's Network-layer protocol**
    - Has a name — IP, for Internet Protocol
        - IP provides logical communication between hosts.
        - The IP service model is a **best-effort delivery service,** meaning the IP makes its best effort to deliver segments between communicating hosts, but it makes no guarantees.
        - For these reasons, IP is said to be an **unreliable service**
- **Service Models provided by UDP and TCP:**
    - A **most** fundamental responsibility of UDP and TCP is to extend IP’s delivery service between two end systems to a delivery service between two processes running on the end systems.
    - Extending host-to-host delivery to process-to-process delivery is called **transport-layer multiplexing** and **demultiplexing.**
    - UDP and TCP also provide integrity checking by including error-detection fields in their segments’ headers.
        - These two minimal transport-layer services — process-to-process data delivery and error checking are the only two services that UDP provides, hence making UDP an **unreliable service** since it doesn't guarantee that data sent by one process would arrive intact.
    - **TCP:**
        - Offers several additional services to applications.
            - **Reliable Data Transfer**
                - Using flow control, sequence numbers, acknowledgments, and timers, TCP ensure that data is delivered from sending process to receiving process, correctly and in order.
            - **Congestion Control**
                - Service provided for the Internet as a whole.
                - TCP congestion control prevents any one TCP connection from swamping the links ad routers between communication hosts with an excessive amount of traffic
            - **Flow Control**
            - **Connection Setup**
    - **UDP:**
        - Offers no services.
            - **Unreliable, unordered delivery**
            - **Non-frills extension of _best effort_ IP**