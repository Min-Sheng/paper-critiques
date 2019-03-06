# Learning From Noisy Large-Scale Datasets With Minimal Supervision

## Abstract
The aurthers propose an approach to effectively and efficiently leverage a small amount of clean annotations in conjunction with 
large amounts of noisy annotated data to learn powerful image representations.

## Novelties

<img width="60%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/LearningFromNoisyLarge-ScaleDatasetsWithMinimalSupervision/Overview.png"/>

First, most of the approaches which tackle the noisy annotation problem pre-train a model with the noisy data and then fine-tune it with the clean dataset. They argue that such methods do not fully leverage the information contained in the clean annotations.
So, they propose an alternative multi-task approach to learn a mapping between noisy and clean annatations using a label-cleaning network, and jointly learn the image classification by a multi-label classifier.

Second, they consider a multi-label image classification problem for present all concepts of image which is a general senario. In stead of assuming that all classes are independent like many approaches, they model the label-cleaning network as conditionally dependent on noisy input labels.

Moreover, to address the *multiple semantic modes*, for example, the calss coconut may include an image containing a drink, a fruit, or a tree, they utilize a CNN as feature extractor to capture the semantic features of the input image.

## Contributions

<img width="100%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/LearningFromNoisyLarge-ScaleDatasetsWithMinimalSupervision/Framework.png"/>

First, they introduce a semi-supervised learning framework for multi-label image classification which facilitates small sets of clean annotations in conjunction with massive sets of noisy annotations.

Second, they provide a first benchmark on the Open Image Dataset which is a large-scale image dataset recently released by Google.

Third, they demonstrate their approach is more effictive than traditional fine-tuning method.

## Assumptions
They assume that in reality learning senarios are closer to semi-supervised learning, a small fraction of data is clean
while a large amount of data is noisy either missing.

## Questions 
To remain the valid label space of the cleaned label output to 0 and 1, this paper applys the clipping operation:

<img width="25%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/LearningFromNoisyLarge-ScaleDatasetsWithMinimalSupervision/Clip.png"/>

And I wonder why not use the sigmoid function just likes the image classifier used?

## Promising Applications
It can be help the image retrieval more precise in social network because everyone can leave any commit or messenge and make the data become noisy.

## Technical Summarizes
The archetecture of the model comprises one Inception V3 as feature extractor, one label-cleaning network, and one image classifier. Both the label-cleaning network and the image classifier share the feautre from the feature extractor while the label-cleaning network concatenate it with word embedding from noisy labels. Then, there are two loss functions－L1 loss between the predicted cleaned labels and the GT cleaned labels; the cross-entropy for classification.
