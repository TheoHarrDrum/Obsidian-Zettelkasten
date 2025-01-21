2024-12-11 - 13:00

Status: Ongoing

Tags: [[LLM]] [[LLM-skeptic]]

## **Procedural Knowledge in Pretraining Drives Reasoning in LLM's**

The key idea is to analyse the pretraining documents used for the LLM using something called [[Influence Functions]] and see when prompted by a particular question how heavily it relies on a document/documents.
They propose that **if the LLM has poor generalisation it will rely heavily from a small set of documents closely related to the prompt input, if it has generalisable reasoning it will pull from a broad range of abstractly related documents.** 

<u>Methodology</u>

I will go through this another time but basically they use some stats to measure the impact traces of certain documents from pretraining then check if those with theb highest impact actually had the answer to the question.
It feeds the models 7B and 35B two types of questions, simple factual recall and reasoning questions. These reasoning questions are math related such as finding gradients.

<u>Results</u>

"Finding 1: There is a significant positive correlation between the influence scores of documents for queries with the same underlying reasoning task, indicating that these documents are relevant for questions requiring the same procedure applied to different numbers."
The LLM does a good job of retrieving a relevant examples of the problem for reasoning tasks though the example may use different input values to the query

"Finding 2: When reasoning, the model on average relies on each individual document less per generated nat of information than when answering factual questions, and the total magnitude of influence is much less volatile, indicating it is generalising from a more general set of documents. The effect is more pronounced for the larger model."
The impact factor of a particular document is well spread out amongst the documents it primarily relies on suggesting the model is not parroting the most relevant example that occurred during pretraining but generalising from an array of relevant examples.

"Finding 3: The answer to the factual questions shows up relatively often in the top influential documents for the factual questions, and almost never for the reasoning questions."
The correct answer (for those particular inputs) is rarely in the pretraining data, only correct other example of the procedure. Whereas for factual questions the correct answer if often available in the pretraining data, this means it cannot regurgitate the information and has to apply generalisation in order to be correct.

"Finding 4: We find that influential documents for the reasoning queries are often doing a similar form of step-by-step reasoning, e.g. also arithmetic. Further, we find that the influential documents often implement a solution to reasoning questions in code or general math."
Formally encoded examples of the problem tend to take priority for the most influential documents, does that mean it is decoding code as instructions and applying procedure?

"One would perhaps expect a steeper power law for factual questions than for reasoning (meaning more of the total positive influence contained at the top parts of the ranking), but our results show evidence for the opposite. Perhaps a model needs to generalise from a broader set of documents for factual retrieval than for reasoning because it needs to see the same information more often to memorise it"

The above makes no sense to be and seems to be in contradiction of finding 2, that factual information needs a broader set of documents.
If we ignore the above excerpt (preprint so possible errors) and go off the findings it would seem generalisation is occurring rather than instance retrieval for a specific problem. Given this why is it that these models are considered to have poor reasoning capabilities?
There are 3 plausible reasons
1) The reasoning questions are too basic to constitute to real reasoning. Perhaps they are not multistep enough or do not have much variability in procedure depending on input. The problems used are certainly not particularly multi-step besides solving x for linear equations (which was only used on 35B) and even then depending on the number of variables this may not be multi-step. The latter is certainly true, none of these reasoning problems have any kind of branching factor in procedure depending on input but rather require a series of calculations. Further they lack any compositionality. The authors note that they specifically choose problems for which the models can achieve an 80% success which gives little insight into the kinds of reasons they fail to "reason" but only why they succeed. I would posit that these kind of questions achieve high accuracy because they are not composed of subprocedures that need to be composed together to solve a larger problem requiring repurposing of previosuly attained knowledge in bespoke ways.
2) Inherent bias of filtering for high success questions may mean the entire hypothesis of the paper revolves around outlier data points. It may be that those problems have a unique property, perhaps the above mentioned in (1).
3) The importance of reasoning is that reasoning problems tend to rarely have an abundance of explicit examples yet can be done by humans, finding the examples with high success rates. The aforementioned problems will have an abundance of explicit examples and the range of documents pulled from may be a result of the bag of heuristics strategy for arithmetic [[Arithmetic without Algorithms]].


#### **References**
https://arxiv.org/pdf/2411.12580 arxiv preprint of paper