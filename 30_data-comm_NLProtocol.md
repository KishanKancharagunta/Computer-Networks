# Network Layer Protocols

## IPv4 Header
![](fig/IP4v-header.png)

- Version: IP protocol version
    + 4 bits
- Header Length: total_length / 4
    + 4 bits
- Differentiated Services Field: type of service
    + 8 bits
- Total Length: data_length + header_length
    + 16 bits
    + max length: 2<sup>16</sup>=65,535
    + data lenght=total_length - header_length
- Identification: 0x7a57
- Flags: 0x00
- Fragement offset: 0
- Time to live: 80 (128)
- Protocol:
    + 1 ICMP
    + 2 IGMP
    + 6 TCP
    + 17 UDP
- Header checksum: 0x3caf
- Source: 0xc0a8013b
- Destination: 0xc0a80101

### IPv4 Header Wireshark example
![](fig/IP4v-header-ex.png)

- Version: 4
    + 4 bits
    + IP protocol version 
- Header Length: 5 (20 bytes)
    + 4 bits
    + (total_length/4)
- Differentiated Services Field: 0x00
    + 8 bits
    + type of service
- Total Length: 0x5a (90 bytes)
    + 16 bits
    + max length: 2<sup>16</sup>=65,535
    + data lenght=total_length - header_length
- Identification: 0x7a57
- Flags: 0x00
- Fragement offset: 0
- Time to live: 80 (128)
- Protocol: 11 (17, UDP)
- Header checksum: 0x3caf
- Source: 0xc0a8013b
- Destination: 0xc0a80101