# Cycle GAN


This is a [Kaggle Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge). Personal Kaggle notebook for this challenge is [here](https://drive.google.com/file/d/1Q9X-XbCXz51fByFKYXqg47_JtFzA2WHV/view?usp=sharing)


The goal of cycleGAN is to learn mapping functions (generators) $G:X\rightarrowY$ and $F:Y\rightarrowX$ between two domains $X$ and $Y$. To acheive this goal
  - Two discriminators (as the name suggest) $D_X$ and $D_Y$ are introduced to distinguish elements $\{x\}$ in $X$ from translated elements $\{F(y)\}$ and elements $\{y\}$ in $Y$ from translated elements $\{G(x)\}$ respectively. 
