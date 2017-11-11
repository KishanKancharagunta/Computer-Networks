Please refer to textbook [chapter 13](https://github.com/cnchenpu/data-comm/blob/master/ppt/Ch13-Forouzan.ppt).

# General Network Issues (Pro and Con)
- Selecting the transmission medium
  - Wired
  - Wireless
- Selecting the link configuration
  - Point-to-point
    - dedicated link for users high, predictable performance
    - need many links, planning of end-points
  - Point-to-multipoint
    - cover multiple users with single link
    - requires sharing of medium: Media Access Control protocol for multiple access
      -  allow one station to use the shared medium at a time 
- Coverage area
  - LAN
  - WAN
  - Backbone
- Network topology
  - Mesh
    - each pair of nodes have dedicated point-to-point link
    - complex and expansive for large network
    - addresses not needed in frames
  - Bus
    - early Ethernet 
    - single multipoint link connects all stations
    - require protocols to share medium
    - faulty link stops all communications
    - limited number of stations
  - Ring
    - Token Ring
    - same as Bus topology
  - Star
    - today most LAN use Star topology
    - fault tolerance for links

![](fig/backbone-network.png)

![](fig/network-topology.png)
