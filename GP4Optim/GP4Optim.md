# Exploring Gaussian Process Regression for Bayesian Optimization

Here we explore possible ways to improve probabilistic regression for surrogate model based optimization of a problem of high dimensional input space.



## 1. Gaussian Process (GP) Model VS. Neural Network (NN) Model 
The GP model is de facto standard surrogate model for Bayesian optimization possibly due to followings:

- GP is a Bayesian regression model: can incorporate prior belief
- GP can estimate uncertainty

However, NN can also be made to satisfy the above. Here, we explore which one to use for Bayesian optimization. Intuitively, we expect GP to outperform NN generally, as [infinitely wide NN is equivalent to GP](https://arxiv.org/abs/1711.00165). 

### Literature comparing NN and GP

A [literature](https://doi.org/10.1063/1.5003074) compares NN and GP on a regression problem (fitting potential energy surface). GP resulted better accuracy as stated in the folllowing abstract:

<kbd>
  <img src="NNvsGP_PotentialSurface.png" width="600" height="400" />
</kbd>


### Comparision with NN ensemble model on a 1D problem

Although, the NN ensemble model is not Bayesian, it can estimate uncertainty and can incorporate new data by training. A [test]() on a 1D regression problem, GP outperformed NN ensemble. For a test, 16 identical MLPs (Multi-Layer Perceptron) are randomly initialized and trained to fit *f(x)=sin(4 &pi; x)* and compared to GPR (GP regression).


## Curse of dimensionality
