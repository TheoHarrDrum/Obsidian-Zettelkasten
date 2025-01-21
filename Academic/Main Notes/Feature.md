2024-12-16 - 18:23

Status: Ongoing

Tags: [[Network Architecture]] [[Mechanistic Interpretability]]

## **Feature**

Features don't have the most exact definition across the field ands will likely be used slightly differently between authors. However the consensus definition from a mechanistic interpretability POV is that a feature is a neuron or set of neurons that consistently activates for a particular input.
E.g. a feature that consistently activates for French text would be a French feature.
However a feature may not be explicitly tangible and have a real manifestation in the world or language, rather it could be an abstract property for which the presence of it helps define multiple other features.

An ideal behaviour of a feature and how connective models are hypothesised to work is that they have linearity, which means that the network activations encode linear vectors that represent facts/relationships. So that direction and magnitude might encode the difference in gender across all words (him and her, king and queen)
Another is decomposability which posits that a networks activations can be separated into a collection of independent features.
These two attributes are from the linear representation hypothesis covered in [2].


#### **References**
[1] https://arxiv.org/pdf/2407.02646#page=2.49
[2] https://arxiv.org/pdf/2209.10652