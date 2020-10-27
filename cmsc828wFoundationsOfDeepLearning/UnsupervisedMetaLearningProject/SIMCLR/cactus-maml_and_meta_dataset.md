***Cactus-MAML:***
Datasets used: MNIST, Omniglot, MiniImageNetm CelebA.

Partition each dataset into meta-train, meta-val, meta-test (each has disjoint set of classes).
1. omniglot split: 1100 characters for meta-train, 100 for meta-val, and 423 for meta-test. (they don't specify what characters they take for each of them.)
2. miniimagenet split: 64 classes for meta-train, 16 for meta-val, and 20 for meta-test. (this is the same as proposed in ravi and larochelle 2017).
3. celeba split: 162770 images for meta-train, 19867 for meta-val and 19962 for meta-test.

Training and evaluation:
1. run unsupervised training on unlabelled meta-train split.
2. report performance on downstream tasks using labels of meta-test split.
3. A fixed number of meta-training iterations used, as no suitable criterion for early stopping available.
4. regarding meta-val data: the paper says: to facilitate anaylsis on meta-overfit, we use the labels of meta-val to construct tasks for meta-validation. but no tuning of any hyperparameters is done on labeled data. (stupid question: not sure why/how meta-val is different from meta-test then?)


Hyperparameters for Cactus-Proto: [link](https://github.com/manasaga/PapersSummary/blob/master/cmsc828wFoundationsOfDeepLearning/UnsupervisedMetaLearningProject/SIMCLR/cactus_protonets_hyperparams.PNG)

Hyperparameters for Cactus-MAML: [link](https://github.com/manasaga/PapersSummary/blob/master/cmsc828wFoundationsOfDeepLearning/UnsupervisedMetaLearningProject/SIMCLR/cactus_maml_hyperparams.PNG)

some additional notes: for cactus-maml, maxpooling not used, some trickery for batch normalization, refer appendix section E1.



***Meta-dataset paper:***
Omniglot split: 883/81/659 by characters or 25/5/20 by alphabet. [link](https://github.com/google-research/meta-dataset/blob/81de10378b91c7fcafcde2c151f09204e74e6878/doc/dataset_conversion.md#omniglot)




