2024-12-09 - 17:13

Status: Incomplete

Tags: [[Network Architecture]]

## CoT

Chain of thought simply involves passing the output from a generative model back into itself. While this is very inefficient there is some sensibility to the idea, it basically make the model into a recurrent network since their might be intuition encoded into the earlier layers of the network that do not get utilised in the initial pass as the network has to make multiple passes to transform a problem into one where it can make a clear association to the correct solution. It not clear if they do some backprop through time for these CoT models but it seems feasible to do so.


#### **References**
Neel Nanda - Machine Learning Street Talk