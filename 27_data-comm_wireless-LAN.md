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

## WLAN Frame Format
![](fig/WLAN-frame.png)

## WLAN Addressing Mechanism
![](fig/WLAN-add-types.png)

![](fig/WLAN-add-type1.png)

![](fig/WLAN-add-type2.png)

![](fig/WLAN-add-type3.png)

![](fig/WLAN-add-type4.png)

## The hidden terminial problem
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
  
- Roaming issue
  - Mobile IP

- Wireless LAN security issue
  - Unauthorized AP
  ![](fig/evil-twin-AP.png)

## 802.11a
- uses 5-GHz band

## 802.11b

## 802.11g
- higher speed extension to 802.11b 
- operates in 2.4GHz band
- compatible with 802.11b devices

# Bluetooth vs. 802.11b
- Both technologies use the 2.4 GHz radio frequency for wireless communications.
- Bluetooth technology is focused on replacing the short cables used to connect consumer electronic devices such as keyboards and mouse devices.
- Bluetooth's range is limited to approximately 3 m to 9.1 m with a raw data rate of 1 Mbps/723 Kbps available.
