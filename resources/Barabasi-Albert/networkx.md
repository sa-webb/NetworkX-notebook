# Networkx docs

## barabasi_albert_graph

`barabasi_albert_graph(n, m, seed=None)[source]`

Returns random graph using Barabási-Albert preferential attachment model.

A graph of n nodes is grown by attaching new nodes each with m edges that are preferentially attached to existing nodes with high degree.

### Parameters

n : int

Number of nodes

m : int

Number of edges to attach from a new node to existing nodes

seed : int, optional

Seed for random number generator (default=None).

Returns:
    G : Graph

Notes

The initialization is a graph with with m nodes and no edges.
