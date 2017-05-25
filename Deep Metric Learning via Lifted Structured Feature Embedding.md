# paper
Tags: Note,PaperRead, Structured Feature Embedding, 3D shape retrieval
## Abstract INFO
>  **key sentence:** * With the remarkable success from the state of art convolutional neural networks, recent works <**1,3**> have shown promissing results on discriminatively training the networks to learn semantic feature embeddings where similar examples are mapped close to each otheer and dissmilar examples are mapped farther apart. *


## Introduction INFO
Extreme Problem was proposed , in order to make classification problem become a nearest neighbor problem.
if images can initialize a similarity metric for distance comparation. Classification problem can be treated as a distance comparation problem. And it will simply the classification problem. So related methodology is *Metric Learning* and *dimensionality reduction*.' (a matric can be projected into a distance vector space . That is dimensionality reduction.)'

In this setting, two major problems arise which renders conventional classification approaches practically obsolete.(this problem makes classical classification methods become old man out of times.)
> - Because of the huge number of classes , classical learning and inference method impracticaliy solve the extreme problems.
> - due to make a main class into several bins, the training data become too fewer to impact the algorithms availability.


So the metric learning is major approach in this theme.

liftes the vector of pairwise distances within the batch to the matrix of pairwise distances (O(m)) within the batch to the matrix of pairwise distances.

**What do they do ?**
> - use the matrix of pairwise distance (O(m^2)) in constract to the vector of pairwise distances(O(m))
> desing a novel structured loss function objective of the lifted problem.

**About the datasets:**

|  datastes name    | numbers of images    |   numbers of classes  | main class type | 
| --- | --- | --- | --- |
| Stanford Online Produts    |  120,000   | 23,000    | online e-commerce websites |
|  CARS196   | 16,185    |  296    | car |
|  CUB200-2011   |  11,788   | 200    |brids(with special annnotations)|

**Its purpose:**
make a generic concept of similarity/ distance.(we can optimize with specific purpose.)

> **`method metric`**:
> *clustering metric*: -standard F1, NMI metrics(?) 
> *retrieval quality* : -standard Recall@K (K means the top K images are  same.)

## Related words INFO
### Deep metric learning for recongnition

|  Authot  |   method  | paper name    |
| --- | --- | --- |
|  Bromley   |   siamese networks  | Signature verification using a 'siamese' time delay neural network    |
|   Chopra  | face verification    | Learning a similarity metricdiscriminatively with application to face verification    |
|  Chechik   |  learn ranking function using triplet loss | Distance metrick learning for large margin nearest neighbor classification |
|   Qian Q  | precomputed activation features embedding via distance metric for calssification |  Imagenet classification with deep convolution neural networks <br>  *precomputed activation features: * <br> Fine-grained visual categorization via multi-stage metric learning. |

### Deep feature embedding with convolutional neural networks

|   method name | procedure  |paper name   | application|
| --- | --- | --- | --- |
| contrastive embedding |     | Learning visual similarity for product design with convolutional neural networks<br>Dimentionality reduction by learning an invariant mapping |product design classification |
| triplet embedding |     | FaceNet: A unified embedding for face recognition and clustering<br> Distance metirck learning for large margin nearest neighbor classification |face extreme detection|
| joint embedding |  | Joint embeddings of shapes and images via cnn image purification |3D Shape and 2D image |
### Zero shot learning and ranking

zreo shot means : learning lions image from cats and tiger.
on shor means: learning liongs image from little lion images.

## Reviews INFO
### contrastive embedding
It aimed at minimizes the distance between  a pair of examples with the same class label and penalizes the negative pair distances for being smaller, than the margin <a href="http://www.codecogs.com/eqnedit.php?latex=\alpha" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\alpha" title="\alpha" /></a>

<a href="http://www.codecogs.com/eqnedit.php?latex=J&space;=&space;\frac{1}{m}\displaystyle\sum_{(i,j)}^{m/2}&space;y_{i,j}&space;D_{i,j}^2&space;&plus;&space;(1-y_{i,j})[\alpha&space;-&space;D_{i,j}]_{&plus;}^{2}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?J&space;=&space;\frac{1}{m}\displaystyle\sum_{(i,j)}^{m/2}&space;y_{i,j}&space;D_{i,j}^2&space;&plus;&space;(1-y_{i,j})[\alpha&space;-&space;D_{i,j}]_{&plus;}^{2}" title="J = \frac{1}{m}\displaystyle\sum_{(i,j)}^{m/2} y_{i,j} D_{i,j}^2 + (1-y_{i,j})[\alpha - D_{i,j}]_{+}^{2}" /></a>


>- <img src="http://latex.codecogs.com/gif.latex?y_{i,j}" title="y_{i,j}" /> means the pairs label is same or not
>-  <img src="http://latex.codecogs.com/gif.latex?m" title="m" /> means the batch images number
> - <img src="http://latex.codecogs.com/gif.latex?D_{i,j}^2" title="D_{i,j}^2" /> means <img src="http://latex.codecogs.com/gif.latex?D_{i,j}^2=||f(x_i)-f(x_j)||^2" title="D_{i,j}^2=||f(x_i)-f(x_j)||^2" /> 
> - <img src="http://latex.codecogs.com/gif.latex?[element]_+=max(0,element)" title="[element]_+=max(0,element)" /> 

### Triplet embedding INFO

compare there image in a batch ${x^i_a, x^i_p, x^i_n}$,
> - <img src="http://latex.codecogs.com/gif.latex?x^i_a" title="x^i_a" /> and <img src="http://latex.codecogs.com/gif.latex?x^i_p" title="x^i_p" /> has same label
> - <img src="http://latex.codecogs.com/gif.latex?x^i_a" title="x^i_a" /> and <img src="http://latex.codecogs.com/gif.latex?x^i_n" title="x^i_n" /> has different label

the training process encourage the network to find an embedding where the distance between <img src="http://latex.codecogs.com/gif.latex?x^i_a" title="x^i_a" /> and <img src="http://latex.codecogs.com/gif.latex?x^i_n" title="x^i_n" /> larger than the distance between <img src="http://latex.codecogs.com/gif.latex?x^i_a" title="x^i_a" /> and <img src="http://latex.codecogs.com/gif.latex?x^i_p" title="x^i_p" /> plus margin <img src="http://latex.codecogs.com/gif.latex?\alpha" title="\alpha" />.

**COST FUNCTION**

<img src="http://latex.codecogs.com/gif.latex?J=\frac{3}{2m}\displaystyle\sum_{m/3}^{i}[D^2_{ia,ip}-D^2_{ia,in}+\alpha]_+" title="J=\frac{3}{2m}\displaystyle\sum_{m/3}^{i}[D^2_{ia,ip}-D^2_{ia,in}+\alpha]_+" />
<img src="http://latex.codecogs.com/gif.latex?D_{ia,ip}=||f(x^i_a)-f(x^i_p)||^2" title="D_{ia,ip}=||f(x^i_a)-f(x^i_p)||^2" />

