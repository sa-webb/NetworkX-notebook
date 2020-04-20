# Dijkstra's Pseudocode

1. Mark all nodes as unvisited by creating a set of all unvisited nodes called unvisited set. 

2. Assign every node a tentative (uncertain) distance value: set it to zero for the intitial node and to infinity for all other nodes. Set the initial starting node as current.

3. For the current node, consider all of its unvisited neighbors and calculate their tentative distances through the current node. Compare the newly calculated tentative distance to the current assigned value and assign the smaller one. 

For **example**, if the current node A is marked with a distance of 6, and the edge connecting it with a neighbor B has length 2, then the distance to B through A will be 6 + 2 = 8. If B was previously marked with a distance greater than 8 then change it to 8. Otherwise, keep the current value.

4. When we are done considering all of the unvisited neighbors of the current node, mark the current node as visited and remove it from the unvisited set. A visited node will never be checked again.

5. If the destination node has been visited, then stop.

6. Otherwise, select the unvisited node that is marked with the smallest tenative distance, set is as the new "current node", and go back to step 3.

