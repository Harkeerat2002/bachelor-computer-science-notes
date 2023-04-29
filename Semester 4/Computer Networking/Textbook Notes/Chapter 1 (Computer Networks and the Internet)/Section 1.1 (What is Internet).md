# 1.1 What is Internet?

>_The **Internet** is a computer network that interconnects billions of computing devices throughout the world._

The internet is a **compound of networks,** interconnected with each other.

## **Computer:**
- *An electronic machine that can store, organize and find information, do processes with numbers and other data, and control other machines. *****

## **Computer Network:**

- _A number of computers and other devices that are connected together so that equipment and information can be shared._
- A number of interconnected computers, machines, or operations.
- There are **hosts** or **end systems.**

## Components of the Internet:
![[Pasted image 20230107170351.png|350]]
**Host/End System:**
- **A _host_ or _end system is a device connected to the Internet._
- **Host** is a computer connected via Internet whereas **End system** are those type of computer connected computer network.
- **Traditional Devices:**
	- Desktop PCs, Linux workstations, servers
- **Non-Traditional Devices (Now-days)**
	- laptops, smartphones, tablets, TVs, gaming consoles, thermostats, home security systems, home appliances, watches, eyeglasses, cars, traffic control systems

The **Internet of things (IoT)** describes the network of **physical objects**.

**End systems** are connected together by a network of **communication links** and **packet switches.**
- Different links can transmit data at different rates, which the **transmission rate** of a link measured in bits/seconds

**Packets:**
- When one end system has data to send to another end system, the sending end system segments the data and **adds** **header** **bytes** to **each** **segment**.
- The resulting packages of information, known as **packets** in the jargon of computer networks to the destination end system, where they are reassembled into the original data.

A **packet switch** takes a packet arriving on one of its incoming communication links and forwards that packet to one of its outgoing communication links.

**Two Prominent types of Packet Switch:**
Both types of switches forward packets toward their ultimate destinations.
- Router
- Link-layer switches
![[Pasted image 20230107170819.png|325]]

**Router:**
- Router are used in the network core.
**Link-layer Switch:**
- Link-layer switches are used in access networks.
![[Pasted image 20230107170912.png|475]]
- *point-to-point link:*
- *multiple access link:*
    - There is going to concurrency, as the multiple computer access the link, there would be crashes.

There are many types of communication links, which are made up of different types of **physical media**.

Different links can transmit data at different rates, with the **transmission rate** of a link measured in bits/second.

**Router vs Switch:**
- Difference between a router and a switch is that router takes the message, reads the message, takes some decision then it goes somewhere else. While switch essentially takes the input and and goes to some output.

The sequence of communication links and packet switches traversed by a packet from the sending end system to the receiving end system is known as a **route** or **path** through the network.

## Service Description:
-   Terms of service → delivers data (reliable) to TCP.
    “Best Effort” data delivery protocol to OP
-   Terms of infrastructure → the internet provides a communication infrastructure. It enables distributed applications i.e. web, games, email.

## Internet Protocols:
End systems, packet switches, and other pieces of the Internet run **protocols** that control the sending and receiving of information within the Internet.
![[Pasted image 20230107171122.png|650]]
The set of communication protocols used on the Internet is known as the **TCP/IP protocol suite.**

All activity on the Internet that involves two or more communication remote entities is governed by a protocol.

_A protocol defines the **format** and the **order** of **messages** exchanged between two or more **communicating entities,** as well as the **action taken** on the transmission and/or receipt of a message or other event._