# Learning to Hash for Indexing Big Data - A Survey

## Abstract
This survey paper provides a comprehensive overview of the learning to hash framework. Facing the dramatic and rapid increaing content of the multimedia data, the hashing techniques becomes popular solutions for query retrieval and pattern matching owning to their efficiency and accuracy. The purpose of this paper is to give the reader a concept and insight of hashing.

## Technical Summarizes
Hashing repeatedly partition the input data and derive each single hash bit to map the input data to a discrete hashing code space. Such procedure not only can substantially reduce storage costs for its binary encoding but also speed up the query time by constructing the inverse lookup table.

The three steps in hashing-based Approximate Nearest Neighbor (ANN) search could be categoried into:
1. Designing hash function
2. Indexing with hash table
3. Online querying with hash codes

For designing hash functions, this paper summaries the data-dependent methods, e.g. random projection and permutation hashing, which are LSH family approaches, and the data-independent methods, which also called the learning-based hashing. 

Diving deeper with the learning-based hashing, there are unsupervised, supervised, and semi-supervised approaches depend on the level of supervision. And according to the kind of similarity metrics, they can be group into several subcategories, including pointwise, pairwise, tripletwise, and listwise. Besides, there have linear and nonlinear methods. The linear one, likes PCA hashing, shows the advantage of simplicity while the nonlinear, likes spectral hashing has more discriminate power.

## Insights


## Promising Applications

