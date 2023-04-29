# 5.2 Error-Detection and Correction Techniques
## 5.2.1 Parity Checks
- The ability of the receiver to both detect and correct errors is known as **forward error correction (FEC)**
- Parity Checks = CA basic Error Checking
## 5.2.2 Check summing Methods
- Same method as earlier for Error Checking. 
- Addition and One's Complement
- Since the transport layer is typically implemented in software in a host as part of the host's operating system. 
- Because transport-layer error-detection is implemented in software, it is important to have a simple and fast error-detection scheme such as check summing. 
- On the other hand, error detection at the link layer is implemented in dedicated hardware in adapters, which can rapidly perform the more complex CRC operations. 
## 5.2.3 Cyclic Redundancy Check (CRC)
- Division with XOR
- Division with binary Numbers


## Parity Checking
- **Single Bit Parity**
	- Even Parity: Set Parity bit, so there is an even number of 1's
	- Two Dimensional Bit Parity: Detect and correct single bit errors
- **Internet Checksum**
- **Cyclic Redundancy Check (CRC)**
