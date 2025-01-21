2024-12-18 - 13:55

Status: Very Ongoing

Tags: [[Ideas]]

## **Turing Robust Cell?**

*Pretty sure this has been done before with Neural Turing Machines or something*

If we can represent things in latent space on a lower dimensional manifold can a sequence of affine transformations be considered Turing complete?

When it comes to mathematics neural networks generalise ([[Procedural Knowledge in Pretraining Drives Reasoning in LLM's]]) but do the actual number work in a very inefficient way ([[Arithmetic without Algorithms]]) by essentially finetuning the probability distributions of the plausible numbers with each consecutive layer. We also know the network has the ability to recall the procedure in writing/code but would appear does not have the ability to execute the procedure for arbitrary inputs.

A [[Circuit (MLP)]] in theory emulates the conditions and processes to transform one feature to another however it doesn't seem that they can fully do this due the above of struggling to apply procedure. Why not? Perhaps sequential affine transformations are not Turing complete?

In general, for an imperative language to be Turing-complete, it needs:

1. A form of conditional repetition or conditional jump (e.g., `while`, `if`+`goto`)
    
2. A way to read and write some form of storage (e.g., variables, tape)
    

For a [lambda-calculus](http://en.wikipedia.org/wiki/Lambda_calculus)–based functional language to be TC, it needs:

1. The ability to abstract functions over arguments (e.g., lambda abstraction, quotation)
    
2. The ability to apply functions to arguments (e.g., reduction)

It makes some sense that it would struggle with math problems since the get the exact correct answer for a model is impossible given the are infinite value in the fundamental domain (Integer, Real, etc) and finite weights therefore it should have the external use of a calculator and be trained with it or be asked questions with algebra inputs (x, y, etc) instead of numbers.
Googles math olympiad models probably have to solve lots of questions like this so probing those models would be more insightful.

Anyway all this is to say what if MLP's aren't Turing complete? What features couold we add to a cell to make it so? We can loop using chain of though however networks do not have memory that is persistent across forward passes (the brain might have this with chemical channels having different activations durations).

It doesn't seem they have a clear way to abstract functions to arguments either

So maybe a cell with some persistent memory and traditional calculator capacity

There is an argument to say that it has both of these at a fundamental capacity since whether the neuron activates is equivalent to a binary bit and it has calculation since it calculates it activation in the traditional transistor style

#### **References**
