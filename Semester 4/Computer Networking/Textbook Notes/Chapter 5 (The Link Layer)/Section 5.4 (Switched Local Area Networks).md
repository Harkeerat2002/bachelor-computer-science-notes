# Section 5.4: Switched Local Area Networks
### Address Resolution Protocol (ARP)
- ARP module in the spending host takes any IP address on the same LAN as input, and returns the corresponding MAC address.
## Link-Layer Switches
- The role of the switch is to receive incoming link-layer frames and forward them onto outgoing links.
- **Filtering** is the switch function that determines whether a frame should be forwarded to some interface or should just be dropped.
- **Forwarding** is the switch function that determines the interfaces to which a frame should be directed, and then moves the frame to those interfaces.
### Switches Versus Router
- Routers are store-and-forward packets switches.
- The switch is also a store-and-forward packet switch, but it's different since it forwards using MAC addresses.