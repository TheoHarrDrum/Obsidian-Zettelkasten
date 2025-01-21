2024-12-09 - 11:52

Status: Initial pass complete

Tags: [[Self-supervised learning]] [[Embedding]] [[Ablative contrastive pre-training]]

## **Contrastive pre-training**
Contrastive pre-training is an semi-supervised method of embedding features in latent space such that similar features are closer together geometrically and is the backbone to token embeddings in chatGPT.
The key to achieving this is to **have the training batches consist of one positive example and the rest negative examples.**  The model will then be incentivised to have the positive examples embedded closer in the latent space, usually within a radius given by the parameter D. The primitive contrastive loss for this takes two data points and calculates the squared distance between them and aims to push them apart to some margin hyperparameter *m* by returning the loss as the difference between the *m* and the distance. If the distance is greater than *m* it returns 0.
This gives us $${L = (1-y)\cdot D^2 + y\cdot max(0, m-D)^2}$$ as the loss function.
This method can be further improved with triplet loss which implements the positive example mentioned above the aim of this anchor point is for the distance between the anchor and positive to be within the margin and the other (negative) points to be outside the margin, hence giving us:
$$L= max(0, D(A,P)-D(A,N)+m)$$
The total loss in henceforce the sum of these losses between all data points in the set. Extending this to the more widely implemented batch version that uses many negative examples we get the InfoNCE loss:
$$L = -log\frac{exp(D_P)}{\Sigma_i exp(D_{N_i})}$$
<u>How are positive and negative examples created</u>
Given this method is not supervised we have no labels no how does the algorithm know between a positive and negative pair? We simply augment the anchor point with some kind of noise/distortion, say a random crop and some colour effect changes for images, then assign that as the positive pair. All the other data points are considered negative even if they are say two images of an pug. Eventually through enough iterations the system will reach an equilibrium loss though admittedly not as quickly as with supervised data.
In the case of text for chatGPT the semantic meanings of words were embedded by sampling different sections of text from the same initial text (spans of tokens as the paper describes it), often with overlap, under the assumption that the surrounding words will give some indication to the meaning of it. This intuitively makes sense as if two smilies will often have the same surrounding words.
#### **References**
https://arxiv.org/pdf/2201.10005 - chatGPT tokenising
https://arxiv.org/pdf/2112.09118 - text CPT initial
https://proceedings.neurips.cc/paper/2016/file/6b180037abbebea991d8b1232f8a8ca9-Paper.pdf - batch version
https://arxiv.org/pdf/2304.12210 - definitive self-supervised guide