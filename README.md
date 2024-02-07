<h1>Net_Practice Basics:</h1>

**IPv4 addressing:** An IPv4 address consists of four 8-bit blocks, represented in decimal or binary format. For instance, 192.168.100.1 in decimal becomes 11000000.10101000.01100100.00000001 in binary. The minimum value for a block is 0 and the maximum is 255.

```
192.168.100.1  = 11000000.10101000.01100100.00000001
```

**Private networks:** Special IP ranges reserved for private networks are 10.0.0.0 - 10.255.255.255, 172.16.0.0 - 172.31.255.255, and 192.168.0.0 - 192.168.255.255.

**Loopback addresses:** The range 127.0.0.0 - 127.255.255.255 is reserved for loopback addresses.

**Subnet masks:** Masks define which IP ranges belong to the same subnet. They can be written in two ways—dot-decimal notation (e.g., 255.255.255.0) 

**Classless Inter-Domain Routing (CIDR)** notation (e.g., /24). As you increase the number of usable IP addresses within a subnet, the number of possible subnets decreases. This table helps illustrate the relationship:
| CIDR   | Dot-decimal       | Number of IP addresses per subnet | Usable IP addresses per subnet | Number of subnets |
|---      | ---               | ---                              | ---                           | ---              |
| /32     | 255.255.255.255   | 1                                | 0                              | 256              |
| /31     | 255.255.255.254   | 2                                | 0                              | 128              |
| /30     | 255.255.255.252   | 4                                | 2                              | 64               |
| /29     | 255.255.255.248   | 8                                | 6                              | 32               |
| /28     | 255.255.255.240   | 16                               | 14 (out of 16)                | 16               |
| /27     | 255.255.255.224   | 32                               | 30                             | 8                |
| /26     | 255.255.255.192   | 64                               | 62                             | 4                |
| /25     | 255.255.255.128   | 128                              | 126                            | 2                |
| /24     | 255.255.255.0     | 256                              | 254                            | 1                |

When calculating the usable IP addresses, note that the first address is reserved as the network address and the last address is reserved as a broadcast address.

**Switches:** A switch allows connecting multiple devices to the same network. Its primary function is distributing packets within the network.

**Routers**: Routers facilitate communication between different networks. In Netpractice, routers are represented by the term "Interface." Understanding the basics of routers and switches is essential for success in this project.

**Routing tables:** A routing table stores various routes to networks the device is associated with. It contains two main components: the destination (represented by the network address and CIDR) and the next hop (the address of the subsequent router required for packet delivery toward the destination network).

**Connecting networks:** To establish connections within a network, devices must be linked, either directly or through routers shared by both networks. To determine whether two devices belong to the same network, perform a bitwise AND operation between the IP and mask of each device, then compare the results. If they match, the devices are part of the same network.
