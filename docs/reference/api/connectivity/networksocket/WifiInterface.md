## Wi-Fi

<span class="images">![](https://os.mbed.com/docs/v5.8/mbed-os-api-doxy/class_wi_fi_interface.png)<span>WiFiInterface class hierarchy</span></span>

The WifiInterface provides a simple C++ API for connecting to the internet over a Wi-Fi device.

### Wi-Fi class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/v5.8/mbed-os-api-doxy/class_wi_fi_interface.html)

### Usage

To bring up the network interface of an external Wi-Fi device (for example, the ESP8266Interface):

1. Instantiate an implementation of the WiFiInterface class.
    1. Initialize the AT command parser.
1. Call the `connect` function with an SSID and password for the Wi-Fi network.
    1. Command the Wi-Fi device to connect to network.
1. Once connected, you can use the WiFiInterface as a target for opening [network sockets](/docs/v5.8/reference/network-socket.html).

### Troubleshooting information

Network interface `connect` failure reasons:

1. Check that the SSID and password are correct.
1. Check that the IP address configuration service is working.

### Wi-Fi example

Here is an example of an HTTP client program. The program brings up an ESP8266 as the underlying network interface, and uses it to perform an HTTP transaction over a TCPSocket. There are multiple [Wi-Fi components](https://os.mbed.com/components/cat/wifi/) that implement the WiFiInterface class. The example below uses the [ESP8266Interface](https://github.com/armmbed/esp8266-driver) and [OdinWiFiInterface](https://github.com/u-blox/ublox-odin-w2-drivers-docs-mbed-5). 

The ESP8266Interface uses AT commands over serial interface to connect to an external Wi-Fi device. The OdinWiFiInterface provides an Ethernet-like driver to the Mbed OS network stack. The network stack uses the driver to connect to Wi-Fi:

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/TCPSocketWiFi_Example/)](https://os.mbed.com/teams/mbed_example/code/TCPSocketWiFi_Example/file/6a4e57edc2b2/main.cpp)

### Related content

- [Wi-Fi components](https://os.mbed.com/components/cat/wifi/).
- [Network socket](/docs/v5.8/reference/network-socket.html) API overview.
