* [SIMCLR](https://github.com/manas1iitr/PapersSummary/blob/master/simclr.pdf)

Major findings/contributions : 
1. No special architectures or memory bank used for learning representations unlike previous work, totally relying on data augmentation techniques and a temperature scaling based contrastive loss function.
2. Composition of augmentations is very very useful for learning good representations (like cropping and coloring together). Moreover unsupervised learning benefits much more from data augmentation than the supervised learning techniques.
3. Appropriate temperature scaling in the contrastive loss function helps greatly in learning good representations.
4. Larger batch size, deeper and wider networks and longer training helps, even more than supervised setting.
5. Introducing a non-linear layer between the representations (that will be used for transfer learning/ fine-tuning), and contrastive loss layer also helps.
                 
Some specifics:
1. Batch-size: 256-8192 (giving total 16384 examples after augmentation), with larger batch size SGD/Momentum becomes unstable, hence they use LARS optimier. ***only need 32-128 cloud tpu cores***, global batchnorm (in distributed training with normal batchnorm the model can get away with cheating), evaluation by leaning a linear classifier on top of the frozen base network learned during the unsupervised procedure.
2. Data augmentation: random crop alongwith resize (with horizontal flipping, rotation, cutout), color distortions (brightness, saturation, hue), gaussian blur, sobel filtering, additional color distortion (equalize, solarize), and motion blur. ***NO SINGLE DATA AUGMENTATION TECHNIQUE IS GOOD ENOUGH. BUT COMPOSITION HELPS GREATLY, WITH RANDOM CROPPING AND RANDOM COLOR DISTORTION BEING THE STANDOUT*** these composition techniques perform even better than the autoaugment augmentation procedure.
3. For the loss function, Normalized cross entropy loss with adjustable temperature works better than alternatives.
4. Results shown on Imagenet classification, FOod, CIFAR10, CIFAR100, Birdsnap, SUN397, Cars, Aircraft, VOC2007, Pets, Flowers, DTD, Caltech-101.


### TECHNIQUES THAT CAN BE USED IN THE COURSE PROJECT: ###
1. composition of augmentations is a simple and a nice idea, definitly worth a try, makes the tasks more diverse I guess.
2. can consider the temperature scaling for the loss function.
3. larger batch sizes help, but I dont think we can match their batch size, so probably ignore this.
