## TCP/IP

### Source URL: https://www.youtube.com/watch?v=kCuyS7ihr_E&list=LL&index=2

### OSI Model vs TCP/IP Model
![TCP/IP model [Internet protocol suite] | Networking basics, Osi model,  Computer basics](https://i.pinimg.com/originals/5d/c8/20/5dc8209ec5c3ede7470f8763b5bb1907.gif)
- Application ~ Session is Application Layer because they handle data. Data is broken up in Transport Layer.

### Application Layer
- Application: Application, protocols, and services that interface with the end user.
- Presentation: Data is formatted, converted, encrypted/decrypted, compressed/decompressed and sent or presented to the user (MIME types). TSL, SSL encryption.
- Session: Open, close, and manage a session between end-user application processes (RPC). 

### Transport Layer
- Facilitate end-to-end communications between multiple application simultaneously (create port numbers). Example. Port 22 (ssh), port 21 (ftp), port 80 (http).
- Reliable and unreliable end-to-end data transport and data stream services. (TCP - reliable -> http, UDP - unreliable -> if no need reliability ex. online feed, live transmission, SCTP mail - new).
- Connection oriented, connectionless communications, and data stream services (session establishment and termination).
- Example: 3 way handshake, establishing connection.

### Network Layer (Internet Layer)
- Packets! Add IP address here. Finds best path of IP address.
- Provide host addressing (IP): Across world and internet.
- Choose the best path to the destination network (Routing)
- Switch packets out of the correct interface (Forwarding)
- Mantain quality of service (QoS). Example. Video needs more bandwidth.
- Connectionless end-to-end networking.

### Network Access Layer
- Data Link: LLC and MSAC.
	- FRAME! MAC address (hardware address, cannot be changed, in every hardware).
	- Error checking.
- Physical: Bits. Actual data transfer, cables, wire.

### Encapsulation
![Encapsulation](https://i.ibb.co/XymwfsS/Screen-Shot-2020-11-18-at-17-57-28.png)

Summary
1. Data
2. TRANSPORT: TH -  Segment 1, TH -  Segment 2
3. NETWORK: (Packet) NH - TH - Segment 1 (Segment 2 same process)
4. DATA LINK: DH - NH - TH - Segment 1
5. PHYSICAL: 010101010101010
6. Physical~Network layer detach in receiving client.
7. Transport layer wait until all segments is received, and combines it, give it to application layer
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MzczMzc5MjksLTE0MzIxNTY5MzYsMT
g2OTk2MTU1NSwtMTQ1NzU3NzMzXX0=
-->