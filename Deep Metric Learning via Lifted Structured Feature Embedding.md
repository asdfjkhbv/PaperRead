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
It aimed at minimizes the distance between  a pair of examples with the same class label and penalizes the negative pair distances for being smaller, than the margin $\alpha$
