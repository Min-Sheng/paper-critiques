# Bi-Directional Attention Flow For Machine Comprehension

## Abstract
Machine comprehension (MC) and question answering (QA) have achieved promising results due to the neural attention mechanism, which enables the system to focus on a most relative part of the context for answering the question. Previous works typically compute attention weights by summarizing the context into a fixed-size vector, couple attentions temporally, and/or only use a uni-directional attention.

In this paper, the authors propose the Bi-Direstional Attention Flow (BIDAF) network, a hierarchical multi-stage architecture,that models the representations of the context paragraph at different levels of granularity and uses bi-directional attention flow to obtain a query-aware context representation without early summarization.

## Novelties
Th novelties of BIDAF are compared with the prvious works in the following:
### Machine comprehension (MC)
  1. Using Dynamic attention, in which the attention weights are qudated dynamically given the query and the context as well as the previous attention. **Instead, BIDAF utilizes a memory-less attention mechanism.**
  2. Computing the attention weights only once. **Instead, BIDAF lets the attention vectors flow through the recurrent model layer.**
  
### Visual question answwering (VQA)
  1. The question attends to different patches in the image.
  2. Each question word attends to each image patch.
  3. Combining questions representations ar multiple levels (unigrams, bigrams, trigrams).
  4. Attending from the image back to the question words.
BIDAF shares the similar idea from 4. and further take advantages of attention flow while these methods do not. 

## Contributions
First, the attention is computed for every time step, and the attended vector at each time step, along with the representations from previous layers, flow through the subsequent modeling layer, intead of summarizing the context into a fixed-size vector.

Second, they use a memory-less attention mechanism. And the attention at each time step could be formulated to a function of only the query and the context paragraph at current time step. It allows the attention layer to focus on learning the attention and the modeling layer to focus on learning the interection within the representation.

Thrid, they introduce bi-directional attention, query-to-context and context-to-query, which provides complimentary information to each other.

Finally, BIDAF outperforms all previous models on SQuAD test set.

## Model
<img width="90%" src="https://github.com/Min-Sheng/paper-critiques/raw/master/week13/Bi-DirectionalAttentionFlowForMachineComprehension/BiDirectional_Attention_Flow_Model.png"/>

The architecture consists of 6 layers
  1. Character Embedding Layer: projects each word to a vector space using character-level CNNs. 
  2. Word Embedding Layer: projects each word to a vector space using a pre-trained word embedding model, GloVe.
  3. Contextual Embedding Layer: utilizes contextual cues from surrounding words to refine the word embedding by LSTM.
  The first three layers are applied to both the query and context paragraph.
  4. Attention Flow Layer: couples the query and context word embedding vectors and generates a set of query-aware representations by bi-directional attention mechanism.
  5. Modeling Layer: employs a LSTM to modeling the interaction within the representations.
  6. Output Layer: predicts an answer to the query.

## Future work
Extening BIDAF to incorporate multiple hops of the attention layer.
