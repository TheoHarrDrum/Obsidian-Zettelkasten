2025-01-21 - 12:14

Status: Very Ongoing

Tags: [[Transformers]] [[Attention]]

## **Untitled**

Googles new paper as an answer to the quadratic cost of increasing transformer context windows. There is also this video which explains it very basically:
https://www.youtube.com/watch?v=x8jFFhCLDJY

Essentially it learns to focus on instances and tokens which most dramatically violate its expectations of what should be there

"This surprise metric, however, can result in missing important information that comes after a big surprising moment. That is, the gradient can become extremely small after several surprising steps, leading to stocking in a flat area (i.e., local minima), and missing information about some parts of the sequence. From the human memory perspective, an event might not consistently surprise us through a long-period of time although it is memorable. The reason is that the initial moment
is surprising enough to get our attention through a long time frame, leading to memorizing the entire time frame. To improve the above surprise metric (Equation 8), we break the surprise metric into (1) past surprise, which measures the surprise amount of a very recent past; and (2) momentary surprise, which measures the surprise of incoming data"


#### **References**
https://arxiv.org/pdf/2501.00663v1