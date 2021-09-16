# Analysing_defi_markets_with_graphs

This is a proof-of-concept, showing that transactions in a specific token (I used pudgy penguins in this case) for a given time period can be represented as directed, weighted knowledge graphs. The "from_address" and "to_address" fields represent the source and target nodes, respectively. The "tx_no" (number of transactions between two addresses) becomes the link weight.

From such graphs, node centrality measures are extracted for each node (i.e. address). Doing so for successive time periods creates an index of features for each node. 

For each node, I compute the eigenvector centrality, which is a centrality measure for a node based on the centrality of its neighbors (i.e. address connectivity), also taking into account the number of transactions (i.e. activity level).

In the directed graph, eigenvector centralities for in- and out-degrees contain information about the behavior of each address. For example, for a given address (i.e. node), the out-degree eigenvector centrality score and its evolution over time conveys information about its selling patterns.

*To be run on Google Colab.*
