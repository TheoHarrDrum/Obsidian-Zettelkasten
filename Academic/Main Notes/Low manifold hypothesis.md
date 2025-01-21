2024-12-09 - 14:35

Status: Ongoing

Tags: [[Embedding]]

## **Low manifold hypothesis**

A manifold is any object of lower dimension than a space such as the perimeter of a circle on a 2D plane or the surface sphere or taurus in a 3D one. A key component of a manifold is that while it may be an object of *n* dimensions, a position on the manifold need only be described by *n-1* dimensions. Angle for circle perimeter and latitude and longitude or 2 angles for sphere.

In the case of a neural network if it has the dimensionality of the hidden layers is the same as the dimensionality of the output it will struggle to classify various patterns of data. This is because the nn layers are a series of affine transformations and need to transform the data in some way where if there are n outputs it can separate the data with an n-1 dimensional hyperplane. However in order to create a transformation in which an n-1 hyperplane can classify the outputs in needs to warp it in a higher dimension (n+1) to separate the data using only affine transformations. Note that the data could be separated with non linear functions however we could not use backprop. [[Invertible Neural Networks]]

The low manifold hypothesis states that a lot of real world high dimensional datasets actually lie along low dimensional manifold within that high dimensional space.
NN's aim to stretch and morph data onto these low dimensional manifolds such that they can easily be classified by a hyperplane.

#### **References**
https://www.youtube.com/watch?v=pdNYw6qwuNc - great visualisation 

https://medium.com/@weidagang/demystifying-the-manifold-hypothesis-17ef5265e211 - some article, bit meh

