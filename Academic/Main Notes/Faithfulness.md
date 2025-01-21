2024-12-10 - 12:46

Status: Ongoing

Tags: [[Mechanistic Interpretability]] [[Model Metrics]]

## **Faithfulness**

Faithfulness measures what proportion of the full models behaviour in a particular domain (the domain being dictated by the content of the evaluation dataset) can be explained by the ablated circuit. Aka probabilistically how responsible is the ablated circuit for the behaviour you are trying to isolate, the equation is given as such:
$$F(c) = \frac{NL(c) - NL(\emptyset)}{NL(M) - NL(\emptyset)}$$
Where *NL(c)* measures the [[Logit]] of the correct answer token normalised by the maximal [[Logit]]. *NL(M)* is the normalised correct answer when no component is ablated (the full model), and *NL(0)* is the correct answer [[Logit]] when all components are mean-ablated.

#### **References**
https://arxiv.org/pdf/2211.00593 - paper deriving faithfulness