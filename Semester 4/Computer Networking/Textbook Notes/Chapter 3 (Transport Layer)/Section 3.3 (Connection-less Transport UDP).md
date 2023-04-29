- Does as little as a transport protocol can do
    - **Multiplexing / De-multiplexing**
    - **Error Checking**
- UDP is **connection-less**
    - There is **no** handshaking between sending and receiving transport-layer entities before sending a segment.
    - Each UDP segment is handled independently of the others.
- Why many applications are better suited for UDP:
    - **Finer application-level control over what data is sent, and when:**
        - Under UDP as soon as an application process passes data to UDP, UDP will package the data inside a UDP segment and immediately pass the segment to the network layer.
        - TCP, on the other hand, has a congestion-control mechanism that throttles the transport-layer TCP sender when one or more links between the source and destination hosts become excessively congested.
    - **No connection establishment**
        - TCP uses a three-way handshake before it starts to transfer data.
        - UDP just blasts away without formal preliminaries.
        - Thus UDP does not introduce any delay to establish a connection.
    - **No connection state**
        - TCP maintains a connection state in the end systems
        - This connection state includes receive and send buffers, congestion-control parameters, and sequence and acknowledgment number parameters.
    - **Small packet header overhead**
        - The TCP segment has 20 bytes of header overhead in every segment, whereas UDP has only 8 bytes of overhead.

## 3.3.1 UDP Segment Structure
![[unkpjxmf.bmp]]
- **Fields in the header**
    - Source port (2 bytes)
    - Destination port (2 bytes)
    - Length (2 bytes)
    - Checksum (2 bytes)

## 3.3.2 UDP Checksum
- The UDP checksum provides for error detection.
- That is, the checksum is used to determine whether bits within the UDP segment have been altered as it moved from source to destination.
- The checksum is needed because of Bit Errors
- **Bit Errors:**
    - Bits may “flip”
        - When transmitted over a physical medium
        - While in storage
    - 0 received as 1
    - 1 received as 0
- **Computing UDP Checksum**
    - The UDP checksum is computed as the one’s complement of the sum of several fields of the UDP header plus some filed from the IP header
    - The part of the IP header used in the computation of the UDP checksum is called the **pseudo-header**
- **UDP Checksum: Sender and Receiver Actions**
    - **Sender** side
        - It treads segment contents as a sequence of 16-bit integers
        - These integers are added. Let's call it a sum
        - Checksum: 1’s complement of the sum
        - Sender puts this checksum value in UDP checksum field
    - **Receiver** side
        - Calculate checksum
        - All segments are added and then the sum is added with the sender’s checksum
        - Check that any 0 bit is presented in the checksum, if the receiver checksum contains any 0 then error is detected. So the packet is discarded by the receiver
- **Checksum Example:**
![[eiolz5kn.bmp]]
- **Checksum: Field to sum**
    - Source port
    - Destination Port
    - Length
    - Checksum
