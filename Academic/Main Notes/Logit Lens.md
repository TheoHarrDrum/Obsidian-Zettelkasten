2024-12-16 - 19:03

Status: 

Tags: [[Logit]] [[Mechanistic Interpretability]]

## **Logit Lens**
A Logit lens as one would expect focusses on the logit layers of networks to see how predictions are refined at each layer for both [[Feature]] and [[Circuit (MLP)]] discovery.
It works by projecting the activation *h* of layer *l* by multiplying it with the unembedding matrix *W* (which one can assume is the inverse of the embedding matrix though it is not clear that an embedding matrix has a determinant, if not an approximation). This yields the logits over the vocabulary space *V* where the highest logits indicate the information encoded. 

#### **References**
