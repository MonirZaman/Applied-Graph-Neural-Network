## Particle Track Reconstruction in Large Hadron Collider
```
Farrell, Steven, et al. "Novel deep learning methods for track reconstruction." arXiv preprint arXiv:1810.06111 (2018).
```
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
    * During inference, graphs are constructed with 4 hits on each detector layer in the region around the true track and connecting all hits together on adjacent layers.
  * Architecture of GNN model
      * An input transformation layer appears first and then is followed by alternating EdgeNetwork and NodeNetwork
      * NodeNetwork computes node features based on the neighboring nodes and weight neighboring nodes information using edge weight.
      * EdgeNetwork computes edge's weight based on the start and end node
      * In each iteration of the GNN, the model propagates information through the graph that helps to stress important connections and weaken useless connections.

  * Identifies a track by performing binary hit classification in a partially labeled graph. It is node classification.
    * Graph is given first three hit labels as True. 7 iteration of information passing is performed. Sigmoid activation is done to identify node label (True or False) denoting whether node belongs to the track.
  * Identifies many tracks at once by performing binary segment classification. It performs classification on graph edges
