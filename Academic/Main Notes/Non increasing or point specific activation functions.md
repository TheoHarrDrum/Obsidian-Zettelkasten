2024-12-26 - 17:39

Status: Very early conceptualisation

Tags: [[Ideas]]

## **Non increasing/point specific activation functions**

An activation function needs to be differentiable to backpropigate loss but all functions are increasing? Why?

Wouldn't it reduce complexity if we could tune the value the curve peaks at? Sin and Cos are both differentiable and if we pass normalised values between a range we can tweak the function to choose a value for where the peak rests creating an activation function which is more flexible

However how does the network know how to tune these values? Since it doesn't clearly work with the loss function


Also a skip toggle for recurrence, if it activates the network outputs the current values?



#### **References**
