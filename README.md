**What does this notebook contain?**

This is a proof-of-concept, showing that transactions in a specific token for a given time period can be represented as directed, weighted knowledge graph, from which features are derived for each address.

In this example, I use all transactions relating to the pudgy penguins token for the month of August 2021.

**Structure of transaction-based graphs**

The "from_address" and "to_address" fields represent the source and target nodes, respectively. The "tx_no" (number of transactions between two addresses) becomes the link weight.

In a directed graph, in-degree refers to the number of links that point inward at a node. Out-degree describes the number of links that originate at a node and point outward to other nodes.

**Graph-based features**

From a graph, centrality measures can be extracted for each node (i.e. address), for a specific time period. Doing so for successive time periods creates an index of features for each address that is active in a specific token.

**Node centrality**

For each node, I compute the eigenvector centrality, which measures the centrality of a node based on the centrality of its neighbors (i.e. address connectivity), also taking into account the connection strength between nodes (here: no of transactions, i.e. activity level).

In a directed graph, eigenvector centralities for in- and out-degrees contain information about the behavior of each address. For example, for a given address (i.e. node), the out-degree eigenvector centrality score and its evolution over time conveys information about its selling behavior. Similarly, the in-degree eigenvector centrality score conveys information about the address' purchasing behavior.

**How can these features be used?**

* Behavioral profiling. Adjust borrowing/trading terms for a specific token based on an address' score.
* Predictive modelling. Use time series of (x most central) addresses' scores for predicting changes in volatility or price levels for a specific token.



*This proof-of-concept was created on Google Colab.*
