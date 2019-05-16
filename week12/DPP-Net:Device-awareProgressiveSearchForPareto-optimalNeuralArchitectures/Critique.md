# DPP-Net: Device-aware Progressive Search for Pareto-optimal Neural Architectures

## Abstract
Previous NAS (Neural Architectural Search) methods ignore the device-related objectives like inference time, memory usage, and power consumption. However, these device-objectives are critical for deploying deep neural networks on portable devices, which resoures are limited. This paper addresses this issue and proposes a device-aware auto-ML approach to optimize both device-related and device-agnostic objectives in a Pareto-optimal way.

## Novelties
Most of the NAS works focus on single objective and others are largely ignored, especially those related to device resources. The authers introduce DPP-Net: Device-aware Progressive Search for Pareto-optimal Neural Architectures for finding Pareto-front optimal archetecture in the multiple objectives space.  

## Contributions
First, their proposed DPP-Net is the first device-aware neural architecture search approach outperforming state-of-the-art handcrafted mobile CNNs.

Second, in three different devices (a workstation with NVIDIA Titan X GPU, NVIDIA Jetson TX1 embedded system, and mobile phone with ARM Cortex-A53) DPP-Net achieves higher accuracy and shorter inference time then CondenseNet and NASNet.

## Technical Summarizes
### Search Architecture
<img width="40%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/searching_network_architechture.png"/>

<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/searching_operations.png"/>

### Search Space
<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/searching_space_design.png"/>

### Search Algorithm
<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/searching_algorithm.png"/>

### Surrogate Function for Pareto Optimality
<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/surrogate_function.png"/>


## Results

<img width="80%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/cifar10_results.png"/>

<img width="80%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week12/DPP-Net:Device-awareProgressiveSearchForPareto-optimalNeuralArchitectures/imagenet_results.png"/>

