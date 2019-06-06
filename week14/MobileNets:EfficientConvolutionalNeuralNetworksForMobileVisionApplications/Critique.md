# MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications

## Abstract
An efficient model called MobileNet is proposed for mobile and embedded vision applications. Originating from the idea of factorization, MobileNet uses depthwise separable convolutions to drastically reduce computation and model size while maintain satisfactory accuracy. The paper also introduces two simple global hyper-parameters which trade off between latency and accuracy.

## Novelties
The general success in deep learning achieves high accuracy but doesn't necessarily consider the efficient with respect to model size and computation cost, which are limited resources in many real world applications such as robotics, self-driving car, and augmented reality. The authers propose an efficient network architecture to build very small and low latency models by using the concept of factorization to match the design needs for mobile and embedded system.

## Contributions
This paper demonstrates a high efficiency network that can make a resonable trade-off between accuracy and model size as well as latency.

## Method
### Depthwise separable convolution
MobileNet is based on depthwise separable convolutions which is a form of factorized convolutions. The standard convolution filters are factorized into a depthwise convolution and a 1 x 1 convolution called pointwise convolution.

<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/depthwise_separable_filter.png"/>

Such factorization could drastically reduce computation cost while cause a small drop in accuracy. The reduction ratio is as below:

<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/computation_reduction_ratio.png"/>

MobileNet consists of the factorized layers with depthwise convolution, 1 x 1 pointwise convolution as well as batchnorm and ReLU after each convolutional layer.

<img width="40%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/layers.png"/>

### Width multiplier
Width multiplier has the effect of reducing computational cost and the number of parameters by roughly α^2 , and could be applied to any model structure to thin the network with a reasonable accuracy, latency and size trade-off.
<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/width_multiplier.png"/>

### Resolution multiplier
Resolution multiplier has the effect of reducing computational cost by ρ^2.
<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/resolution_multiplier.png"/>

## Results
<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week14/MobileNets:EfficientConvolutionalNeuralNetworksForMobileVisionApplications/comparison.png"/>
