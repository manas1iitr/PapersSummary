* [SIMCLR](https://github.com/manas1iitr/PapersSummary/blob/master/simclr.pdf)
Major findings : * No special architectures or memory bank used for learning representations unlike previous work, totally relying on data augmentation techniques and a temperature scaling based contrastive loss function.
                 * Composition of augmentations is very very useful for learning good representations (like cropping and coloring together). Moreover unsupervised learning benefits much more from data augmentation than the supervised learning techniques.
                 * Appropriate temperature scaling in the contrastive loss function helps greatly in learning good representations.
                 * Larger batch size, deeper and wider networks and longer training helps, even more than supervised setting.
                 * Introducing a non-linear layer between the representations (that will be used for transfer learning/ fine-tuning), and contrastive loss layer also helps.
                 
Some specifics: *