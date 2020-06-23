# Papers Summary
Blogs/Own scribbling
* [Neural nets tips and tricks](https://github.com/manas1iitr/PapersSummary/blob/master/NeuralNetsTipsAndTricks)
* [WeightNorm vs LayerNorm vs BatchNorm](https://mlexplained.com/2018/01/13/weight-normalization-and-layer-normalization-explained-normalization-in-deep-learning-part-2/) (***Key thing:*** in deep learning anything is legal as long as it is differentiable, and all these normalization operations are differentiable.)

Summary of papers (mainly in NLP and Machine Learning) that I read:

* [Batch Normalization](https://github.com/manas1iitr/PapersSummary/blob/master/BatchNorm.pdf) (The summation sign over the mini-batch size is important while computing the derivatives of mean and variance of mini-batch, which in turn are required for computing the derivative with respect to a particular x_i, more suitable for conv nets, but with recurrent nets a problem that the test sequence may be larger than any of the training sequence, then how to normalize? Goodfellow found that using something called as virtual batch normalization is essential for training GANs to be able to generate good images. References for batch norm: Goodfellows lecture for discussion([link](https://www.youtube.com/watch?v=Xogn6veSyxA) from the book website), the deep learning book, and yannic kilcher's review of the paper)
* [Layer Normalization](https://github.com/manas1iitr/PapersSummary/blob/master/LayerNormalization.pdf) (overcomes the shortcomings of batch norm for RNNs, though for CNN batchnorm is still more effective, basically helps in making the model more robust to scaling and initializations of parameters, and the input values (invariant to weight rescaling and recentering and input rescaling and recentering), while solving ***internal covariate shift***. A nice table given in this paper comparing layernorm, batchnorm and weightnorm. If layer normalization is working on the outputs from a convolution layer, the math has to be modified slightly since it does not make sense to group all the elements from three distinct channels together and compute the mean and variance. Each channel is considered as an “independent” sample and all the normalization was done for that specific channel only within the sample.)
* [Weight Normalization](https://github.com/manas1iitr/PapersSummary/blob/master/WeightNormalization.pdf) (aims to alleviate the significance of batch sizes as a design decision as in batch normalization, and claims to be faster for CNNs, and applicable to noise sensitive applications like deep reinforcement learning, but is affected by the way parameters are initialized.)
* [What BERT LEARNS](https://github.com/manas1iitr/PapersSummary/blob/master/CS294BerkeleyPapers/self_supervised_transfer_learning/NLP/bertlearns.pdf) (Attention heads show some general patterns like attending to the previous and the next word, a large number of heads attend to the SEP token, especially in the middle layers, while the higher layers attend to periods and commas. Attention to SEP token can be thought of as a no operation, implying that that particular word is not much affected by any other word. Moreover the attention heads in the lower layers in particular dont focus on any particular word, rather the attention is much more dispersed across the whole sentence, giving a bag-of-vectors representation. Also the CLS token in the last layer has a very dispersed attention, making it an ideal candidate to be input to a classifier. There are some attention heads which learn some syntactic feature, like object of verb attending to the verb, preposition attending to its verb, coreference is also handled well by some heads. Another interesting point is that heads in the same layer tend to behave together (probably making them an ideal candidate to be pruned). This can be an artifact of dropout as well as we force the model to be not dependent on one head. Making attention non-uniform has been studied in [link](https://arxiv.org/pdf/1810.10183.pdf) which seems to improve the performance of machine translation.)
* [BERT](https://github.com/manas1iitr/PapersSummary/blob/master/CS294BerkeleyPapers/self_supervised_transfer_learning/NLP/BERT.pdf) (***First true bidirectional embedding*** in the sense that in elmo, either the token attends only its left context or only its right context, and then the 2 embeddings are concatenated, while in BERT, the token can attend to its left and right context simultaneously.)

