The Graph Neural Network (GNN) architecture implemented in the code is based on Graph Convolution Networks (GCN).
 
    Layer Structure:– Input Layer: GCNConv(input dim− > hidden dim)– Hidden Layer: GCNConv(hidden dim− > hidden dim)– Scoring Layer: Linear(hidden dim− > 1)
    Activation: ReLU after first GCN layer
    Aggregation: Mean pooling of neighbor features (default for GCNConv)
 
 The model processes node features (e.g., passage embeddings) and edge indices (graph connectivity) to propagate information across connected nodes.
 After the first GCNConv layer, ReLU activation introduces non-linearity, followed by a second GCNConv layer to refine node embeddings. 
 The final linear layer outputs relevance scores for each node. A ranking loss function enforces positive passages to score higher than negatives using a margin-based approach.
 The system handles variable numbers of positive/negative samples and optimizes ranking quality through backpropagation
