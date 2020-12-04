# Exploring Gaussian Process Regression for Bayesian Optimization

Here we explore possible ways to improve probabilistic regression for surrogate model based optimization of a high dimensional input space problem.  

## 1. Gaussian Process (GP) Model VS. Neural Network (NN) Model 
The GP model is de facto standard surrogate model for Bayesian optimization possibly due to followings:

- GP is a Bayesian regression model: can incorporate prior belief
- GP can estimate uncertainty

However, NN can also be made to satisfy the above. Here, we explore which one to use for Bayesian optimization.

#### Literature comparing NN and GP

A [literature](https://doi.org/10.1063/1.5003074) compares NN and GP on a regression problem (fitting potential energy surface). GP resulted bettwe accuracy. 



#### Comparision with NN ensemble model

Although, the NN ensemble model is not Bayesian, it can estimate uncertainty and can incorporate new data by training.


