# Skill Set:
## **Structured Computer Organization**
1.  **Explain the difference between the translation and interpretation of instructions**
    
    Both Translator and interpretation are different ways of converting the instructions to machine readable instructions. Translator converts the whole code in machine language program . In the other hand interpretation converts instruction by instruction in machine language program.
    
    -   **Translation** = Replacing each instruction `L1` by an equivalent sequence of instruction in `L0.` Hence the resulting program consists entirely of `L0` instruction
    -   **Interpretation** = `l0` takes one instruction from `L1` , examines it and then executes it.
2.  **Explain the key characteristics of the digital logic level, the micro-architecture level, the ISA level, and the operating system machine level**
    
    ![[Semester 1/attachments/Untitled 1.png]]
    
    **Digital Logic Level (Level 0):**
    
    -   Digital logic level is the Level 0 in which the program is written in binary. It has _Gates_ in them which is built from the analog components. Gates can be also modeled as digital devices.
    -   _Digital Inputs_ represents `0` or `1` and could only compute as output some smple functions such as `AND` or `OR`.
    -   Small number of gates can be combined to form a _1-bit memory_ which can store a `0` or `1`. Then each _1-bit memories_ can be combined in groups of `16`, `32` or `64` to form _registers._
    -   _1 register_ can hold a single _binary number_ upto some maximum. Gates can also be combined to form the main computing engine.
    
    **Micro-Architecture Level (Level 1):**
    
    -   At this level there is a collection of typically `8` to `32` registers seen which form a local memory and also a circuit called as _ALU (Arithmetic Logic Unit)._
    -   The registers are then connected to the ALU which form a _data path._
    -   The basic operation of the data path consists of selecting one or two registers, having the ALU operate on them, and storing the result stored back in some register.
    
    **Instruction Set Architecture Level (Level 2):**
    
    -   It is a part of the abstract model of a computer which defines how the CPU is controlled by the software.
    -   The ISA acts as an interface between the hardware and the software, specifying both what the processors is capable of doing as well as how it gets done.
    
    **Operating System Machine Level (Level 3):**
    
    -   Also called as an "Hybrid Level"
    -   This level provides the complete set of instructions to the application programmers.
    -   Contains all the ISA level instructions plus the new _system calls_ that the OSM adds.
    
    **Assembly Language Level (Level 4):**
    
    -   It is a low-level programming language.
    -   It equates to machine code but is more readable.
    
    **Problem Oriented Language Level (Level 5):**
    
    -   It usually consists of language which are designed to be used by applications programmers with the problems to solve.
    -   Such languages are often called high-level languages.
3.  **Explain the boundary between software and hardware, given the above levels**
    
    -   As the technology improves the boundary between software and hardware reduces by a lot.
    -   This is because it depends on the factors of costs, speed, reliability, and frequency of expected changes to put the features either in hardware or software.
4.  **Explain how the terms "level", "abstraction", and "virtual machine" relate**
    
    -   Virtual Machines are the different levels of a machine in which each machine has a different level of machine language. For example:
        
       ![[Semester 1/attachments/Untitled 2.png]]
        
        L0 is machine language which is written in Binary which computer can understand.
        
5.  **Explain the structure of the "Von Neumann Machine"**
    

-   Basics of all digital computer even now.
    
-   It has 5 basic ports:
    
    -   Arithmetic Logic Unit
    
    [Control Unit](https://www.notion.so/Control-Unit-976d318d20e2478c973a36d1b9b34cfd)
    
    -   Input and Output Equipment
    -   Memory

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/22d13456-ed7c-44d1-8bbd-76c7290c9566/Untitled.png)

## **The Computer Spectrum**

1.  **Explain Moore's Law**
    -   The observation in which each new generation had four times as much memory as its predecessor, it was realized that the number of transistor on a chip was increasing at a constant rate and this predicted growth would continue for decades to come is known as Moore's Law.
    -   Now-days Moore's law is often expressed as the number of transistors doubling every 18 months.
2.  **Explain the key characteristics of (and distinctions between) disposable computers, microcontrollers, game computers, personal computers, servers, collections of workstations, and mainframes**

-   **Disposable Computers:**
    -   It is a small data processing unit having input/output, memory and communication capabilities.
    -   Disposable computers are only meant to be used for a limited number of times and then discarded.
-   **Micro-controllers:**
    -   There are computers which are embedded inside devices that are not sold as computers.
    -   It manages the devices and handle the user interface.
    -   They are found in large variety of different devices.
-   **Game Computers:**
    -   There are normal computers, with special graphics and sound capability, but limited software and little extensibility.
-   **Personal Computers:**
    -   These includes desktop and notebooks models.
    -   They usually come with hundreds of megabytes of memory, a hard disks holding arround 100 gigabytes of data.
-   **Servers:**
    -   Beefed-up personal computers are workstations are often used as network servers, both for local area networks.
-   **Collections of Workstations:**
    -   There are connecting personal computers to each other to form COWs (Clusters of to thousands of them).
    -   They consist of standard personal computers or workstations connected by gigabit/sec networks and running special software that allow all the machine to work together on a single problem.
    -   Due to their low component price, individual departments can now own such machines.

## **Processor Organization**

1.  **Explain the structure of a data path**

-   The internal organization of part of a typical von Neuman CPU is shown bellow:
    
-   That part is called the Data path and consists of the registers (typically 1 to 32), the ALU (Arithmetic Logic Unit(, and several buses connecting the pieces.
    
    ![The data path of a typical “Von Neumann Machine”](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7b76f4f7-c176-4f1c-a61a-1edded6f17f3/Untitled.png)
    
    The data path of a typical “Von Neumann Machine”
    

1.  **Given a simple data path, set the control signals so it performs a given operation**
2.  **Explain the purpose of registers, the control unit, and the ALU**

-   **Registers:**
    -   It is a small very fast storage area inside CPU.
    -   It is used to tore intermediate values from calculations or instruction that is needed again immediately.
-   It acts like a manager in a computer as it receives orders from RAM in form of instruction
-   **ALU (Arithmetic Logic Unit):**
    -   It performs operations such as addition, subtraction and other simple operations on its inputs, and then yielding a result in the output register, which can be stored into register.

1.  **Explain the difference between RISC and CISC**

-   Both RISC and CISC are terms for different architectures.
    
-   **RISC:**
    
    -   The term RISC stands for "Reduced Instruction Set Computer".
    -   Typically fast and more efficient
    -   RISC: Small # of simple instruction
    -   Properties:
        -   ISA instruction = microinstructions
        -   Only load/store instructions access memory
    -   RISC Design Principles
        -   All ISA instructions directly execute on hardware
        -   Only loads and store should reference memory
        -   Provide plenty of registers
        -   Maximize rate which instructions are issued
        -   Instructions should be easy to decode
-   **CISC:**
    
    -   The term CISC stands for "Complex Instruction Set Computer".
    -   Offers backward compatibility
    -   CISC: Large # of complex instructions
    -   A typical ISA instruction are broken down to multiple simple micro-instructions.
    -   Not only load/store, but also other ISA instructions access memory
    -   Retroactively coined term, usually means "not RISC"
    
    **Difference between RISC and CISC**
    
    RISC
    
    CISC
    
    Average clock per instruction (CPI) is 1.5
    
    Average clock cycle per instruction (CPI) is range at 2 and 15.
    
    Performance is optimized with more focus
    
    Performance is optimized with more focus on hardware.
    

## **Parallelism**

1.  **[Explain the differences and similarities of the various kinds of instruction-level (pipelining, superscalar architectures) parallelism](https://www.notion.so/Exercise-2-745c4f920fe84289b38e49e970736293)**
    
    -   I**nstruction-Level Parallelism:**
        
        -   Divide instruction execution into parts.
        -   Each part works independently of others.
    -   **Fetch-Decode-Execute Cycle:**
        
        -   Fetch (load) instruction from memory
        -   Decode instruction
        -   Fetch (load) its operands
        -   Run operands through ALU
        -   Write (store) result back
    -   **5-Stage Instruction Execution Pipeline (Exploiting Parallelism)**
        
        ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c50d740a-2fff-4598-bae8-f20d12096778/Untitled.png)
        
    -   **Computing Instruction Issue Rate:**
        
        -   Typically measured in MIPS:
            -   Million Instruction per Seconds
        -   `Example A`: 1 instruction per 10ns, no pipeline
            -   $1 MIPS = 10^6$ instruction per second
            -   For 1 instruction we need $10 \times 10^-9 s = 10^-8 \space seconds$
            -   Hence $10^8$ instruction per second = 100 MIPS
        -   `Example B:` 5-stage pipeline, each stage 4ns (total 20ns)
            -   Once loaded, pipelines issues instruction every 4ns = $4 \times 10^{-9}$
            -   Hence 10^9 / 4 instructions per second = 250 MIPS
    -   **Multiple Pipelines:**
        
        -   Parallelized instructions may not
            -   conflict over resources
            -   depend on the result of each other
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f99fe936-df1d-4758-88ee-ae2347cf6268/Untitled.png)
    
2.  **Explain the principle of pipelining**
    
    -   Pipelining tends to reduce the time for instructions to be executed.
    -   It brings the instruction from memory in advance in register called prefetched buffer.
    -   Hence, depending on instruction execution the time for one instruction be executed decreases.

## **Machine-Level Representation of Data**

1.  **Explain why today's computers use a binary data representation**
    
    -   Reliability:
        -   It is very reliable because it is either 1 or 0.
        -   Hence there is very little room for an error in this.
    
    [Bits:](https://www.notion.so/Bits-751da821ef0b41d38b967beab692ff2b)
    
2.  **Explain reasons for grouping bits into memory cells (common cell size: 8 bits = 1 byte)**
    

-   Memory cell is consisted of 8 bits of information. the purpose of memory cells is represent 1 bit of information. I bit = 8 byte. A bit is the smallest data type to represent on information.

1.  **Explain reasons for grouping bits into registers (common register sizes: 8, 16, 32, or 64 bits = 1, 2, 4, or 8 bytes)**

1.  **Explain the purpose of a memory address**

-   A memory address represent a number which is assigned to each byte in computer’s memory. CPU could then use it to track where data and instructions are stored in RAM.

1.  **Explain aligned and unaligned memory accesses**

-   A memory access is said to be aligned when the data being accessed is n bytes long and the datum address is n-byte aligned. Otherwise it is said to be unaligned

1.  **Explain big endian and little endian architectures**

-   A byte in a word can be numbered from left-to-right or right-to-left.
    
-   System in which numbering begins at the high order = **Big Endian**
    
-   System in which numbering begins at the lower order = **Little Endian**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6c2160ca-5dbe-4584-8267-3608833e0b87/Untitled.png)
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/66abbeef-c2df-4c8e-8b4b-e502825683e7/Untitled.png)
    

1.  **Given a memory access instruction (e.g. LD R1, 12 - a load instruction loading 4 bytes from address 12 into register R1), the contents of the registers, the contents of the memory, the memory cell size (e.g. 1 byte), register size (e.g. 8 byte), endianness (e.g. big endian), and alignment policy (e.g. accesses have to be 4-byte aligned), determine the new contents of the register and memory**

## Error Detection and Correction

1.  **Explain the terms "memory word", "code word", "data bits", and "redundant/check bits"**

-   **Memory Word:**
    -   A group of memory bits in a RAM or ROM block.
-   **Code Word:**
    -   Suppose that a memory word consists of m data bits to which we will ad r redundant or check bits. Let the total length be n (i.e., n = m + r). A n-bit unit containing m data and r check bits is often referred to as an n-bit **code word.**
-   **Data Bits:**
    -   Bits in the code word, which has the actual data contain in it.
-   **Redundant/Check Bits:**
    -   There are the extra bits in the code word to check if word code word is valid or not.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b4925ec3-352d-48c1-ba2f-fcd7ba72014e/Untitled.png)

1.  **Given the number of data bits, m, and the number of redundant bits, r, determine the number of possible code words, the number of possible memory words, and the number of _valid_ code words**
2.  **Explain the difference between error _detecting_ and error _correcting_ codes**

-   **Error Detecting Codes:**
    -   It tends to only detect it if the code word is valid or not. It does not show where the error is but only identifies if the code word is valid or not.
-   **Error Correcting Codes:**
    -   It tends to detect the error in code and correct it to make it valid.

1.  **Explain the concepts of Hamming distance _between two code words_, and Hamming distance _of an entire code_**

-   The number of bit positions which two code words differ is called the Hamming Distance. Its main significance is that if two code words are Hamming Distance d apart, it will require d single-bit errors to convert one into the other.

1.  **Determine what Hamming distance of the code is needed to _detect_ a d-bit error, or to _correct_ a d-bit error**
2.  **Given a code word in an error _detecting_ code (based on a parity bit) with m data bits and 1 redundant bit, detect a 1-bit error**
3.  **Given a code word in an error _correcting_ code (Hamming code) with 4 data bits and 3 redundant bits, correct a 1-bit error**

## Caches

1.  **Explain the concept of a "memory hierarchy" and the similarities and differences between the various levels in that hierarchy**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7c83dcfb-7082-4f88-80db-e248b0862623/Untitled.png)
    

-   Memory Hierarchy is the speed between various hardware devices. At the top Level are the **registers** which can be accessed in full speed. Depending on which level the instructions are set, the speed gets slower.

1.  **Explain the principles of "temporal locality" and "spatial locality" in memory accesses**

-   **Spatial Locality:**
    -   It is the observation that memory locations with addresses numerically similar to a recently accessed memory location are likely to be accessed in the near future.
    -   0X00, 0X01, 0X02, 0X03, ....
-   **Temporal Locality:**
    -   It occurs when recently accessed memory locations are accessed again. This may occur, for example, to memory locations new the top of the stack, or instructions inside a loop.
    -   0X00, 0X00, 0X00, 0X00, ....

1.  **Given the number of cache hits and misses, compute the miss ratio**
2.  **Given the number of hits and misses, and the hit and miss latencies (in cycles), compute the mean access time**
3.  **Given the number of sets, the number of lines per set, the number of words per line, and the number of cells (e.g. bytes) per word, determine the various fields of a memory address (tag, set, word, cell)**
4.  **Given the number of sets, the number of lines per set, the number of words per line, and the number of cells (e.g. bytes) per word, draw the structure of a cache (show tags, valid bits, and data, structured in sets, lines, words, and cells)**
5.  **Given the number of sets, the number of lines per set, the number of words per line, and the number of cells (e.g. bytes) per word, and assuming the LRU (least recently used) replacement policy, simulate a sequence of LOAD instructions accessing that cache**
6.  **Describe the difference between an instruction cache and a data cache**

-   The instruction and data caches have a subtle difference: instructions are only fetched (read) from memory, but data can be read from or written to memory.

1.  **Given a set of IJVM instructions, explain what cache type (instruction or data) is accessed, what data is loaded or stored, and from/to what memory area (cf. skill 22.1)**

## Machine-Level Representation of Data: Integer

1.  **Convert between binary, hexadecimal, decimal, and BCD integer numbers**
2.  **[Convert between an unsigned integer number and a bit pattern](https://www.notion.so/Exercise-2-745c4f920fe84289b38e49e970736293)**
3.  **[Convert between a signed integer number and a bit pattern in sign-magnitude, one's complement, two's complement, or excess-N representation](https://www.notion.so/Exercise-2-745c4f920fe84289b38e49e970736293)**

## Binary Arithmetic

1.  **[Perform binary addition](https://www.notion.so/Exercise-1-fd99ec883e5d4654a8a17c21ce04a2d1)**
2.  **Perform binary subtraction (using two's complement and addition)**
3.  **Write an ISA-level assembly language program (IJVM JAL) or a micro program (Mic-1 MAL) using addition, subtraction, and comparison instructions**

## Machine-Level Representation of Data: Floating Point

1.  **Explain the benefits of using more bits for the _exponent_ vs. using more bits for the _fraction_**

-   In many calculations the range of numbers used is very large. For example, a calculation in astronomy might involve the mass of the electron 9 * 10^-28 grams, and the mass of the sun , a range exceeding 10^60.
    
-   What is needed is a system for representing numbers in which the range of expressible numbers is independent of number of significant digits.
    
-   One way of separating the range from the precision is to express numbers in the familiar scientific notion
    
    $n = f \times 10^e$
    
    where f is called the **fraction,** or **mantissa,** and e is a positive or negative integer called the **exponent.** The computer version of this notation is called floating point.
    
-   The range is effectively determined by the number of digits in the exponent and the precision is determined by the number of digits in the fraction.
    

1.  **Explain the difference between _unnormalized_, _normalized_, and _denormalized_ floating-point numbers**
2.  **Convert between a floating point number and its binary representation in IEEE standard (for simple cases)**

## Secondary Memory

1.  **Explain the key properties of secondary memory, such as magnetical vs. optical technology, concentric vs. spiral tracks, constant vs. variable angular velocity (RPM), # of platters, # of surfaces, # of layers, disk diameter, # of tracks, track width, bit length, seek time, and transfer rate**
2.  **Explain the similarities and differences between RAID-1, RAID-2, RAID-3, RAID-4, RAID-5, and multi-parity RAID (e.g., RAID-6 and RAID-7.x)**

-   **RAID-0:**
    -   It splits striped data evenly across two or more disks, without parity information, redundancy, or fault tolerance.

![Diagram of a RAID 0 setup](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/de0b8533-a3d1-425c-8637-cd424e7e8ebc/Untitled.png)

Diagram of a RAID 0 setup

-   **RAID-1:**
    -   It consist of exact copy (or mirror) of a set of data on two or more disks; a classic RAID-1 mirrored pair contains two disks. This configuration offers no parity, striping, or spanning of disk space across multiple disks, since the data is mirrored on all disks belonging to the array, and the array can only be as big as the smallest member disk

![Diagram of a RAID 1 setup](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/18ecb628-a5a2-42ed-acde-b35b1cbe2067/Untitled.png)

Diagram of a RAID 1 setup

-   **RAID-2:**
    -   This is rarely used in practice, but it stripes data at the bit(rather than block) level, and uses a Hamming Code for error correction. The disks are synchronized by the controller to spin at the same angular orientation, so it generally cannot service multiple requests simultaneously.

![Diagram of a RAID 2 setup](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ced4fad6-d6ca-445b-abd2-3ed555cc9a40/Untitled.png)

Diagram of a RAID 2 setup

-   **RAID-3:**
    -   This is rarely used in practice, but it consists of byte-level striping with a dedicated parity disk. One of the characteristics of RAID-3 is that it generally cannot service multiple requests simultaneously.

![Diagram of a RAID 3 setup of six-byte blocks and two parity bytes, shown are two blocks of data in different colors.](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cd428d17-49b0-46b4-8952-eed1369c1877/Untitled.png)

Diagram of a RAID 3 setup of six-byte blocks and two [parity](https://en.wikipedia.org/wiki/Parity_bit) bytes, shown are two blocks of data in different colors.

-   **RAID-4:**
    -   It consists of block-level striping with a dedicated parity disk. AS a result of its layout, RAID 4 provides good performance of random reads, while the performance of random writes is low due to the need to write all parity data to a single disk.

![Diagram 1: A RAID 4 setup with dedicated parity disk with each color representing the group of blocks in the respective parity block (a stripe)](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1a04177c-ba1b-491e-bc3f-3362f0683189/Untitled.png)

Diagram 1: A RAID 4 setup with dedicated [parity](https://en.wikipedia.org/wiki/Parity_bit) disk with each color representing the group of blocks in the respective [parity](https://en.wikipedia.org/wiki/Parity_bit) block (a stripe)

-   **RAID-5:**
    -   It consists of block-level striping with distributed parity. Unlike in RAID-4, parity information is distributed among the drives.

![Diagram of a RAID 5 layout with each color representing the group of data blocks and associated parity block (a stripe). This diagram shows Left Asynchronous layout](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b66dcc3a-3bf7-4d16-8158-94b87202b35d/Untitled.png)

Diagram of a RAID 5 layout with each color representing the group of data blocks and associated [parity](https://en.wikipedia.org/wiki/Parity_bit) block (a stripe). This diagram shows _Left Asynchronous_ layout

-   **RAID-6:**
    -   It extends RAID-5 by adding another parity block; this, it uses block-level striping with two parity block distributed across all member disks.

![Diagram of a RAID 6 setup, which is identical to RAID 5 other than the addition of a second parity block](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e38d0755-8d87-405f-b5dd-44b23704e506/Untitled.png)

Diagram of a RAID 6 setup, which is identical to RAID 5 other than the addition of a second [parity](https://en.wikipedia.org/wiki/Parity_bit) block

## Buses

1.  **Explain the purpose of a bus**
    
    -   A **bus** is a common electrical pathway between multiple devices.
    -   They can be used internal to the CPU to transport data to and from the ALU, or external to the CPU, to connect it to memory or to I/O devices.
2.  **Explain why a computer might contain _multiple_ buses, such as a special memory bus, a PCI bus, an ISA or EISA bus, and a SCSI bus**
    
    -   Multiple buses permit several devices to work simultaneously, reducing time spent waiting and improving the computer’s speed. Performance improvements are the main reason for having multiple buses in a computer design.
3.  **Explain the difference between a bus _master_ and a bus _slave_**
    
    -   Some devices that attach to a bus are active and can initiate bus transfer, whereas others are passive and wait for requests.
    -   The active ones are called masters; the passive ones are called slaves.
        -   When the CPU orders a disk controller to read or write a block, the CPU is acting as a master and the disk controller is acting as a slave.
4.  **Explain the difference between a bus _driver_, a bus _receiver_, and a bus _tranceiver_**
    
    -   The binary signals that computer devices output are frequently too weak to power a bus, especially if it is relatively long or has many devices on it.
    -   This is why most bus master are connected to the bus by a chop called a **bus driver**, which is essentially a digital amplifier.
    -   Similarly, most slaves are connected to the bus by a **bus receiver.**
    -   For devices that can act as both master and slave, a combined chip called a **bus transceiver** is used.
5.  **Explain the differences between bus _arbitration_ schemes: centralized (daisy chaining, explicitly prioritized), decentralized (daisy chaining, explicitly prioritized)**
    
    -   For I/O chips to read and write in the memory, they have to become the bus master, and also to cause interrupts.
    -   **Bus arbitration** mechanism is needed to prevent the chaos of two devices wanting to become bus master at the same time.
    
    ### Centralized Bus Arbitration:
    
    There are **3** types of centralized bus arbitration:
    
    1.  **Centralized Bus Arbitration 1:**
    
    Centralized because it has an arbiter and has lines that go from and to all devices. There is a grant line and a request line. If a device wants to talk it will assert (high 1 or low 0) on the bus and the arbiter sees that. Arbiter checks if the bus is free and gives access. It gives the access to first and second and third until it gets to the device that needs access after-which it stops the passing access further and sends the data. The cycle then repeats. This process is also called as **daisy chaining.**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25ea1694-ffe3-4248-a72f-9c121461f371/Untitled.png)
    
    1.  **Centralized Bus Arbitration 2:**
    
    The same thing happens in this case but we have each device being wired to request 1 or request 2 and the arbiter sees request with different priority. SO the arbiter can assert the grant based on the level or the priority.
    
    ---
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/dd1cbc18-b831-458c-99b0-8d7d9b53d086/Untitled.png)
    
    1.  **PCI:**
    
    On this version we have a more elaborate system where the arbiter is wired to every single device and the arbiter can chose the device with different priority which allows for more flexibility.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f37e1ca4-4f46-4585-93b0-af3f86513f3e/Untitled.png)
    
    ### Decentralized Bus Arbitration:
    
    There is only **1** type of decentralized bus arbitration
    
    -   We can get by without the arbiter where there is always a granted bus. They all are connected to the bus request line. Since we have no centralized arbiter there is a busy line which shows if the bus is busy or not.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3e050cab-2fe4-42c2-bd52-f3b523d95473/Untitled.png)
    
6.  **Explain the difference between a _synchronous_ and an _asynchronous_ bus**
    
    There are two types of Buses:
    
    -   **Synchronous Bus**
    -   **Asynchronous Bus**
    
    **Synchronous Bus:**
    
    A synchronous bus governs all communication on the bus by utilizing a synchronous clock.
    
    **Advantages:** Simple to implement and fast
    
    **Disadvantages:** Same clock rate for all devices and clock skew limits the bus length.
    
    ---
    
    **Asynchronous Bus**
    
    Asynchronous bus has no clock so the data transfer happens when a device is ready.
    
    **Advantages:** No clock skew, so it can have an arbitrary length. Supports all devices (no common clock needed)
    
    **Disadvantages:** Slow and complex to implement
    
7.  ## **Explain how _DMA_ (direct memory access) works**
    

## Interfacing

1.  **Explain the different options to connect multiple (memory and I/O) chips to the CPU by using address lines and chip select (CS) lines**
2.  **Explain the purpose and typical operation of an IO-Chip, e.g., such as the 8255A described in the book**
3.  **Explain the principle of _memory-mapped I/O_**
4.  **Explain the difference between _full address decoding_ and _partial address decoding_**
5.  **Given a set of memory and/or I/O chips and a diagram with their locations in address space (cf. Figure 3-61), provide a circuit that provides the interfacing to these chips**

## Machine-Level Representation of Data:

1.  **Explain the difference between ASCII code, ISO-8859-1, and Unicode**
    -   ASCI (`7` bit)I:
        -   old terminals
    -   ISO 8859 (`8` bit):
        -   Almost every computer system
    -   Unicode (`16` bit):
        -   Windows (support since NT)
        -   UNIX (provides support)
        -   Java (100%)
        -   Mac OS X
2.  **Explain the difference between zero-terminated strings and length-prefixed strings**

-   **Zero-Terminated Strings:**
    -   The Strings are terminated by a null character at the end of the string
    -   Advantages:
        -   Single byte overhead
        -   There is no limit on the length of the string
    -   Disadvantages:
        -   To find the length of a string, it has to be searched by character until null character is found
-   **Length-Prefixed Strings:**
    -   This works by prefixing the actual string with its length.
    -   Advantages:
        -   Finding the length of a string is constant time operations
        -   Can contain any character
        -   Since the length is always know, it’s harder to have buffer overflows
    -   Disadvantages:
        -   Extra Overhead of up to 64 bits

1.  **Given an ASCII table, encode text as a zero-terminated or length-prefixed ASCII string**
2.  **Given an ASCII table, decode a zero-terminated or length-prefixed ASCII string into text**

## Gates and Boolean Algebra

1.  **Convert between the following representations of Boolean functions: algebraic expressions, truth tables, Karnaugh maps, and combinational circuits**
2.  **Convert a Boolean function into _disjunctive normal form (DNF, OR-of-ANDs, Sum-of-Products)_, or conjunctive normal form (CNF, AND-of-ORs, Product-of-Sums)**
3.  **Simplify a Boolean function using Karnaugh maps**
4.  **Create a combinational circuit given an English description of its functionality**
5.  **Express an n-ary Boolean function (function of n arguments) using only binary Boolean functions (functions of 2 arguments); that is, explain and apply _Boolean Function Reduction_**

## Basic Combinational Circuits

1.  **Explain how you can implement an arbitrary Boolean function in a Multiplexer**
    
2.  **Design a multiplexer for a given number of inputs**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/14120467-d72b-469f-a648-7ce4711ef3c7/Untitled.png)
    
3.  **Design a demultiplexer for a given number of outputs**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2f0c434c-27af-4f4a-a8b5-00e0a1cc3929/Untitled.png)
    
4.  **Design a decoder for a given number of outputs**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a82d130b-0687-4284-89d3-ced221991b9a/Untitled.png)
    
5.  **Design an encoder for a given number of inputs**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ee27784f-5a34-4724-95ed-0745b24e5b0e/Untitled.png)
    
6.  **Design an n-bit comparator (A=B)**
    
7.  **Design n-bit shifter**
    
8.  **Design a 1-bit half adder**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e83d8897-5998-4aca-81c1-59f915ea6721/Untitled.png)
    
9.  **Design a 1-bit full adder**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1b70a914-cafc-403e-8d61-6a8edc0092a1/Untitled.png)
    
10.  **Design an n-bit ripple carry adder**
    
11.  **Design a 1-bit ALU slice**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e1c18983-fa8d-435d-ab96-830b140f250b/Untitled.png)
    
12.  **Design an n-bit ALU**
    

## Sequential Circuits

1.  **Draw a timing diagram given a circuit and a gate delay for each gate**
2.  **Explain the behavior of latches and flip-flops**
3.  **Explain the difference between SR latches, clocked SR latches, clocked D latches, and D flip-flops**
4.  **Explain the various ways in which 1-bit memory cells can be organized to form larger memory chips**

## Mic-1 Micro-Architecture

1.  **Explain the functionality of the Mic-1 datapath (the meaning of everything in Figure 4-1)**
    
    -   This example of the micro-architecture includes the subset of the Java Virtual Machine.
        
    -   The goal is to create the Micro-architecture that runs and executes IJVM.
        
    -   This subset contains only integer instructions, so this is we it is names as **IJVM**.
        
    -   This micro-architecture will contain a micro-program (in ROM), whose job is to _fetch, decode_ and _execute IJVM instruction._
        
    -   The micro-program has a set of variables, called the **state** of the computer, which can be accessed by all the functions.
        
    -   IJVM instructions are short and sweet. Each instructions has a few fields, usually one or two, each of which has some specific purpose.
        
        -   **Opcode (Operation Code):** Identifies the instruction, telling whether it is an ADD or BRANCH, or something else.
        -   **Additional Field:** Many instructions have additional field, which specifies the operand. For example, instructions that access a _local variables_ need a field to tell which variable.
        
        This Model of execution, sometimes called the **fetch-execute cycle.**
        
    
    ### The Data Path
    
    The **data path** is that part of the CPU containing the ALu, its inputs, and its outputs.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5e22c3a6-d8ad-4965-8349-800bb8cbffe5/Untitled.png)
    
    PC (Program Counter)
    
    It indicates the memory location containing the next function to be executed.
    
    SP (Stack Pointer)
    
    Points to the Top of the Stack.
    
    MDR (Memory Data Register)
    
    One of the ways to communicate with memory, and it controls the 32-bit port.
    
    MAR (Memory Address Register)
    
    It contains word addresses, so that the values 0, 1, 2, etc., refer to the consecutive words. Putting a 2 in MAR and starting a memory read will read out bytes 8 - 11 from memory and put them in MDR
    
    PC (Program Counter)
    
    It contains the byte addresses, so that the values 0, 1, 2, etc. refer to consecutive bytes. Thus putting a 2 in PC and starting a memory read will read out byte 2 from memory and put it in the low-order 8 bits of MBR
    
    H (Holding Register)
    
    Holds the left input for the ALU.
    
    -   The data path for MIC1 contains a number of 32-bit registers.
        
    -   These registers are only accessible at the micro-architecture level (by micro-program).
        
    -   Most registers can drive their contents onto the B bus.
        
    -   Each of these register are driven by one or two **control signals.**
        
    -   The output of the ALU drives the **shifter** and then the C bus, whose value can be written into one or more registers at the same time.
        
    -   The **ALU’s** function is determined by six control lines. The ALU needs two data inputs:
        
        -   a left input (A)
        -   a right input (B)
        
        Attached to the left input is a holding register **H,** and attached to the right input is the B bus.
        
        **H** can be loaded by choosing an ALU function that just passes the right input (from the B bus) through to the ALU output.
        
2.  **Given a table with the meaning of the F0 and F1 ALU control inputs, and given the 6 control inputs (F0, F1, ENA, ENB, INVA, and INC) for the ALU, describe the function computed by the ALU**
    
3.  **Given a table with the meaning of the F0 and F1 ALU control inputs, and given the function to be computed by the ALU, describe how to set the 6 control inputs**
    
4.  **Given the [Microinstruction Cheat Sheet](https://www.icorsi.ch/brokenfile.php#/3392/user/draft/806873407/Microinstruction-Cheat-Sheet.pdf) , the 24 least significant bits of a 36-bit Mic-1 microinstruction, and the values of all registers and memory cells, determine the resulting value of all registers and memory cells**
    
5.  **Given the Microinstruction Cheat Sheet, the 12 most significant bits of a 36-bit Mic-1 microinstruction, and the value of the MBR register and the N and Z flags, determine the address of the next microinstruction**
    
6.  **Given the Microinstruction Cheat Sheet, assemble a human-readable MAL microinstruction into the 24 least significant bits of a 36-bit Mic-1 microinstruction**
    
7.  **Given the Microinstruction Cheat Sheet, disassemble the 24 least significant bits of a 36-bit MAL microinstruction into the corresponding human-readable MAL microinstruction**
    
8.  **Given a MAL instruction, determine the memory regions (constant pool, local variable frame, operand stack, method area) that is accesses and its type of access (read, write).**
    

## Stacks

1.  **Explain the concept of a stack and its push and pop operations**
    
    -   A stack is a data type in which data is stored on top of each other. Hence when a data is added on the stack it would be at the top of it.
    -   It is in the LIFO - Last in First out
2.  **Explain why a recursive function that needs local variables cannot store them at a fixed memory address**
    
    -   The simplest solution to give each variable an absolute memory address, does not work. the problem that a procedure may call itself. If a procedure is active and called twice, it is impossible to store its variables in absolute memory locations because the second invocation will interfere with the first.
3.  **Explain how a _call stack_ can be used to store local variables of functions (recursive or not), and how it can be used to store the return address**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/727fd622-73da-4e0b-93b2-cb9f66ea3fbe/Untitled.png)
    
    The Stack Frame Local variables exist in within subroutines but they only exist within that scope.
    
    PC is used, the called places the PC on the stack and the Subroutine restores from the PC
    
    IRETURN is I-int prepend because it return an integer. This is now we place current LV on the stack which is the Return Address.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bbe2d01a-d362-4798-9d10-31c6cfa0966d/Untitled.png)
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5edee8bd-72ab-498e-a0ae-5b6ef6759913/Untitled.png)
    
4.  **Explain how an _operand stack_ can be used to evaluate an arithmetic expression**
    
    Stacks have another use, in addition to holding local variables. They can be used for holding operands during the computation of an arithmetic expression. When used this way, the stack is referred to as the **operand stack**. Suppose, for example, that before calling B, A has to do the computation
    
    a1 = a2 + a3
    
    One way of doing this sum is to push a2 onto the stack, as show in bellow figure. Here SP has been incremented by the number of bytes in a word, say, 4, and the first operand stored at the address now pointed to by SP. Next a3 is pushed onto the stack. As an aside on notation, we will typeset all program fragments in Helvetica, as above.
    
    The actual computation can be done by now executing an instruction that pops two words off the stack, adds them together, and pushes the result back onto the stack. Finally, the top word can be popped of the stack and stored back in local variable.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f7c1fa9d-596c-4f0a-81ac-e1aeb07ec5d6/Untitled.png)
    
5.  **Convert an expression given in infix notation to postfix and prefix notation, and vice versa.**
    

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/aaa8fe38-4c25-42e4-b0b2-436cfd7524b6/Untitled.png)

## IJVM Instruction Set Architecture

1.  **Explain the IJVM Memory Model (constant pool, local variable frame, operand stack, and method area; CPP, SP, LV and PC registers)**
    
    **The Constant Pool:** This area cannot be written by an IJVM program and consists of constants, strings, and pointers to other areas of memory that can be referenced. It is loaded when the program is brought into memory and not changed afterward. there is an implicit register, CPP, that contains the address of the first word of the constant pool.
    
    **The Local Variable Frame:** For each invocation of a method, an area is allocated for storing variables during the lifetime of the invocation. it is called the local variable frame. At the beginning of this frame reside the parameters (also called arguments) with which the method was invoked. The local variable frame does not include the operand stack, which is separate. However, for efficiency reasons, our implementation chooses to implement the operand stack immediately above the local variable frame. there is an implicit register that contains the address of the first location in the local variable frame. We will call this register LV. The parameters passed at the invocation of the method are stored at the beginning of the local variable frame.
    
    **The Operand Stack:** The stack frame is guaranteed not to exceed a certain size, computed in advance by the Java Compiler. The operand stack space is allocated directly above the local variable frame. In any case, there is an implicit register that contains the address of the top word of the stack.
    
    **The Method Area:** Finally, there is a region of memory containing the program, referred to as the “text” area in a UNIX process. there is an implicit register that contains the address of the instruction to be fetched next. This pointer is referred to as the Program counter, or PC. Unlike the other regions of memory, the Method Area is treated as a byte array.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3933206b-fb7d-4401-a8da-28845d11e2a5/Untitled.png)
    
2.  **Explain the meaning of the IJVM ISA instructions (BIPUSH, DUP, GOTO, IADD, IAND, IFEQ, IFLT, IF_ICMPEQ, IINC, ILOAD, INVOKEVIRTUAL, IOR, IRETURN, ISTORE, ISUB. LDC_W, NOP, POP, SWAP, and WIDE)**
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bd64d059-2377-42c2-b5af-32c5ddcf2f86/Untitled.png)
    
3.  **Given Figure 4-11 (including its caption), assemble a human-readable IJVM/JAS program into an IJVM binary program**
    
4.  **Given Figure 4-11 (including its caption), disassemble an IJVM binary program into a human-readable IJVM/JAS program**
    
5.  **Given an IJVM/JAS program and the contents of the operand stack, the current values of the local variables, and the contents of the constant pool, interpret the program (i.e., be able to write out Microinstructions for it, and/or count the number of Microinstructions needed to execute it)**
    
6.  **Given the contents of all registers, the constant pool, the method area, and the stack, interpret the (IJVM) byte codes in the method area and show how they change the contents of the registers and the stack (that is, show exactly how the Mic-1 would interpret the program)**
    
7.  **Given a subroutine definition (input parameters, output parameters, local variables), write IJVM assembly code that calls this subroutine and that uses the return value of the subroutine**
    
8.  **Given a subroutine definition (input parameters, output parameters, local variables), write IJVM assembly code for a subroutine, i.e., write IJVM assembly code that accesses parameters and local variables, and that provides a return value upon returning**
    

## Mic-1 Design Improvements

1.  **Give an example of how Micro-Architecture design trades-off speed vs. costs**
    
    While faster technology has resulted in the greatest speedup over any period of time, that is beyond the scope of this text. Speed improvements due to organization, while less amazing than that due to faster circuits, have nevertheless been impressive. Speed can be measured in a variety of ways, but given a circuit technology and an ISA, there are thee basic approaches for increasing the speed of execution:
    
    1.  Reduce the number of clock cycles needed to execute an instruction.
    2.  Simplify the organization so that the clock cycle can be shorter.
    3.  Overlap the execution of instructions.
    
    The number of clock cycles needed to execute a set of operations is known as the **path length.** Sometime the path length can be shortened by adding specialized hardware. For example, by adding an incrementer to PC, we no longer have to use the ALU to advance PC, eliminating cycles.
    
2.  **Give three examples how the execution path length in the Mic-1 design can be shortened**
    
    The Mic-1 was designed to be both moderately simple and moderately fast although there is admittedly an enormous tension between these two goals.
    
    Having seen how IJVM can be implemented in a straightforward way in microcode with little hardware, it is now time to look at alternative, faster implementation. We will next look at ways to reduce the number of micro-instructions per ISA instruction.
    
    **Merging the Interpreter Loop with the Microcode**
    
    In the MIC-1, the main loop consists of one micro-instruction that must be executed at the beginning of every IJVM instruction. In some cases it is possible to overlap it with the previous instruction.
    
    The main loop can in be reduced to nothing in some cases. This can occur in the following way. Consider each sequence of micro-instruction that terminates by branching to Main1. At each of these places, the main loop micro-instruction can be tacked on the end of the sequence (rather than at the beginning of the following sequence), with the multi way branch now replicated man places.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25305033-c847-4548-a10b-cb8913d8d2e4/Untitled.png)
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/85748205-75d5-47ef-b720-8d5dfb175505/Untitled.png)
    
    **A Three-Bus Architecture**
    
    Another easy fix to reduce the execution path length is to have two full input buses to the ALU, an A bus and a B bus, giving three buses in all. All of the register should have access to both input buses. The advantage of having two input buses is that it then becomes possible to add any register to any other register in one cycle.
    
    Many times the ALU is used often to copy a value from one register to another. Thee cycles might be eliminated by introducing additional data paths not going through the ALU.
    
    In the Mic-1, much of the load can be removed from the ALU by creating an independent unit to fetch and process the instructions. This unit, called an **IFU (Instruction Fetch Unit),** can independently increment PC and fetch bytes from the byte stream before they are needed.
    
    **An Instruction Fetch Unit**
    
    To get a dramatic improvement we need something much more radical. Ever instruction the following operations may occur:
    
    1.  The PC is passed through the ALU and incremented.
    2.  The PC is used to fetch the next byte in the instruction stream.
    3.  Operands are read from memory.
    4.  Operands are written to memory.
    5.  The ALU does a computation and the results are stored back
3.  **Draw up the Finite State Machine for the Mic-2 Instruction Fetch Unit (IFU)**
    

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/784e2943-9bd7-48a0-a58e-751680c79b93/Untitled.png)

1.  **Explain the rationale for inserting additional latches (A, B, and C-latch) into the Mic-3 datapath**
    
    The MIC-2 is clearly an improvement over the MIC-1. It is faster and uses less control store, although the cost of the IFU will undoubtedly more that offset the real estate won by having a smaller control store. Thus it is a considerably faster machine at a marginally higher price.
    
    It could still get faster by trying to decrease the cycle time. To a considerable extend, the cycle time is determined by the underlying technology. The smaller the transistors and the smaller the physical distances between them, the faster the class can be run.
    
    However, this option is not possible, hence another option is to introduce more parallelism into the machine. At the moment, the Mic-2 is highly sequential. It puts registers onto its buses, waits for the ALU and shifter to process them. and then writes the results back to the registers. Except for the IFU, little parallelism is present. Adding parallelism is a real opportunity.
    
    The clock cycle is limited by the time needed for the signals to propagate through the data path. There tends to be a delay through various components during each cycle. there three major components to the actual data path cycle:
    
    1.  The time to drive the selected registers onto the A and B buses.
    2.  The time for the ALU and shifter to do their work
        1.  The time for the results to get back to the registers and be stored.
    
    Hence a new three-bus architecture, including the IFU, but with three additional latches (registers), one inserted in the middle of each bus. the latches are written on every cycle.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/784e2943-9bd7-48a0-a58e-751680c79b93/Untitled.png)
    
    How can these extra registers possibly help? Now it takes three clock cycles to use the data path: one fore loading the A and B latches, one for running the ALU and shifter and loading the C latch, and one for storing the C latch back into the registers. The point of inserting the latches is twofold:
    
    1.  We can speed up the clock because the maximum delay is now shorter
    2.  We can use all parts of the data path during every cycle.
2.  **Given Figure 4-30 (the Mic-2 microprogram) and Figure 4-31 (the Mic-3 datapath), determine the number of cycles needed to execute a particular instruction (e.g., using a table like in Figure 4-33)**
    
3.  **Explain the term _hazard_ in the context of the Mic-3 design**
    
    Sometimes when the tasks are being done in the cycle, in a cycle a particular operation may still not be done. The situation that a micro-step cannot start because it is waiting for a result that a previous micro-step has not yet produced is called a **true dependence** or a **RAW dependence.** Dependences are often referred to as **hazards.** RAW stands for Read after Write and indicates that a micro-step wants to read a register that has not yet been written.
    
4.  **Explain how the Mic-4 design is able to continue pipelining even beyond branch instructions (i.e., explain the use of its decoding and queuing unit)**
    
    **Decoding Unit:**
    
    In the decoding unit we have a table to know if the byte is an opcode or an operand. The decoding unit needs to know what is the length of the opcode and look up what it is e.g. IADD and execute accordingly.
    
    **Queuing Unit:**
    
    They are listed on after the other and there is a bit flag that says if the command is done so we can execute a new one.
    
    **Decoding Unit and Queuing Unit:**
    
    We don’t have NEXT ADDRESS anymore and the Micro-instructions will not be selected and GOTO their own successor because it is too late if we want to implement the latched data path. We have only the Decoding and Queuing Unit feeding into the data path while the previous command is still running. Therefore trailing command GOTOs are redundant.
    

## Instruction Formats

1.  **Explain the purpose of an opcode and an operand**
    
    Each assembly language statement is split into an **opcode** and an **operand**. The opcode is the instructions that is executed by the CPU and the operand is the data or memory locations used to execute that instruction.
    
    An operand (written using hexadecimal notation) provides the data itself, or the location where the data to be processed is stored. Some instructions do not require an operand and some may requires more that one operand.
    

## Branch Prediction

1.  **Explain the difference between _dynamic branch prediction_ and _static branch prediction_**
2.  **Explain the purpose of _delay slots_ in the design of pipelines machines**

-   the CPU attempts to overlap instruction execution by pipelining

1.  **Given an IJVM/JAS program and the contents of all registers, the constant pool, the method area, and the stack, maintain a 1-bit or 2-bit _branch history table_**

## Out of Order Execution, Speculative Execution

1.  **Explain the benefits of in-order retiring over out-of-order retiring**
2.  **Explain the three different types of hazards (RAW, WAR, WAW) and how they can be addressed in a superscalar machine**
3.  **Given a set of ISA-level instructions and a machine configuration (i.e., how many instructions can be decoded and issued per cycle, and what type of issuing and retiring - in-order or out-of-order - is permitted), write out a per-cycle scoreboard of all instructions issued and retired in each cycle**
4.  **Explain the concept of hoisting in the context of speculative execution**