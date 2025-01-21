2024-12-09 - 17:11

Status: Incomplete

Tags: [[Network Architecture]] [[Ideas]]

## **Ablative contrastive pre-training**
**Name to be finalised!!!**
This my idea for creating an architecture which involves ablating subnetworks which represent subprograms for solving various problems. The key is that if we can map these subnetworks/subprograms on a latent space a model can see where they might be easily re-used resulting in analogical reasoning and abstraction/compositionality.
To give an analogy for word embedding, we interpret the meaning of a word in latent space by seeing how it is utilised in sentences, how it combines with other words, which words are a substitute for it and map it into continuous space accordingly. In theory we should be able to do the same with subprograms by seeing what other subprograms they are commonly combined with or substituted with.

Achieving this will require some way to effectively ablate features which will require research into mechanistic interpretability.
It will also be necessary to find a way to map problems onto this same latent space??
From using LEAN it is clear to see that a problem is a point in space that undergoes transformations (such as algebraic substitution) to translate it to a simpler defined space. Thus a subprogram is a vector transformation so probably cannot be mapped onto the same space as the points/problems/training data themselves?? Unless we use vastly higher dimensions with problem and solution space holding little overlap?

In any case mapping solutions and problems on the same latent space may not be necessary but an additional generative meta network will be needed for identifying subnetworks to be composed together to solve the problem

This meta network represents conscious thought required for out of distribution problem solving whereas the base network represents intuition, in distribution problems for which many examples have been seen and there is a generalised solution function. Ideally once the meta-network has seen enough examples of a problem it can be encoded into the intuition network just like how learning to add becomes intuition or making a coffee (adding this to base network may encounter [[catastrophic forgetting]] so more research needed there)

{
Thoughts from my notes page which need to be reformed into the above:

If facts/attributes live in vector transformations we need a system that can find the transformation common to that attribute and pull it out so it can compose it onto something novel

Can it store itself as in the network as a culmination of many complex attributes seen before. Strange loop vibes

A network which takes its own parameters and pattern matches activation traces to find analogical scenarios,  the problem is activation mappings in terms of position mean nothing, the system would need to be able to map learned representations into vector space to create a world model similar to how a tokeniser works but unsupervised so it can do it with arbitrary representations.

How were tokenisers trained?

It would also be helpful to be able to compress activations sequences that are extremely common into a single neutron activation for instance the AND operation

Is this not done by some meta-learning system? Check survey

Inversion capacity, is it necessary? Can a meta networks with activations traces perform invert a function. That is to say if we know the son of X is Y then the mother of Y is X, neural networks are not invertible functions so how can they handle bi-directional relationships such as this one? Neural nets cannot be bijective therefore and cannot be circular so how is this solved

Lastly we need some decomposition, learned representations can either be in the form of a composite or a combinatorial dependency. In the case of composites how do we decompose a representation that was either hard-coded (first layer of network) into subcomponents particularly in the rigid structure mandated by feed forward networks. For instance what we had the knowledge of atoms and built a world model around this and then discovered quarks, our brains need to extend the network to left so that what was fundamental is now a composite of newly discovered fundamentals. It’s very unlikely that the brain does this and works like a formal hierarchical tree systems of ground proofs then composed into complex structures (little alchemy style). Again is it possible to discover a way to connect composites and components in a non-circular way

Since we would assume layer 1 of feed forward networks would be the inputs of our human senses plus the thoughts processes at time T-1 for inference T it has to at least be recurrent with the activations being representative of something

In this case the Meta networks could do some convolution of the activation patterns at each time step to find analogically patterns perhaps?

Also there would surely be a filtrations network on whether the online inputs are relevant to the current thought process, ie does what you are visual processing now contribute to solving your current train of thought
}
#### **References**
