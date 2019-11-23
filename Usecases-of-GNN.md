## Particle Track Reconstruction in Large Hadron Collider
* Data are space-point representation of HEPtrackingdata
* Contains Hits, interactions information
* Track building with Recurrent Neural Networks(RNNs)  
* Particle tracks can be represented as a sequence of hits
* Given a sequence of hit coordinates, the model produces for every element a prediction of the position of the next hit conditioned on its position and the preceding hit positions.
   * A track seed using the first three hits of a true track and the RNN models are used to make remaining predictions 
   * It selects the highest scoring hit in the event on each successive layer
* Track ﬁnding with Graph Neural Networks (GNNs)
  * How graph is constructed
    * Connects hits using geo-metric constraints or by using preprocessing algorithm
    * Hits are also connected on adjacent layers when they are compatible according to some criteria
  * Architecture of GNN model
      * An input transformation layer appears first and then is followed by alternating EdgeNetwork and NodeNetwork
      * NodeNetwork computes node features based on the neighboring nodes and weight neighboring nodes information using edge weight.
      * EdgeNetwork computes edge's weight based on the start and end node
      * In each iteration of the GNN, the model propagates information through the graph that helps to stress important connections and weaken useless connections.

  * Identifies a track by performing binary hit classification in a partially labeled graph. It is node classification.
  * Identifies many tracks at once by performing binary segment classification. It performs classification on graph edges
