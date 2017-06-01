## Introduction INFO
Deep metric often suffer the problem of slow convergence and poor local optima, partially due to that the loss fuction employs ***only one negative sample*** while not interacting with the other negative classes per each update.

The Contrastive loss is 
<img src="http://latex.codecogs.com/latex.gif?\latin{L}_{cont}^m(x_i,x_j;f)=\mathbf{1}\{y_i=y_j\}||f_i-f_j||_2^2+\mathbf{1}\{y_i\neq{y_j}\}max(0,m-||f_i-f_j||_2)^2)" />
