# Discovering Discrete Latent Topics with Neural Variational Inference

## Abstract
Probablilistic models such as LSA, PLSA, LDA have provide a foundation for document modelling by inducing latent topics for each token. However, in order to capture topic dependencies or exploit conditional information, these models have grown to more expressive. So, a fast and accurate inference method is needed. This paper introduces the deep neural networks to such topic modelling problem. With the help of the non-linear and scalable characteristic of neural networks, their proposed framworks could perform much better then the traditional Dirichlet-Multinomial topic models.
 

## Contribution
First, The authers propose three different neural topic models which comines both the advantages of the trditional probabilistic topic models and neural networks.

Second, the proposed models could be trained efficiently along with variational inference by backpropagation.

Third, as probabilistic graphical models, they are interpretable and explicitly represent the dependencies amongst the random variables.

Fourth, through evaluations on several datasets, the authers demonsrate that the proposed models are more robust and effective than previous methods. 
