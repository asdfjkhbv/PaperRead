title: 'MMDML for Image Set Classification' 

`Extreme Classification`
`Metric Learning`
`Image Set Classification`
---

Prior Extreme Classification forcused on the face verification, however, the image set classification aimed at find `subcategory` from `a rough category`.
So The Introduction just summary little about algorithm(two much same.)
## Key Note of the introduction

> Key of image set classificationn
>> 1. High nonlinearity of saamples make the image representation become hard
>>> Classical ways: single Gaussian, Gaussian mixture models subspace or mixture of subspaces.
>> 2. Classical methods can be categorized into two classes: parametric and non-parametric
>>> - First One: each image set is moedled as a specific distribution and the the Kullback-Leibler(KL) divergence is used to compute the similarity of two image sets.

## LOSS FUNCTION
> <center><img src="http://latex.codecogs.com/gif.latex?\min_{f_1,f_2,\cdots,f_C}H=H_1+\frac{\lamda}{2}H_2"/> </center>
> <center><img src="http://latex.codecogs.com/gif.latex?=\Sigma_{c=1}^C\Sigma_{i=1}^{N_c}g(D_1(h^L_{ci})-D_2(h_{ci}^L))"></center>
> <center><img src="http://latex.codecogs.com/gif.latex?+\frac{\lamda}{2}\Sigma_{c=1}^C\Sigma_{l=1}^{L}(||W_c^l||_F^2+||b_c^l||_2^2)"/></center>

> where <img src="http://latex.codecogs.com/gif.latex?g(a=\frac{1}{\r})">


