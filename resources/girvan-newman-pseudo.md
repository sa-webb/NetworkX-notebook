# Girvan-Newman Pseudocode

1. Compute the betweenness of all existing edges in the network.

2. Remove the edge with the highest betweenness.

3. Recompute the betweenness of all edges after the removal of this edge.

4. Repeat steps 2 and 3 until no edges remain.

## DOES NOT SCALE