---
title: Discriminative Deep Metric Learning for Face Verification in the Wild 
tags: Beginning of DDML, 
grammar_cjkRuby: true
---


# Title: Discriminative Deep Metric Learning for Face Verification in the Wild
 


## Motivation 
Before this paper, metric learning and deep learning is sepreate task of machine learning.

Image classification in face detection hast two categories 
- [ ] face identification
  > recognize the person from a set of gallery face images or videos and find the most similar one to the probe sample
- [x] face verification
  > determine whethewe a given pair of images or video is from the same person or not.
  
And this proposal method aimed at face verification performance in unconstrained environments.

feature descriptor based and metric learning-based method.

metric has two types 
1. Kernel trick
	Map input into a higher dimensional space.
2. Metric learning 
	Metric learning is  
	<img src="http://latex.codecogs.com/gif.latex?d_M(s_i,x_j)=\sqrt{(x_i-x_j)^TM(x_i-x_j)}"/>
	
	
	where is <img src="http://latex.codecogs.com/gif.latex?M=W^TW"/>

if the <img src="http://latex.codecogs.com/gif.latex?M"/> is <img src="http://latex.codecogs.com/gif.latex?dxd"/> and the inputs is 1xd and the M is positive definite , and si the correlation matrix of two samples.
	the distance was defined by Indian stastician mahalanobis distance. which means 
	<img src="http://latex.codecogs.com/gif.latex?x_1,x_2"/> means the two sample from the inputs 
	and the mahalanobis distance is <img src="http://latex.codecogs.com/gif.latex?D=(x_i-x_j)^T\sigma^{-1}(x_i-x_j)"/>
	if the M matric is positive definite, the <img src="http://latex.codecogs.com/gif.latex?||x-y||_A=0/> is possible even if <img src="http://latex.codecogs.com/git.latex?x\neg{y}/>
