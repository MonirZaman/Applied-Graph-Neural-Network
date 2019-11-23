## Particle Track Reconstruction in Large Hadron Collider
* Data are space-point representation of HEPtrackingdata
* Contains Hits, interactions information
* Track building with Recurrent Neural Networks(RNNs)  
* Particle tracks can be represented as a sequence of hits
* Given a sequence of hit coordinates, the model produces for every element a prediction of the position of the next hit conditioned on its position and the preceding hit positions.
   * A track seed using the first three hits of a true track and the RNN models are used to make remaining predictions 
   * It selects the highest scoring hit in the event on each successive layer
* Track ﬁnding with Graph Neural Networks (GNNs).
