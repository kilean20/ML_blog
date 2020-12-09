# Perturbative Correction Using ML 

this is part of the contents from a [slide](MLdecoherence1.pdf) which is presented in IOTA (Accelerator in Fermi Lab) collaboration meeting.

### Data Model and Goal

We assume the data to be time series of complex valued scalar. To be more specific, it is simulated measurement data of beam centroid from Beam Position Monitor (BPM). The details can be found from [here](Decoherence.md) or the [slide](MLdecoherence1.pdf). The data depends on the bare frequency *w<sub>0</sub>* and the frequency detuning parameter *w<sub>1</sub>* that we want to measure and other hidden parameters including initial offset, beam emittance, optics parameter, and etc that we assume that we are not interested in discovering. 

### Leading order theory

It can be shown that in the limit of large initial offset (compared to initial beam emittance), leading order term of centroid in frequency domain can be used to measure the  bare frequency *w<sub>0</sub>* and the frequency detuning parameter *w<sub>1</sub>*. 

### Correction to the leading order theory using NN model

However, the intial offset cannot be made arbitrarily large due to beam pipe and higher order nonlinearities. In addition, perturbative analytic calucation of the next leading order can be very complex. We model the perturbative correction using neural networks. 

### Strategies

##### 1. Input feature engineering: 1/x<sub>0</sub>
Since the leading order theory works in the limit of large offset, the next leading order would be smaller than the leading order term by factor of 1/x<sub>0</sub>. Therefore, additional input feature of 1/x<sub>0</sub> may boost the model performance. Further input features based on terms appearing in the leading order theory or based on EDA (Explanatory Data Analysis) might be good to be added. (see more details on the [slide](MLdecoherence1.pdf))

##### 2. Convolution Layers for centroid data
Since the time series data is correlated between adjacent point in time ( or adjacent frequency in frequency domain), convolution layers may be more efficient than MLP. 


### Model
we use the following structure of NN model
<p align="center">
  <img src="model.H2.1D.DFT.jpg"/>
</p>

### Result
Following results shows histogram of model error (orange) compared to the error of the leading order theory (blue). 

- Scalar inputs only except 1/x<sub>0</sub>:

<p align="center">
  <img src="1DH2gaussian_ScalarInputOnly_simpleModel_X0.png"/>
</p>

- Add centroid data inputs in addition to the Scalar inputs (except 1/x<sub>0</sub>):

<p align="center">
  <img src="1DH2gaussian_ScalarInputOnly_simpleModel_inverseX0.png"/>
</p>

- Include all input features including 1/x<sub>0</sub>:

<p align="center">
  <img src="1DH2gaussian_inverseX0.png"/>
</p>


# Important remark

I also tried to build a NN model that takes centroid data input and predict the bare frequency *w<sub>0</sub>* and the frequency detuning parameter *w<sub>1</sub>* without incoporating the leading order theory. However, the model failed to train well (almost all times of serveral different set of random initial model parameters and many different model structures) to predict them in a good accuracy. I believe this is because the data depends on the bare freuqncy and detuning parameter in a complex way so that the model should be complex enough and the training is not guranteed on such complex model and data. 



# Conclusion 

NN model as a perturbative correction to the leading order theory is a simple and natural way of incorporating (physics guided) domain knowledge. We applied this on simulated beam decoherence data to extract frequency and detuning parameter to better accuracy than leading order theory. 




