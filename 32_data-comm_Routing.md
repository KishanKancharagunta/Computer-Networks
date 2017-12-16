# Routing Protocol
## Least-Cost Routing
- Internet is modeled as a weighted graph
- Find the least cost between the source to the destination router
- The source router chooses a route to the destination router in such a way that the total cost for the route is the least cost among all possible routes. 

![](fig/Least-Cost-Tree.png)

# Routing Algorithm
## Bellman-Ford Equation
- __D<sub>_ij_</sub>__ is the shortest distance and __c<sub>_ij_</sub>__ is the cost between nodes ___i___ and ___j___.

__D<sub>_xy_</sub> = min{(c<sub>_xa_</sub> + D<sub>_ay_</sub>), (c<sub>_xb_</sub> + D<sub>_by_</sub>), (c<sub>_xc_</sub> + D<sub>_cy_</sub>),...}__

## Distance Vector Algorithm
- each node creates is its own least-cost tree about its immediate neighbors
- exchange information between immediate neighbors to make the tree more and more complete

![](fig/distance-vector.png)

## Link State Algorithm
