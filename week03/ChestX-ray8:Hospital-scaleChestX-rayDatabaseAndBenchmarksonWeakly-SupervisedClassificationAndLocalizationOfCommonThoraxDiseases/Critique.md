# ChestX-ray8: Hospital-scale Chest X-ray Database and Benchmarks on Weakly-Supervised Classification and Localization of Common Thorax Diseases

## Abstract
The authers propose a new chest X-ray database － "ChestX-ray8", which comprises 108,948 frontal-view X-ray from 32,717 patients along with the text-mined 8 disease image labels. They claim that the new dataset is hospital-scale since that it is one order of mignitude larger than previous largest OpenI dataset for chest X-ray. Moreover, they build a benchmark for weakly-supervised classification and localization on this dataset.

## Novelties

<img width="80%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/ChestX-ray8:Hospital-scaleChestX-rayDatabaseAndBenchmarksonWeakly-SupervisedClassificationAndLocalizationOfCommonThoraxDiseases/Framework.png"/>

They apply the deep learning pre-trained model as feature extractor to extract the "importance" of each pixel which makes a contribution to the detection of a particular disease. Then, it comes out to be a heatmap and can be consider as a probabilistic map of the disease.

## Contributions
They public a hospital-scale X-ray dataset for the deep learning research in medical domain and construct a valid benchmark for the image classification and localization by weakly-supervised learning.

## Assumptions
The heatmap assumes that the activation layers from the pre-train model pays more attention to the region of interest which indicates the disease and weitghts from prediction layers imply the importance of each spatial maps seen by the model. By inner-product the both, we can get the localization of each lesion.

## Questions 
They did not explain why the hyper-parameter "r" in the LSE (Log-Sum-Exp) pooling function:

<img width="40%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/ChestX-ray8:Hospital-scaleChestX-rayDatabaseAndBenchmarksonWeakly-SupervisedClassificationAndLocalizationOfCommonThoraxDiseases/LSE.png"/>

make the AUC drop down at r=5 and climb to the peak at r=10?

<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week03/ChestX-ray8:Hospital-scaleChestX-rayDatabaseAndBenchmarksonWeakly-SupervisedClassificationAndLocalizationOfCommonThoraxDiseases/Global_pooling.png"/>

## Promising Applications
Although the truly latge-scale and fully-automated high precision medical diagnosis system still remians a strenuous task to be fulfilled. This work give us some insight for using finite annotations to assist the developement of a data-driven model.

## Technical Summarizes
They experiment on 4 kind of ImageNet pre-trained model (AlexNet, GoogLeNet, VGGNet-16, and ResNet-50) as the feature extractors and various hyper-parameter "r" in {0.1, 0.5, 1, 5, 8, 10, 12} to train the classifer. And turn out that the ResNet-50 and r=10 can achieve the best situation.
