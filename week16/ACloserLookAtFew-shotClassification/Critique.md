# A Closer Look at Few-shot Classification

## Abstract
The strong performance of deep network heavily relies on abundant labeled examples which requires human annotation cost and are often limited by their scarcity. Few-shot learning aims to recognize novel classes by training with limited labeled examples like human visual system. 

This paper presents a comprehensive comparative analysis of existing few-shot classification algorithms and shows that using deeper backbones significantly reduce the performance differences among them with limited domain differences. 

Moreover, the authers introduce a modified baseline model and show it achieves competitive performance with state-of-the-art. 

A new realistic cross-domain evaluation setting is also investigated to demonstrate that current algorithms fail to address domain shifts. 

## Contributions
First, a fair comparison for several different few-shot clasiification algorithms are conducted. The results reveal that the skills of reducing intra-class proposed in existing works which use shallow backbones lead to favorable results, while increasing the model capacity by using deep backbane reduces the performance gap among these methods. 

Second, a baseline method is introduced with a distance-based classifier suprisingly achieves competitive performance comparing with the state-of-the-art meta-learning methods on two datasets.

Three, they propose a realistic evaluation setting which samples base and novel classes from different domains, and argue that current algorithms fail to address such domain shifts problem and inferior even to the baseline model.
