## UDPSocket

The UDPSocket class provides the ability to send packets of data over UDP, using the `sendto` and `recvfrom` member functions. Packets can be lost or arrive out of order, so we suggest using a [TCPSocket](/docs/v5.7/reference/tcpsocket.html) when you require guaranteed delivery.

The constructor takes in the NetworkStack pointer to open the socket on the specified NetworkInterface. If you do not pass in the constructor, then you must call `open` to initialize the socket.

### UDPSocket class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/v5.7/mbed-os-api-doxy/class_u_d_p_socket.html)

### UDPSocket Example

Here is a UDP example to read the current UTC time by sending a request to the NIST Internet Time Service.

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets)](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets/file/cf516d904427/main.cpp)

### Related content

- [TCPSocket](/docs/v5.7/reference/tcpsocket.html) API reference.
