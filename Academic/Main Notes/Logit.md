2024-12-10 - 12:59

Status: Ongoing (small topic)

Tags: [[Mathematics]] [[Model Layers]]

## **Logit**
A logit that maps the probability space [0, 1] to the real space [-inf, inf].
Equation:
$$L = ln\frac{p}{1-p}$$
In context of deep learning the logits layer means the layer that feeds in to softmax (or other such normalization). The output of the softmax are the probabilities for the classification task and its input is logits layer. The logits layer typically produces values from -infinity to +infinity and the softmax layer transforms it to values from 0 to 1.

If the model is solving a multi-class classification problem, logits typically become an input to the softmax function. The softmax function then generates a vector of (normalized) probabilities with one value for each possible class.


#### **References**
https://stackoverflow.com/questions/41455101/what-is-the-meaning-of-the-word-logits-in-tensorflow
