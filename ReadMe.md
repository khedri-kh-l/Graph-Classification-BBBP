Graph Classification(BBBP)
---------------------------------------------


The BBBP (Blood-Brain Barrier Penetration) \cite{wu2018moleculenet} is another molecular dataset for graph classification tasks. The BBBP dataset includes binary labels for over 2000 compounds on their permeability properties, where the goal is to predict whether a compound can cross the blood-brain barrier based on its molecular features. 

The model consists of a series of GCN layers. Each GCN layer applies a graph convolution operation to the node features, enabling the model to learn local and global patterns in the graph structure. After the GCN layers, the model applies readout operations to aggregate node embeddings into graph-level embeddings, and their purpose is to capture the graph-level information from the node embeddings. Following the readout layers, the model uses a series of MLP layers to process the graph-level embeddings. The MLP layers are used to learn non-linear mappings from the graph-level embeddings to the final output space.


## Evaluation
|Dataset   |Model       |Epoch| Time-inference    | Test Accuracy      |
|--        |--          |--   |---                |       --           |
|Proteins  |HGP-SL      |100  |00.103 $\pm$ 0.005  |  0.827 $\pm$ 0.015 |


### Requirements

    python==3.10.6
    dgl==1.1.2
    pytorch==2.0.1+cpu
    torch-scatter==2.1.1+pt20cpu
    torch-sparse==0.6.17
    torch-geometric==2.4.0