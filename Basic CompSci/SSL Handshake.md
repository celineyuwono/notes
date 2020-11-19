## SSL/TLS Handshake

### Source URL: https://www.youtube.com/watch?v=sEkw8ZcxtFk

- Cryptographic protocol that provide security in the internet.
- Used between client and server to establish trust and negotiate which secret key should be used to encrypt and decrypt the conversation.
- Eavesdropper can see connection endpoints, but not data nor modify data.
Steps
1. Client sends message, including 3 things: SSL/TLS version, cryptographic algorithms, data compression methods.
2. Server returns with: cryptographic algorithms chosen, session ID, server's digital certificate, server's public key.
3. Client contacts server's CA.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY0NjAwMzY3M119
-->