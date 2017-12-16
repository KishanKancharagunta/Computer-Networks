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

## Link State Algorithm
