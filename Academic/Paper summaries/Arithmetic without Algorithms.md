2024-12-10 - 12:12

Status: Ongoing

Tags: [[LLM]] [[LLM-skeptic]] 

## **Untitled**

<u>Arithmetic circuit discovery</u>
With LLM tokenisation numbers are grouped together for a ingle token, in the case of Llama3-8B the numbers from 0-1000 are grouped together in one token.
To extract the relevant features they input 100 prompts all consisting of two values and an operator (plus, minus, mult, div) and then end it with the = operator. They also use an identical amount for evaluation.
The values for the inputs are chosen so that they and the resulting output land within the same token range i.e. 0-1000. They ensure the model is not linked to an external component such as the internet or calculator.

To locate the circuit components they take two prompts, p and p'. They first input p' and compute the activations for that prompt, they then input p however intervene with one of the layers, replacing its activation with that of the precomputed activation of p' on that layer. They then measure how this changes the output by looking at the probability distributions for both a non intervened and intervened output. This can be done with MLP layers or attention heads it should be mentioned but it is found that doing this with MLP layers has much more effect.

To gage how well the particular ablated circuit captures the full models behaviour in that subdomain they use a metric called [[Faithfulness]] and find it achieves a high faithfulness of 0.96 across the four arithmetic operations giving strong confidence that those ablated circuits comprise the arithmetic portions.

Using some experimentation with output classifiers on each layer they find that the first 16 layers serve to extract representation, and it is from the middle to late layers (16-32) that the model tries to compute the correct answer.

<u>MLP's to heuristic neurons</u>

They then do the activation matching technique described above however instead of doing it on layers they do it on individual neurons instead of layers to discover which have a high affect on the output. They then further verify this by removing the low affect neurons from the lowers and once again testing the [[Faithfulness]] to verify their findings. In the end they discover that about 45% of the neurons that are important to each operator (plus, minus...) are unique in to that operator, i.e. not useful or activated for the others. They further find that only about 200 neurons (1.5% of the layers neurons) are needed to achieve high faithfulness.

From here they identify what specific outputs neurons correspond to by using a key value system outlined by [[Key Value Memories]]. What they find is that a specific neuron tends to activate for a specific value range for a certain operation, i.e. the neuron will activate for subtraction where the result is between 150-180. They find two types of neurons, some who's activation is dependant on operand and value ranges (direct heuristics) and some who's activation depends on just the operand and the value heuristics and encoded downstream (indeirect heuristics).

<u>Analysing how heuristics become output</u>
TL;DR I haven't fully read section 4 of the paper but form what I can tell it is found that the model narrows down a correct answer by having these value range activations nudge the [[Logit]] value in the correct direction, essentially composing these value range probabilities to narrow down a specific value. It is found that the most common reason for failure is that there aren't enough neurons associated with a particular value range to accurately narrow down the answer. Neuron imperfect recall is find to have a minimal affect on error.

<u>How does this behaviour emerge from training?</u>
Again TL;DR but it seems that this heuristic method arises pretty gradually and linearly during training and is not a sudden emergent feature. There are also little changes in how it operates throughout the training process, only further refining and finetuning of its heuristics

<u>What does this mean to my research?</u>
It confirms the stochastic parrot idea though under a different alias. If we consider a neuron here to essentially be a memory its clear to see arithmetic is done by memorising input output pairs under a quantized and combinatorial system to narrow down output ranges. There is no implementation of a robust memorised algorithm that takes arbitrary input and applies a method which is what we would like to see for a system with abstraction as an emergent behaviour.

#### **References**
https://arxiv.org/pdf/2410.21272
