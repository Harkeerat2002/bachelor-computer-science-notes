- **Link layer** has responsibility of transferring a datagram from one node to **a physically adjacent** node over a link.
- Link layer implemented in **network interface card (NIC)** or on a chip.
## Link Layer: Services
- **Framing, link access:**
	- encapsulate datagram into frame, adding header, trailer
	- **Medium Access Control (MAC)** protocol specifies the rules by which a frame is transmitted onto the link. If there are multiple nodes sharing a single broadcast link, then MAC protocol serves to coordinate the frame transmissions of many nodes.
- **Reliable delivery between adjacent nodes**
- **Flow Control**
- **Error Detection**
- **Error Correction**
- **Half-Duplex and Full Duplex**
	- Half duplex nodes at both ends of link can transmit, but not at the same time. With full duplex nodes, both end of the link can transmit at the same time.



