# Algorithms

## 3 Main Categories

* Pathfinding: identify the optimal path depending on availability and quality for example. We’ll also include search algorithms in this category. This can be used to identify the quickest route or traffic routing for example.

* Community detection: evaluate how a group is clustered. This can be used to segment customers and detect fraud for example.

* Centrality: determine the importance of the nodes in the network. This can be used to identify influencers in social media for example or identify potential attack targets in a network.

### Pathfinding and Graph Search

Pathfinding: find the **shortest path** between two nodes

Search: explore graphs by considering neighbors or depths.

#### Search Algorithms

There are two main Graph Search Algorithms **BFS & DFS**

#### Pathfinding Algorithms

Shortest Path calculates the shortest weighted path between a pair of nodes.

Can be used to find a degree of separation between two people on a social network.

Returns shortest path between each node using Dijkstra's algorithm is the default algorithm in Networkx.

`nx.shortest_path(G_karate)`

Single Source Shortest Path:
The Single Source Shortest Path (SSSP) finds the shortest path between a given node and all other nodes in the graph.
It is often used for routing protocol for IP networks for example.

#### Community Detection

Community detection partitions the nodes into several groups according to a given quality criterion.

Typically used to identify social communities, customer behavior or web page topics.

A community is a set of connected nodes (usually densely connected).

Common algorithm to find communities is the Girvan Newman algorithm. 

It identifies communities by progressively removing edges within the network. We’ll refer to betweenness as the “edge betweenness”. It is a score proportional to the number of shortest paths between pairs of nodes that go through this edge.

Louvain Modularity

Modularity  is a measure of how well groups have been partitioned into clusters.

#### Strongly Connected Components

The Strongly Connected Components (SCC) algorithm finds groups of connected nodes in a directed graph. Note that each node must be reachable in both directions from any other node in the same group.

It is often used early in a graph analysis process to give us an idea of how our graph is structured, for example, to explore financial statements data when we look at who owns shared in what company (think about Panama papers for example).

#### Weak Connected Components (Union Find)

The Weakly Connected Components, or Union Find algorithm finds sets of connected nodes in a directed graph where each node is reachable from any other node in the same set.

It only needs a path to exist between pairs of nodes in one direction, whereas SCC needs a path to exist in both directions. As with SCC, Union Find is often used early in analysis to understand a graph’s structure.

Union-Find is a pre-processing step that is essential before any kind of algorithm, to understand the graph’s structure.

#### Hierarchical Clustering

The idea is to analyze community structures at different scales. We usually build the dendrogram bottom-up. We start with a cluster at each node and merge the two “closest” nodes.

But how do we measure if clusters are close? We use similarity distances. Let d(i,j) be the length of the shortest path between i and j.

For the maximum linkage, at each step, the two clusters separated by the shortest distance are combined. The similarity distances can be illustrated as follows : <linkage-example png/>

#### Clustering Coefficient

Measures how well two nodes tend to cluster together.

The local clustering coefficient is a ratio of the number of triangles centered at node i over the number of triples centered at node i. In some sense, it measures how close aa node i and its neighbors are to being a complete graph.

##### Random graph clustering coefficients

Erdos-Renyi: E[Clustering Coefficient]=E[Ci]=p || where p = probability

Barabasi-Albert: the global clustering coefficient follows a power law depending on the number of nodes. The average clustering coefficient of nodes with degree k is proportional to the inverse of k

Nodes with a low degree are connected to other nodes in their community. Nodes with high degrees are linked to nodes in different communities.

### Centrality Algorithms

Centrality measures **how important a node is.** Important for identifying important web pages and bottlenecks in transportation networks.

A walk is a path which can go through the same node several times. Centrality measures vary with the type of walk considered and the way of counting them.

1. PageRank Algorithm

PageRank estimates a current node's importance from its linked neighbors and then again from their respective neighbors.

It's a way of detecting influential nodes in any network. It is used to suggest connections on social networks.

PageRank is usually computed on directed graphs. However, it will also execute on undirected graphs by converting each edge in the directed graph to two edges.

2. Degree Centrality

Degree Centrality is used to identify the most influential persons on a social network for example.

3. Eigenvector Centrality

This gives more importance to nodes with well-connected neighbors.

4. Closeness Centrality

Detects nodes that are can spread information efficiently through a graph.

It can be used to identify fake news accounts or in terrorist cells to isolate the individuals that can spread information to the rest of the graph.

5. Betweenness Centrality

Detects the amount of influence a node has over the flow of information in a graph.

It is often used to find nodes that serve as a bridge from one part of a graph to another, for example in the package delivery processor in a telecommunication network, or in the propagation of fake news.

betweenness-equality.png
where:
σjk the number of shortest paths between j and k
σjk(i) the number of shortest paths between j and k going through i

The betweenness centrality measures the number of times a node acts as a bridge between two nodes.