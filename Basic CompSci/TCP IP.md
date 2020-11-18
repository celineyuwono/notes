## TCP/IP

### Source URL: https://www.youtube.com/watch?v=kCuyS7ihr_E&list=LL&index=2

### OSI Model vs TCP/IP Model
![TCP/IP model [Internet protocol suite] | Networking basics, Osi model,  Computer basics](https://i.pinimg.com/originals/5d/c8/20/5dc8209ec5c3ede7470f8763b5bb1907.gif)
- Application ~ Session is Application Layer because they handle data. Data is broken up in Transport Layer.

### Application Layer
- Application: Application, protocols, and services that interface with the end user.
- Presentation: Data is formatted, converted, encrypted/decrypted, compressed/decompressed and sent or presented to the user (MIME types).
- Session: Open, close, and manage a session between end-user application processes (RPC). 

### Transport Layer
- Facilitate end-to-end communications between multiple application simultaneously (ports). Example. Port 22 (ssh), port 21 (ftp), port 80 (http).
- Reliable and unreliable end-to-end data transport and data stream services (TCP - reliable -> http, UDP - unreliable -> if no need reliability, SCTP mail - new).
- Connection oriented, connectionless communications, and data stream services (session establishment and termination).
- Example: 3 way handshake, establishing connection.

### Network Layer (Internet Layer)
- Provide host addressing (IP): Across world and internet.
- Choose the best path to the destination network (Routing)
- Switch packets out of the correct interface (Forwarding)
- Mantain quality of service (QoS). Example. Video needs more bandwidth.
- Connectionless end-to-end networking.

### Network Access Layer
- Data Link: LLC and MSAC
- Physical: Bits.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMjc5Mzg5MjFdfQ==
-->