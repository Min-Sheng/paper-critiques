# Scalable Face Image Retrieval using Attribute-Enhanced Sparse Codewords

## Abstract
The authers propose a novel method to utilize automatically detected human attributes which contain semantic meaning of face to imporve content-based face retrieval accuracy and efficiency.  

## Novelties
This paper provides a new perspective on face retrieval by combining low-level features with high-level human attributes.

<img width="40%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week09/ScalableFaceImageRetrievalUsingAttribute-EnhancedSparseCodewords/attribute influence.png"/>

The picture above shows that the face images of two different people can be very close in traditional low-level feature space. But incorporating the high-level attributes can represent better discriminability.

## Contributions
First, they are the first proposal of combining the low-level features and automatically detected human attributes to construct semantic codewords for content-based face image retrieval.

Second, they propose two orthogonal methods, which referred to as Attribute-enhanced Sparse Coding (ASC) and Attribute Embedded Inverted Indexing (AEI), to balance the global representations in image collections and locally embedded facial characteristics of query and improve the accuracy and efficiency in the large-scale content-based face image retrieval.

Third, they conduct sufficient experiments to demonstrate their methods is promising on two separate datasets.

Fourth, they identify the semantic codewords are useful for other related applications such as the face verification.

And the following is the overview of the whole framework:

<img width="90%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week09/ScalableFaceImageRetrievalUsingAttribute-EnhancedSparseCodewords/overview.png"/>

## Technical Summarizes

<img width="50%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week09/ScalableFaceImageRetrievalUsingAttribute-EnhancedSparseCodewords/attribute enhancing coding.png"/>

<img width="40%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week09/ScalableFaceImageRetrievalUsingAttribute-EnhancedSparseCodewords/attribute embedded inverted indexing.png"/>
