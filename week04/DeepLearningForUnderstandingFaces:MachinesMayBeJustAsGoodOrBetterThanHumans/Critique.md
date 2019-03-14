# Deep Learning for Understanding Faces: Machines May Be Just as Good, or Better, than Humans

## Abstract
The review paper presents an overview of the recent developments and researches in deep learning methods used for human face detection, facial landmark localization, head orientation estimation, and face recognition (including face identification and verification).

## Contributions
The authers amply organize the facial analysis problems and the corresponding CNN-based methods for automatic face recognition.

## Technical Summarizes
Three important modules in the face recognition pipeline:
  - Face detector localizes faces with varying conditions (including pose, illumination, and scale) and precisely predict the bounding boxes of faces. 
  - Face keypoint detector localizes the critical facial landmark (such as eye centers, nose tip, mouth corners, etc.) which are used to align the faces to normalized canonical coordinates to alleviate the rotation and scaling effect.
  - From the well-aligned face, feature descriptor encodes the identity information into the face representation which can be used to calculate the similarity metric to determine whether two faces are from the same subject.

- Face detection: 
  - Region based: Faster R-CNN
  - Sliding-window based: Single-shot detector (SSD)

<img width="75%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week04/DeepLearningForUnderstandingFaces:MachinesMayBeJustAsGoodOrBetterThanHumans/Face_Detector.png"/>

- Facial landmark detection and head orientation estimation:
  - Model based
  - Cascaded regression based

<img width="75%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week04/DeepLearningForUnderstandingFaces:MachinesMayBeJustAsGoodOrBetterThanHumans/Regression-based_Keypoint_Estimator.png"/>

- Face verification and identification:
  - Face verification: Given a pair of face images, the system requires to predict whether they belong to the same subject or not.
  - Face identification: Given a unknown face image, the system should determine the subject's identity by matching the features from the database.  

<img width="75%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week04/DeepLearningForUnderstandingFaces:MachinesMayBeJustAsGoodOrBetterThanHumans/Face_Recognizer.png"/>

## Insights
- Multi-task learning (MTL) is beneficial for improving the accuracy of facial analytics.

<img width="75%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week04/DeepLearningForUnderstandingFaces:MachinesMayBeJustAsGoodOrBetterThanHumans/MTL-based_Methods.png"/>

- Developing a robust strategy to learn from small-scale or noisy data is challenging but prospective.
- Choosing more informative pairs or triplets to better perform the metric learning and end-to-end online training the network is still an open issue. 

## Promising Applications
The paper can be a fundamental knowledge and provides some insights for the researches in the field of facial analytics.

## Questions

The sentance: "... for smaller models, training using wider data sets is better than training using deeper data sets, while for deeper models, training using **wider** data sets is better." seems to have a mistake.

<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week04/DeepLearningForUnderstandingFaces:MachinesMayBeJustAsGoodOrBetterThanHumans/Question.png"/>

Shoudn't it be: "training using **deeper** data sets is better." ?
