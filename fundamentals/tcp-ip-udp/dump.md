

# Transmission Control Protocol (TCP)

TCP is the fundamental way data is transferred over networks. You can think of TCP as a package delivery system. TCP/UDP is the process of encapsulating and decapsulating packets on a network. 

**IP is connection-less**, this means every packet is treated individually and separately on the network. Packets can also arrive to their destination out of the order they were sent. Delivery and Error-free delivery are not guaranteed.
## Comparing TCP and UDP

## Encapsulation Types

Encapsulation occurs at the different layers of the OSI Model. These units are called (PDU's) or, Protocol Data Units.

- Layer 1: Bits (ETH/RJ45)
- Layer 2: Frames (MAC Addresses)
- Layer 3: Packets (IP Addresses)
- Layer 4: Segments (TCP/UDP)
- Layer 5-7: Data

### UDP vs TCP

**UDP**

UDP is similar to IP being connection-less. Delivery and quality of data is not guaranteed with UDP. It prioritizes speed and delivery over quality and accuracy.

**TCP**

Is a connection based network protocol. It uses a 3-way handshake to provide delivery acknowledgement and reliability. The 3-way handshake starts with a SYN(Synchronize) packet, the receiver of the SYN packet will respond with ACK, the sender will then send SYN-ACK to complete the connection and start data transfer.

#### Socket

Sockets are combinations of the IP Address of the host, the port number used, and protocol used. These 3 variables are called a socket.

#### Session Multiplexing

A single host with a single IP Address is able to communicate with multiple servers. Without this feature, we would not be able to operate the way we do today. You right now are most likely using session multiplexing.

#### Maximum Transmission Unit

This is the largest packet that can be transmitted over a medium. This is specific the the medium.

- TCP supports 65495 bytes
- FastETH supports 1500 bytes

#### Maximum Segment Size (MSS)

#### Path MTU Discovery

#### Flow Control

Sliding windows.


