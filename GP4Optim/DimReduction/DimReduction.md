# Supervised dimension reduction

Popular dimension reduction techniques including PCA, kernelPCA, ICA, AutoEncoder etc are unsupervised learning. In optimization problem where input parameters are explored to find the optimal output, the unsupervised or semi-unsupervised dimension reduction techniques are not applicable generally. 

On the other hand, the supervised dimension reduction techniques (e.g. [Sliced Inverse Regression](https://doi.org/10.2307/2290563), [Kernel Dimension Reduction](https://dl.acm.org/doi/10.5555/1005332.1005335), [Covariance Operator Inverse Regression](https://ieeexplore.ieee.org/document/4587404)) are inverse transformation based and are reltively old and not well known compared to the unsupervised dimension reduction techniques. 

Here, we apply a relatively new but very simple technique: the [bottleneck NN](https://link.springer.com/chapter/10.1007/978-3-642-15381-5_5), for supervised dimension reduction. The (reduced dimension) latent variables are then used as input parameters for GP. 
