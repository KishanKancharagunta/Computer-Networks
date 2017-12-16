# Routing Protocol
## Least-Cost Routing
- Internet is modeled as a weighted graph
- Find the least cost between the source to the destination router
- The source router chooses a route to the destination router in such a way that the total cost for the route is the least cost among all possible routes. 

![](fig/Least-Cost-Tree.png)

# Routing Algorithm
## Bellman-Ford Equation
  - __D<sub>_ij_</sub>__ is the shortest distance and __c<sub>_ij_</sub>__ is the cost between nodes ___i___ and ___j___.
- __D<sub>_xy_</sub> = min{(c<sub>_xa_</sub> + D<sub>_ay_</sub>), (c<sub>_xb_</sub> + D<sub>_by_</sub>), (c<sub>_xc_</sub> + D<sub>_cy_</sub>),...}__

![](fig/Bellman-Ford-a.png)

- __D<sub>_xy_</sub> = min{D<sub>_xy_</sub>, (c<sub>_xz_</sub> + D<sub>_zy_</sub>)}__

![](fig/Bellman-Ford-b.png)


## Distance Vector Algorithm
- each node creates is its own least-cost tree about its immediate neighbors
- exchange information between immediate neighbors to make the tree more and more complete

![](fig/distance-vector.png)

- B receives a copy of A’s vector

  ![](fig/DV-update-1.png)

- B receives a copy of E’s vector

  ![](fig/DV-update-2.png)

![](fig/DVR-algo.png)

### Problem of Distance Vector Algorithm
- Count to Infinity
  - if a link is broken (cost becomes infinity), every other router should be aware of it immediately, but in distance-vector routing, this takes some time
- Two-Node Loop
  - ![](fig/Two-Node-Loop.png)

### Solution of problem of Distance Vector Algorithm
- Split Horizon
  - if node B thinks that the optimum route to reach X is via A, it does not need to advertise this piece of information to A
  - In our scenario, node B eliminates the last line of its forwarding table before it sends it to A. In this case, node A keeps the value of infinity as the distance to X. Later, when node A sends its forwarding table to B, node B also corrects its forwarding table.

## Link State Algorithm
