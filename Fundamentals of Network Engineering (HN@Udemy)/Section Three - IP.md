- Internet Protocol (IP) : which is a set of rules for routing and addressing data packets online
- IP Address : Is a unique address that Identify a network.
- IP Address is layer 3 property
- Can Be set automatically or statically
- A.B.C.D/X (IP Address or subnet)
  - Has 'X' Bits represent Network.
  - The rest of Bits represent Host.
  - So we can Have 2^X netowrks, 2^Rest hosts
---
- Subnet mask : an IP Address isolating Network portion (e.g. 255.255.255.0) .
- If you got Two different IPs `192.168.1.1`, `192.168.1.2`, you can use `255.255.255.0` as a subnet mask .. so when you AND each IP with this mask it produces the same network bits `192.168.1.0`. 
- Each Subnet have a subnet mask, why? To know wheter the reciever's IP address in the same subnet of the sender ... Why again ?! to call it through MAC Address if they are in the same subnet, or use IP Address if reciever outside.
---
- Each Network has the IP Address of the target router or the gateway (the first router to get the packets from this network)
- Why Public Networks is Insecure ? Because a device within the network can act as a target router and get the packets and decrypt it in his device.
---
<img width="980" height="505" alt="New Project" src="https://github.com/user-attachments/assets/82ae35ba-e24c-4b28-9c8d-d3c124613753" />


- IP Packet : a unit of data specifically formatted for transport over the Internet Protocol (IP) network.
- 20 Bytes for headers (up to 60 if options included) + Data (up to 65,535 bytes) (Limited by MTU)
- MTU (Max transimission unit) : the largest size of a data packet, measured in bytes, that can be sent in a single network transmission
- if Data > MTU, so u need to fragment ur packet.

- Anatomy of IP Packet (not all of them):
  - Version(4 bits) : IPV4 or IPV6 *so it used only 3 bits*
  - IHL (4) : options length
  - Total Length (16) : packet length
  - Identification (16) : Unique Id for identifying the group of fragments (if fragmented).
  - Flags(3) : flags used in the fragemtation opertion. 
  - Fragment Offset: Represents the number of Data Bytes ahead of the particular fragment in the particular Datagram.
  - Time to live: how many hops packet visit till its death (to avoid circular or infinity routes)
  - Protocol: Name of the protocol to which the data is to be passed.
 
