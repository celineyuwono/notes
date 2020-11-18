## Rest API

### Source URL: https://www.youtube.com/watch?v=pY-oje5b5Qk&list=LL

### Tim Berners-Lee
- Scientist at CERN, inventor of WWW.
- Implemented the first successful communication between a HTTP client and server via the Internet.
- Internet already has TCP, IP, and DNS. New protocol = HTTP.
- Existing Hypertext Standard: Documents with links that connects with other documents.

### HTTP Request Authentication (Django)
1. Basic Authorization: For testing
![Basic Auth](https://i.ibb.co/KVRF33t/Screen-Shot-2020-11-18-at-17-34-57.png)
2. Session Authorization: Simple website
![Session Auth](https://i.ibb.co/VHRGbC5/Screen-Shot-2020-11-18-at-17-36-35.png)
Cons: Multiple session between multiple devices and multiple servers.
3. Token Authorization: Recommended DEFAULT
![Token Auth](https://i.ibb.co/xfBLpJc/Screen-Shot-2020-11-18-at-17-39-29.png)
Cons: Never expire, so if token is stolen, anyone can use it.


### JWT
- Payload
- Header
- Verify Signature
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxODQ1NjIxMF19
-->