# Applied-Graph-Neural-Network

## Extracting embedding from Graph Neural Network
[Notebook](Graph%20Convolutional%20Networks%20Demo.ipynb)
![Cora embedding](/image/cora_embedding.png)

## Attention in Graph Neural Network (GNN)
Attention introduces weight to quantify how relevant information from neighboring nodes are. In GNN, representation of a node is a combination of its own information as well as the information from its neighbors. Attention weights are used to scale up and down information from neighbors that are relevant and not relevant, respectively. 

To be more concrete, representation of a node i and its neighbors (j) are multipled with a learnable weight matrix a which is then activated through RELU or LeakyRELU. This is akin to similarity calculation between the node and its neighbor. 
Resulting weight is softmaxed over all the neighbors to normalize it. Normalized weight are used to multiply neighbor representation and finally, all the neighbor's representations are added to make up node's representation.  

In Multi-head attention, mutiple attention matrices are calculated. Motivation is that each attention head will learn a specific aspect of neighbors. At the end, all attention heads are either averaged or concatenated into one attention matrix. When attention distribution are uniformly distributed over all the neighbors, then applying attention has less value.  


* [GAT tutorial](https://docs.dgl.ai/en/latest/tutorials/models/1_gnn/9_gat.html)
* [Understanding Attention in GNN](https://slideslive.com/38915806/understanding-attention-in-graph-neural-networks)
