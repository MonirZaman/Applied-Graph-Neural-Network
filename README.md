# Applied-Graph-Neural-Network

## Attention in Graph Neural Network (GNN)
Attention introduces weight to quantify how relevant information from neighboring nodes are. In GNN, representation of a node is a combination of its own information as well as the information from its neighbors. Attention weights are used to scale up and down information from neighbors that are relevant and not relevant, respectively. 

To be more concrete, representation of a node i and its neighbors (j) are multipled with a learnable weight matrix a which is then activated through RELU or LeakyRELU. This is akin to similarity calculation between the node and its neighbor. 
Resulting weight is softmaxed over all the neighbors to normalize it. Normalized weight are used to multiply neighbor representation and finally, all the neighbor's representations are added to make up node's representation.


* [Understanding Attention in GNN](https://slideslive.com/38915806/understanding-attention-in-graph-neural-networks)
