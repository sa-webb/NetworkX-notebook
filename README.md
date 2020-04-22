# Graphy Theory exploration using NetworkX

Introduction to Graphs (Part 1)
Graph Algorithms (Part 2)
Learning with Graphs in Python (Part 3)

This code corresponds with [Towards Data Science Introduction to Graphs](https://towardsdatascience.com/introduction-to-graphs-part-1-2de6cda8c5a5)

## Tools

NetworkX is a Python package for the creation, manipulation, and study of the structure, dynamics, and functions of complex networks.

Matplotlib is a Python package for data visualization.

## Networks

Real networks are often scale-free networks inhomogeneous in degree, having hubs and a scale-free degree distribution. Such networks are better described in that respect by the preferential attachment family of models, such as the Barabási–Albert (BA) model.

### Types of Generative Models

#### Erdos-Rényi

ER graphs **do not** have two important properties observed in many real-world networks:

They do not generate local clustering and triadic closures.
Instead, because they have a constant, random, and independent probability of two nodes being connected,
ER graphs have a low clustering coefficient.

Are low in low clustering, unlike many social networks.

They do not account for the formation of hubs. Formally, the degree distribution of ER graphs converges to a Poisson distribution, rather than a **!power law** observed in many real-world, scale-free networks.

#### Barabasi-Albert

The aim of such graph is to model **preferential attachment**, which is often observed in real networks.

A preferential attachment process is any of a class of processes in which some quantity, typically some form of wealth or credit, is distributed among a number of individuals or objects according to how much they already have, so that those who are already wealthy receive more than those who are not. "Preferential attachment" is only the most recent of many names that have been given to such processes.

Barabási–Albert model fails to produce the high levels of clustering seen in real networks, a shortcoming not shared by the Watts and Strogatz model. Thus, neither the Watts and Strogatz model nor the Barabási–Albert model should be viewed as fully realistic.

#### Watts–Strogatz

Is a random graph generation model that produces graphs with small-world properties, including short average path lengths and high clustering.

## Random Graph properties

### Scale-free Graph Property

There are two major components that explain the emergence of the scale-free property in a complex networks: the growth and the preferential attachment.

Growth is where, over an extended period of time, new nodes join an already existing system.

### Preferential Attachment

Preferential Attachment is called a new coming node who prefers to connect to another node which has already a certain number of links with others. Thus, there is a higher probability that more and more nodes will link themselves to that one which has already many links.

* Assortativity would be found in social networks in which well-connected/famous people would tend to know better each other.
* Disassortativity would be found in technological (Internet, World Wide Web) and biological (protein interaction, metabolism)networks.

### Immunization

The question of how to immunize efficiently scale free networks which represent realistic networks such as the Internet and social networks has been studied extensively.

* One such strategy is to immunize the largest degree nodes.
* Realistic nodes the global structure is not available and the largest degree nodes are not known.
* Properties of random graph may change or remain invariant.
[Scale-free Networks](https://en.wikipedia.org/wiki/Scale-free_network)

### Percolation

Percolation Theory describes the behaviour of connected clusters in a random graph.

Bootstrap percolation removes active cells from clusters when they have too few active neighbors, and looks at the connectivity of the remaining cells.

### Graph Learning Tasks

#### Link Prediction

Social media suggestions after signup.

predict future relations or missing edges.

##### Similarity scoring

Common neighbors

Intersection : S(i,j)=∣ N(i) ∩ N(j)∣

Union : S(i,j)=∣ N(i) ∩ N(j)∣

Jaccard Coefficient = Intersection / Union

Preferential attachment : S(i,j)=∣N(i,j)∣∗∣N(j)∣

Adamic-Adar index
Common elements with very large neighborhoods are less significant.
When predicting a connection between two nodes compared to elements shared between a small number of nodes.
For each common neighbor of nodes i and j,
we add 1 divided by the total number of neighbors of that node.

##### Performance metrics

How do we perform the evaluation of the link prediction? We must hide a subset of node pairs, and predict their links based on the rules defined above. This is the equivalent of the train-test-split in supervised learning.
We then evaluate the proportion of correct predictions for dense graphs, or use Area under the Curve criteria for Sparse graphs.

##### Implementation

Corresponds to [Jupyter Notebook](Graph-Theory-Part-3.ipynb)

#### Node label prediction

The Label Propagation Algorithm (LPA) is a fast algorithm for finding communities in a graph using network structure alone as its guide, without any predefined objective function or prior information about the communities.

The Smoothness assumption states that points connected via a path through high-density regions on the data are likely to have similar labels.

##### Node embedding

Classification
node2vec

##### Edge embedding

Classification

Given any graph, it can learn continuous feature representations for the nodes, which can then be used for various downstream machine learning tasks.”

#### Graph embedding

[Graph2Vec](https://github.com/benedekrozemberczki/graph2vec)

python src/graph2vec.py --input-path data_folder/ --output-path output.csv
