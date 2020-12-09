
# Mean Power Error Loss 

The following histogram shows randomly generated 204800 data of the 4D test problem (of the sinc function) in log-scale

<p align="center">
  <img src="train_data_histo_4D_204800sample.png" width="400" />
</p>


Note that there are only a few data for *f(x)>0.2*. This is because, as the input dimension become larger, the volume occupied by the peak of sinc function becomes relatively smaller. On the other hand, the mean square error (MSE) is the de-facto standard loss for regression. However, in the test problem, the sum of square error on these data (*f(x)>0.2*) can be only a small portion compared to other points. Often this behavior is desirable in ML as such points are often statistical outliers. However, simulation based optimization problem, we do not want to ignore such data (*f(x)>0.2* for our test problem). In order to penalize (very) few data points with large error, we can increase the power from square to larger even number: Mean Power Error Loss (MPELoss)

*Caveat.* MPELoss may suffer from teh folowings:
- Deep local minima. 
  - Momentum driven optimization like Adam can escape local minima due to training momentum. However, when the loss potential have deep local minima the optimizers are more likely stuck. 
  - We use following techniques to solve this: multiple batch, re-training with re-initialization and change of learning rate during training.
- Loss can become NaN easily for large power
  - Can be alleviated by using small learning rate
