Please refers to textbook [chapter 15](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch15-Forouzan.ppt).

# Wireless LAN (IEEE 802.11)
- [CSMA/CA](https://github.com/cnchenpu/data-comm/blob/master/24_data-comm_datalink-MAC.md#carrire-sense-multiple-access-with-collision-avoidance-csmaca)

![](fig/CSMACA-flow.png)

  - DIFS: Distributed inter-frame space
    - a wait-time before transmission for coordination
  - RTS: Request To Send
  - SIFS: Short Inter-Frame Space
    - a wait-time before RTC, CTS and ACK
  - CTS: Clear To Send
    - inform sender that I am ready to receive your data, and tell others I am busy (to avoid collision)
  - ACK: Acknowledgement
  - NAV: Network Allocation Vector
    - control other nodes not to send data
  - Contention Window
    - random backoff time (to avoid collision)
  
- Ad hoc (Peer-to-Peer)
  - connect without __Access Point (AP)__
- Infrastruct
  - single access point: __Basic Service Set (BSS)__
  - multiple access point: __Extend Service Set (ESS)__
  
  ![](fig/wireless-LAN.png)

## 802.11 a/b/g/n/ac
- 802.11a
  - uses 5-GHz band
  - 54Mbit/s

- 802.11b
  - uses 2.4-GHz band
  - 11Mbit/s
  
- 802.11g
  - uses 2.4-GHz band
  - 54Mbit/s
  
- 802.11n
  - uses 2.4-GHz and 5-GHz band
  - 72~150Mbit/s
  
- 802.11ac
  - uses 5-GHz band
  - 87~866Mbit/s
  
## WLAN Frame Format
![](fig/WLAN-frame.png)

## WLAN Addressing Mechanism
![](fig/WLAN-add-types.png)

- case 1: A to B directlly (in the same BSS)

  ![](fig/WLAN-add-type1.png)

- case 2: A to AP (different BSS)

  ![](fig/WLAN-add-type3.png)

- case 3: AP to B (different BSS)

  ![](fig/WLAN-add-type2.png)

- case 4: AP tp AP (different BSS)

  ![](fig/WLAN-add-type4.png)

## The hidden terminal problem
![](fig/hidden-terminal-problem.png)

## The exposed terminal problem
![](fig/exposed-terminal-problem.png)

- RTS (Request to Send) / CTS (Clear to Send) - Collision-Avoidance
  - Sender transmits special Request-to-send (RTS) packet: the packet contains the length of data to be sent, L.
  - Receiver replies with Clear-to-send (CTS) packet: this packet also contains the length of data (same as before).
  - Every node hearing the RTS remains quiet for CTS+L.
  - Every node hearing the CTS remains quiet for L.
  - If sender does not receive CTS, it knows the receiver is busy and does not transmit data.
  - CTS/RTS packets may still collide, but they are small, so the probability of collisions is reduced.
  
  ![](fig/RTS-CTS.png)

## HW : How to solve the Exposed Terminal Problem (due date: 12/4)

# Mobile IP
  - Roaming issue 
  - Home Agent(HA): A router on the home network which represents the MN while it’s not attached to the home network
  - Home Address (HoA): A (static) IP address out of the mobile nodes home network
  - Foreign Agent(FA): new visited place and provides Care of Address (CoA)
  - Mobile Node(MN)
  - Correspondent Node(CN): send message to MN
  - Care-of-Address(CoA): physical IP address of a MN while visiting a foreign network
  - Binding: association of the home address with the Care-of-address of a MN

  ![](fig/MobileIP.png)
  
- MN connects to foreign network and gets a CoA
- MN sends binding updateto HA
- HA uses proxy neighbor discovery (ARP) to represent the MN in the home network
- Every traffic destined to the MN will be encapsulated in a IPv6-in-IPv6 Tunnel and send to the CoA of the MN
  
## Mobile IP Registration
![](fig/mobileip-reg.gif)
  
  ![](fig/mobile-encap.gif)

## Mobile IP Routing issues
- Traffic from MN will be send directly to CN, but outgoing traffic can't use the HoA as source address (anti-spoofing)

  ![](fig/mobileIP-route1.png)

- Routing optimization
  1. MN sends __binding updates__ to CN
  2. MN sends __traffic to CN__ with CoA as source address
    - packet contains a HoA destination option
  3. CN replace the source address with the home address before passing the packet to the upper layer protocol
  
  ![](fig/mobileIP-route2.png)

  4. CN sends __traffic to MN__ with CoA as destination address
    - packet contains a special __Routing Header__ with HoA as second hop
  5. MN removes the routing header and __forward__ the packet to the next hop specified by the __routing header__
    - upper layer protocol is only aware of HoA
    
  ![](fig/mobileIP-route3.png)


## Wireless LAN security threats
- Signal interception - sniffing
- Unauthorized network access
- Unauthorized AP - no access control and direct access to the intranet behind firewall
- Denial of service - logical attackes with signal jamming
- AP spoofing

  ![](fig/evil-twin-AP.png)

# Bluetooth vs. 802.11b
- Both technologies use the 2.4 GHz radio frequency for wireless communications.
- Bluetooth technology is focused on replacing the short cables used to connect consumer electronic devices such as keyboards and mouse devices.
- Bluetooth's range is limited to approximately 3 m to 9.1 m with a raw data rate of 1 Mbps/723 Kbps available.

## Bluetooth Piconet
![](fig/bluetooth-net.png)

- connection of devices connected in an ___ad hoc___ fasion
- all device participating in the __piconet__ are synchronized to a common clock and frequency
- slaves can communicate only with the master and not with other slaves
- one __Master__
  - set clock and frequency
  - can connect __7 active__ or 255 inactive __(parked) slaves__
  - determines bit rate allocated to each slave

## Bluetooth connection process
1. Inquiry
    - One device sends out the inquiry request, and any device listening for such a request will respond with its address, and possibly its name and other information.
2. Paging (Connecting) 
    - Bonding
      - Bonded devices automatically establish a connection whenever they’re close enough
    - Pairing
      - Bonds are created through one-time a process called pairing.
      - When devices pair up, they share their addresses, names, and profiles, and usually store them in memory. 
      - The also share a common secret key, which allows them to bond whenever they’re together in the future.
3. Connection State
    - Active mode
    - Sniff mode
      - power-saving mode, where the device is less active
      - sleep and only listen for transmissions at a set interval
    - Hold mode
      - a temporary, power-saving mode 
      - device sleeps for a defined period and then returns back to active mode when that interval has passed
      - master can command a slave device to hold
    - Park mode
      - deepest of sleep modes
      - master can command a slave to park, and that slave will become inactive until the master tells it to wake back up   

