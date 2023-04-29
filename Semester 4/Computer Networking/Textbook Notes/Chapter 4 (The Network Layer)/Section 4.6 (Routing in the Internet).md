- The routing algorithm running within an autonomous system is called an **intra-autonomous system routing protocol**.
- **Gateway Routers** are routers which are responsible for forwarding packets to destinations outside AS.
- Obtaining reachability information from neighboring ASs and propagating the reachability information to all routers internal to the AS -- are handled by the **inter-AS routing Protocol**
- In **hot-potato routing,** the AS gets rid of the packet as quickly as possible. 
## 4.6.1 Intra-AS Routing on the Internet: RIP
- In RIP, routing updates are exchanged between neighbors approximately every 30 seconds using a **RIP response message**.
### BGP:
BGP provides each AS a means to:
1. Obtain subnet reachability information from neighboring ASs.
2. Propagate the reachability information to all routers internal to the AS.
3. Determine “good” routes to subnets based on the reachability information and on AS policy.


- aggregate routers into regions known as **autonomous systems (a.k.a. domains)(AS)**.
# Intra-AS (intra-domain)
>routing among withing same AS (*network*)
- All routers in AS must run same intra-domain protocol
- Routers in different AS can run different intra-domain routing protocols.
- **Gateway Router:** At *edge* of its own AS, has link(s) to router(s) in other AS'es.
## Intra-AS routing protocols
- **RIP: Routing Information Protocol**
	- classic DV: DVs exchanged every 30 secs
	- no longer widely used
- **EIGRP: Enhanced Interior Gateway Routing Protocol**
	- DV Based
	- Firmly Distance Vector based
- **OSPF: Open Shortest Path First**
![[Pasted image 20220830154940.png]]
	- **Link-state routing**
	- *open:* publicly available
	- Classic Link-State
	- Gives **security**
	- **Hierarchical OSPF:**
		- two-level hierarchy: local area, backbone.
		- Has hierarchy within the routers
		- With this the link-layer advertisement is advertised within the area.

# Inter-AS (inter-domain)
>routing among AS'es
- **gateways** perform inter-domain routing.
## Inter-AS Routing: BGP
- **BGP (Border Gateway Protocol):** the de facto inter-domain routing protocol.
- Allows subnet to advertise its existence, and the destinations it can reach, to the rest of the internet.
- BGP provides each AS a means to:
	- **eBGP:** obtain subnet reachability information from neighboring ASes
	- **iBGP:** propagate reachability information to all AS-internal routers
- Distance Vector Flavor
- **Policy-Based Routing:**
	- Gateway receiving route advertisement uses **import policy** to accept/decline path
	- AS policy also determines whether to **advertise** path to other neighboring ASes
- **BGP Route Selection**
	- Router may learn about more than one route to destination AS, selects route based on:
		- Local Perference value attribute: policy decision
		- Shortest AS-PATH
		- closest NEXT-HOP router: hot potato routing
		- additional criteria
## Hot Potato Routing
- **Hot Potato Routing:** Choose local gateway that has least *intra-domain* cost.

# ICMP:
- **Internet Control Message Protocol** (ICMP)
- used by hosts and routers to communicate network-level information.
	- error reporting: unreachable host, network, port, protocol
	- echo request/replyy (used by ping)
- carried inside IP datagrams
