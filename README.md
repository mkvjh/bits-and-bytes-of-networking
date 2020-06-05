# bits-and-bytes-of-networking
it's my notes I created while studying this course on coursera

an IP address will be assigned to it automatically through a technology known as Dynamic Host Configuration Protocol. An IP address assigned this way is known as a dynamic IP address
IP Datagrams and Encapsulation
5:28 - 5:54
Up next, we have the IP options field. This is an optional field and is used to set special characteristics for datagrams primarily used for testing purposes. The IP options field is usually followed by a padding field. Since the IP options field is both optional and variable in length, the padding field is just a series of zeros used to ensure the header is the correct total size.
IP Datagrams and Encapsulation
5:12 - 5:28
After all of that, we finally get to two very important fields, the source and destination IP address fields. Remember that an IP address is a 32 bit number so, it should come as no surprise that these fields are each 32 bits long
IP Datagrams and Encapsulation
4:48 - 5:12
So next, we find the header checksum field. This field is a checksum of the contents of the entire IP datagram header. It functions very much like the Ethernet checksum field we discussed in the last module. Since the TTL field has to be recomputed at every router that a datagram touches, the checksum field necessarily changes, too.
IP Datagrams and Encapsulation
3:41 - 4:01
This field is an 8-bit field that indicates how many router hops a datagram can traverse before it's thrown away. Every time a datagram reaches a new router, that router decrements the TTL field by one. Once this value reaches zero, a router knows it doesn't have to forward the datagram any further.
IP Datagrams and Encapsulation
3:01 - 3:14
Fragmentation is the process of taking a single IP datagram and splitting it up into several smaller datagrams. While most networks operate with similar settings in terms of what size an IP datagram is allowed to be,
IP Datagrams and Encapsulation
2:46 - 3:01
Next up, we have two closely related fields. The flag field and the Fragmentation Offset field. The flag field is used to indicate if a datagram is allowed to be fragmented, or to indicate that the datagram has already been fragmented.
IP Datagrams and Encapsulation
1:59 - 2:35
The identification field, is a 16-bit number that's used to group messages together. IP datagrams have a maximum size and you might already be able to figure out what that is. Since the Total Length field is 16 bits, and this field indicates the size of an individual datagram, the maximum size of a single datagram is the largest number you can represent with 16 bits: 65,535. If the total amount of data that needs to be sent is larger than what can fit in a single datagram, the IP layer needs to split this data up into many individual packets.
IP Datagrams and Encapsulation
1:48 - 1:59
The next field is a 16 bit field, known as the Total Length field. It's used for exactly what it sounds like; to indicate the total length of the IP datagram it's attached to
IP Datagrams and Encapsulation
1:28 - 1:48
Next, we have the Service Type field. These eight bits can be used to specify details about quality of service or QoS technologies. The important takeaway about QoS is that there are services that allow routers to make decisions about which IP datagram may be more important than others.
IP Datagrams and Encapsulation
1:04 - 1:28
After the version field, we have the Header Length field. This is also a four bit field that declares how long the entire header is. This is almost always 20 bytes in length when dealing with IPv4. In fact, 20 bytes is the minimum length of an IP header. You couldn't fit all the data you need for a properly formatted IP header in any less space.
IP Datagrams and Encapsulation
0:42 - 0:56
The very first field is four bits, and indicates what version of Internet protocol is being used. The most common version of IP is version four or IPv4
IP Datagrams and Encapsulation
0:18 - 0:36
Under the IP protocol, a packet is usually referred to as an IP datagram. Just like any Ethernet frame, an IP datagram is a highly structured series of fields that are strictly defined. The two primary sections of an IP datagram are the header and the payload
IP Address Classes
1:50 - 2:09
If the very first bit of an IP address is a zero, it belongs to a class A network, if the first bits are one, zero, it belongs to a class B network. Finally, if the first bits are 110, it belongs to a class C network.
IP Address Classes
0:36 - 1:22
The address class system is a way of defining how the global IP address space is split up. There are three primary types of address classes. Class A, class B, and class C. Class A addresses are those where the first octet is used for the network ID, and the last three are used for the host ID. Class B addresses are where the first two octets are used for the network ID, and the second two, are used for the host ID. Class C addresses, as you might have guessed, are those where the first three octets are used for the network ID, and only the final octet is used for the host ID. Each address class represents a network of vastly different size.
IP Address Classes
0:10 - 0:25
IP addresses can be split into two sections, the network ID, and the host ID. Earlier, we mentioned that IBM owns all IP addresses that having a nine as the value of the first octet in an IP address
Address Resolution Protocol
0:28 - 0:34
ARP is a protocol used to discover the hardware address of a node with a certain IP address.
Subnet Masks
3:23 - 3:41
A subnet mask is a binary number that has two sections. The beginning part, which is the mask itself is a string of ones just zeros come after this, the subnet mask, which is the part of the number with all the ones, tells us what we can ignore when computing a host ID.
Subnet Masks
0:10 - 0:20
network IDs, which are used to identify networks, and host IDs, which are used to identify individual hosts
CIDR
1:56 - 2:09
we relied on a network ID, subnet ID, and host ID to deliver an IP datagram to the correct location. With CIDR, the network ID and subnet ID are combined into one
CIDR
1:46 - 1:56
When discussing computer networking, you'll often hear the term demarcation point to describe where one network or system ends and another one begins.
CIDR
1:28 - 1:43
his is where CIDR or classless inter-domain routing comes into play. CIDR is an even more flexible approach to describing blocks of IP addresses. It expands on the concept of subnetting by using subnet masks to demarcate networks
CIDR
0:29 - 0:53
With traditional subnetting and the address classes, the network ID is always either 8 bit for class A networks, 16 bit for class B networks, or 24 bit for class C networks. This means that there might only be 254 classing networks in existence, but it also means there are 2,970,152 potential class C networks.
Basic Routing Concepts
1:40 - 1:55
From a very basic standpoint, a router is a network device that forwards traffic depending on the destination address of that traffic. A router is a device that has at least two network interfaces, since it has to be connected to two networks to do its job.
Dissection of a TCP Segment
0:48 - 1:13
A TCP segment is made up of a TCP header and a data section. This data section, as you might guess, is just another payload area for where the application layer places its data. A TCP header itself is split into lots of fields containing lots of information.
The Many Steps of Name Resolution
1:25 - 1:37
There are five primary types of DNS servers; caching name servers, recursive name servers, root name servers, TLD name servers, and authoritative name servers.
DNS and UDP
3:14 - 3:39
This brings us to a grand total of 44 packets at the minimum in order for a fully recursive DNS request to be fulfilled via TCP. 44 packets isn't really a huge number in terms of how fast modern networks operate. But it adds up fast as you can see.
Overview of DHCP
1:04 - 1:34
DHCP is an application layer protocol that automates the configuration process of hosts on a network. With DHCP, a machine can query a DHCP server when the computer connects to the network and receive all the network configuration in one go. Not only does DHCP reduce the administrative overhead of having to configure lots of network devices on a single network, it also helps address the problem of having to choose what IP to assign to what machine.
DHCP in Action
0:39 - 2:25
The process by which a client configured to use DHCP attempts to get network configuration information is known as DHCP discovery. The DHCP discovery process has four steps. First, we have the server discovery step. The DHCP clients sends what's known as a DHCP discover message out onto the network. Since the machine doesn't have an IP and it doesn't know the IP of the DHCP server, a specially crafted broadcast message is formed instead. DHCP listens on UDP port 67 and DHCP discovery messages are always sent from UDP port 68. So the DHCPDISCOVER message is encapsulated in a UDP datagram with a destination port of 67 and a source port of 68. This is then encapsulated inside of an IP datagram with a destination IP of 255.255.255.255, and a source IP of 0.0.0.0. This broadcast message would get delivered to every node on the local area network. And if a DHCP server is present, it would receive this message. Next, the DHCP server would examine its own configuration and would make a decision on what, if any, IP address to offer to the client. This would depend on if it's configured to run with dynamic, automatic or fixed address allocation. The response would be sent as a DHCPOFFER message with a destination port of 68, a source port of 67, a destination broadcast IP of 255.255.255.255, and its actual IP as the source.
Go to videonote
NAT and the Transport Layer
2:01 - 2:13
Now, when traffic returns to the router and port 51,300, it knows that this traffic needs to be forwarded back to the IP 10.1.1.100.
Fiber Connections
2:32 - 2:49
Instead of a modem, the demarcation point for fiber technologies is known as Optical Network Terminator, or ONT. An ONT converts data from protocols the fiber network can understand to those that are more traditional twisted pair copper networks can understand.
Introduction to Troubleshooting and the Future of Networking
0:37 - 0:49
Error-detection, is the ability for a protocol or program to determine that something went wrong. Error-recovery is the ability for a protocol or program to attempt to fix it
Traceroute
2:26 - 2:57
Two more tools that are similar to traceroute are mtr on Linux and MacOS and pathping on Windows. These two tools act as long running traceroutes. So you can better see how things change over a period of time. Mtr works in real time and will continually update its output with all the current aggregate data about the traceroute. You can compare this with pathping, which runs for 50 seconds and then displays the final aggregate data all at once.
Traceroute
2:06 - 2:26
On Windows, the command has a shortened name tracert, and defaults to using ICMP echo request. On all platforms, traceroute has more options than can be specified using command line flags

