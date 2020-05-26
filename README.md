# Papers Summary
Blogs/Own scribbling
* [Neural nets tips and tricks](https://github.com/manas1iitr/PapersSummary/blob/master/NeuralNetsTipsAndTricks)
* [WeightNorm vs LayerNorm vs BatchNorm](https://mlexplained.com/2018/01/13/weight-normalization-and-layer-normalization-explained-normalization-in-deep-learning-part-2/)

Summary of papers (mainly in NLP and Machine Learning) that I read:

* [Structured Pruning of Bert based Question Answering model](https://github.com/manas1iitr/PapersSummary/blob/master/Structured%20Pruning%20of%20a%20BERT-based%20Question%20Answering%20Model)
* [Batch Normalization](https://github.com/manas1iitr/PapersSummary/blob/master/BatchNorm.pdf) (The summation sign over the mini-batch size is important while computing the derivatives of mean and variance of mini-batch, which in turn are required for computing the derivative with respect to a particular x_i, more suitable for conv nets, but with recurrent nets a problem that the test sequence may be larger than any of the training sequence, then how to normalize?)
* [Layer Normalization](https://github.com/manas1iitr/PapersSummary/blob/master/LayerNormalization.pdf) (overcomes the shortcomings of batch norm for RNNs, though for CNN batchnorm is still more effective, basically helps in making the model more robust to scaling and initializations of parameters, and the input values (invariant to weight rescaling and recentering and input rescaling and recentering), while solving ***internal covariate shift***. A nice table given in this paper comparing layernorm, batchnorm and weightnorm.)

