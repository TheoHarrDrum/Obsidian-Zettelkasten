2024-12-09 - 14:07

Status: Very Incomplete (not read the paper)

Tags: [[Bijective Functions]] [[Network Architecture]]

## **INN's**
Often the most useful and well behaved functions in mathematics are bijective (one input maps to one output). This condition is sufficient and necessary for a function to have an inverse. It can quite easily be shown however that MLP's/neural nets do not satisfy this condition, for starters the dimensionality of the input is often different to that of the output.

(if dimensions were the same would it be invertible??)

To solve this it creates a new latent space for the output in which the dimensionality is the same as the input to allow a one to one mapping and uses Maximum Mean Discrepancy. 

An extension of this is normalising flows in which the INN has a tractable determinant and inverse of the weight matrix can be calculated.
#### **References**
https://arxiv.org/pdf/1808.04730 - initial paper
https://vamsivk1995.medium.com/what-are-invertible-neural-networks-and-why-do-they-matter-71f4f2040806 - summary article
https://stats.stackexchange.com/questions/414847/difference-between-invertible-nn-and-flow-based-nn - stack exchange differentiating INN and norm flow
