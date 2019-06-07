# Model Compression and Acceleration for Deep Neural Networks

## Abstract
Recently, the extraordinary success of deep neural networks relies on a great amount of the parameters. However, as the model size grows larger, develope an efficient way to compact the model and reduce the storage and computation cost becomes critical for the real-time applications. In this paper, the authers summarizes recent works on the compressing and accelerating issues for DNNs and give some general suggestions about how to choose a compression approach for different situations. 

## Approaches Summarization
The approaches could be classified into 4 categories:
  1. Parameter pruning and sharing: exploring and trying to remove the redundancy in the model parameters.
  2. Low-rank factorization: using tensor decomposition to estimate the informative parameters.
  3. Transferred/compact convolutional filters: designing special structual convolutional kernels to reduce the complexity.
  4. Knowledge distillation (KD): learning a distilled model to teach a compact student model.

The table below briefly summarizes the properties of the 4 types of approaches.
<img width="100%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/ModelCompressionAndAccelerationForDeepNeuralNetworks/different_approaches_for_network_compression.png"/>

### Parameter pruning and sharing
Hessian weight could be used to measure the importance of network parameters.
#### Quantization and binarization
  - Reducing the number of bits required to represent each weight.
  - The accuracy is significantly lowered when dealing with large models.
#### Pruning and sharing
  - Could both reduce network complexity as well as address the overfitting issue.
  - Pruning with l1 or l2 regularization requires more iterations to converge. 
  - All pruning criteria require manual setup of sensitivity for each layer.
#### Structural matrix
  - Causing loss in accuracy since the constraint might bring bias to the model. 
  - Finding a proper structural matrix is difficult since there is no theoretical way from which to derive it.

### Low-rank factorization
  - Simplifying the convolution operation would have a direct impact on the overall speedup.
  - Performing factorization approximation layer by layer cannot perform global
parameter compression, which is important as different layers hold different information. 
  - Requiring extensive model retraining to achieve convergence.

<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/ModelCompressionAndAccelerationForDeepNeuralNetworks/low-rank_regularization.png"/>

### Transferred/compact convolutional filters
  - For example, decomposing 3 x 3 convolution into two 1 x 1 convolutions.
  - Sometimes, the assumptions are too strong to guide the algorithm, making the results unstable on some data sets.

### Knowledge distillation
  - Distilling knowledge from a large teacher model into a small student one by learning the class distributions output by the teacher via softened softmax.
  - Can make deeper models thinner and help significantly reduce the computational cost.
  - Can only be applied to classification tasks with softmax loss function.
  - Sometimes, the assumptions are too strict to make the performance competitive with other types of approaches.

## General Suggestions
1. If end-to-end solutions are needed, low-rank factorization and transferred/compact convolutional filters can be easily implemented. 
2. If the applications needs compacted models from pretrained models, one can choose pruning and sharing or low-rank factorization.
3. Usually, pruning and sharing could give a reasonable compression rate while not hurting the accuracy.
4. If a problem involves small size of data set, the KD approach is preferred.
5. For applications in some specific domains (e.g. medical images), methods with human prior (like the transferred convolutional filters and structural matrix) sometimes have benefits.
6. All the methods are orthogonal and could be comined with each others. 
