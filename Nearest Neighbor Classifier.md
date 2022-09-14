---
aliases: NN Classifier
---

[[Deep Learning]]

# Nearest Neighbor Classifier

Not used anymore, as it is obsolete, and has been replaced with [[Convolutional Neural Network|convolutional neural networks]].

## Example classification with [[CIFAR-10]] dataset
The dataset consists of 60000 images labeled with one of ten classes. It has been split up into a 50000 images training set, and a 10000 images test set.

The Nearest Neighbor Classier, when given a test image, will have to compare that image to each and every one of the training images to make a prediction.

![[Pasted image 20220913193319.png]]

In the image above, ten images from each class has been given to the classifier, and the classifier has returned 10 of each class that it predicted to be correct.
But only 3 in 10 were correct across the board.

Given two images {one training, one test}, and representing them as vectors $I_1$, $I_2$, a reasonable choice for comparing them might be the [[L1 distance]]:

$$d_1(I_1,I_2)=\sum\limits_{p}|I_1^p-I_2^p|$$

Where the sum is taken over all pixels.
Visualized:
![[Pasted image 20220913193942.png]]

The more like the images are, the smaller the value. When running this in code, the classifier only manages around 38-39%.

Another choice of distance, also common, is using the [[L2 distance]]:

$$d_2(I_1,I_2)=\sqrt{\sum\limits_{p}(|I_1^p-I_2^p|)^2}$$

The difference between L1 and L2, is that we square them before adding them, and then take the square root.

L2 ran in code, compared to the L1, only manages to achieve a ~35% accuracy.