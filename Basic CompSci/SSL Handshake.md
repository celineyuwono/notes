## SSL/TLS Handshake

### Source URL: https://www.youtube.com/watch?v=sEkw8ZcxtFk https://www.youtube.com/watch?v=4nGrOpo0Cuc

### What is it?
- Cryptographic protocol that provide security in the internet.
- Used between client and server to establish trust and negotiate which secret key should be used to encrypt and decrypt the conversation.
- Eavesdropper can see connection endpoints, but not data nor modify data.

![SSL/TLS Encryption Process](https://i.ibb.co/kSFw5z8/Screen-Shot-2020-11-19-at-14-07-11.png)

### Steps
1. Through Asymmetric Key Exchange
- Client request SSL connection.
- Server responds with SSL Certificate and Public Key.
- Client verify SSL Certificate.
2. Through Symmetric Key Exchange
- Client generates symmetric key for use of both Client and Server.
- SSL Session is established.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMTM1ODM2OTIsLTY0NjAwMzY3M119
-->