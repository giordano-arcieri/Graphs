# Graphs
API for Graphs.
This repo allows you to create a graph data structure in any of the 3 main ways. There are 3 header files. 
Include "Graph.hpp" if you would like to create a graph data structure rappresented by an adjecency list. 
Include "Graph_AdjecencyMatrix.hpp" if you would like to create a graph data structure rappresented by an adjecency matrix. 
Include "Graph_EdgeList.hpp" if you would like to create a graph data structure rappresented by a list of edges.

The reason why Graph.hpp is not Graph_AdjecencyList.hpp is because this is the most common and usually most efficient way of storing a graph in memory. 

Graph.hpp is implemented with a map of lists where the head of each lists rappresnets the node and the following nodes after the head rappresnet the edges. In a weighted graph the lsit node holds both the graph node and the weight.

Graph_AdjecencyMatrix.hpp is implmented with a 2D vector. This is just one vector behind the scenes but it rappresnets a 2D vector where the index rappresnets a node and a non-zero value in position (row, column) rappresnets an edge between node row and node column. In an undirected graph (row, column) is the same as (column, row). This also supports both weighted and unweighted graphs meaning it will created a vector of booleans in an unweighted graph and one of integers in a weighted graph reducing the needed bits by a factor of 32 for unweighted graphs.

Graph_EdgeList.hpp is implemented with a vector of Edges which is a struct with node A and B and an Edge(A,B) rappresnetes an edge from node A to B. This can only be used for unwighted graphs.
