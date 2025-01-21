2024-12-30 - 11:05

Status: Ongoing

Tags: [[Mathematics]] [[Optimisation Methods]]

## **Backpropigation**

Let *C* be the cost function, *a* be the activation function and *z* be the affine node function, then the cost backpropigates as such
$$\frac{\partial C}{\partial a^{(n)}_m} \rightarrow \frac{\partial a^{(n)}_m}{\partial z^{(n)}_m} \rightarrow \frac{\partial z^{(n)}_m}{\partial w^{(n-1)}_{mm}} \rightarrow \frac{\partial w^{(n-1)}_{mm}}{\partial a^{(n-1)}_m} \rightarrow \frac{\partial a^{(n-1)}_m}{\partial z^{n-1}_m} \cdots$$

As we can see using the chain rule the error can be proportionally distributed to specific node *m* in layer *(n)*.

So in the end the derivative for weight *mm* in layer *n-1* is:
$$\frac{\partial C}{\partial w^{(n-1)}_{mm}} = \frac{\partial C}{\partial z^n_m}\cdot \frac{\partial z^n_m}{\partial w^{(n-1)}_{mm}} = \frac{\partial C}{\partial a^n_m}\cdot \frac{\partial a^n_m}{\partial z^n_m}\cdot a^{(n-1)}_m = \frac{\partial C}{\partial a^n_m}\cdot f'(z^n_m)\cdot a^{(n-1)}_m$$
#### **References**
https://towardsdatascience.com/understanding-backpropagation-algorithm-7bb3aa2f95fd
